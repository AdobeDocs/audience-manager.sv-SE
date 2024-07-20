---
title: Uppdatera ditt datainsamlingsbibliotek för Audience Manager från AppMeasurement JavaScript-biblioteket till Web SDK JavaScript-biblioteket.
description: Lär dig hur du uppdaterar ditt datainsamlingsbibliotek för Audience Manager från AppMeasurement JavaScript-biblioteket till Web SDK JavaScript-biblioteket.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---

# Uppdatera ditt datainsamlingsbibliotek för Audience Manager från AppMeasurement JavaScript-biblioteket till Web SDK JavaScript-biblioteket

## Målgrupp {#intended-audience}

Den här sidan är avsedd för Audience Manager-kunder som använder AppMeasurement för att hämta webbsamlingsdata till Audience Manager. För kunder som använder [Audience Manager-taggtillägget](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) kan du läsa guiden om hur du uppdaterar ditt datainsamlingsbibliotek för Audience Manager [ från taggtillägget Audience Manager till SDK-taggtillägget för webben](dil-extension-to-web-sdk.md).

## Fördelar och nackdelar med implementeringsvägen

Att använda den här migreringsmetoden har både fördelar och nackdelar. Väg noga in varje alternativ för att avgöra vilken metod som är bäst för er organisation.

| Fördelar | Nackdelar |
| --- | --- |
| <ul><li>**Använder din befintliga implementering**: Även om den här metoden kräver vissa implementeringsändringar krävs ingen helt ny implementering från början. Du kan använda ditt befintliga datalager och kod med minimala ändringar av implementeringslogiken.</li><li>**Kräver inget schema**: För den här migreringsfasen till Web SDK behövs inget XDM-schema. I stället kan du fylla i objektet `data`, som skickar data direkt till Audience Manager. När migreringen till Web SDK är klar kan du skapa ett schema för din organisation och använda datastream-mappning för att fylla i tillämpliga XDM-fält. Om det krävs ett schema i det här skedet av migreringsprocessen måste din organisation använda ett Audience Manager XDM-schema. Om du använder det här schemat blir det svårare för din organisation att använda ditt eget schema i framtiden.</li></ul> | <ul><li>**Implementering av teknisk skuld**: Eftersom den här metoden använder en modifierad form av din befintliga implementering, kan det vara svårare att spåra implementeringslogik och utföra ändringar i framtiden vid behov.</li><li>**Kräver mappning för att skicka data till plattformen**: När din organisation är redo att använda Real-Time CDP måste du skicka data till en datauppsättning i Adobe Experience Platform. Den här åtgärden kräver att alla fält i objektet `data` är en post i datastream-mappningsverktyget som tilldelar det till ett XDM-schemafält. Mappning behöver bara göras en gång för det här arbetsflödet, och implementeringen behöver inte ändras. Det är dock ett extra steg som inte krävs när du skickar data i ett XDM-objekt.</li></ul> |

Adobe rekommenderar att du följer den här implementeringsvägen i följande scenarier:

* Du har en befintlig implementering som använder Adobe Analytics AppMeasurement JavaScript-biblioteket. Om du har en implementering med taggtillägget Audience Manager följer du i stället [Migrera från taggtillägget Audience Manager till Web SDK-taggtillägget](dil-extension-to-web-sdk.md).
* Du avser att använda Real-Time CDP i framtiden, men vill inte ersätta din Audience Manager-implementering med en Web SDK-implementering från grunden. Att ersätta implementeringen från grunden i Web SDK kräver mest arbete, men erbjuder även den mest livskraftiga långsiktiga implementeringsarkitekturen. Om din organisation är beredd att använda en ren Web SDK-implementering kan du läsa [dokumentationen för Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) för mer information.

## Steg som krävs för att migrera till Web SDK

Följande steg innehåller konkreta mål att arbeta mot. Klicka på varje steg om du vill ha detaljerade anvisningar om hur du slutför det.

+++**1. Skapa och konfigurera en datastream**

Skapa ett datastream i Adobe Experience Platform Data Collection. När du skickar data till den här datastreamen vidarebefordrar den data till Audience Manager. I framtiden skickar samma dataström data till Real-Time CDP.

1. Navigera till [experience.adobe.com](https://experience.adobe.com) och logga in med dina autentiseringsuppgifter.
1. Använd hemsidan eller produktväljaren i det övre högra hörnet för att navigera till **[!UICONTROL Data Collection]**.
1. Välj **[!UICONTROL Datastreams]** i den vänstra navigeringen.
1. Välj **[!UICONTROL New Datastream]**.
1. Ange önskat namn och välj sedan **[!UICONTROL Save]**.
1. Välj **[!UICONTROL Add Service]** när dataströmmen har skapats.
1. Välj **[!UICONTROL Audience Manager]** på den nedrullningsbara menyn för tjänster.

   ![Lägg till tjänsten Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Din datastream är nu redo att ta emot och skicka data till Audience Manager. Observera dataStream ID, eftersom detta ID krävs när du konfigurerar Web SDK i koden.

+++

+++**2. Installera JavaScript-biblioteket för Web SDK**

Mer information och kodblock som ska användas finns i [Installera Web SDK med JavaScript-biblioteket](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library). Referera till den senaste versionen av `alloy.js` så att dess metodanrop kan användas.

+++

+++**3. Konfigurera Web SDK**

Konfigurera implementeringen så att den pekar på datastream som skapats i steg 1 med hjälp av Web SDK-kommandot [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview). Kommandot `configure` måste anges på alla sidor, så du kan inkludera det bredvid bibliotekets installationskod.

Använd egenskaperna [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) och [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) i Web SDK `configure`-kommandot:

* Ange `edgeConfigId` till det datastream-ID som hämtats från föregående steg.
* Ange `orgId` som din organisations IMS-org-ID.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Du kan ange andra egenskaper i kommandot [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) beroende på organisationens implementeringskrav.

+++

+++**4. Uppdatera kodlogik för att använda en JSON-nyttolast**

Ändra implementeringen av Audience Manager så att den inte är beroende av `AppMeasurement.js` eller `s`-objektet. I stället anger du variabler till ett korrekt formaterat JavaScript-objekt, som konverteras till ett JSON-objekt när det skickas till Adobe. Att ha ett [datalager](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) på din webbplats är till stor hjälp när du anger värden, eftersom du kan fortsätta att referera till samma värden.

Om du vill skicka data till Audience Manager måste Web SDK-nyttolasten använda `data.__adobe.audiencemanager` med alla analysvariabler som anges i det här objektet. Variabler i det här objektet delar identiska namn och format som deras AppMeasurement-variabelmotsvarigheter. Om du till exempel anger variabeln `products` ska du inte dela upp den i enskilda objekt som du skulle göra med XDM. Ta i stället med den som en sträng exakt om du anger variabeln `s.products`:

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

I slutändan innehåller den här nyttolasten alla önskade värden och alla referenser till objektet `s` i implementeringen tas bort. Du kan använda vilken som helst av de resurser som JavaScript tillhandahåller för att ställa in det här nyttolastobjektet, inklusive punktnotation för att ställa in enskilda värden.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**5. Uppdatera metodanrop för att använda Web SDK**

Uppdatera alla instanser där du anropar [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) och [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method) och ersätt dem med kommandot [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview). Det finns tre scenarier:

* **Spårning av sidvy**: Ersätt spårningsanropet för sidvyn med kommandot Web SDK `sendEvent`:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Automatisk länkspårning**: Konfigurationsegenskapen [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) är aktiverad som standard. Den ställer automatiskt in rätt länkspårningsvariabler för att skicka data till Audience Manager. Om du vill inaktivera automatisk länkspårning anger du den här egenskapen till `false` i kommandot [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview).

* **Manuell länkspårning**: Web SDK har inte olika kommandon mellan sidvyanrop och icke-sidvisningsanrop. Ange den skillnaden i nyttolastobjektet.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Validera och publicera ändringar**

När du har tagit bort alla referenser till AppMeasurementet och objektet `s` publicerar du ändringarna i utvecklingsmiljön för att validera att den nya implementeringen fungerar. När du har kontrollerat att allt fungerar som det ska kan du publicera dina uppdateringar i produktionen.

Om det migreras korrekt krävs inte längre `AppMeasurement.js` på din plats och alla referenser till det här skriptet kan tas bort.

+++

I nuläget är implementeringen av Audience Manager helt migrerad till Web SDK och är redo att gå över till Real-Time CDP i framtiden.
