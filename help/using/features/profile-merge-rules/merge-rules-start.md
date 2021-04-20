---
description: Om du vill skapa en granskning av regler för profilsammanslagning och slutföra stegen i varje procedur som beskrivs i det här avsnittet.
seo-description: Om du vill skapa en granskning av regler för profilsammanslagning och slutföra stegen i varje procedur som beskrivs i det här avsnittet.
seo-title: Komma igång med regler för profilsammanslagning
solution: Audience Manager
title: Komma igång med regler för profilsammanslagning
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 3%

---

# Komma igång med regler för profilsammanslagning {#getting-started-with-profile-merge-rules}

Om du vill skapa [!UICONTROL Profile Merge Rules] granskar och slutför du stegen i varje procedur som beskrivs i det här avsnittet.

<!-- merge-rules-start.xml -->

## Skapa en datakälla för olika enheter {#create-data-source}

Om du vill skapa en datakälla för olika enheter går du till **[!UICONTROL Audience Data > Data Sources > Add New]** och slutför stegen för varje avsnitt som beskrivs här. Administratörsbehörigheter krävs för att skapa eller redigera en datakälla för olika enheter.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Mer information om de olika kontrollerna finns i [Inställningar för datakälla och Menyalternativ](../datasources-list-and-settings.md#settings-menu-options).

## Information om datakälla {#details}

Så här slutför du avsnittet [!UICONTROL Data Source Details]:

1. Ge datakällan ett namn.
2. *(Valfritt)* Beskriv datakällan. En kortfattad beskrivning hjälper dig att definiera datakällans roll eller syfte.
3. Ange en integreringskod. En integrationskod är ditt eget unika ID för den här datakällan.
4. Välj **[!UICONTROL Cross Device]** i listan **[!UICONTROL ID Type]**.
5. Välj ett alternativ som definierar datakälltypen i listan **[!UICONTROL ID Definition]**. Alternativen är:
   * **[!UICONTROL Person]**: Ett ID som definierar en person. Detta ID kan mappas till flera [!DNL Audience Manager] ID:n.
   * **[!UICONTROL Household]**: Ett ID som definierar en grupp personer. Detta ID kan mappas till flera [!DNL Audience Manager] ID:n.

## Kontroller vid dataexport {#export-controls}

[Dataexportkontroller är ](../data-export-controls.md) valfria klassificeringsregler som du kan tillämpa på en datakälla och ett mål. De förhindrar dig från att skicka data till ett mål när den åtgärden bryter mot en datasekretess eller användaravtal. Hoppa över det här avsnittet om du inte använder [!UICONTROL Data Export Controls].

## Inställningar för datakälla {#settings}

[!UICONTROL Data Source Settings] -avsnittet innehåller flera alternativ, men dessa två är viktiga när du vill skapa en datakälla för olika enheter:

* **[!UICONTROL Use as Authenticated Profile]**: Med den här inställningen kan du skapa en  [!UICONTROL Profile Merge Rule] med dina egna autentiserade data.

* **[!UICONTROL Use as a Device Graph]**: Den här kontrollen är bara tillgänglig för konton som listas som DataProvider. Om du markerar den här kryssrutan skapas datakällan som ett enhetsdiagram så att du kan dela den med andra [!DNL Audience Manager]-kunder. Arbeta med din [!DNL Audience Manager]-konsult för att konfigurera dig som dataleverantör och för att ange vilka kunder denna [!UICONTROL Data Source] ska delas med. Din konsult kommer att tillhandahålla ditt konto och din enhets diagramdelning via en intern provisioneringsprocess.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Med den här kontrollen kan du ange datalagringsperioden för inaktiva kund-ID:n. Detta avgör hur länge Audience Manager behåller sina ID:n i vår databas efter att de senast sågs på Audience Manager-plattformen. Standardvärdet är 24 månader (720 dagar). Det minsta värde du kan ange är 1 månad och det högsta värdet är 5 år. Observera att vi räknar alla månader som 30 dagar. Audience Manager kör en process som tar bort inaktiva kund-ID:n en gång i veckan, i enlighet med den datalagring du anger för inaktiva kund-ID:n.

Med textfälten som är kopplade till de här inställningarna kan du byta namn på [!UICONTROL Data Source] till ett alias som visas i [alternativen för profilkopplingsregel](merge-rule-definitions.md). Om du till exempel lägger till ett alias i **[!UICONTROL Use as Authenticated Profile]** visas det namnet i listan [!UICONTROL Authenticated Profile Options]. Om du lägger till ett alias i **[!UICONTROL Use as a Device Graph]** visas det namnet i [!UICONTROL Device Options]-listan.

## Skapa en profilkopplingsregel {#create-profile-merge-rule}

Om du vill skapa en [!UICONTROL Profile Merge Rule] går du till **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** och slutför stegen för varje avsnitt som beskrivs här.

Du kan skapa upp till 3 kopplingsregler efter att du har konfigurerat en datakälla för olika enheter. Du får åtkomst till en fjärde profilkopplingsregel ([!UICONTROL All Cross-Device Profiles]) om du registrerar dig för [personbaserade mål](../destinations/people-based-destinations-overview.md).

Administratörsbehörighet krävs för att skapa, redigera eller ta bort en regel. Alla användare kan visa och använda befintlig [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Krav:** En datakälla för olika enheter krävs för att skapa en  [!UICONTROL Profile Merge Rule]. Se [Skapa en datakälla](../manage-datasources.md#create-data-source).

>[!TIP]
>
>I [Alternativ för profilkopplingsregel definierade](merge-rule-definitions.md) finns beskrivningar av de olika kontrollerna.

## Grundläggande information {#basic-info}

Så här slutför du avsnittet [!UICONTROL Basic Information]:

1. Namnge [!UICONTROL Profile Merge Rule].
2. *(Valfritt)* Beskriv  [!UICONTROL Profile Merge Rule]. En kortfattad beskrivning hjälper dig att definiera regelns roll eller syfte.
3. *(Valfritt)* Välj  **[!UICONTROL Set as default]** om du vill göra det här till standard  [!UICONTROL Profile Merge Rule]. Nya segment kopplas automatiskt till standardregeln.

## Kontroller vid dataexport {#data-export-controls}

[Dataexportkontroller ](../data-export-controls.md) är valfria klassificeringsregler som du kan tillämpa på dina  [!UICONTROL Profile Merge Rule]. De förhindrar dig från att skicka data till ett mål när den åtgärden bryter mot en datasekretess eller användaravtal. Hoppa över det här avsnittet om du inte använder [!UICONTROL Data Export Controls].

## Inställningar för profilkopplingsregel {#profile-merge-rule-setup}

Så här slutför du avsnittet [!UICONTROL Proflie Merge Rule Setup]:

1. Välj en **[!UICONTROL Authenticated Option]**. Alternativen är:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Välj en **[!UICONTROL Authenticated Profile Option]** (upp till 3, max). Detta är de [datakällor för olika enheter](merge-rules-start.md) som du har skapat tidigare.
3. Välj en **[!UICONTROL Device Option]**. Alternativen är:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Klicka på **[!UICONTROL Save]**.

### Överväganden för Adobe Campaign-destinationer som använder enhets-ID:n som användar-ID:n {#considerations}

I slutet av 2019 har vi släppt en serie förbättringar av reglerna för profilsammanslagning för att förbättra exaktheten hos gruppfiler som genererats med hjälp av enhets-ID:n. Dessa förbättringar respekteras strikt i din Audience Manager-instans från och med måndagen den 16 mars 2020. Därför kommer segment som mappas till ett mål med hjälp av enhets-ID att sluta producera exporter i vissa konfigurationer av profilkopplingsregler.

Kontrollera att du uppfyller följande krav för att se till att Audience Manager-instansen och destinationerna är korrekt integrerade med olika enhets-ID, t.ex. Adobe Campaign:

1. Granska den profilkopplingsregel som används av de segment som är mappade till ditt Adobe Campaign-deklarerade ID-mål. Regeln för profilsammanslagning måste använda alternativet [!UICONTROL Last Authenticated Profile], så alla autentiserade profiler kan inkluderas i exporten. Om din profilkopplingsregel använder ett annat alternativ växlar du till [!UICONTROL Last Authenticated Profile].
2. Markera datakällan för det deklarerade Adobe Campaign-ID:t i inställningarna för profilkopplingsregeln.

>[!NOTE]
>
> Om du har uppnått det maximala antalet [!UICONTROL Profile Merge Rules] och behöver hjälp med att konfigurera dem enligt instruktionerna ovan, kontakta kundtjänst.

## Konfigurera kopplingsregelkod {#configure-merge-rule-code}

Följ de här instruktionerna för att konfigurera [!UICONTROL Adobe Experience Platform Identity Service]-, [!UICONTROL DIL]- och mobilkoden [!DNL SDK] så att den fungerar med kopplingsreglerna.

<!-- merge-rules-configure-code.xml -->

### Förutsättningar

Du måste konfigurera en [datakälla för olika enheter](#create-data-source) och [profilkopplingsregler](#create-profile-merge-rule) *innan du slutför dessa procedurer.*

## För Adobe Experience Platform identitetstjänstkunder {#id-service-customers}

[!UICONTROL Adobe Experience Platform Identity Service] och den senaste versionen av [DIL](../../dil/dil-overview.md) rekommenderas när du arbetar med [!UICONTROL Profile Merge Rules]. Du behöver dock inte använda [!UICONTROL Adobe Experience Platform Identity Service] för att arbeta med den här funktionen. Om du bara använder [!UICONTROL DIL], se [det äldre DIL-avsnittet](#legacy-dil) nedan.

### Konfigurera funktionen Ange kundens ID

När du arbetar med [!UICONTROL Adobe Experience Platform Identity Service] skickar funktionen `setCustomerIDs` deklarerade ID:n till [!DNL Audience Manager]. Om du vill använda en profilkopplingsregel måste du ändra `setCustomerIDs` så att integreringskoden som angavs när du skapade en datakälla mellan enheter används. Exempel: du har skapat en datakälla för olika enheter med integreringskoden `my_datasource_ic`. Om du vill skicka in ett deklarerat ID lägger du till integreringskoden i funktionen för besökar-ID enligt det ändrade kodexemplet nedan.

#### Allmänt kodexempel

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Ändrat kodexempel

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Mer information finns i [Skapa en datakälla för olika enheter](#create-data-source) och [Kund-ID:n och autentiseringstillstånd](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html).

### Konfigurera funktionen `DIL.create`

De senaste versionerna av [!UICONTROL DIL] hämtar nu automatiskt [!UICONTROL declared ID] från funktionen `visitorService` i `DIL.create` (se [Deklarerade ID-variabler](../declared-ids.md#declared-id-variables)). Kontrollera din `DIL.create`-funktion för att se till att den är korrekt konfigurerad enligt exemplet nedan.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

I namnutrymmets nyckelvärdepar är variabeln `*`MCORG`*` ditt [!DNL Experience Cloud] organisations-ID. Om du inte har det här ID:t kan du hitta det i [!UICONTROL Administration]-avsnittet på kontrollpanelen [!DNL Experience Cloud]. Du behöver administratörsbehörighet för att kunna visa den här instrumentpanelen. Se [Administration: Huvudtjänster](https://docs.adobe.com/content/help/sv-SE/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Konfigurera SDK:er

Se avsnittet [Konfigurera SDK](#configure-sdks-legacy-dil) nedan.

## Äldre DIL {#legacy-dil}

Om du inte använder [!DNL Adobe Experience Platform Identity Service] än så borde du verkligen göra det. Men vi förstår att en övergång till ny kod kräver noggranna genomgångar och tester. I dessa fall kontrollerar du din `DIL.create`-funktion för att kontrollera att den är korrekt konfigurerad enligt exemplet nedan.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Mer information finns i det äldre avsnittet [!UICONTROL DIL] i [Deklarerade ID-variabler](../declared-ids.md#declared-id-variables).

### Konfigurera SDK:er {#configure-sdks-legacy-dil}

Kontrollera de metoder i din [!DNL SDK]-kod som gör att du kan skicka [!UICONTROL declared IDs] från [!DNL Android] och [!DNL iOS] mobila enheter. Variabelnamnen för kodbiblioteken [!DNL Android] och [!DNL iOS] är samma:

* `dpid`: ID för datakälla mellan enheter.
* `dpuuid`: The  [!UICONTROL declared ID] (d.v.s. användar-ID).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Enhetstyp </th> 
   <th colname="col2" class="entry"> Metod </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android  </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntax:</b> </p> <p> <pre> public static void setDpidAndDpuid(String dpid, String dpuuid); </pre> </p> <p> <b>Exempel:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS  </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>Syntax:</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>Exempel:</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Se även [Audience Manager-metoder för Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) och [Audience Manager-metoder för iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Skapa en datakälla](../manage-datasources.md#create-data-source)

