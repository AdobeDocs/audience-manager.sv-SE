---
description: En boolesk konfiguration som avgör om DIL skickar (eller inte skickar) data till Adobe Experience Cloud Device Co-op.
seo-description: An optional, Boolean configuration that determines if DIL sends (or does not send) data to the Adobe Experience Cloud Device Co-op.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
feature: DIL Implementation
exl-id: 33dca495-6923-4966-9ec3-8b0fd2f17649
hide: true
hidefromtoc: true
index: n
source-git-commit: 3f4a161ee856357b5cb5eb757ad779dee5357b09
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 1%

---

# isCoopSafe{#iscoopsafe}

>[!WARNING]
>
>Den här funktionen har tagits bort.

En boolesk konfiguration som avgör om DIL skickar (eller inte skickar) data till Adobe Experience Cloud Device Co-op.

## Krav {#requirements}

Används `isCoopSafe` du måste:

* Använd [!UICONTROL DIL] v6.11 eller senare.
* Delta i [Experience Cloud Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/home.html). Potentiella medarbetare bör också granska denna dokumentation för att avgöra om `isCoopSafe` åtgärdar möjliga problem med hur data används för att skapa enhetsdiagrammet.

* Arbeta med dina [!DNL Adobe] konsult för att ange en tillåtelselista- eller blockeringslista-flagga på ditt Device Co-op-konto. Det finns ingen självbetjäningssökväg för att aktivera dessa flaggor.

## Användningsexempel {#use-cases}

`isCoopSafe` hjälper till att lösa 2 användningsfall som rör datainsamling av aktuella eller potentiella medlemmar i Device Co-op. De här användningsexemplen gäller hur besöksdata för webbplatsen skickas vidare till Device co-op för att hjälpa till att skapa enhetsdiagrammet. I följande tabell beskrivs hur `isCoopSafe` fungerar med de här användningsfallen för att blockera eller skicka data till enhetsdiagrammet

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Användningsexempel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Autentiserade besökare</b> </p> </td> 
   <td colname="col2"> <p>Lägg till <code> isCoopSafe </code> till <span class="wintitle"> DIL </span> kod för att styra hur data för autentiserade besökare som har eller inte har godkänt avtal om användartid används av Device Co-op för att skapa enhetsgrafen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>DIL på tredjepartswebbplatser</b> </p> </td> 
   <td colname="col2"> <p>Lägg till <code> isCoopSafe </code> till <span class="wintitle"> DIL </span> kod som ska användas på tredjepartswebbplatser där du: </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">Det går inte att se till att autentiserade besökare har eller inte har godkänt användningsvillkor. </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">Måste styra hur dessa data används av Device Co-op för att skapa enhetsgrafen. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempel på syntax och kod {#syntax-code-sample}

**Syntax:** `isCoopSafe: true | false`

De booleska alternativen avgör hur kunddata används eller inte används av Device Co-op.

* `isCoopSafe: true`: Besöksdata som samlats in av en mobil SDK eller webbplats *kan* användas för att skapa enhetsgrafen.

* `isCoopSafe: false`: Besöksdata som samlats in av en mobil SDK eller webbplats *inte* användas för att skapa enhetsgrafen.

**Exempel på kod**

Ange detta när DIL instansierar.

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## Parametrar för POST av händelseanrop {#post-parameters}

Beroende på vilken flagga du anger ( `true` eller `false`), [!UICONTROL DIL] translates `isCoopSafe` till de här POSTERNA och skickar dem till [!DNL Adobe] i ett händelseanrop:

* `d_coop_safe=1`
* `d_coop_unsafe=1`

Parametrarna för POST anger [!DNL Experience Cloud] Device Co-op om det kan eller inte kan inkludera användardata i enhetsdiagrammet. Tabellen nedan definierar relationen mellan `isCoopSafe` Booleska flaggor och POST-parametrar som skickas vid ett händelseanrop. Om du inte använder `isCoopSafe`, skickas ingen av dessa i ett händelseanrop.

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Konfigurationsstatus </th> 
   <th colname="col2" class="entry"> POST-parameter </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: true </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_safe=1 </code> </p> <p>Device Co-op kan använda besöksdata för att skapa enhetsdiagrammet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: false </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_unsafe=1 </code> </p> <p>Device Co-op kan inte använda besöksdata för att skapa enhetsdiagrammet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## API:er efter instansiering {#post-instantiation}

Med dessa API:er kan du åsidosätta `isCoopSafe` status. Dessa är nödvändiga eftersom de gör att du kan ändra en besökares status efter instansiering/efter inloggning på en webbplats eller i en app för en sida där sidan inte uppdateras. Du måste till exempel anropa dessa API:er om en användare autentiserar till din webbplats eller app och senare accepterar en användarvillkorsprincip som tillåter Device Co-op att använda deras data.

<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopSafe(); </code> </p> </td> 
   <td colname="col2"> <p>Anger POST-parameter <code> d_coop_safe=1 </code> i alla efterföljande händelseanrop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>Anger POST-parameter <code> d_coop_unsafe=1 </code> i alla efterföljande händelseanrop. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->
