---
description: Visa en lista över dina konfigurerade datakällor, lägg till nya datakällor och redigera befintliga källor.
seo-description: Visa en lista över dina konfigurerade datakällor, lägg till nya datakällor och redigera befintliga källor.
seo-title: Lista över datakällor och inställningar
solution: Audience Manager
title: Lista över datakällor och inställningar
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 0%

---


# [!UICONTROL Data Sources] Lista och inställningar {#data-sources-list-and-settings}

Visa en lista över din nuvarande konfiguration [!UICONTROL data sources], lägg till nya [!UICONTROL data sources]och redigera befintliga [!UICONTROL data sources].

Du kan också hantera [!UICONTROL data sources] med [!DNL API] metoder. Mer information finns i API-metoder för [datakälla](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Listvy {#list-view}

Kontrollpanelen är en central arbetsyta för hantering av datakällor [!UICONTROL Data Sources] .

Kontrollpanelen ( [!UICONTROL Data Sources]**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) innehåller funktioner och verktyg som du kan använda för att:

* Se alla era befintliga [!UICONTROL data sources]data, inklusive varje datakällas beskrivning, status och om det är [!UICONTROL Inbound], [!UICONTROL Outbound], båda eller en [!UICONTROL Shared Provider].
* Sök efter [!UICONTROL data sources] namn.
* Skapa, redigera och ta bort [!UICONTROL data sources].

## [!DNL Data Source] Inställningar och menyalternativ {#settings-menu-options}

Inställningarna i de olika avsnitten i [!UICONTROL Data Source] hanteringsgränssnittet identifierar dina foton [!DNL data source], avgör hur de används eller delas samt gör att du kan aktivera felrapportering för [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] Detaljer {#details}

Förutom textfält innehåller avsnittet de kontroller och alternativ som anges nedan [!UICONTROL Data Source Details] .

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Inställning </th> 
   <th colname="col2" class="entry"> Menyalternativ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-typ</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: Det cookie-ID som identifierar en enhet. Du väljer detta när datakällan är en webbläsare eller när du arbetar med anonyma data eller data som inte kan kopplas till en enskild person. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> Enhetens annons-ID</span></b>: Identifieraren för den mobila enheten. Välj det här alternativet när datakällan är en mobil enhet eller en Internetaktiverad enhet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Enhetsövergripande</span></b>: Ett autentiserat ID som tillhandahålls av kunden. Välj det här alternativet när du vill skapa: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">En datakälla för olika enheter och bygg en <span class="wintitle"> profilkopplingsregel</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">En datakälla som använder länkar från <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> eller ett annat enhetsdiagram från tredje part som är integrerat med <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-definition</span></b> </p> </td> 
   <td colname="col2"> <p>Alternativen för <b><span class="uicontrol"> ID-definition</span></b> definierar relationen mellan en datakälla och ett UUID ( <span class="keyword"> Audience Manager</span> user ID) och tillhörande enheter som är länkade av <span class="keyword"> Adobe Experience Cloud Device Co-op</span> eller ett annat enhetsdiagram från tredje part som är integrerat med <span class="keyword"> Audience Manager</span>. Alternativen är: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Person:</span></b> Det ID som används för att definiera en person. Detta ID kan mappas till flera <span class="keyword"> Audience Manager</span> -ID:n. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Hushåll:</span></b> Det ID som används för att definiera en grupp med personer. Detta ID kan mappas till flera Audience Manager ID:n. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Dataexportkontroller](../features/data-export-controls.md) är valfria klassificeringsregler som du kan tillämpa på en [!UICONTROL data source] och [!UICONTROL destination]. De förhindrar dig från att skicka data till en [!UICONTROL destination] när den åtgärden bryter mot en datasekretess eller användaravtal. Hoppa över det här avsnittet om du inte använder det [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Exportbegränsningar fungerar inte om du inte anger en matchande exportetikett för en [!UICONTROL destination].

Alternativen är:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Inställningar {#data-source-settings}

Den [!UICONTROL Data Source Settings] innehåller de kontroller och alternativ som listas nedan. Vissa av dessa inställningar har ytterligare underalternativ och menyalternativ som du kan välja för att ändra en datakälla.

### [!UICONTROL Inbound Data Source] Inställningar

Markera kryssrutan **[!UICONTROL Inbound]** när datakällan är avsedd att ta emot inkommande data. Om du markerar **[!UICONTROL Inbound]** kryssrutan visas ytterligare två grupper av kontroller som beskrivs nedan.

>[!NOTE]
>
>Kryssrutan är bara avsedd att visa eller dölja de **[!UICONTROL Inbound]** [!UICONTROL data source] kontroller som beskrivs nedan. Om du avmarkerar alternativet påverkas inte dataanvändningen på något sätt. **[!UICONTROL Inbound]** Dina inbyggda data kommer att bearbetas oavsett vilket alternativ du markerar.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Inställning </th> 
   <th colname="col2" class="entry"> Menyalternativ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-typ</span></b> </p> </td> 
   <td colname="col2"> <p>Alternativet <b><span class="uicontrol"> Inkommande</span></b> kräver en ID-typ. Alternativen är: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> Kund-ID</span></b>: Identifierar inkommande data med ett kund-ID. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager-ID</span></b>: Identifierar inkommande data med ett <span class="keyword"> Audience Manager</span> -ID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud-ID</span></b>: Identifierar inkommande data med ett <span class="keyword"> Experience Cloud</span> -ID. See <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Felsökning av filformat</span></b> </p> </td> 
   <td colname="col2"> <p>Markera <b><span class="uicontrol"> Aktivera felsampling</span></b> när du behöver felsöka problem med inkommande filbearbetning. Den här funktionen genererar en felexempelrapport som visar filformat och syntaxfel. </p> <p>Se <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Statusrapport för introduktion: Om</a> du vill ha information om felrapportering och felsampling. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Andra [!UICONTROL Data Source] inställningar

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Inställning </th> 
   <th colname="col2" class="entry"> Markera när </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utgående</span></b> </p> </td> 
   <td colname="col2"> <p>Datakällan skickar data till ett mål. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Delning aktiverad</span></b> </p> </td> 
   <td colname="col2"> <p>Din datakälla kan delas med andra partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Använd som autentiserad profil</span></b> </p> </td> 
   <td colname="col2"> <p>Din datakälla för olika enheter innehåller ett autentiserat ID. Ett autentiserat ID samlas in och synkroniseras till ett <span class="keyword"> Audience Manager</span> ID under en autentiseringshändelse (t.ex. när en användare loggar in på plats, i appen osv.). Det autentiserade ID:t kan användas för att inhämta data från andra källor som lagrar detta ID. Den kan också användas för att länka flera enhets-ID:n i <span class="wintitle"> Profile Link</span>. </p> <p>Med det här alternativet visas ett textfält där du kan byta namn på datakällan med ett alias. Om du använder ett alias åsidosätter det här nya namnet datakällans namn och visas i <span class="wintitle"> Autentiserade profilalternativ</span> när du <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> skapar en profilsammanfogningsregel</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Använd som enhetsdiagram</span></b> </p> </td> 
   <td colname="col2"> <p>Skapar en datakälla som ett enhetsdiagram som du kan förse andra <span class="keyword"> Audience Manager</span> -kunder med. Innan du väljer det här alternativet bör du informera din <span class="keyword"> Audience Manager</span> -konsult om vilka kunder den här <span class="wintitle"> datakällan</span> ska delas med. Din konsult måste tillhandahålla dessa företag genom våra interna processer. </p> <p>Med det här alternativet visas ett textfält där du kan byta namn på datakällan med ett alias. Om du använder ett alias åsidosätter det nya namnet datakällans namn och visas i <span class="wintitle"> Enhetsalternativ</span> när du <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> skapar en profilsammanfogningsregel</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Dela associerade besökar- eller enhets-ID:n med specifika Audience Manager-kunder</span></b> </p> </td> 
   <td colname="col2"> <p>Datakällan för olika enheter innehåller ID:n från ett enhetsdiagram. Ett enhetsdiagram är en samling ID:n som mappar till ett eller flera <span class="keyword"> Audience Manager</span> ID:n till ett kluster. Klustret representerar vanligtvis en person eller en större hushållsgrupp. Endast tillgängligt för konton som listas som"Data Provider". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Dela associerade besökar- eller enhets-ID:n över Audience Manager Platform</span></b> </p> </td> 
   <td colname="col2"> <p>Datakällan innehåller besökar- eller enhets-ID:n som kan delas med andra <span class="keyword"> Experience Cloud</span> -lösningar. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Datalagring för inaktiva kund-ID:n</span></b> </p> </td> 
   <td colname="col2"> <p>Gör att du kan ange datalagringsperioden för inaktiva kund-ID:n. Detta avgör hur länge Audience Manager behåller sina ID:n i vår databas efter att de senast sågs på Audience Manager-plattformen.</p> <p>Standardvärdet är 24 månader (720 dagar). Det minsta värde du kan ange är 1 månad och det högsta värdet är 5 år. Observera att vi räknar alla månader som 30 dagar.</p> <p>Audience Manager kör en process som tar bort inaktiva kund-ID:n en gång i veckan, i enlighet med den datalagring du anger för inaktiva kund-ID:n.</p> <p>Audience Manager kör en process som tar bort inaktiva kund-ID:n en gång i veckan, i enlighet med den datalagring du anger för inaktiva kund-ID:n.</p> <p><b>Obs</b>: Den här kontrollen är bara tillgänglig för datakällor mellan enheter. Se även <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Skapa en datakälla för olika enheter </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Integreringskoder för unikt fack</span></b> </p> </td> 
   <td colname="col2"> <p>Du vill se till att två egenskaper från samma datakälla inte har samma integreringskod. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unika integreringskoder för segment</span></b> </p> </td> 
   <td colname="col2"> <p>Du vill se till att två segment från samma datakälla inte har samma integreringskod. </p> </td> 
  </tr>
 </tbody>
</table>
