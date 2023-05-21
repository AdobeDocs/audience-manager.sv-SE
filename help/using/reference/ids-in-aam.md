---
description: Se det här dokumentet för en fullständig lista över Adobe Audience Manager ID:n.
keywords: DPID, DPUUID CID, UUID uuid; uuid, uuid, uuuid, uuid, uuid, uuid, uuuid, uuuid, uuuid, uuuid, uuuid, uuuid, uuid, uuuid, uuuid, uuuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Index över ID:n i Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: e408c118870fb331c40758be8a7e6b38690aeb5f
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 3%

---

# Index för ID:n i [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Översikt {#overview}

[!DNL Audience Manager] använder flera ID:n för att identifiera och hantera data som du skickar till den. I den här artikeln finns en fullständig lista över [!DNL Audience Manager] ID:n, tillsammans med exempel på de prefix du ska använda dem med.

## ID-prefix {#prefixing}

Även om du kan referera till de flesta av dessa ID:n med deras fristående namn, är de flesta av dem avsedda att användas med olika prefix, när du skickar in data via [!DNL DCS] samtal. Vissa av dessa ID:n används av [!DNL Audience Manager] utan att exponeras för användare, medan andra också visas i användargränssnittet.

Mer information om de prefix som används i följande exempel finns i [Attribut som stöds för DCS API-anrop](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Lista med ID:n {#id-list}

| ID | Namn och beskrivning | Användning och exempel | Plats för användargränssnitt |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], även känt som [!UICONTROL Device ID]. Ett numeriskt 38-siffrigt enhets-ID som [!DNL Audience Manager] associeras med varje enhet som interagerar med. Tänk på det här ID:t när du ser ett omnämnande av unika användare i [!DNL Audience Manager] Gränssnitt. Audience Manager sparar detta ID som [!DNL cookie] i `demdex.net` Domän från tredje part. | I [!DNL DCS] samtal, `uuid` föregås av `d_` prefix. <br>Exempel: `d_uuid = 07955261652886032950143702505894272138` | Du kan filtrera [!DNL traits] av [!UICONTROL Device ID] när du skapar [Utseendeliknande modeller](../features/algorithmic-models/create-model.md)och [bygga segment](../features/segments/segment-builder.md). Du kan också filtrera resultaten efter [!UICONTROL Device ID] vid körning [Allmänna rapporter för Traits](../reporting/general-reports.md) och [Trendrapporter för Traits](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Detta är det ID som ett företag får när det registrerar sig för ett [!DNL Experience Cloud] konto. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Inte synlig i [!DNL Audience Manager] användargränssnitt. För att lära dig hur du kan hitta ditt företags [!DNL Organization ID], läsa [Hitta ditt företags-ID](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. The [!DNL PID] är ett företags-ID i [!DNL Audience Manager]. Audience Manager associerar en [!DNL imsOrgId] till [!DNL PID]. | `1352` | Inte synlig i [!DNL Audience Manager] användargränssnitt. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. The [!DNL Experience Cloud] ID ([!DNL ECID], gamla förkortningar [!DNL MID] eller [!DNL MCID]) hämtas matematiskt från [!DNL Organization ID] och [!DNL Audience Manager] [!UICONTROL Unique User ID]. Så länge dessa ID:n är konstanta genereras rätt [!DNL ECID] för en viss användare är helt enkelt ett viktigt problem. Med samma [!DNL Organization ID] och [!DNL Audience Manager] [!DNL UUID] du får samma [!DNL ECID] värde varje gång. Du kan läsa mer om [!DNL ECID] i [Cookies och Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) dokumentation. | `mid = 08382830887934830189014177072406221371` | Inte synlig i [!DNL Audience Manager] användargränssnitt. |
| [!DNL SID] | [!UICONTROL Trait ID]. The [!UICONTROL Trait ID] unikt identifierar [!DNL traits] i [!DNL Audience Manager] miljö. | I [!DNL DCS] samtal, `SID` föregås av `d_` prefix. <br>Exempel `d_sid=289983`. | A [!UICONTROL Trait ID] tilldelas varje [!DNL trait]och visas i användargränssnittet i [Traits](../features/traits/trait-details-page.md) sida. |
| [!DNL SID] | [!UICONTROL Segment ID]. The [!UICONTROL Segment ID] unikt identifierar [!DNL segments] i [!DNL Audience Manager] miljö. | I [!DNL DCS] samtal, `SID` föregås av `d_` prefix. <br>Exempel `d_sid=4798574`. | A [!UICONTROL Segment ID] tilldelas varje [!DNL segment]och visas i användargränssnittet i [Segment](../features/segments/segment-summary-view.md) sida. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Detta ID identifierar segment unikt i [!DNL Audience Manager] miljö. | `741232` | A [!UICONTROL Legacy Segment ID] tilldelas varje segment och visas i användargränssnittet i [Segment](../features/segments/segment-summary-view.md) sida. |
| [!DNL destID] | [!UICONTROL Destination ID]. The [!UICONTROL Destination ID] unikt identifierar [!DNL destinations] i [!DNL Audience Manager] miljö. Ett ID tilldelas varje [!DNL destination] i användargränssnittet. | `2523` | A [!UICONTROL Destination ID] tilldelas varje [!DNL destination]och visas i användargränssnittet i [Destinationer](../features/destinations/destinations-home.md) sida. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (kallas även [!UICONTROL Data Provider ID]). The [!UICONTROL Data Source ID] är ett namnutrymme för ID:n eller [!DNL traits]. Ett ID tilldelas varje [!DNL data source] (DataProvider) i användargränssnittet. | I [!DNL DCS] samtal, `dpid` föregås av `d_` prefix. <br>Exempel: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] tilldelas varje [!DNL data source]och visas i användargränssnittet i [Datakällor](../features/datasources-list-and-settings.md) sida. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]som också kallas [!DNL CRM ID] eller [!UICONTROL Cross-Device ID]. Ett ID för tredje part. Detta är det ID som du använder för att identifiera slutanvändare i din egen [!DNL CRM] system. Du kan synkronisera [!DNL DPUUIDs] med [!DNL Audience Manager] [!DNL UUIDs] och du kan synkronisera [!DNL DPUUIDs] från dina [!UICONTROL Data Sources] ([!DNL DPIDs]) i ID-synkroniseringsprocessen. | I [!DNL DCS] callls, `dpuuid` föregås av `d_` prefix. <br> Exempel `d_dpuuid=2132-3423vn-343fds-3432r`. | Du kan filtrera [!DNL traits] av [!UICONTROL Cross-Device ID] när du skapar [Utseendeliknande modeller](../features/algorithmic-models/create-model.md)och [bygga segment](../features/segments/segment-builder.md). Du kan också filtrera resultaten efter [!UICONTROL Cross-Device ID] vid körning [Allmänna rapporter för Traits](../reporting/general-reports.md) och [Trendrapporter för Traits](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Se `DPUUID`. | Se `DPUUID`. | Se `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. The [!DNL CID] och [!DNL CID_IC] ersätta nyckelvärdepar [!DNL DPID] och [!DNL DPUUID]. De har samma funktioner som [!DNL DPID] och [!DNL DPUUID], men är mer effektiva eftersom de innehåller data provider-ID och användar-ID (eller integreringskod) i ett enda nyckelvärdepar. | I [!DNL DCS] anrop, dessa ID:n föregås av `d_` prefix. <br>Exempel: `d_cid_ic=39217_myIntegrationCode`. | Se `DPID` och `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Ett ID som är unikt för varje maskinvaruenhet och som ska användas i annonssyfte. Anges vanligtvis av tillverkaren av enhetens eller enhetens operativsystem. | Se [Globala enhets-ID](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Globala enhets-ID:n är enhets-ID:n som är unika för varje enhet och tillhandahålls av enhetstillverkaren eller operativsystemet. Tabellen nedan förklarar vad dessa ID:n är och vilket format de har. Mer information om globala enhets-ID:n och hur du använder dem i [!DNL Audience Manager], läsa [Globala datakällor](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Namn och beskrivning | Exempel |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID:n är mobilenhetsidentifierare som tillhandahålls av enhetstillverkaren. Dessa ID:n representerar enheter som kör [!DNL iOS] operativsystem. | Formatet består strikt av 32 hexadecimala versaler, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken.<br> Exempel: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]Det är mobilenhetsidentifierare som tillhandahålls av Android-enhetstillverkare. Dessa ID:n representerar enheter som kör [!DNL Android] operativsystem. | Formatet består strikt av 32 små hexadecimala siffror, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken. <br>Exempel: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representera [!DNL Roku] direktuppspelningsenheter. | Formatet består strikt av 32 små hexadecimala siffror, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken. <br>Exempel: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]är enhetsidentifierare som genereras av [!DNL Windows 10] per enhet, per användare. | [!DNL MAID]s formateras som alfanumeriska strängar. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] är enhetsidentifierare från [!DNL Samsung] Smarta TV:er. | [!DNL Samsung] [!DNL TIFA] ID:n formateras som alfanumeriska strängar. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Enhetsidentifierare som representerar enheter som kör [!DNL Fire OS] operativsystem. | Formatet består strikt av 32 små hexadecimala siffror, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken. <br>Exempel: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | Enhetsidentifierare som representerar enheter som kör [!DNL LG webOS] operativsystem. | Formatet består strikt av 32 små hexadecimala siffror, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken. <br>Exempel: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | Enhetsidentifierare som representerar enheter som kör operativsystemet Vizio smart TV. | [!DNL Vizio IFA] ID:n formateras som alfanumeriska strängar. <br>Exempel: `7XCBNROQJQPYW`. |
