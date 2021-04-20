---
description: Vanliga frågor och problem som rör produkter och funktioner.
keywords: cookies för målgruppshanterare
seo-description: Vanliga frågor och problem som rör produkter och funktioner.
seo-title: Vanliga frågor om produktfunktioner
solution: Audience Manager
title: Vanliga frågor om produktfunktioner
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
translation-type: tm+mt
source-git-commit: 65598677498ede26e4961cd4849c9b655dac38dc
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 89%

---


# Vanliga frågor om produktfunktioner {#product-features-and-functions-faq}

Vanliga frågor och problem som rör produkter och funktioner.

 

<!-- 

faq_features_functions.xml

 -->

**Vad är mitt organisations-ID och hur hittar jag det?**

*`Organization ID`* är ett unikt ID som identifierar din organisation i [!DNL Audience Manager] och [!DNL Adobe Experience Cloud]. Det består av en skiftlägeskänslig, 24-siffrig alfanumerisk sträng följt av [!UICONTROL @AdobeOrg].

Ett *`Organization ID`* ser till exempel ut så här: `1FD6776A524453CC0A490D44@AdobeOrg`.

Detta *`Organization ID`* används av Audience Managers [DIL](../dil/dil-overview.md) API, [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/sv-SE/id-service/using/home.html) och andra [!DNL Experience Cloud]-lösningar. Användare med administratörsbehörighet kan hitta *`Organization ID`* på [!DNL Adobe Admin Console]. Se [Administration – Vanliga frågor om användarhantering](https://docs.adobe.com/content/help/sv-SE/core-services/interface/manage-users-and-products/admin-getting-started.html).

 

**Kan jag skapa traits eller destinationer satsvis?**

Ja. Se [Verktyg för satsvis hantering](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]-verktygen stöds *inte* av [!DNL Audience Manager]. De tillhandahålls endast av praktiska skäl. För satsvisa ändringar rekommenderar vi att du arbetar med [Audience Managers API:er](../api/api.md) i stället.

 

**Vissa kund-ID saknas när du exporterar satsvis-ID till ett mål. Varför händer det?**

När ett enhets-ID ([AAM UUID](../reference/ids-in-aam.md)) är länkat till flera CRM-ID ([DPUID](../reference/ids-in-aam.md)) exporteras endast den senaste mappningen. Det är därför du kan se ett lägre antal enhets-ID än förväntat som exporteras.

 

**Kan [!DNL Audience Manager] minska behovet av tredjepartstaggar eller pixlar och förbättra sidinläsningstiderna?**

Om [!DNL Audience Manager] är integrerat med er tredjepartsdatapartner kan ni ersätta deras pixlar och taggar med ett server-till-server ID-anrop till [!DNL Audience Manager]. I sådana fall aktiverar [!DNL Audience Manager] ett enskilt ID-anrop första gången en användare avkänns och informationen synkroniseras med er tredjepartspartner. På så sätt elimineras behovet av flera pixelanrop från varje sida. Genom att minska antalet pixelanrop kan sidinläsningstiderna förbättras.

 

**Jag prenumererar på en datafeed. Var lagras dessa data?**

Din datafeed och alla traits som finns i flödet visas som undermappar och traits i [!DNL Audience Manager]. Gå till **[!UICONTROL Audience Data > Traits]** och expandera [!UICONTROL 3rd-Party Data]-mappen för att visa dina traits eller skapa segment och modeller med dessa data.

 

**Vad är [!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager använde [!UICONTROL Tag Insertion Manager] (TIM) för att skapa och hantera [!UICONTROL data collection code (DIL)]. Den här funktionen är föråldrad och har ersatts först av [!UICONTROL Dynamic Tag Manager (DTM)] och därefter av [!DNL Adobe Experience Platform Launch]. Mer information finns i [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html) och [Dynamic Tag Management](https://docs.adobe.com/content/help/sv-SE/dtm/using/dtm-home.html).

 

**Vilka är skillnaderna mellan algoritmiska modeller och trait-rekommendationer? När ska jag använda dem?**

**Algoritmiska modeller**

Algoritmiska modeller hittar inte bara inflytelserika traits, de klassificerar även användare baserat på dessa traits och tilldelar varje användare en individuell poäng. Sedan skapar du algoritmiska traits som riktar sig till användarna. Med precisions- och räckviddsverktygen i Trait Builder kan du ange vilka användare som du vill nå bland alla de som har de traits du vill ha som mål.

Med algoritmiska modeller kan du välja användare på olika precisionsnivåer och testa i Audience Lab vilken grupp användare som lättast konverteras. Se det detaljerade användningsexemplet i [Jämför modeller i Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

I algoritmiska modeller körs modellen var 8:e dag och uppdaterar de användare som kvalificerade för algoritmiska traits.

**Trait-rekommendationer**

Trait-rekommendationer är ett snabbt sätt att få insikter om andra traits som liknar de du använder i ett segment.

Du bör använda trait-rekommendationer när:

* Ni behöver snabba insikter när ni skapar segment
* Ni använder segmenten för korta kampanjer eller när ni snabbt vill exkludera målgrupper som konverterar
* Ni försöker maximera räckvidden.

 

**Är det någon skillnad mellan Adobe Analytics- och Audience Manager-segment?**

Ja, läs [Förstå segment i Analytics och Audience Manager](https://docs.adobe.com/content/help/sv-SE/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) för en ingående beskrivning av skillnaderna.
