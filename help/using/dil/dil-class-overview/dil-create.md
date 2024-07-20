---
description: Skapar en partnerspecifik DIL-instans.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL create
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 0%

---

# DIL create-metod{#dil-create}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av tillägget [!DNL Data Integration Library (DIL)] och [!DNL DIL].
>
>Befintliga kunder kan fortsätta använda sin [!DNL DIL]-implementering. Adobe kommer dock inte att utveckla [!DNL DIL] efter den här punkten. Kunder uppmuntras att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) för sin långsiktiga datainsamlingsstrategi.
>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) i stället.

## DIL create {#dil-create-new}

Skapar en partnerspecifik [!UICONTROL DIL]-instans.

**Funktionssignatur:** `DIL.create: function (initConfig) {}`

**initConfig-element**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>Egenskapen `visitorService` är *always* obligatoriskt. Andra egenskaper som anges här är valfria, såvida inte annat anges.

`initConfig` accepterar följande element:

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
   <td colname="col3"> <p>Den här egenskapen anger behållar-ID som används av <span class="keyword"> Audience Manager </span> för ID-synkroniseringar. Du skulle ange <code> containerNSID </code> om du har <span class="wintitle"> DIL </span> distribuerat över flera platser. Var och en av dessa platser kommer att ha sina egna behållar-ID- och ID-synkroniseringar. När du bara har en plats är behållar-ID 0 som standard och du behöver inte ange detta korrekt. Kontakta din konsult för att få en lista över dina webbplatser och deras behållar-ID. </p> <p>I <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a> motsvarar egenskapen <code> idSyncContainerID </code> <code> containerNSID </code> i <span class="wintitle"> DIL </span>. Observera följande om du använder <span class="wintitle"> DIL </span> <i> och</i> ID-tjänsten på flera platser: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">För varje plats anger du samma behållar-ID på <code> containerNSID </code> och <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Både <span class="wintitle"> DIL </span> och ID-tjänsten kommer att försöka skicka ID-synkroniseringar till vår datainsamling iFrame. iFrame säkerställer dock att <span class="wintitle"> DIL </span> inte startar en ID-synkronisering. Detta förhindrar duplicering. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Endast <span class="wintitle"> DIL </span> skickar data till ett <a href="../../features/destinations/destinations.md"> URL-mål </a>. </li> 
     </ul> </p> <p>Se även <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> används för att skicka in: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: Datapartner-ID tilldelat dig av <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Ditt unika ID för en användare. </li> 
    </ul> <p> <p>Viktigt: Använd endast okodade värden för dina ID:n. Kodningen skapar dubbelkodade identifierare. </p> </p> <p> <p>Obs! Om du använder <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a> anger du kundens ID med metoden <code> setCustomerIDs </code> i stället för <span class="wintitle"> DIL </span>. Se <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Kund-ID och autentiseringstillstånd </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Om värdet är true avbryts alla begäranden (IFRAME, händelseanrop, ID-synkronisering och mål) från att köras tills händelsen <code> Page Load </code> aktiveras. Standardvärdet är <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Falskt som standard, vilket innebär att <span class="keyword"> Audience Manager </span> anger en cookie i partnerdomänen (anger en cookie för första part). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Viktigt: Det här elementet har ersatts med <span class="wintitle"> DIL </span> version 8.0 (släppt augusti 2018). Använd <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> function </a> i Adobe Experience Platform Identity Service i stället. </p> </p> <p> Om <code> true </code> bifogas inte målpubliceringens IFRAME till DOM- eller brandmålen. Standardvärdet är <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Viktigt: Det här elementet har ersatts med <span class="wintitle"> DIL </span> version 8.0 (släppt augusti 2018). Använd <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> function </a> i Adobe Experience Platform Identity Service i stället. </p> </p> <p>Inaktiverar ID-synkronisering. Du måste inaktivera ID-synkronisering när du använder DIL v6.2+ och Visitor ID-tjänsten. Funktionen <code> visitorService </code> (se exempelkod nedan) hanterar den här åtgärden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Ange <code> true </code> om du vill aktivera felrapportering för alla <span class="wintitle"> DIL </span> -instanser på sidan. Fungerar endast med Boolean <code> true </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Viktigt: Det här elementet har ersatts med <span class="wintitle"> DIL </span> version 8.0 (släppt augusti 2018). Använd <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> function </a> i Adobe Experience Platform Identity Service i stället. </p> </p> <p> Anger om målpubliceringsmallen ska använda Akamai för HTTPS-anslutningar. Aktiverat per partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Associerar värdet från ett nyckelvärdepar till ett annat. Se <a href="../../dil/dil-use-cases.md#map-key-values"> Mappa nyckelvärden till andra nycklar </a>. Släppt med v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>Obligatoriskt. </p> <p>Nyckelvärdepar <code> namespace </code> innehåller ditt organisations-ID <span class="keyword"> Experience Cloud </span> . Om du inte har det här ID:t kan du hitta det i avsnittet <span class="wintitle"> Administration </span> på kontrollpanelen <span class="keyword"> Experience Cloud </span>. Du behöver administratörsbehörighet för att kunna visa den här instrumentpanelen. Se <a href="../../faq/faq-features.md"> Frågor och svar om produktfunktioner </a> och <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administration - Användarhantering och vanliga frågor </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>Obligatoriskt. </p> <p> Partnernamn som anges av <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Tar bort skript och återanrop. Standardvärdet är <code> False </code>. Gäller endast den aktuella <span class="wintitle"> DIL </span>-instansen. Har släppts med v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Anger en cookie med det unika användar-ID som returneras från <span class="keyword"> Audience Manager </span>. Se <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uidCookie-egenskaper </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Krävs med <span class="wintitle"> DIL </span> 6.2 eller senare. </p> <p> DIL förlitar sig på funktionen <code> setCustomerIDs </code> i <span class="wintitle"> Adobe Experience Platform Identity Service </span> för att skicka deklarerade ID:n till <span class="keyword"> Audience Manager </span>. Mer information finns i <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Kund-ID och autentiseringstillstånd </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exempelkod**

Ett exempel på [!UICONTROL DIL]-anrop kan se ut ungefär så här:

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

Ett svar returnerar instansen [!UICONTROL DIL]. Ett misslyckat försök returnerar ett felobjekt (kastas inte) om koden har konfigurerats felaktigt eller om ett fel påträffas.

## uidCookie-egenskaper {#uuidcookie-props}

Definierar egenskaperna som används av variabeln `uuidCookie`. Den här variabeln ingår i metoden `DIL.create`.

`uuidCookie` har följande egenskaper:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Namn | Beskrivning |
|---|---|
| `name` | Cookie-namnet ( `aam_did` är standard). |
| `days` | Cookie-livstid (100 dagar är standard). |
| `path` | Cookie-sökväg, t.ex. `'/test'` ( `/` är standard). |
| `domain` | Domänen som cookien är inställd i, t.ex. `'adobe.com'` ( `'.'+document.domain` är standard). |
| `secure` | Anger en flagga som endast skickar data via en HTTPS-anslutning. |

## visitorService-egenskaper {#visitor-service-props}

Definierar egenskaperna som används av variabeln `visitorService`. Den här variabeln ingår i metoden `DIL.create`.

`visitorService` har följande egenskaper:

| Namn | Typ | Beskrivning |
|---|---|---|
| `namespace` | Sträng | Obligatoriskt. Representerar Org-ID:t för Experience Cloud. Detta krävs för Experience Cloud Core Service-funktionaliteten. Samma parameter som används för att instansiera funktionaliteten för besökar-ID. |

**Kodexempel:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
