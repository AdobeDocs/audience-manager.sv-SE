---
description: Den här sidan innehåller stegvis vägledning om hur man kombinerar offline-CRM-data med realtidsbeteendedata för autentiserade användare för att skapa målgruppssegment och sedan skickar dessa målgruppssegment till personbaserade destinationer.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: Arbetsflöde C - Personalization baserat på autentiserad aktivitet i kombination med offlinedata
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 0%

---

# Arbetsflöde C - Personalization baserat på autentiserad aktivitet i kombination med offlinedata {#workflow-c}

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

Den här sidan innehåller stegvisa anvisningar om hur du kombinerar offline-data för [!DNL CRM] med beteendedata i realtid för autentiserade användare för att skapa målgruppssegment, och sedan skickar du dessa målgruppssegment till [!DNL People-Based Destinations].

## Steg 1 - Konfigurera Source-inställningar för data {#configure-data-source-settings}

Beroende på om dina [DPUID:n](../../reference/ids-in-aam.md) är gemener, hash-kodade e-postadresser, kan du behöva konfigurera datakällan som ska lagra de hash-kodade e-postadresserna.

 

**Scenario 1: [DPUID:n](../../reference/ids-in-aam.md) är redan små och har e-postadresser som hashas.**

I det här fallet går du till [Steg 5 - Konfigurera personbaserad plattformsautentisering](#configure-authentication).

 

**Scenario 2: dina [DPUID:n](../../reference/ids-in-aam.md) är inte gemener, hash-kodade e-postadresser.**

I det här fallet måste du skapa en ny datakälla för olika enheter som lagrar dina hashade e-postadresser. Så här gör du:

1. Logga in på ditt Audience Manager-konto, gå till **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** och klicka på **[!UICONTROL Add New]**.
1. Ange **[!UICONTROL Name]** och **[!UICONTROL Description]** som ny datakälla.
1. Välj **[!UICONTROL ID Type]** i listrutan **[!UICONTROL Cross Device]**.
1. I avsnittet **[!UICONTROL Data Source Settings]** markerar du både alternativen **[!UICONTROL Inbound]** och **[!UICONTROL Outbound]** och aktiverar alternativet **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Använd listrutan för att välja etiketten **[!UICONTROL Emails(SHA256, lowercased)]** för den här datakällan.

   >[!IMPORTANT]
   >
   >Med det här alternativet anges endast att datakällan innehåller data som har hash-kodats med den specifika algoritmen. Audience Manager hash-kodar inte data i det här steget. Kontrollera att e-postadresserna som du planerar att lagra i den här datakällan redan har hash-kodats med algoritmen [!DNL SHA256]. Annars kan du inte använda den för [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Se [Datainhämtning](people-based-destinations-prerequisites.md#data-onboarding) för vanliga frågor om hur du ska överföra offlinedata till Audience Manager för personbaserade destinationer.

I videon nedan finns en videosjälvstudiekurs om hur du skapar en datakälla för [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Steg 2 - Använd deklarerade ID:n för att matcha DPUUID:n med hashed-e-postadresser via HTTP-anrop i realtid {#match-email-addresses}

Om du vill kvalificera autentiserade användare för regelbaserade egenskaper måste du skicka trait-kvalificeringen via [deklarerade ID:n](../declared-ids.md).

### Exempel

Säg att du har skapat följande två datakällor.

| ID för datakälla | Innehåll i datakälla |
| -------------- | -------------------------- |
| 999999 | Befintliga DPUID (CRM ID) |
| 987654 | Hårda e-postadresser |

 

Sedan vill du kvalificera CRM-ID:n nedan för egenskapen i tabellen.

| DPUID (CRM-ID) | E-postadress | Hash-kodad e-postadress | Trait |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f16625093a19bc32fff15041 149 | location = US |

 

Ditt deklarerade ID ska följa den här syntaxen:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

I exemplet ovan ska det deklarerade ID-anropet se ut så här:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Steg 3 - Skapa en profilkopplingsregel för segmentering {#create-profile-merge-rule-segmentation}

Nästa steg är att skapa en ny sammanfogningsregel som hjälper dig att skapa målgruppssegment som ska skickas till [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Om du redan har en regel definierad med alternativen **[!UICONTROL Current Authenticated Profiles]** eller **[!UICONTROL Last Authenticated Profiles]** kan du hoppa till [Steg 4 - Skapa målgruppssegment](#create-audience-segments).

1. Logga in på ditt Audience Manager-konto och gå till **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Klicka på **[!UICONTROL Add New Rule]**.
3. Ange en profilkopplingsregel **[!UICONTROL Name]** och **[!UICONTROL Description]**.
4. I avsnittet **[!UICONTROL Profile Merge Rule Setup]** väljer du regeln **[!UICONTROL Current Authenticated Profiles]** eller **[!UICONTROL Last Authenticated Profiles]** i listan **[!UICONTROL Cross-Device Options]**.
5. I listan **[!UICONTROL Cross-Device Profile Options]** väljer du de datakällor som du vill köra segmenteringen på. Dessa ska vara de datakällor som innehåller dina befintliga DPUID.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Steg 4 - Skapa målgruppssegment {#create-audience-segments}

Om du vill skapa nya segment använder du [Segmentverktyget](../segments/segment-builder.md). Om du har befintliga målgruppssegment som du vill skicka till [!DNL People-Based Destinations] går du till [Steg 5 - Konfigurera personbaserad plattformsautentisering](#configure-authentication).

## Steg 5 - Konfigurera personbaserad plattformsautentisering {#configure-authentication}

1. Logga in på ditt Audience Manager-konto och gå till **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Om du har en tidigare konfigurerad integrering med en social plattform bör du se den här sidan. I annat fall är sidan tom.
   ![Personbaserad integration](assets/pbd-config.png)
2. Klicka på **[!UICONTROL Add Account]**.
3. Använd listrutan **[!UICONTROL People-Based Platform]** för att välja den plattform som du vill konfigurera integreringen med.
   ![Personbaserad-plattform](assets/pbd-add.png)
4. Klicka på **[!UICONTROL Confirm]** om du vill omdirigeras till autentiseringssidan för den valda plattformen.
5. När du har autentiserat dig på ditt konto för sociala plattformar omdirigeras du till Audience Manager där du ska se dina associerade annonskonton. Välj det annonserarkonto som du vill använda och klicka på **[!UICONTROL Confirm]**.
6. Audience Manager visar ett meddelande högst upp på sidan för att tala om för dig om kontot har lagts till. I meddelandet kan du även lägga till en e-postadress för kontakt för att få meddelanden när autentiseringen för den sociala plattformen håller på att gå ut.

>[!IMPORTANT]
>
>Audience Manager hanterar integreringen med sociala plattformar genom autentiseringstoken som upphör efter en viss tid. Mer information om hur du förnyar utgångna token finns i Förnyelse av autentiseringstoken.

## Steg 6 - Skapa ett personbaserat mål {#create-destination}

1. Logga in på ditt Audience Manager-konto, gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** och klicka på **[!UICONTROL Create Destination]**.
1. I avsnittet **[!UICONTROL Basic Information]** anger du **[!UICONTROL Name]** och **[!UICONTROL Description]** för den nya datakällan och använder följande inställningar:
   * **[!UICONTROL Category]**: Integrerade plattformar;
   * **[!UICONTROL Type]**: Personbaserad;
   * **[!UICONTROL Platform]**: välj den personbaserade plattform som du vill skicka målgruppssegment till;
   * **[!UICONTROL Account]**: välj önskat annonserarkonto som är associerat med den valda plattformen.
     ![create-destination](assets/pbd-create-destination.png)
1. Klicka på **[!UICONTROL Next]**.
1. Välj den **[!UICONTROL Data Export Labels]** som du vill ange för det här målet.
1. I avsnittet **[!UICONTROL Configuration]** väljer du datakällan som innehåller dina hash-kodade datakällor.
1. I avsnittet **[!UICONTROL Segment Mappings]** markerar du de segment som du vill skicka till det här målet. Detta är de segment som du skapade i [Steg 4 - Skapa målgruppssegment](#create-audience-segments).
1. Spara målet.
