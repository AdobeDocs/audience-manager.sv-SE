---
description: Se det här dokumentet för en fullständig lista över Adobe Audience Manager-ID:n.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Se det här dokumentet för en fullständig lista över Adobe Audience Manager-ID:n.
seo-title: Index över ID:n i Audience Manager
solution: Audience Manager
title: Index över ID:n i Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 3%

---


# Index of IDs in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Översikt {#overview}

[!DNL Audience Manager] använder flera ID:n för att identifiera och hantera data som du skickar till den. I den här artikeln finns en fullständig lista över [!DNL Audience Manager] ID:n samt exempel på de prefix du bör använda dem med.

## ID-prefix {#prefixing}

Du kan referera till de flesta av dessa ID:n med deras fristående namn, men de flesta av dem är avsedda att användas med olika prefix när du skickar data via [!DNL DCS] anrop. Vissa av dessa ID:n används av [!DNL Audience Manager] utan att exponeras för användare, medan andra också visas i användargränssnittet.

Mer information om de prefix som används i följande exempel finns i [Attribut som stöds för DCS API-anrop](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Lista med ID:n {#id-list}

| ID | Namn och beskrivning | Användning och exempel | Plats för användargränssnitt |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], kallas även [!UICONTROL Device ID]. Ett numeriskt 38-siffrigt enhets-ID som associeras med varje enhet som det interagerar med. [!DNL Audience Manager] Tänk på det här ID:t när du ser ett omnämnande av unika användare i [!DNL Audience Manager] användargränssnittet. Audience Manager sparar det här ID:t som en [!DNL cookie] i domänen för `demdex.net` tredje part. | I [!DNL DCS] anrop `uuid` föregås av `d_` prefixet . <br>Exempel: `d_uuid = 07955261652886032950143702505894272138` | Du kan filtrera [!DNL traits] efter [!UICONTROL Device ID] när du skapar [stilfulla modeller](../features/algorithmic-models/create-model.md)och [skapar segment](../features/segments/segment-builder.md). Du kan också filtrera resultaten efter [!UICONTROL Device ID] när du kör [allmänna rapporter för Traits](../reporting/general-reports.md) och [Trend Reports for Traits](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Detta är det ID som ett företag får när det registrerar sig för ett [!DNL Experience Cloud] konto. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Visas inte i [!DNL Audience Manager] användargränssnittet. Om du vill veta mer om hur du kan hitta ditt företags [!DNL Organization ID]information läser du [Hitta ditt företags-ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. Det [!DNL PID] är ett företags-ID i [!DNL Audience Manager]. Audience Manager associerar en [!DNL imsOrgId] till en [!DNL PID]. | `1352` | Visas inte i [!DNL Audience Manager] användargränssnittet. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. ID:t ( [!DNL Experience Cloud] , tidigare förkortningar[!DNL ECID]eller [!DNL MID] ) hämtas matematiskt från din [!DNL MCID]och [!DNL Organization ID][!DNL Audience Manager] [!UICONTROL Unique User ID]. Så länge dessa ID:n är konstanta är det helt enkelt ett viktigt problem att generera rätt [!DNL ECID] för en viss användare. Med samma [!DNL Organization ID] och [!DNL Audience Manager] samma [!DNL UUID] värde får [!DNL ECID] du alltid samma värde. Du kan läsa mer om [!DNL ECID] dem i dokumentationen för [cookies och Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | Visas inte i [!DNL Audience Manager] användargränssnittet. |
| [!DNL SID] | [!UICONTROL Trait ID]. Den [!UICONTROL Trait ID] unika identifieringen [!DNL traits] i [!DNL Audience Manager] miljön. | I [!DNL DCS] anrop `SID` föregås av `d_` prefixet . <br>Exempel `d_sid=289983`. | En [!UICONTROL Trait ID] tilldelas varje [!DNL trait]och visas i användargränssnittet på sidan [Traits](../features/traits/trait-details-page.md) . |
| [!DNL SID] | [!UICONTROL Segment ID]. Den [!UICONTROL Segment ID] unika identifieringen [!DNL segments] i [!DNL Audience Manager] miljön. | I [!DNL DCS] anrop `SID` föregås av `d_` prefixet . <br>Exempel `d_sid=4798574`. | En [!UICONTROL Segment ID] tilldelas varje [!DNL segment]och visas i användargränssnittet på sidan [Segment](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Detta ID identifierar unikt segment i [!DNL Audience Manager] miljön. | `741232` | En [!UICONTROL Legacy Segment ID] tilldelas varje segment och visas i användargränssnittet på sidan [Segment](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | [!UICONTROL Destination ID]. Den [!UICONTROL Destination ID] unika identifieringen [!DNL destinations] i [!DNL Audience Manager] miljön. Alla [!DNL destination] i användargränssnittet tilldelas ett ID. | `2523` | En [!UICONTROL Destination ID] tilldelas varje [!DNL destination]och visas i användargränssnittet på sidan [Destinationer](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | [!UICONTROL Data Source ID] (kallas även [!UICONTROL Data Provider ID]). Detta [!UICONTROL Data Source ID] är ett namnutrymme för ID:n eller [!DNL traits]. Varje [!DNL data source] (dataleverantör) i användargränssnittet tilldelas ett ID. | I [!DNL DCS] anrop `dpid` föregås av `d_` prefixet . <br>Exempel: `d_dpid=39217`. | En [!UICONTROL Data Provider ID] tilldelas varje [!DNL data source]och visas i användargränssnittet på sidan [Datakällor](../features/datasources-list-and-settings.md) . |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], kallas även [!DNL CRM ID] eller [!UICONTROL Cross-Device ID]. Ett ID för tredje part. Detta är det ID med vilket du identifierar slutanvändare i ditt eget [!DNL CRM] system. Du kan synkronisera [!DNL DPUUIDs] med [!DNL Audience Manager] [!DNL UUIDs] och du kan synkronisera [!DNL DPUUIDs] från olika [!UICONTROL Data Sources] ([!DNL DPIDs]) i ID-synkroniseringsprocessen. | I [!DNL DCS] anrop `dpuuid` föregås av `d_` prefixet . <br> Exempel `d_dpuuid=2132-3423vn-343fds-3432r`. | Du kan filtrera [!DNL traits] efter [!UICONTROL Cross-Device ID] när du skapar [stilfulla modeller](../features/algorithmic-models/create-model.md)och [skapar segment](../features/segments/segment-builder.md). Du kan också filtrera resultaten efter [!UICONTROL Cross-Device ID] när du kör [allmänna rapporter för Traits](../reporting/general-reports.md) och [Trend Reports for Traits](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Se `DPUUID`. | Se `DPUUID`. | Se `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Paren [!DNL CID] och [!DNL CID_IC] nyckelvärdepar ersätter [!DNL DPID] och [!DNL DPUUID]. De har samma funktioner som [!DNL DPID] och [!DNL DPUUID], men är mer effektiva eftersom de innehåller data provider-ID och användar-ID (eller integrationskod) i ett enda nyckelvärdepar. | I [!DNL DCS] anrop föregås dessa ID:n av `d_` prefixet. <br>Exempel: `d_cid_ic=39217_myIntegrationCode`. | Se `DPID` och `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Ett ID som är unikt för varje maskinvaruenhet och som ska användas i annonssyfte. Anges vanligtvis av tillverkaren av enhetens eller enhetens operativsystem. | Se [Globala enhets-ID](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Globala enhets-ID:n är enhets-ID:n som är unika för varje enhet och tillhandahålls av enhetstillverkaren eller operativsystemet. Tabellen nedan förklarar vad dessa ID:n är och vilket format de har. Mer information om globala enhets-ID:n och hur du använder dem i [!DNL Audience Manager]finns i [Globala datakällor](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Namn och beskrivning | Exempel |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID:n är mobilenhetsidentifierare som tillhandahålls av enhetstillverkaren. Dessa ID:n representerar enheter som kör [!DNL iOS] operativsystemet. | Formatet består strikt av 32 hexadecimala versaler, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken.<br> Exempel: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]Det är mobilenhetsidentifierare som tillhandahålls av Android-enhetstillverkare. Dessa ID:n representerar enheter som kör [!DNL Android] operativsystemet. | Formatet består strikt av 32 små hexadecimala siffror, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken. <br>Exempel: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representerar [!DNL Roku] direktuppspelningsenheter. | Formatet består strikt av 32 små hexadecimala siffror, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken. <br>Exempel: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]är enhetsidentifierare som genereras av [!DNL Windows 10] per enhet och användare. | [!DNL MAID]s formateras som alfanumeriska strängar. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]är enhetsidentifierare som tillhandahålls av [!DNL Samsung] smarta TV:er. | [!DNL Samsung] [!DNL DUID]s formateras som alfanumeriska strängar. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Enhetsidentifierare som representerar enheter som kör [!DNL Fire OS] operativsystemet. | Formatet består strikt av 32 små hexadecimala siffror, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken. <br>Exempel: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |