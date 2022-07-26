---
description: Dataexportkontroller förhindrar att du skickar data till mål när den här åtgärden bryter mot datasekretess eller dataanvändningsavtal.
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: Kontroller vid dataexport
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: c7a6de018a0ddd782eecec0844c4f5c824431119
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 1%

---

# Kontroller vid dataexport {#data-export-controls}

[!UICONTROL Data Export Controls] hindra dig från att skicka data till mål när den här åtgärden bryter mot datasekretess eller dataanvändningsavtal.

## Översikt {#overview}

[!UICONTROL Data Export Controls] kan du klassificera [datakällor](../features/datasources-list-and-settings.md#data-sources-list-and-settings) och [mål](../features/destinations/destinations.md). De klassificeringar du använder avgör när data kan exporteras eller inte till ett mål. Den här funktionen består av:

* **[!UICONTROL Data Export Controls]**: Du kan ställa in dataexportkontroller på *datakällor*. När de anges för en datakälla begränsar dessa kontroller hur datakällan och dess egenskaper kan användas.
* **[!UICONTROL Data Export Labels]**: Du kan ange dataexportetiketter på *mål*. När de anges på ett mål identifierar de här etiketterna hur målet använder data. Se [Lägg till dataexportetiketter till ett mål](/help/using/features/destinations/add-data-export-labels.md) om du vill veta hur du lägger till exportetiketter till ett mål.

Exportkontrollerna förhindrar dig från att:

* Lägga till en egenskap i ett segment när egenskapen tillhör en datakälla som har en dataexportkontroll som inte är kompatibel med en dataexportetikett på ett eller flera av de mål som segmentet är mappat till.
Exempel: ett segment är mappat till ett mål med exportetiketten **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. Exportkontroller hindrar dig från att lägga till en egenskap i det segmentet om datakällan som trait tillhör har en dataexportkontroll som säger **[!DNL Cannot be tied to personally identifiable information (PII)]**.
* Skicka alla data till ett mål som har en dataexportetikett som blockeras av en dataexportkontroll på något av följande sätt:
   * Datakällan för en egenskap som ingår.
   * Datakällan för en egenskap som används i ett inkluderat segment.
   * Den profilsammanfogningsregel som används av ett inkluderat segment.
   * Alla datakällor som används av ett inkluderat segments profilkopplingsregel.

[!UICONTROL Data Export Controls] är automatiskt tillgängliga för alla Audience Manager-kunder. Du behöver dock administratörsbehörighet för att lägga till exportkontroller i en datakälla. Om du vill lägga till exportetiketter till ett mål måste du ha administratörsbehörighet *eller* tillräcklig behörighet för att skapa eller redigera ett mål.

## Definierade kontroller och etiketter {#controls-labels}

[!UICONTROL Data Export Controls] innehåller följande kontroller som hjälper dig att klassificera datakällor och mål.

Om du vill blockera dataleverans måste du klassificera en datakälla med en exportkontroll och lägga till en exportetikett till ett mål. Om du använder exportkontroller på en datakälla eller ett mål begränsas inte dataöverföringen av den här funktionen. När den anges för båda datakällorna *och* mål begränsar exportkontrollerna de egenskaper som du kan lägga till i ett segment och förhindrar att segmentmedlemmarna skickas till ett mål.

Dessutom måste minst en exportetikett matcha en exportkontroll innan dataleveransbegränsningarna börjar gälla. Anta att du lägger till [!UICONTROL PII] exportkontroll till en datakälla. Sedan lägger du till etiketten för målinriktning på plats till ett mål. I det här fallet begränsas inte dataleveransen av exportkontrollerna eftersom inställningarna inte matchar. Om du lägger till [!UICONTROL PII] exportetiketten till målet, kommer exportkontrollerna att blockera exporten.

>[!IMPORTANT]
>
>Du kan inte blockera exporten av ett segment genom att placera en dataexportkontroll i segmentets datakälla, du måste ange kontrollen på något av följande:
> * Datakällor för de egenskaper som används i segmentet.
> * Den profilsammanfogningsregel som används av segmentet.
> * Alla datakällor som segmentets profilkopplingsregel använder.


<br>

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dataexportkontroller för en datakälla </th> 
   <th colname="col2" class="entry"> Dataexportetiketter för ett mål </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ingen begränsning</span></b> </td> 
   <td colname="col2"> n/a </td> 
   <td colname="col3"> Som standard anges inte exportbegränsningar för nya datakällor och mål. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kan inte knytas till personligt identifierbar information</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Denna destination kan möjliggöra en kombination med personligt identifierbar information (PII)</span></b> </td> 
   <td colname="col3">När du väljer det här alternativet kan du inte: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Lägg till egenskaper i segment som är mappade till mål som använder PII. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Mappa segment som skapats med ett drag från datakällan till mål som använder PII. </li> 
    </ul> <p>Detta krävs ofta av dataleverantörer från tredje part och när datakällor som innehåller annons-/mediespårningsinformation används. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kan inte användas för annonsanpassning på plats</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Det här målet kan användas för annonsinriktning på plats</span></b> </td> 
   <td colname="col3">När du väljer det här alternativet kan du inte: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Lägg till egenskaper i segment som är mappade till mål som anpassar annonsleveranser baserat på besökarens webbhistorik. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Mappa segment som skapats med ett egenutvecklat beteende från datakällan till mål som anpassar annonsleveransen baserat på besökarens webbhistorik. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kan inte användas för annonsanpassning utanför webbplatsen</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Den här destinationen kan användas för annonsinriktning utanför webbplatsen</span></b> </td> 
   <td colname="col3">Dessa begränsningar används vanligtvis med När du har valt det här alternativet kan du inte: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Lägg till egenskaper i segment som är mappade till mål som återanvänder användare på andra webbplatser. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Mappa segment som skapats med en egenskap från datakällan till mål som återanvänder användare på andra webbplatser. </li> 
    </ul> <p>Krävs ofta när du arbetar med data från plattformar för sociala medier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kan inte användas för anpassning av webbplatser</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Det här målet kan användas för anpassning av annonser på plats</span></b> </td> 
   <td colname="col3">När du väljer det här alternativet kan du inte: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Lägg till egenskaper i segment som är mappade till mål som anpassar innehåll baserat på användarintressen eller webbläsarhistorik. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Mappa segment som byggts med ett drag från datakällan till mål som anpassar innehåll baserat på användarintressen eller webbläsarhistorik. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Arbetsflöde {#workflow}

Kom igång genom att granska datakällan och måldokumentationen. De här artiklarna innehåller instruktioner om hur du lägger till exportkontroller och etiketter i datakällor och mål.

* [Skapa en datakälla](../features/manage-datasources.md#create-data-source)
* [Lägg till dataexportetiketter till ett mål](../features/destinations/add-data-export-labels.md)
