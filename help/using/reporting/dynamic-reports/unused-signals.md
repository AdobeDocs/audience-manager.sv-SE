---
description: Den här rapporten returnerar ett frekvensantal av all oanvänd information som samlats in i ditt lager och skickats till Audience Manager.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: Rapport om oanvända signaler
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 9c980b8fd5c3cb6ba7b3031726da726ee5caeec6
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Rapport om oanvända signaler{#unused-signals-report}

Den här rapporten returnerar ett frekvensantal av all oanvänd information som samlats in i ditt lager och skickats till Audience Manager. Navigera till **Analytics > Audience Reports > Other Reports > Unused Signals** om du vill komma åt den här rapporten.

>[!NOTE]
>
>Om du ser meddelandet&quot;Du har inte tillgång till målgruppsrapporter&quot; kan du kontakta din Audience Manager-konsult eller Kundtjänst för att få rapporten.

![Skärmbild av rapport om oanvända signaler](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Översikt

En signal är information från din webbplats som skickas till [!DNL Audience Manager] i form av [nyckelvärdepar](../../reference/key-value-pairs-explained.md) (t.ex. `color=blue, price>100, gender=female`).

Oanvända signaler består av data som du samlar in men som inte har mappats till ett drag. Rapporten [!UICONTROL Unused Signals] visar data i en tabell utifrån datum, nyckel, värde och frekvens. Alla omappade signaler som skickas till [!DNL Audience Manager] minst 100 gånger per dag kvalificerar sig för rapporten [!UICONTROL Unused Signals].

Oanvända signaler lagras i 45 dagar och kasseras sedan. I rapporten med oanvända signaler visas data från de senaste 10 dagarna.

Läs den här rapporten för att identifiera överblivna signaler som kan mappas till nya eller befintliga egenskaper.

>[!NOTE]
>
>Ange ett nyckel- eller värdenamn i sökfälten för att begränsa resultaten till specifika poster.

## Användningsexempel

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exempel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Se till att trait-överensstämmelse är uppfyllt eller lägg till relaterade värden i en enskild nyckel</b> </p> </td> 
   <td colname="col2"> <p>Granska rapporten för att ta hänsyn till olika värdevariationer för en viss signal. </p> <p>Anta till exempel att du har ett drag för läget "North Carolina" som definierats i ett nyckel/värde-par som <code> c_state = North Carolina</code>. Rapporten kan hjälpa dig att hitta namnvarianter och lägga till dem i egenskapen (t.ex. <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Alternativt kan du identifiera namnvarianter med rapporten och ersätta dem med ett enhetligt värde på alla webbplatser. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Skapa nya egenskaper</b> </p> </td> 
   <td colname="col2"> <p>Granska rapporten för att se vilka nya värden som skickas in för en viss nyckel. Du kan skapa nya nyckelvärdepar baserat på dessa nya värden. </p> <p> <p>Obs! Kontrollera om rapporten innehåller värden som ändras ofta (t.ex. visningar, kampanjer, kändisar osv.) varannan vecka. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Sök efter omappade värden</b> </p> </td> 
   <td colname="col2"> <p>Granska rapporten för nummer 1. Numret 1 i en <span class="wintitle"> oanvänd signal</span> -rapport representerar ett null-värde. Det här är inte nödvändigtvis dåligt. Det betyder helt enkelt att en viss nyckel inte har någon associerad värdemappning. När du ser många 1-värden för en viktig variabel bör du kontrollera med webbplatsteamet att alla sidor är rätt taggade. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bästa praxis

Kör och kontrollera rapporten [!UICONTROL Unused Signals]:

* När du har skapat ett spår eller uppdaterat trait-regler. Detta bidrar till att säkerställa att era egenskaper och regler är korrekt konfigurerade. Resultat nummer 1 visar att ett nytt spår kanske inte är korrekt konfigurerat.
* Varje vecka eller månad. Med schemalagda granskningar kan du säkerställa att alla kundanpassade mappningar är aktuella.

>[!NOTE]
>
>När du söker efter oanvända värden i rapporten bör du tänka på följande. Det finns en skillnad i uttryck mellan de två exemplen nedan:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a)=23))
* Båda exemplen visar ett trait som innehåller två nyckelvärdepar v och a. Det första uttrycket översätts till: trait innehåller nyckel v med värdet 1 [!UICONTROL AND NOT], nyckeln a med värdet 23. Det andra uttrycket innehåller nyckel v med värdet 1 [!UICONTROL AND], nyckeln a med värdet [!UICONTROL NOT EQUAL] 23.
* Med tanke på de två olika uttrycken ovan kan vi säga att du i [!UICONTROL Unused Signals Report] söker efter de värden som skickas på nyckel a med ett annat värde än 23, så får du bara resultat i det första fallet eftersom värden för nyckel inte skickades till ALLA. I det andra fallet skickades värden som inte är 23 så att nyckel a inte används.

## Skapa massfack

Kontakta din representant för Partner Solutions om du behöver skapa många egenskaper baserat på data från rapporten [!UICONTROL Unused Signals].
