---
description: Med reglerna för profilsammanslagning får du kontroll över de datauppsättningar som används för segmentering och kan rikta sig till en person exakt på flera enheter.
seo-description: Med reglerna för profilsammanslagning får du kontroll över de datauppsättningar som används för segmentering och kan rikta sig till en person exakt på flera enheter.
seo-title: Regler för profilsammanslagning - översikt
solution: Audience Manager
title: Regler för profilsammanslagning - översikt
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Regler för profilsammanslagning - översikt {#profile-merge-rules-overview}

Med [!UICONTROL Profile Merge Rules] hjälp av kan ni styra vilka datauppsättningar som används för segmentering och rikta in er på rätt sätt till användarna på flera enheter.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Datainsamling och målinriktning med anonyma och autentiserade profiler {#data-collection-targeting}

Vanligtvis bygger målgruppssegmentering och målgruppsanpassning på data som samlas in från alla användare på en enhet. Datainsamling och målinriktning baserat på data på enhetsnivå har vissa nackdelar. Du kan t.ex. inte skilja mellan flera användare som delar en enhet eller målar användare korrekt på flera enheter. Enhetscentrerad datainsamling räcker inte längre för digitala marknadsföringskampanjer eller målinriktning mellan olika enheter.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] förändrar i grunden hur data och segment [!DNL Audience Manager] samlas in för målinriktning. Du kan arbeta med två olika typer av profiler, en enhetsprofil och en [autentiserad profil](../../reference/visitor-authentication-states.md).

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Profiltyp </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Enhetsprofil </td> 
   <td colname="col2"> <p>En enhetsprofil är kopplad till ett ID för en viss enhet, till exempel ett cookie-ID eller ett mobilenhets-ID. Den innehåller följande uppgifter: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Regelbaserade egenskaper som realiseras när en användare inte autentiseras. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Inbyggda egenskaper kopplade till ett enhets-ID, t.ex. cookie-baserade data från tredje part. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Autentiserad profil </td> 
   <td colname="col2"> <p>Den autentiserade profilen är kopplad till ett användar-ID som skickas när en person loggar in på din plats. Den innehåller </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Regelbaserade egenskaper som samlas in på olika enheter när en användare autentiseras. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Integrerade egenskaper i en offlinefil som är länkad till samma användar-ID. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Dessa olika profiler styr vilka data du kan använda för segmentering. Med en [autentiserad profil](../../reference/visitor-authentication-states.md)kan du till exempel skapa korrekta segment baserat på data från flera enheter för en enskild användare. Detta innebär att ni kan leverera en enhetlig varumärkesupplevelse till kunder på flera enheter. Audience Manager uppnår detta genom att lagra mappningen av de olika enheter som en person använder för sina onlineaktiviteter i sin [autentiserade profil](../../reference/visitor-authentication-states.md). De här mappningarna kallas [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Fördelar {#advantages}

Med [!UICONTROL Profile Merge Rules] dig kan du

* Rikta in er mot användare baserat på [autentiserad profil](../../reference/visitor-authentication-states.md), anonyma profiler eller kombinationer av båda.
* Rikta in er till en viss kund på olika enheter.
* Skapa ett enhetsdiagram baserat på deterministiska data.
* Finjustera data i era segment baserat på olika profiler.
* Få ytterligare insikter om er målgrupp.
