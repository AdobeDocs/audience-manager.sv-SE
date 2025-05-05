---
title: Migrera från taggtillägget Audience Manager till Web SDK-taggtillägget
description: Förstå stegen för att uppdatera ditt datainsamlingsbibliotek för Audience Manager från taggtillägget Audience Manager till taggtillägget Web SDK
exl-id: 7f0486db-4511-4311-90df-290580fdcd78
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---

# Uppdatera datainsamlingsbiblioteket för Audience Manager från taggtillägget Audience Manager till Web SDK-taggtillägget

## Målgrupp

Den här sidan är avsedd för Audience Manager-kunder som använder taggtillägget [Audience Manager](https://experienceleague.adobe.com/sv/docs/experience-platform/tags/extensions/client/audience-manager/overview) för att hämta webbsamlingsdata till Audience Manager. Kunder som använder AppMeasurement JavaScript-biblioteket kan läsa guiden om hur du uppdaterar ditt datainsamlingsbibliotek för Audience Manager [ från AppMeasurement JavaScript-biblioteket till Web SDK JavaScript-biblioteket](appmeasurement-to-web-sdk.md).

## Fördelar och nackdelar med implementeringsvägen

Att använda den här migreringsmetoden har både fördelar och nackdelar. Väg noga in varje alternativ för att avgöra vilken metod som är bäst för er organisation.

| Fördelar | Nackdelar |
| --- | --- |
| <ul><li>**Inga kodändringar på din plats**: Eftersom implementeringen redan har installerade taggar kan alla migreringsuppdateringar göras i tagggränssnittet.</li><li>**Använder din befintliga implementering**: Den här metoden kräver ingen ny implementering. Även om det kräver nya regelåtgärder kan du återanvända befintliga dataelement och regelvillkor med minimala ändringar.</li><li>**Kräver inget schema**: För den här migreringsfasen till Web SDK behövs inget XDM-schema. I stället kan du fylla i objektet `data`, som skickar data direkt till Adobe Audience Manager. När migreringen till Web SDK är klar kan du skapa ett schema för din organisation och använda datastream-mappning för att fylla i tillämpliga XDM-fält. Om det krävs ett schema i det här skedet av migreringsprocessen måste din organisation använda ett Adobe Audience Manager XDM-schema. Om du använder det här schemat blir det svårare för din organisation att använda ditt eget schema i framtiden.</li></ul> | <ul><li>**Implementeringens tekniska skuld**: Eftersom den här metoden använder en modifierad form av din befintliga implementering, kan det vara svårare att spåra implementeringslogik och utföra ändringar vid behov. Anpassad kod kan vara särskilt svår att felsöka.</li><li>**Kräver mappning för att skicka data till plattformen**: När din organisation är redo att använda Real-Time CDP måste du skicka data till en datauppsättning i Adobe Experience Platform. Den här åtgärden kräver att alla fält i objektet `data` är en post i datastream-mappningsverktyget som tilldelar det till ett XDM-schemafält. Mappning behöver bara göras en gång för det här arbetsflödet, och implementeringen behöver inte ändras. Det är dock ett extra steg som inte krävs när du skickar data i ett XDM-objekt.</li></ul> |

Adobe rekommenderar att du följer den här implementeringsvägen när du har en befintlig implementering med Adobe Audience Manager-taggtillägget.

## Steg som krävs för att migrera till Web SDK

Följande steg innehåller konkreta mål att arbeta mot. Välj varje steg om du vill ha detaljerade anvisningar om hur du slutför det.

+++**1. Skapa och konfigurera en datastream**

Följ instruktionerna nedan för att skapa ett datastam i Adobe Experience Platform Data Collection. När du skickar data till den här datastreamen vidarebefordrar den data till Audience Manager. I framtiden skickar samma dataström data till Real-Time CDP.

1. Navigera till [experience.adobe.com](https://experience.adobe.com) och logga in med dina autentiseringsuppgifter.
1. Använd hemsidan eller produktväljaren i det övre högra hörnet för att navigera till **[!UICONTROL Data Collection]**.
1. Välj **[!UICONTROL Datastreams]** i den vänstra navigeringen.
1. Välj **[!UICONTROL New Datastream]**.
1. Ange önskat namn och välj sedan **[!UICONTROL Save]**.
1. Välj **[!UICONTROL Add Service]** när dataströmmen har skapats.
1. Välj **[!UICONTROL Adobe Audience Manager]** på den nedrullningsbara menyn för tjänster.
1. Kontrollera att alternativet **[!UICONTROL Enable XDM Flattened Fields]** inte är markerat.

   ![Lägg till tjänsten Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Din datastream är nu redo att ta emot och skicka data till Audience Manager.

+++

+++**2. Lägg till Web SDK-tillägget i taggegenskapen**

I det här avsnittet förbereds taggen för den mesta migreringen som görs i nästa steg.

1. Markera hamburger-ikonen i det övre vänstra hörnet i Adobe Experience Platform-gränssnittet och välj sedan **[!UICONTROL Tags]**.
1. Välj önskad taggegenskap.
1. Välj **[!UICONTROL Extensions]** i den vänstra navigeringen för taggegenskapen.
1. Välj **[!UICONTROL Catalog]** i den övre delen om du vill se en lista över alla tillgängliga tillägg.
1. Sök efter och välj tillägget **[!UICONTROL Adobe Experience Platform Web SDK]** och välj sedan **[!UICONTROL Install]** till höger.

   ![Katalog](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Konfigurationsinställningarna för tillägget visas. Leta reda på avsnittet **[!UICONTROL Datastreams]**, markera den sandlåda som du använder och den datastream som du skapade i föregående steg.

   ![Val av dataström](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Välj **[!UICONTROL Save]**.

Din taggegenskap har nu Web SDK installerat.

+++

+++**3. Skapa ett dataobjektdataelement**

Dataobjektets dataelement tillhandahåller ett intuitivt ramverk för att konfigurera en nyttolast som Web SDK använder för att skicka till en datastam. De flesta regler som du uppdaterar i följande steg interagerar med det här dataelementet.

1. Välj **[!UICONTROL Data Elements]** i den vänstra navigeringen i tagggränssnittet.
1. Välj **[!UICONTROL Add Data Element]**
1. Ge dataelementet följande inställningar:
   * **[!UICONTROL Name]**: Allt du vill, till exempel &quot;Datalager&quot; eller &quot;Dataobjekt&quot;
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**: [!UICONTROL Variable]
   * Kryssrutor kan vara som de är.
1. Välj följande inställningar till höger:
   * Egenskapens alternativknapp: **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**: [!UICONTROL Adobe Audience Manager]
1. Välj **[!UICONTROL Save]**.

   ![Skapa dataelement](assets/create-data-element.png) {style="border:1px solid lightslategray"}

Din taggegenskap har nu allt som behövs för att uppdatera varje regel.

+++

+++**4. Uppdatera regler för att använda Web SDK-tillägget i stället för Audience Manager-tillägget**

Det här steget innehåller det mesta som krävs för att migrera till Web SDK och kräver kunskap om hur implementeringen fungerar. Nedan visas ett exempel på hur du redigerar en typisk taggregel. Uppdatera alla taggregler i implementeringen så att alla referenser till tillägget Audience Manager ersätts med tillägget Web SDK.

1. Välj **[!UICONTROL Rules]** i den vänstra navigeringen i tagggränssnittet.
1. Markera en regel som du vill redigera.
1. Välj åtgärden **[!UICONTROL Audience Manager - Set Variables]**
1. Observera alla Audience Manager-variabler som anges i den här regeln. Inkludera båda variablerna som angetts i listrutorna och variablerna som angetts i anpassad kod.
1. Ändra [!UICONTROL Action Configuration] till följande inställningar:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: Uppdatera variabel
1. Kontrollera att dataobjektet som du skapade i steg 3 är markerat i listrutan till höger i fältet **[!UICONTROL Data element]**.
1. Ställ in nyckelvärdepar för Audience Manager på samma respektive värden som de konfigurerades i tillägget Audience Manager.
1. När all regellogik har replikerats med Web SDK-tillägget väljer du **[!UICONTROL Keep Changes]**.
1. Upprepa dessa steg för varje åtgärdskonfiguration som använder taggtillägget Audience Manager för att ange värden.

Stegen ovan gäller bara regler som anger värden. Följande steg ersätter alla åtgärder som använder [!UICONTROL Action Configuration] [!UICONTROL Send Event].

1. Välj en regel som skickar en Web SDK-händelse.
1. Välj åtgärdstypen **[!UICONTROL Send Event]**.
1. Ändra [!UICONTROL Action Configuration] till följande inställningar:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: [!UICONTROL Send event]
1. Till höger ändrar du åtgärdsinställningarna till följande:
   * **[!UICONTROL Type]**: Använd **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]**: Markera dataobjektet som du skapade i steg 3.
1. Välj **[!UICONTROL Keep Changes]**.
1. Upprepa dessa steg för varje åtgärdskonfiguration som använder Audience Manager för att skicka en händelse.

+++

+++**5. Publish uppdaterade regler**

Publicering av uppdaterade regler följer samma arbetsflöde som andra ändringar av taggkonfigurationen.

1. Välj **[!UICONTROL Publishing Flow]** i den vänstra navigeringen i tagggränssnittet.
1. Välj **[!UICONTROL Add Library]**.
1. Ge den här taggen ett namn, till exempel&quot;Uppgradera till Web SDK&quot;.
1. Välj **[!UICONTROL Add All Changed Resources]**.
1. Välj **[!UICONTROL Save]**.
1. Publiceringsarbetsflödet visar en orange punkt som anger att den håller på att byggas. När punkten blir grön är dina ändringar tillgängliga i utvecklingsmiljön.
1. Testa ändringarna i utvecklingsmiljön för att säkerställa att alla regler aktiveras korrekt och att dataobjektet fylls med förväntade värden.
1. När det är klart skickar du biblioteket för godkännande, bygg till staging, och sedan godkänner och publicerar det i produktion.

   ![Publiceringsflöde](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Inaktivera Audience Manager-tillägget**

När taggimplementeringen är helt migrerad till Web SDK kan du inaktivera tillägget Audience Manager.

1. Välj **[!UICONTROL Extensions]** i den vänstra navigeringen i tagggränssnittet.
1. Leta reda på och välj tillägget [!UICONTROL Audience Manager]. Välj **[!UICONTROL Disable]** till höger.
1. Följ samma publiceringsarbetsflöde ovan för att publicera borttagningen av tillägget [!UICONTROL Audience Manager].
1. När tillägget har inaktiverats i produktionen kan du avinstallera det helt. Välj tillägget, välj menyn med tre punkter till höger och välj sedan **[!UICONTROL Uninstall]**.
1. Följ samma publiceringsarbetsflöde ovan för att publicera dessa ändringar i produktionen.

+++

I nuläget är implementeringen av Audience Manager helt migrerad till Web SDK och är redo att gå över till Real-Time CDP i framtiden.
