---
description: Lär dig hur du aktiverar datadelning och hur målgrupper delas mellan Audience Manager och Adobe Experience Platform
solution: Audience Manager
title: Experience Platform segmentdelning med Audience Manager och andra Experience Cloud-lösningar
keywords: AEP målgruppsdelning, AEP-segment, plattformssegment, segmentdelning, målgruppsdelning, delade segment, AAM AEP-segmentdelning
feature: Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: 14e0ddd00d3a25674090ea9dbe485c77ad1d2aed
workflow-type: tm+mt
source-wordcount: '1862'
ht-degree: 0%

---

# Experience Platform segmentdelning med Audience Manager och andra Experience Cloud-lösningar

## Översikt {#overview}

Tack vare funktionen för målgruppsdelning mellan Audience Manager och Adobe Experience Platform kan ni dela era Audience Manager-egenskaper och segment till Adobe Experience Platform och vice versa. Du behöver [[!DNL Audience Manager Connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) för att möjliggöra målgruppsdelning mellan Audience Manager och Adobe Experience Platform.

Ni kan använda Audience Manager-egenskaper och segment i Experience Platform för att lägga till Audience Manager-data i era kundprofiler och dra nytta av Experience Platform [segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en).

I Audience Manager kan du använda Experience Platform-segment för datahanteringsplattformens användningsfall, till exempel:
* Lägg till [data från tredje part](/help/using/overview/data-types-collected.md#third-party-data) till era segment,
* [Algoritmisk modellering](/help/using/features/algorithmic-models/understanding-models.md);
* Aktivera dina segment till mål som ännu inte stöds i Experience Platform [målkatalog](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Dessutom delas era Experience Platform-segment med andra Experience Cloud-lösningar via [Centrala tjänster](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * Du behöver en Audience Manager-licens för att kunna aktivera de datahanteringsplattformar som nämns ovan.
> * Du *behöver inte* en Audience Manager-licens för att dela Experience Platform-segment med Adobe Advertising Cloud, Adobe Target, Marketo och andra Experience Cloud, via integreringen av bastjänsterna.


Se tabellen nedan för en översikt över användningsfall för målgruppsdelning:

| **Användningsexempel** | **Adobe Experience Platform** | **Audience Manager** | **Centrala tjänster** |
|---------|----------|---------|---------|
| **Målgruppsdelning** | <ul><li>Förbättra kundprofiler med data från Audience Manager</li><li>Använd data från Audience Manager i segmenteringen Experience Platform</li></ul> | <ul><li>Lägg till data från tredje part i segment</li><li>Algoritmisk modellering</li><li>Aktivering till ytterligare destinationer</li></ul> | Använd Experience Platform-segment i andra Experience Cloud-lösningar, som Adobe Target, Advertising Cloud eller Marketo. |

{style=&quot;table-layout:auto&quot;}

## Kom igång - Så här aktiverar du datadelning mellan Audience Manager och Experience Platform {#enable-data-sharing-aam-aep}

De två avsnitten nedan visar hur du aktiverar datadelning mellan Audience Manager och Experience Platform.

### Aktivera datadelning från Audience Manager till Experience Platform {#enable-aam-to-aep-data}

Om du vill skicka segment och egenskaper från Audience Manager till Experience Platform måste du skapa källkopplingen för Audience Manager i Experience Platform källkatalogen. Detta är ett självbetjäningsarbetsflöde som inte kräver medverkan av Adobe kundtjänst eller ingenjörsteam. Läs mer om hur du konfigurerar källkopplingen för Audience Manager:

* [Audience Manager source](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [Skapa en Adobe Audience Manager-källanslutning i användargränssnittet](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>Adobe uppmuntrar kunderna att konfigurera anslutningen utan att välja **[!UICONTROL Select all segments]** och **[!UICONTROL Select all traits]** enligt nedan. Intag av stora Audience Manager-segmentpopulationer har en direkt inverkan på det totala antalet profiler när du för första gången skickar ett Audience Manager-segment till plattformen via Audience Manager. Det innebär att om du väljer alla segment kan det eventuellt leda till ett profilantal som överskrider licensanvändningsbehörigheten.
>
>![Skärmbild med alternativen Markera alla segment och Markera alla egenskaper avmarkerade i arbetsflödet för anslutning till Audience Manager-källkopplingen.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Aktivera datadelning från Experience Platform till Audience Manager {#enable-aep-to-aam-data}

>[!NOTE]
>
> Kontakta din Customer Success Manager eller kundtjänst på Adobe om du vill låsa upp åtkomsten till den här funktionen.

Om du vill skicka segment från Experience Platform till Audience Manager måste du kontakta kundtjänst eller en Customer Success Manager. Kundtjänst- och kundsupportteam måste registrera en biljett (se mallbiljett AAM-52354) för att kunna ansluta från Platform till Audience Manager.

Dela planer för data från Platform till Audience Manager för att säkerställa att anslutningen är korrekt konfigurerad. Om du till exempel vill att regionala data ska delas för segment som skickas till Adobe Target, måste dessa uppgifter meddelas i biljetten. Datadelningsanslutningen från Experience Platform till Audience Manager upprättas inom sex arbetsdagar efter den inlämnade begäran.

## Audience Manager segment och egenskaper i Adobe Experience Platform {#aam-segments-traits-in-aep}

När du har konfigurerat Audience Manager-källkopplingen för att importera egenskaper och segment från Audience Manager, visas Audience Manager-data i Experience Platform som **Målgrupper** i segmentarbetsflödet. Mer information om segment och egenskaper för Audience Manager i Experience Platform finns i:

* [Översikt över segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Användarhandbok för Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Adobe Experience Platform segment i Audience Manager {#aep-segments-in-aam}

Segment som du skapar i Experience Platform visas i Audience Manager som signaler, egenskaper och segment, med följande dispositionsregler:

* Signal: För varje Experience Platform-segment ska du se signalerna i formuläret `segID = segment ID`.
* Fack: Regeln trait är Experience Platform-segmentets ID.
* Segment: Segmentet består av den egenskap som beskrivs ovan.

### Signaler {#aep-segments-as-aam-signals}

Välj **[!UICONTROL Audience Data > Signals > General Online Data]** och söka efter `SegId` för att hitta signaler från Experience Platform. Du kan använda den här skärmen i felsökningssyfte för att kontrollera om integreringen mellan Experience Platform och Audience Manager har konfigurerats korrekt.

![Se Experience Platform signaler i Audience Manager på kontrollpanelen för signaler](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Traits  {#aep-segments-as-aam-traits}

Audience Manager skapar automatiskt en egen mapp med namnet **Experience Platform traits** i din egen lagring.

![Traits from Experience Platform dashboard](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Du kan använda automatiskt skapade egenskaper i segment tillsammans med andra egenskaper. Du kan till exempel blanda egenskaper som skapats från Experience Platform-segment med egenskaper från tredje part som förvärvats via [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Ett exempel på ett trait som skapats automatiskt från ett Experience Platform-segment finns i skärmbilden nedan:

![Fälla från Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Artikelnummer | Namn | Beskrivning |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Traits created from Experience Platform segments are created as onboard traits in Audience Manager. |
| 2 | [!UICONTROL Data Source] | Automatiskt skapat. Alla egenskaper och segment som skapas automatiskt från Experience Platform-segment lagras i datakällan **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Integrationskoden motsvarar segment-ID:t i Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | trait-uttrycket är `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Ett automatiskt skapat segment som använder det här tecknet som komposition. |

{style=&quot;table-layout:auto&quot;}

### Segment  {#aep-segments-as-aam-segments}

Audience Manager skapar automatiskt en segmentmapp med namnet **Experience Platform segment** i ert segmentlagringsutrymme.

![Skärmbild av instrumentpanelen](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Ett exempel på ett segment som skapats automatiskt från ett Experience Platform-segment finns i skärmbilden nedan:

![Skärmbild av segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Artikelnummer | Namn | Beskrivning |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | Integrationskoden motsvarar segment-ID:t i Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatiskt skapat. Alla egenskaper och segment som skapas automatiskt från Experience Platform-segment lagras i datakällan **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** anger att automatiskt skapade segment följer den sammanfogningsprincip som har konfigurerats i Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Segmentet består av det drag som beskrivs i [Traits section](#aep-segments-as-aam-traits). |

{style=&quot;table-layout:auto&quot;}

## Stöd för dataexportkontroll i Audience Manager i Experience Platform {#aam-data-export-control-in-aep}

För att se till att dataanvändningen efterlevs i Experience Platform måste alla tillämpliga datauppsättningar och fält anges på lämpligt sätt [etiketter för dataanvändning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html). Dessutom [dataanvändningsprinciper](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html) måste aktiveras för specifika marknadsföringsåtgärder mot dessa etiketter, vilket anges av [Systemet för märkning och verkställighet av dataanvändning (DULE)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework).

I målgruppsdelningsprocessen mellan Audience Manager och Experience Platform översätts alla dataexportkontroller som har tillämpats på Audience Manager-segment till likvärdiga etiketter och marknadsföringsåtgärder som har godkänts av Experience Platform Data Governance, och vice versa.

>[!NOTE]
>
>Mer allmän information om dataexportkontroller finns i [Dokumentation för dataexportkontroller](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html).
>
>Det här dokumentet innehåller en referens för hur specifika dataexportkontroller för Audience Manager mappas till dataanvändningsetiketter och marknadsföringsåtgärder i Platform.

### Dataexportkontroller till dataanvändningsetiketter

I följande tabell visas hur specifika dataexportkontroller mappas till kända dataanvändningsetiketter:

| Dataexportkontroll | Dataanvändningsetikett |
| --- | --- |
| Kan inte användas med personligt identifierbar information | C3: Data kan inte kombineras eller på annat sätt användas med direkt identifierbar information |
| Kan inte användas för annonsanpassning utanför webbplatsen | C5: Data kan inte användas för intressebaserad, övergripande målinriktning av innehåll eller annonser |
| Kan inte användas för annonsanpassning på plats | C6: Data kan inte användas för annonsanpassning på plats |
| Kan inte användas för anpassning på plats | C7: Data kan inte användas för målanpassning av innehåll på plats |

{style=&quot;table-layout:auto&quot;}

### Dataexportkontroller för marknadsföringsåtgärder

Följande tabell visar hur specifika dataexportetiketter mappas till kända marknadsföringsåtgärder:

| Dataexportetikett | Marknadsföringsåtgärd |
| --- | --- |
| Denna destination kan möjliggöra en kombination med personligt identifierbar information (PII) | Kombinera med PII |
| Den här destinationen kan användas för annonsinriktning utanför webbplatsen | Målgruppsövergripande |
| Det här målet kan användas för annonsinriktning på plats | Annonsering på plats |
| Det här målet kan användas för anpassning av annonser på plats | Personalisering på plats |

{style=&quot;table-layout:auto&quot;}

## Förstå skillnaderna i segmentbefolkning mellan Audience Manager och Experience Platform {#aep-aam-segment-population-differences}

Antalet segmentpopulationer kan variera mellan Audience Manager och Experience Platform. Segmentnummer för liknande eller identiska målgrupper bör vara nära, men skillnaderna i populationer kan bero på faktorer som listas nedan.

### Segmentutvärdering i Experience Platform

Audience Manager uppdaterar rapportnummer i gränssnittet en gång om dagen. Tidpunkten för den här uppdateringen justeras sällan mot tidpunkten för segmentutvärderingen i Experience Platform.

### Skillnader mellan regler för profilsammanslagning och kopplingsprofiler

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) i Audience Manager och [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html) i Experience Platform fungerar olika, och det identitetsdiagram som används för varje bild varierar. På grund av detta förväntas vissa skillnader mellan segmentpopulationerna.

>[!NOTE]
>
> När ni delar segment från Experience Platform till Audience Manager är det er plattformsorganisation [standardprincip för sammanslagning](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy) har företräde framför [sammanfogningsprincip som används av segmentet](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies) delas med Audience Manager. Om t.ex. det delade segmentets kopplingsregel tillåter [ID-sammanfogning](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure)Men det gör inte organisationens standardpolicy för sammanfogning, vilket kan leda till skillnader i befolkningsgrupper mellan Platform och Audience Manager.

### Segmentdisposition i Experience Platform

Integrationen mellan Adobe Experience Platform och Audience Manager delar ett antal standarder [identitetsnamnutrymmen](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types) för alla kunder: ECID, IDFA, GAID, hash-kodade e-postadresser (EMAIL_LC_SHA256), AdCloud ID. Om era Experience Platform-segment använder någon av dessa som primär identitet för de kvalificerade profilerna räknas profilerna i Audience Manager-egenskaper och segment.

>[!NOTE]
>
> Målgrupper i Experience Platform med identiteter som är märkta med råa e-postmeddelanden visas aldrig i Audience Manager.

Om du till exempel hade ett Experience Platform-segment,&quot;Alla mina kunder&quot;, och de kvalificerade profilerna skulle vara CRM-ID, ECID, IDFA, raw och hash-adresser, skulle motsvarande segment i Audience Manager endast innehålla profiler som är avaktiverade från ECID, IDFA och hash-kodade e-postadresser. Segmentpopulationen i Audience Manager skulle vara mindre än den i Experience Platform.

![Segmentdelning mellan Experience Platform och Audience Manager - segmentdisposition](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Översikt över segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Användarhandbok för Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

