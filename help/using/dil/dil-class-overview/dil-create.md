---
description: Skapar en partnerspecifik DIL-instans.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: Skapa DIL
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 1%

---

# DIL create method{#dil-create}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av [!DNL Data Integration Library (DIL)] och [!DNL DIL] tillägg.
><br>
>Befintliga kunder kan fortsätta använda sina [!DNL DIL] implementering. Adobe kommer dock inte att utvecklas [!DNL DIL] bortom denna punkt. Kunder uppmanas att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) för deras långsiktiga strategi för datainsamling.
><br>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) i stället.

## Skapa DIL {#dil-create-new}

Skapar en partnerspecifik [!UICONTROL DIL] -instans.

**Funktionssignatur:** `DIL.create: function (initConfig) {}`

**initConfig-element**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>The `visitorService` egenskapen är *alltid* krävs. Andra egenskaper som anges här är valfria, såvida inte annat anges.

`initConfig` använder följande element:

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Namn </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>Heltal </p> </td> 
   <td colname="col3"> <p>Den här egenskapen anger behållar-ID som används av <span class="keyword"> Audience Manager </span> för ID-synkronisering. Du skulle ställa in <code> containerNSID </code> om du har <span class="wintitle"> DIL </span> distribueras på flera platser. Var och en av dessa platser kommer att ha sina egna behållar-ID- och ID-synkroniseringar. När du bara har en plats är behållar-ID 0 som standard och du behöver inte ange detta korrekt. Kontakta din konsult för att få en lista över dina webbplatser och deras behållar-ID:n. </p> <p>I <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, egenskapen <code> idSyncContainerID </code> motsvarar <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Observera följande om du använder <span class="wintitle"> DIL </span> <i>och</i> ID-tjänsten på flera platser: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">För varje plats anger du samma behållar-ID på <code> containerNSID </code> och <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Båda <span class="wintitle"> DIL </span> och ID-tjänsten kommer att försöka skicka ID-synkroniseringar till vår datainsamling iFrame. Men iFrame säkerställer att <span class="wintitle"> DIL </span> aktiverar inte en ID-synkronisering. Detta förhindrar duplicering. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Endast <span class="wintitle"> DIL </span> skickar data till en <a href="../../features/destinations/destinations.md"> URL-mål </a>. </li> 
     </ul> </p> <p>Se även <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> används för att skicka in </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: Datapartners ID som du har tilldelats av <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Ditt unika ID för en användare. </li> 
    </ul> <p> <p>Viktigt: Använd endast okodade värden för dina ID:n. Kodningen skapar dubbelkodade identifierare. </p> </p> <p> <p>Obs! Om du använder <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, ange kund-ID:n med <code> setCustomerIDs </code> i stället för <span class="wintitle"> DIL </span>. Se <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Kund-ID och autentiseringstillstånd </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Om true avbryts alla begäranden (IFRAME, händelseanrop, ID-synkronisering och mål) från att köras tills <code> Page Load </code> utlöses. Standard är <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Falskt som standard, vilket betyder <span class="keyword"> Audience Manager </span> anger en cookie i partnerdomänen (anger en cookie för första part). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Viktigt: Det här elementet har ersatts med <span class="wintitle"> DIL </span> version 8.0 (släppt augusti 2018). Använd <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> function </a> i Adobe Experience Platform identitetstjänst i stället. </p> </p> <p> If <code> true </code>, kommer inte att bifoga destinationspubliceringen IFRAME till DOM eller branddestinationerna. Standard är <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Viktigt: Det här elementet har ersatts med <span class="wintitle"> DIL </span> version 8.0 (släppt augusti 2018). Använd <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> function </a> i Adobe Experience Platform identitetstjänst i stället. </p> </p> <p>Inaktiverar ID-synkronisering. Du måste inaktivera ID-synkronisering när du använder DIL v6.2+ och Visitor ID-tjänsten. The <code> visitorService </code> funktionen (se exempelkoden nedan) hanterar den här åtgärden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Ange till <code> true </code> för att aktivera felrapportering för alla <span class="wintitle"> DIL </span> instanser på sidan. Fungerar med Boolean <code> true </code> endast. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Viktigt: Det här elementet har ersatts med <span class="wintitle"> DIL </span> version 8.0 (släppt augusti 2018). Använd <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> function </a> i Adobe Experience Platform identitetstjänst i stället. </p> </p> <p> Anger om målpubliceringsmallen ska använda Akamai för HTTPS-anslutningar. Aktiverat per partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Associerar värdet från ett nyckelvärdepar till ett annat. Se <a href="../../dil/dil-use-cases.md#map-key-values"> Mappa nyckelvärden till andra nycklar </a>. Släppt med v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>Obligatoriskt. </p> <p>The <code> namespace </code> nyckelvärdepar innehåller <span class="keyword"> Experience Cloud </span> Organisations-ID. Om du inte har detta ID kan du hitta det i <span class="wintitle"> Administration </span> i <span class="keyword"> Experience Cloud </span> kontrollpanel. Du behöver administratörsbehörighet för att kunna visa den här instrumentpanelen. Se <a href="../../faq/faq-features.md"> Funktioner och funktioner Frågor och svar </a> och <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administration - Användarhantering och vanliga frågor och svar </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>Obligatoriskt. </p> <p> Partnernamn enligt <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Tar bort skript och återanrop. Standard är <code> False </code>. Gäller den aktuella <span class="wintitle"> DIL </span> Endast instans. Har släppts med v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Anger en cookie med det unika användar-ID som returneras från <span class="keyword"> Audience Manager </span>. Se <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uidCookie-egenskaper </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Krävs med <span class="wintitle"> DIL </span> 6.2 eller senare. </p> <p> DIL förlitar sig på <code> setCustomerIDs </code> funktionen i <span class="wintitle"> Adobe Experience Platform Identity Service </span> skicka deklarerade ID:n till <span class="keyword"> Audience Manager </span>. Se <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Kund-ID och autentiseringstillstånd </a> för mer information. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exempelkod**

Ett exempel [!UICONTROL DIL] anropet kan se ut ungefär så här:

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

Ett godkänt svar returnerar [!UICONTROL DIL] -instans. Ett misslyckat försök returnerar ett felobjekt (kastas inte) om koden har konfigurerats felaktigt eller om ett fel påträffas.

## uidCookie-egenskaper {#uuidcookie-props}

Definierar egenskaperna som används av `uuidCookie` variabel. Den här variabeln är en del av `DIL.create` -metod.

`uuidCookie` har följande egenskaper:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Namn | Beskrivning |
|---|---|
| `name` | Cookie-namn ( `aam_did` är standard). |
| `days` | Cookie-livstid (100 dagar är standard). |
| `path` | Cookie-sökväg, t.ex. `'/test'` ( `/` är standard). |
| `domain` | Domänen som cookien är inställd i, t.ex. `'adobe.com'` ( `'.'+document.domain` är standard). |
| `secure` | Anger en flagga som endast skickar data via en HTTPS-anslutning. |

## visitorService Properties {#visitor-service-props}

Definierar egenskaperna som används av `visitorService` variabel. Den här variabeln är en del av `DIL.create` -metod.

`visitorService` har följande egenskaper:

| Namn | Typ | Beskrivning |
|---|---|---|
| `namespace` | Sträng | Obligatoriskt. Representerar Org-ID:t för Experience Cloud. Detta krävs för Experience Cloud Core Service-funktionaliteten. Samma parameter som används för att instansiera funktionaliteten för besökar-ID. |

**Exempel på kod:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
