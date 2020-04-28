---
description: Se det här dokumentet för en fullständig lista över Adobe Audience Manager-ID:n.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Se det här dokumentet för en fullständig lista över Adobe Audience Manager-ID:n.
seo-title: Index för ID:n i Audience Manager
solution: Audience Manager
title: Index för ID:n i Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 723c75e8946c42779b4c27727ff9e6398b5fc9b1

---


# Index för ID:n i Audience Manager{#index-of-ids-in-audience-manager}

## Översikt {#overview}

Audience Manager använder flera ID:n för att identifiera och hantera data som du skickar till den. I den här artikeln finns en fullständig lista över Adobe Audience Manager-ID:n, tillsammans med exempel på de prefix du bör använda dem med.

## ID-prefix {#prefixing}

Du kan referera till de flesta av dessa ID:n med deras fristående namn, men de flesta av dem är avsedda att användas med olika prefix när du skickar data via DCS-anrop. Vissa av dessa ID:n används av Audience Manager utan att vara exponerade för användarna, medan andra också är synliga i användargränssnittet.

Mer information om de prefix som används i följande exempel finns i [Attribut som stöds för DCS API-anrop](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## Audience Manager List of IDs {#id-list}

| ID | Namn och beskrivning | Användning och exempel | Användargränssnittets plats |
|---|---|---|---|
| [!DNL AAM UUID] | Unikt användar-ID för Audience Manager, även kallat [!UICONTROL Device ID]. Ett numeriskt 38-siffrigt enhets-ID som Audience Manager associerar med varje enhet som det interagerar med. Tänk på det här ID:t när du ser ett omnämnande av unika användare i gränssnittet för Audience Manager. Audience Manager sparar detta ID som en cookie i domänen från `demdex.net` tredje part. | I [!DNL DCS] anrop `uuid` föregås av `d_` prefixet . <br>Exempel: `d_uuid = 07955261652886032950143702505894272138` | Du kan filtrera egenskaper efter [!UICONTROL Device ID] när du skapar [stilfulla modeller](../features/algorithmic-models/create-model.md)och [skapar segment](../features/segments/segment-builder.md). Du kan också filtrera resultaten efter [!UICONTROL Device ID] när du kör [allmänna rapporter för Traits](../reporting/general-reports.md) och [Trend Reports for Traits](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | Organisations-ID. Detta är det ID som ett företag får när det registrerar sig för ett Experience Cloud-konto. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Visas inte i gränssnittet för Audience Manager. Om du vill veta mer om hur du kan hitta ditt företags organisations-ID läser du [Hitta ditt företags-ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| PID | Partner-ID. PID är ett företags-ID i Audience Manager. Audience Manager kopplar en [!DNL imsOrgId] till en [!DNL PID]. | `1352` | Visas inte i gränssnittet för Audience Manager. |
| [!DNL ECID], [!DNL MID] | Experience Cloud ID. Experience Cloud ID ([!DNL ECID], tidigare förkortningar [!DNL MID] eller [!DNL MCID]förkortningar) hämtas matematiskt från ditt organisations-ID och Audience Manager Unikt användar-ID. Så länge dessa ID:n är konstanta är det helt enkelt ett viktigt problem att generera rätt [!DNL ECID] för en viss användare. Med samma organisations-ID och Audience Manager får [!DNL UUID] du samma [!DNL ECID] värde varje gång. Du kan läsa mer om ECID i dokumentationen för [cookies och Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | Visas inte i gränssnittet för Audience Manager. |
| [!DNL SID] | Trait ID. Trait ID identifierar unikt egenskaper i Audience Manager-miljön. | I [!DNL DCS] anrop `SID` föregås av `d_` prefixet . <br>Exempel `d_sid=289983`. | Ett Trait ID tilldelas varje trait och visas i användargränssnittet på sidan [Traits](../features/traits/trait-details-page.md) (Traits). |
| [!DNL SID] | Segment-ID. Segment-ID:t identifierar unikt segment i Audience Manager-miljön. | I [!DNL DCS] anrop `SID` föregås av `d_` prefixet . <br>Exempel `d_sid=4798574`. | Ett segment-ID tilldelas varje segment och visas i användargränssnittet på sidan [Segment](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | Äldre segment-ID. Detta ID identifierar unikt segment i Audience Manager-miljön. | `741232` | Ett äldre segment-ID tilldelas varje segment och visas i användargränssnittet på sidan [Segment](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | Mål-ID. Mål-ID:t identifierar unikt mål i Audience Manager-miljön. Varje mål i användargränssnittet tilldelas ett ID. | `2523` | Ett mål-ID tilldelas varje mål och visas i gränssnittet på sidan [Destinationer](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | ID för datakälla (kallas även dataproviderns ID). Datakällans ID är ett namnutrymme för ID:n eller egenskaper. Varje datakälla (DataProvider) i användargränssnittet tilldelas ett ID. | I [!DNL DCS] anrop `dpid` föregås av `d_` prefixet . <br>Exempel: `d_dpid=39217`. | Ett Data Provider-ID tilldelas varje datakälla och visas i användargränssnittet på sidan [Datakällor](../features/datasources-list-and-settings.md) . |
| [!DNL DPUUID] | Dataproviderns unika användar-ID, kallas även [!DNL CRM ID] eller [!UICONTROL Cross-Device ID]. Ett ID för tredje part. Detta är det ID med vilket du identifierar slutanvändare i ditt eget [!DNL CRM] system. Du kan synkronisera [!DNL DPUUIDs] med Audience Manager [!DNL UUIDs] och du kan synkronisera [!DNL DPUUIDs] från olika datakällor ([!DNL DPIDs]) i ID-synkroniseringsprocessen. | I DCS-anrop `dpuuid` föregås av `d_` prefixet . <br> Exempel `d_dpuuid=2132-3423vn-343fds-3432r`. | Du kan filtrera egenskaper efter [!UICONTROL Cross-Device ID] när du skapar [stilfulla modeller](../features/algorithmic-models/create-model.md)och [skapar segment](../features/segments/segment-builder.md). Du kan också filtrera resultaten efter [!UICONTROL Cross-Device ID] när du kör [allmänna rapporter för Traits](../reporting/general-reports.md) och [Trend Reports for Traits](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Se `DPUUID`. | Se `DPUUID`. | Se `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | Kund-ID, integreringskod för kund-ID. Paren [!DNL CID] och [!DNL CID_IC] nyckelvärdepar ersätter [!DNL DPID] och [!DNL DPUUID]. De har samma funktioner som [!DNL DPID] och [!DNL DPUUID], men är mer effektiva eftersom de innehåller data provider-ID och användar-ID (eller integrationskod) i ett enda nyckelvärdepar. | I DCS-anrop föregås dessa ID:n av `d_` prefixet. <br>Exempel: `d_cid_ic=39217_myIntegrationCode`. | Se `DPID` och `DPUUID`. |
| [!DNL DAID] | Enhetens annons-ID. Ett ID som är unikt för varje maskinvaruenhet och som ska användas i annonssyfte. Anges vanligtvis av tillverkaren av enhetens eller enhetens operativsystem. | Se [Globala enhets-ID](#global-device-ids). |  |

## Globala enhets-ID {#global-device-ids}

Globala enhets-ID:n är enhets-ID:n som är unika för varje enhet och tillhandahålls av enhetstillverkaren eller operativsystemet. Tabellen nedan förklarar vad dessa ID:n är och vilket format de har. Mer information om globala enhets-ID:n och hur du använder dem i Audience Manager finns i [Globala datakällor](/help/using/features/global-data-sources.md).

| ID | ID för global datakälla | Namn och beskrivning | Exempel |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID:n är mobilenhetsidentifierare som tillhandahålls av enhetstillverkaren. Dessa ID:n representerar enheter som kör iOS-operativsystemet. | Formatet består strikt av 32 hexadecimala versaler, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken.<br> Exempel: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]Det är mobilenhetsidentifierare som tillhandahålls av Android-enhetstillverkare. Dessa ID:n representerar enheter som kör [!DNL Android] operativsystemet. | Formatet består strikt av 32 små hexadecimala siffror, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken. <br>Exempel: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] representerar [!DNL Roku] direktuppspelningsenheter. | Formatet består strikt av 32 små hexadecimala siffror, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken. <br>Exempel: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]är enhetsidentifierare som genereras av [!DNL Windows 10] per enhet och användare. | [!DNL MAID]s formateras som alfanumeriska strängar. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]Dessa är enhetsidentifierare från Samsung Smart TV. | Samsung [!DNL DUID]är formaterade som alfanumeriska strängar. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Enhetsidentifierare som representerar enheter som kör [!DNL Fire OS] operativsystemet. | Formatet består strikt av 32 små hexadecimala siffror, som visas i fem grupper och avgränsas med bindestreck, i formatet 8-4-4-4-12, med totalt 36 tecken. <br>Exempel: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |

