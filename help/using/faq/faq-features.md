---
description: Vanliga frågor och problem som rör produkter och funktioner.
keywords: audience manager cookies
seo-description: Vanliga frågor och problem som rör produkter och funktioner.
seo-title: Funktioner och funktioner Frågor och svar
solution: Audience Manager
title: Funktioner och funktioner Frågor och svar
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Funktioner och funktioner Frågor och svar{#product-features-and-functions-faq}

Vanliga frågor och problem som rör produkter och funktioner.

<br> 

<!-- 

faq_features_functions.xml

 -->

**Vad är mitt organisations-ID och hur hittar jag det?**

Detta *`Organization ID`* är ett unikt ID som identifierar din organisation för [!DNL Audience Manager] och [!DNL Adobe Experience Cloud]. Den består av en skiftlägeskänslig, 24-siffrig alfanumerisk sträng följt av [!UICONTROL @AdobeOrg].

En *`Organization ID`* stil ser till exempel ut så här: `1FD6776A524453CC0A490D44@AdobeOrg`.

Detta *`Organization ID`* används av Audience Managers [DIL](../dil/dil-overview.md) API, [Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/)och andra [!DNL Experience Cloud] lösningar. Användare med administratörsbehörighet kan hitta *`Organization ID`* på [!DNL Adobe Admin Console]. Se Vanliga frågor om [administration - Användarhantering](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**Kan jag skapa traits eller destination satsvis?**

Ja. Se [Masshanteringsverktyg](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>Verktygen [!UICONTROL Bulk Management Tools] stöds inte *av* [!DNL Audience Manager]. De tillhandahålls av praktiska skäl och endast för att vara artiga. För större förändringar rekommenderar vi att du arbetar med API:erna [för](../api/api.md) Audience Manager i stället.

<br> 

**Kan[!DNL Audience Manager]minska behovet av tredjepartstaggar eller pixlar och förbättra sidinläsningstiden?**

Om [!DNL Audience Manager] är integrerat med din tredje parts datapartner kan du ersätta deras pixlar och taggar med ett server-till-server-ID-anrop till [!DNL Audience Manager]. I det här fallet [!DNL Audience Manager] utlöses ett enskilt ID-anrop första gången en användare visas och informationen synkroniseras med din tredjepartspartner. På så sätt elimineras behovet av att anropa flera pixlar från varje sida. Genom att minska antalet pixelanrop kan sidinläsningstiden förbättras.

<br> 

**Jag har prenumererat på en datafeed. Var lagras dessa data?**

Din datafeed och alla egenskaper som finns i feeden visas som undermappar och egenskaper i [!DNL Audience Manager]. Gå till **[!UICONTROL Audience Data > Traits]** och expandera [!UICONTROL 3rd-Party Data] mappen för att visa dina egenskaper eller skapa segment och modeller med dessa data.

<br> 

**Vad är[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager använde [!UICONTROL Tag Insertion Manager] (TIM) för att skapa och hantera [!UICONTROL data collection code (DIL)]. Den här funktionen är föråldrad och har ersatts först av [!UICONTROL Dynamic Tag Manager (DTM)] och därefter av [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**Vilka är skillnaderna mellan algoritmiska modeller och trait Recommendations? När ska jag använda var och en av dem?**

**Algoritmiska modeller**

Algoritmiska modeller hittar inte bara de mest inflytelserika egenskaperna, utan även användare baserat på dessa egenskaper och tilldelar varje användare en individuell poäng. Sedan skapar du algoritmiska egenskaper som riktar sig till användarna. Med precision och räckvidd i Trait Builder kan du ange vilka användare bland alla som har de inflytelserika egenskaper du vill ha som mål.

Med algoritmiska modeller kan du välja användare på olika noggrannhetsnivåer och testa i Audience Lab vilken grupp användare som konverterar bättre. Se det detaljerade användningsexemplet i [Jämför modeller i Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

I algoritmiska modeller körs modellen var 8:e dag och uppdaterar de användare som är kvalificerade för algoritmiska egenskaper.

**Trait Recommendations**

Trait Recommendations är ett snabbt sätt att få insikter om andra egenskaper som liknar de du använder i ett segment.

Du bör använda Trait Recommendations när:

* Ni behöver snabba insikter när ni skapar segment,
* Ni använder segmenten för korta kampanjer eller när ni snabbt vill hindra målgrupper som konverterar;
* Du försöker maximera räckvidden.

<br> 

**Är det någon skillnad mellan Adobe Analytics- och Audience Manager-segmenten?**

Ja, läs [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) för en ingående beskrivning av skillnaderna.
