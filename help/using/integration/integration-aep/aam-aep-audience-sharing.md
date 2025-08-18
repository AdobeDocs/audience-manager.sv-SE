---
description: Lär dig hur du aktiverar datadelning och hur målgrupper delas mellan Audience Manager och Adobe Experience Platform
solution: Audience Manager
title: Experience Platform segmentdelning med Audience Manager och andra Experience Cloud-lösningar
keywords: AEP målgruppsdelning, AEP segment, plattformssegment, segmentdelning, målgruppsdelning, dela segment, AAM AEP segmentdelning
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 0%

---

# Experience Platform segmentdelning med Audience Manager och andra Experience Cloud-lösningar

## Översikt {#overview}

Tack vare målgruppsdelningsfunktionen mellan Audience Manager och Adobe Experience Platform kan ni dela era Audience Manager-egenskaper och -segment till Adobe Experience Platform och Experience Platform till Audience Manager.

Du behöver målplatsen [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=sv-SE) och [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=sv-SE) i Experience Platform för att kunna dela målgrupper mellan Audience Manager och Adobe Experience Platform.

Du kan använda Audience Manager-egenskaper och segment i Experience Platform för att lägga till Audience Manager-data i dina kundprofiler och dra nytta av Experience Platform [segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=sv-SE).

I Audience Manager kan du använda Experience Platform-segment för datahanteringsplattformens användningsfall, till exempel:
* Lägg till [data från tredje part](/help/using/overview/data-types-collected.md#third-party-data) i dina segment;
* [Algoritmisk modellering](/help/using/features/algorithmic-models/understanding-models.md);
* Aktivera dina segment för mål som ännu inte stöds i Experience Platform [målkatalog](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html?lang=sv-SE).

Dessutom delas dina Experience Platform-segment med andra Experience Cloud-lösningar via [bastjänster](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=sv-SE).

>[!IMPORTANT]
>
> * Du behöver en Audience Manager-licens för att kunna aktivera de användningsfall för datahanteringsplattformen som nämns ovan.
> * Du *behöver inte* någon Audience Manager-licens för att dela Experience Platform-segment med Adobe Advertising Cloud, Adobe Target, Marketo och andra Experience Cloud-lösningar via integreringen med bastjänsterna.

Se tabellen nedan för en översikt över användningsfall för målgruppsdelning:

| **Använd skiftläge** | **Adobe Experience Platform** | **Audience Manager** | **Centrala tjänster** |
|---------|----------|---------|---------|
| **Målgruppsdelning** | <ul><li>Berika kundprofiler med Audience Manager-data</li><li>Använd Audience Manager-data vid segmentering med Experience Platform</li></ul> | <ul><li>Lägg till data från tredje part i segment</li><li>Algoritmisk modellering</li><li>Aktivering till ytterligare destinationer</li></ul> | Använd Experience Platform-segment i andra Experience Cloud-lösningar, som Adobe Target, Advertising Cloud eller Marketo. |

{style="table-layout:auto"}

## Audience Manager segment och egenskaper i Adobe Experience Platform {#aam-segments-traits-in-aep}

I avsnitten nedan beskrivs hur du aktiverar datadelning från Audience Manager till Experience Platform och hur du använder Audience Manager-egenskaper och -segment i Experience Platform.

### Aktivera datadelning från Audience Manager till Experience Platform {#enable-aam-to-aep-data}

Om du vill skicka segment och egenskaper från Audience Manager till Experience Platform måste du konfigurera Audience Manager källkoppling i Experience Platform källkatalog. Det här är ett självbetjäningsarbetsflöde som inte kräver medverkan av Adobe kundtjänst eller tekniska team. Läs mer om hur du konfigurerar Audience Manager-källkopplingen:

* [Audience Manager-källa](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=sv-SE)
* [Skapa en Adobe Audience Manager-källanslutning i användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=sv-SE)

>[!IMPORTANT]
>
>Adobe uppmuntrar kunderna att konfigurera anslutningen utan att välja alternativen **[!UICONTROL Select all segments]** och **[!UICONTROL Select all traits]**, vilket visas nedan. Intag av stora Audience Manager-segmentpopulationer påverkar direkt det totala antalet profiler när du skickar ett Audience Manager-segment till Platform via Audience Manager-källan. Det innebär att om du väljer alla segment kan det eventuellt leda till ett profilantal som överskrider licensanvändningsbehörigheten.
>
>![Skärmbild med alternativen Markera alla segment och Markera alla egenskaper avmarkerade i arbetsflödet för att ansluta till Audience Manager-källkopplingen.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Använda Audience Manager-egenskaper och -segment i Experience Platform {#use-aam-data-in-aep}

När du har konfigurerat Audience Manager-källkopplingen för att importera egenskaper och segment från Audience Manager visas dina Audience Manager-data i Experience Platform som **Publiker** i segmentarbetsflödet. Mer information om Audience Manager segment och egenskaper i Experience Platform finns i:

* [Översikt över segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=sv-SE#audiences)
* [Användarhandbok för Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=sv-SE#audiences)

## Adobe Experience Platform segment i Audience Manager {#aep-segments-in-aam}

I avsnitten nedan beskrivs hur du aktiverar datadelning från Experience Platform till Audience Manager och hur du använder Experience Platform-segment i Audience Manager.

### Aktivera datadelning från Experience Platform till Audience Manager {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> I det här avsnittet beskrivs den tidigare integreringen av segmentdelning från Experience Platform till Audience Manager. Nu kan du konfigurera integreringen utan support från Adobe kundrepresentanter. Mer information finns i måldokumentationen för [Experience Cloud-målgrupper](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=sv-SE).

>[!NOTE]
>
> Kontakta en av Adobe Customer Success Manager eller kundtjänst om du vill låsa upp åtkomsten till den här funktionen.

Om du vill skicka segment från Experience Platform till Audience Manager måste du kontakta kundtjänst eller en Customer Success Manager. Kundtjänst- och kundsupportteamen måste registrera en biljett (se mallbiljetten AAM-52354) för att kunna ansluta från Platform till Audience Manager.

Dela planer för data från Platform till Audience Manager för att säkerställa att anslutningen är korrekt konfigurerad. Om du till exempel vill att regionala data ska delas för segment som skickas till Adobe Target, måste dessa uppgifter meddelas i biljetten. Datadelningsanslutningen från Experience Platform till Audience Manager upprättas inom sex arbetsdagar från det att begäran skickades.

### Använda Experience Platform-segment i Audience Manager {#use-aep-data-in-aam}

Segment som du skapar i Experience Platform visas i Audience Manager gränssnitt som signaler, egenskaper och segment, med följande dispositionsregler:

* Signal: För varje Experience Platform-segment ska du se signaler i formatet `segID = segment ID`.
* Trait: The trait rule is the ID of the Experience Platform segment.
* Segment: Segmentet består av den egenskap som beskrivs ovan.

### Signaler {#aep-segments-as-aam-signals}

Välj **[!UICONTROL Audience Data > Signals > General Online Data]** och sök efter `SegId` för att hitta signaler som kommer in från Experience Platform. Du kan använda den här skärmen i felsökningssyfte för att kontrollera om integreringen mellan Experience Platform och Audience Manager har konfigurerats korrekt.

![Se Experience Platform-signaler i Audience Manager på kontrollpanelen Signaler](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Traits {#aep-segments-as-aam-traits}

Audience Manager skapar automatiskt en trait-mapp med namnet **Experience Platform Traits** i ditt fack.

![Egenskaper från Experience Platform-kontrollpanelen](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Du kan använda automatiskt skapade egenskaper i segment tillsammans med andra egenskaper. Du kan till exempel blanda egenskaper som skapats från Experience Platform-segment med egenskaper från tredje part som förvärvats via [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Ett exempel på ett trait som skapats automatiskt från ett Experience Platform-segment finns i skärmbilden nedan:

![Trait from Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Artikelnummer | Namn | Beskrivning |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Traits created from Experience Platform segments are created as onboard traits in Audience Manager. |
| 2 | [!UICONTROL Data Source] | Automatiskt skapad. Alla egenskaper och segment som skapas automatiskt från Experience Platform-segment lagras i datakällan **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Integrationskoden motsvarar segment-ID i Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | trait-uttrycket är `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Ett automatiskt skapat segment som använder det här tecknet som komposition. |

{style="table-layout:auto"}

### Segment {#aep-segments-as-aam-segments}

Audience Manager skapar automatiskt en segmentmapp med namnet **Experience Platform Segments** i segmentlagringen.

![Skärmbild av instrumentpanelen](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Ett exempel på ett segment som skapats automatiskt från ett Experience Platform-segment finns i skärmbilden nedan:

![Skärmbild av segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Artikelnummer | Namn | Beskrivning |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | Integrationskoden motsvarar segment-ID i Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatiskt skapad. Alla egenskaper och segment som skapas automatiskt från Experience Platform-segment lagras i datakällan **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** anger att automatiskt skapade segment följer den sammanslagningsprincip som har konfigurerats i Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Segmentet består av det trait som beskrivs i avsnittet [Traits](#aep-segments-as-aam-traits). |

{style="table-layout:auto"}

## Stöd för Audience Manager Data Export Control i Experience Platform {#aam-data-export-control-in-aep}

Om du vill framtvinga efterlevnad av dataanvändning i Experience Platform måste alla tillämpliga datauppsättningar och fält tilldelas lämpliga [etiketter för dataanvändning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=sv-SE). Dessutom måste [dataanvändningsprinciper](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=sv-SE) aktiveras för specifika marknadsföringsåtgärder mot dessa etiketter, enligt riktlinjerna i [ramverket för etiketter och verkställighet (DULE)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=sv-SE#dule-framework).

I målgruppsdelningsprocessen mellan Audience Manager och Experience Platform översätts alla dataexportkontroller som har tillämpats på Audience Manager-segment till likvärdiga etiketter och marknadsföringsåtgärder som har godkänts av Experience Platform Data Governance, och vice versa.

>[!NOTE]
>
>Mer allmän information om dataexportkontroller finns i [dokumentationen för dataexportkontroller](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=sv-SE).
>
>Det här dokumentet innehåller en referens för hur specifika Audience Manager Data Export Controls mappas till dataanvändningsetiketter och marknadsföringsåtgärder i Platform.

### Dataexportkontroller till dataanvändningsrubriker

I följande tabell visas hur specifika dataexportkontroller mappas till kända dataanvändningsetiketter:

| Dataexportkontroll | Dataanvändningsetikett |
| --- | --- |
| Kan inte användas med personligt identifierbar information | C3: Data kan inte kombineras eller på annat sätt användas med direkt identifierbar information |
| Kan inte användas för annonsanpassning utanför webbplatsen | C5: Data kan inte användas för intressebaserad, övergripande målinriktning av innehåll eller annonser |
| Kan inte användas för annonsanpassning på plats | C6: Data kan inte användas för annonsanpassning på plats |
| Kan inte användas för anpassning på plats | C7: Data kan inte användas för målanpassning av innehåll på plats |

{style="table-layout:auto"}

### Dataexportkontroller för marknadsföringsåtgärder

I följande tabell beskrivs hur specifika dataexportetiketter mappas till kända marknadsföringsåtgärder:

| Dataexportetikett | Marknadsföringsåtgärd |
| --- | --- |
| Denna destination kan möjliggöra en kombination med personligt identifierbar information (PII) | Kombinera med PII |
| Den här destinationen kan användas för annonsinriktning utanför webbplatsen | Målgruppsövergripande |
| Det här målet kan användas för annonsinriktning på plats | Advertising på plats |
| Det här målet kan användas för anpassning av annonser på plats | Personalization på plats |

{style="table-layout:auto"}

## Förstå skillnader i segmentpopulationen mellan Audience Manager och Experience Platform {#aep-aam-segment-population-differences}

Antalet segmentpopulationer kan variera mellan Audience Manager- och Experience Platform-segmenten. Segmentnummer för liknande eller identiska målgrupper bör vara nära, men skillnaderna i populationer kan bero på faktorer som listas nedan.

### Segmentutvärdering i Experience Platform

Audience Manager uppdaterar rapportnummer i gränssnittet en gång om dagen. Tidpunkten för den här uppdateringen justeras sällan efter tidpunkten för segmentutvärderingen i Experience Platform.

### Skillnader mellan regler för profilsammanslagning och kopplingsprofiler

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) i Audience Manager och [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html?lang=sv-SE) i Experience Platform fungerar annorlunda, och identitetsdiagrammet som används för varje funktion varierar. På grund av detta förväntas vissa skillnader mellan segmentpopulationerna.

>[!NOTE]
>
> När du delar segment från Experience Platform till Audience Manager har plattformsorganisationen [standardprincipen för sammanslagning](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=sv-SE#default-merge-policy) företräde framför den [sammanslagningsprincip som används av segmentet](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=sv-SE#merge-policies) som delas med Audience Manager. Om t.ex. det delade segmentets kopplingsprofil tillåter [ID-sammanslagning](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=sv-SE#configure), men organisationens standardkopplingsregel inte gör det, kan det leda till populationsskillnader mellan plattformen och Audience Manager.

### Segmentdisposition i Experience Platform

Integrationen mellan Adobe Experience Platform och Audience Manager delar ett antal standardnamnutrymmen för [identitet](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=sv-SE#identity-types) för alla kunder: ECID, IDFA, GAID, hash-kodade e-postadresser (EMAIL_LC_SHA256), AdCloud ID. Om era Experience Platform-segment använder någon av dessa som primär identitet för de kvalificerade profilerna räknas profilerna i Audience Manager-egenskaper och -segment.

>[!NOTE]
>
> Målgrupper i Experience Platform med identiteter som är märkta med råa e-postmeddelanden visas aldrig i Audience Manager.

Om du t.ex. hade ett Experience Platform-segment som&quot;Alla mina kunder&quot; och de kvalificerade profilerna skulle vara CRM-ID, ECID, IDFA, raw och hash-adresser, skulle motsvarande segment i Audience Manager endast innehålla profiler som är avaktiverade för ECID, IDFA och hash-kodade e-postadresser. Segmentpopulationen i Audience Manager är mindre än den i Experience Platform.

![Segmentdelning mellan Experience Platform och Audience Manager - segmentdisposition](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Översikt över segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=sv-SE#audiences)
>* [Användarhandbok för Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=sv-SE#audiences)
>* [Audience Manager Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=sv-SE)
