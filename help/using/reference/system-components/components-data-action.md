---
description: Komponenter för dataåtgärder är bland annat kunddataflöden, datainsamlingsservern, SFTP/S3/HTTP-utgivare, IRIS och profilcacheservern.
seo-description: Komponenter för dataåtgärder är bland annat kunddataflöden, datainsamlingsservern, SFTP/S3/HTTP-utgivare, IRIS och profilcacheservern.
seo-title: Dataåtgärdskomponenter
solution: Audience Manager
title: Dataåtgärdskomponenter
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 3%

---


# Dataåtgärdskomponenter{#data-action-components}

Komponenter för dataåtgärder är bland annat kunddataflöden, datainsamlingsservern, SFTP/S3/HTTP-utgivare, IRIS och profilcacheservern.

<!-- 

c_compact.xml

 -->

Åtgärdskomponenter är system och processer som gör att du kan flytta in och ut data [!DNL Audience Manager] och (utan en bättre fras) göra saker med dem. Dessa [!DNL Audience Manager] komponenter omfattar:

## Kunddataflöden (CDF) {#cdf}

[!UICONTROL CDF] är filer som skickas varje timme till kunderna. Dessa innehåller användar-ID:n tillsammans med tillhörande segment-ID:n, trait-ID:n och andra data. Mer information finns i Översikt över [kunddataflöden](../../features/cdf-files.md).

## Datainsamlingsserver (DCS) {#dcs}

Se [Komponenter för datainsamling](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Utgivare får synkroniserade ID-data från [!UICONTROL SFTP/S3] utgivaren [!UICONTROL Outbound Feed Converter]. När dessa filer är klara skickar klienten dessa data till ett mål som anges av klienten [!UICONTROL SFTP/S3 publishers] . Dessa filer innehåller synkroniserade ID-data med en 1:N-mappning av [!DNL Audience Manager] användar-ID:n (UUID) till:

* Enhets-ID/DataProvider-ID (DPUID)
* Kvalificerade segment-ID:n
* Trait IDs

[!DNL Audience Manager] kunderna inte har tillgång till funktioner som direkt styr [!UICONTROL SFPT/S3 publishers]dem. Kunder använder den här tjänsten indirekt när de skapar och skickar data till destinationer. Systemet är i stort sett en automatiserad jobbprocess som körs med schemalagda intervall [!UICONTROL SFTP/S3] .

## IRIS {#iris}

I grekisk mytologi [!UICONTROL Iris] är en figur som reser och levererar budskap snabbt. Systemet är ett [!UICONTROL IRIS] namnmärke som återspeglar den här figurens egenskaper från den gamla världen. I modern mening [!UICONTROL IRIS] är detta en cookie-synkroniseringstjänst med låg latens och hög frekvens.

[!UICONTROL IRIS] fungerar med samma typ av data som [!UICONTROL SFTP/S3] systemet. Men det [!UICONTROL IRIS] är annorlunda eftersom data skickas till destinationer i realtid i stället för med fasta intervall. Det här är ett separat system eftersom [!UICONTROL SFTP/S3] utgivaren inte kan skicka data till en HTTP-destination och de är inte utformade för dataöverföringar i realtid.

Det finns inga gränssnittskontroller som gör att kunderna kan arbeta direkt med [!UICONTROL IRIS]. Kunderna arbetar med [!UICONTROL IRIS] indirekt när de skapar och skickar data till destinationer och för andra processer som kräver snabba dataöverföringar.

Exempel på [!UICONTROL IRIS] tjänster och funktioner är:

* Snabb synkronisering (inom 30 sekunder) för cookies och segment. Den kan synkronisera [!DNL Audience Manager] cookie-filen, partnercookies eller båda.
* Dataöverföringar i realtid. [!UICONTROL IRIS] ansvarar för att skicka kvalificeringshändelser för segment i realtid till en partner eller annan destination. Dessa data är JSON-formaterade och skickas via en HTTP- `POST` begäran.

* Dataöverföringar mellan servrar och servrar gruppvis: Om du utbyter stora mängder data med [!DNL Audience Manager]är det [!UICONTROL IRIS] systemet som dina servrar använder för att överföra data.

* Tillförlitlig infrastruktur som fungerar i stor skala och är feltolerant. Styrka system [!UICONTROL IRIS] är bland annat Amazon SQS, Amazon EC2 och Cassandra.

**Regler för segmentmappning**

Om du vill optimera trafiken mellan [!UICONTROL IRIS] och segmentmål skickar segment [!UICONTROL IRIS] till mål baserat på en uppsättning regler.

1. **Ny segmentkvalificering**: när en enhet kvalificerar sig för ett nytt segment, skickar alla segment som är associerade med den enheten till alla mål som är mappade till dessa segment. [!UICONTROL IRIS]

1. **Ny segmentdiskvalificering**: när en enhet inte längre är kvalificerad för ett segment, skickar alla segmentkvalifikationer och diskvalifikationer som är kopplade till den enheten till alla destinationer som är mappade till dessa segment. [!UICONTROL IRIS]

1. **Målmappningsuppdateringar**: När en målmappning uppdateras skickar alla segment som är kopplade till en enhet till alla mål som är mappade till dessa segment nästa gång Audience Manager ser enheten. [!UICONTROL IRIS]

1. **Uppdateringar** av enhetsdiagram: När ett enhets-ID läggs till eller tas bort från enhetsdiagrammet som används för att utvärdera ett segment, skickas alla segment som är kopplade till den enheten till alla mål som är mappade till dessa segment nästa gång Audience Manager ser enheten. [!UICONTROL IRIS]

>[!IMPORTANT]
>
>Om Audience Manager inte hittar någon av uppdateringarna ovan under 3 dagar i följd skickar alla segment som är kopplade till en enhet till alla mål som är mappade till dessa segment nästa gång Audience Manager ser enheten. [!UICONTROL IRIS]

**Exempeldatafil**

Följande exempel innehåller segmentdata i realtid från [!UICONTROL IRIS]. Tänk på att detta bara är exempeldata. Varje kund kan ha olika formateringskrav så att innehållet kan variera.

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## PCS (Profile Cache Server) {#pcs}

Se [Komponenter för datainsamling](../../reference/system-components/components-data-collection.md).
