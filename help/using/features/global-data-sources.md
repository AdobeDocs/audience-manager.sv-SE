---
description: Använd globala datakällor för att importera enhets-ID:n.
seo-description: Använd globala datakällor för att importera enhets-ID:n.
seo-title: Globala datakällor
solution: Audience Manager
title: Globala datakällor
feature: Data Sources
translation-type: tm+mt
source-git-commit: cb84f95d52c2e851cb0c016cb25f408f2d79d01b
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 3%

---


# Globala datakällor {#global-data-sources}

## Översikt

Globala datakällor är tillgängliga för alla Audience Manager-kunder och innehåller enhetsreklam-ID:n som genererats av enhetstillverkare som [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] och [!DNL Android] enhetstillverkare. Dessa ID:n är tillgängliga för tillverkare i reklamsyfte. Audience Manager-kunder kan använda globala datakällor för att synkronisera enhets-ID:n och importera eller exportera data som är avaktiverade från mappningarna.

I följande tabell beskrivs de globala datakällor som stöds av Audience Manager.

| ID för datakälla | Beskrivning |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** -  **[!DNL GAID]** ID:n representerar enheter som kör  [!DNL Android] operativsystemet. |
| 20915 | **[!DNL Apple ID For Advertising]** -  **[!DNL IDFA]** ID:n representerar enheter som kör  [!DNL iOS] operativsystemet. |
| 121963 | **[!DNL Roku ID for Advertising]** -  **[!DNL RIDA]** ID:n representerar  [!DNL Roku] direktuppspelningsenheter. |
| 389146 | **[!DNL Microsoft Advertising ID]** -  **[!DNL MAID]** ID:n representerar enheter som kör  [!DNL Windows 10] operativsystemet. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** -  **[!DNL TIFA]** ID:n representerar  [!DNL Samsung] smarta TV:er. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** representerar enheter som körs  [!DNL Amazon Fire OS] |

## Importera data från globala datakällor

Du kan importera enhets-ID:n från globala datakällor genom både [dataöverföring i realtid](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) och [batchdataöverföring](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>När du skickar data till Audience Manager med ett globalt enhets-ID måste du se till att använda motsvarande datakälla för det aktuella enhets-ID:t. Exempel: Om du vill importera data för [!DNL Apple IDFA] använder du datakällans ID 20915.

## Begränsningar

På enheter som kör operativsystemen [!DNL iOS] och [!DNL Android] kan bara inbyggda program hämta och använda enhets-ID:n ([!UICONTROL DAID]s). Webbprogram som körs i mobilwebbläsare har inte tillgång till enhetens reklam-ID.

## Verifiering av globalt enhets-ID

Audience Manager validerar de enhets-ID:n ([!UICONTROL DAID]) som importeras av kunder, baserat på deras format, för att säkerställa att de matchar det standardformat som anges av enhetstillverkarna. Se [Index för ID:n i Audience Manager](../reference/ids-in-aam.md) för en detaljerad mappning av enhets-ID:n till globala datakällor och rätt format för varje ID. Kontrollera att du importerar enhets-ID:n i rätt format, baserat på enhetstypen. Audience Manager avvisar enhets-ID:n som inte har rätt format och returnerar ett felmeddelande som anger att ID:t avvisades.

* Felmeddelanden för batchdataöverföringar beskrivs här: [Villkor och definitioner för introduktionsstatusrapport](../reporting/onboarding-status-report.md#report-terms-conditions).
* Felmeddelanden för dataöverföringar i realtid beskrivs här: [DCS-felkoder, meddelanden och exempel](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Förfalloprincip för enhets-ID

Audience Manager tar automatiskt bort enhets-ID:n efter 120 dagars inaktivitet, ungefär som [AAM UUID](../faq/faq-privacy.md)s.

## Begär nya globala datakällor

Om du vill begära att nya globala datakällor ska läggas till i Audience Manager kontaktar du Adobe Consulting eller Adobe Customer Care och lämnar detaljerad information om de datakällor som krävs:

* Namnet på den begärda plattformen (t.ex. [!UICONTROL Apple IDFA]).
* Namnet på det företag/den organisation som ansvarar för plattformen (t.ex. [!UICONTROL Apple Inc.]).
* Länkar till de tekniska specifikationerna för namnutrymmet för enhetens annonserings-ID (t.ex. [AdSupport Documentation](https://developer.apple.com/documentation/adsupport)).