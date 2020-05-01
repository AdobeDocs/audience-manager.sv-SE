---
description: Om du vill skapa en granskning av regler för profilsammanslagning och slutföra stegen i varje procedur som beskrivs i det här avsnittet.
seo-description: Om du vill skapa en granskning av regler för profilsammanslagning och slutföra stegen i varje procedur som beskrivs i det här avsnittet.
seo-title: Komma igång med profilkopplingsregler
solution: Audience Manager
title: Komma igång med profilkopplingsregler
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Komma igång med profilkopplingsregler {#getting-started-with-profile-merge-rules}

Om du vill skapa, granska [!UICONTROL Profile Merge Rules]och slutföra stegen i varje procedur som beskrivs i det här avsnittet.

<!-- merge-rules-start.xml -->

## Skapa en datakälla för olika enheter {#create-data-source}

Om du vill skapa en datakälla för olika enheter går du till **[!UICONTROL Audience Data > Data Sources > Add New]** och slutför stegen som beskrivs här. Administratörsbehörigheter krävs för att skapa eller redigera en datakälla för olika enheter.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Mer information om de olika kontrollerna finns i Inställningar för [datakälla och Menyalternativ](../datasources-list-and-settings.md#settings-menu-options) .

## Information om datakälla {#details}

Så här slutför du [!UICONTROL Data Source Details] avsnittet:

1. Ge datakällan ett namn.
2. *(Valfritt)* Beskriv datakällan. En kortfattad beskrivning hjälper dig att definiera datakällans roll eller syfte.
3. Ange en integreringskod. En integrationskod är ditt eget unika ID för den här datakällan.
4. In the **[!UICONTROL ID Type]** list, select **[!UICONTROL Cross Device]**.
5. I **[!UICONTROL ID Definition]** listan väljer du ett alternativ som definierar datakälltypen. Alternativen är:
   * **[!UICONTROL Person]**: Ett ID som definierar en person. Detta ID kan mappas till flera [!DNL Audience Manager] ID:n.
   * **[!UICONTROL Household]**: Ett ID som definierar en grupp personer. Detta ID kan mappas till flera [!DNL Audience Manager] ID:n.

## Dataexportkontroller {#export-controls}

[Dataexportkontroller](../data-export-controls.md) är valfria klassificeringsregler som du kan tillämpa på en datakälla och ett mål. De förhindrar dig från att skicka data till ett mål när den åtgärden bryter mot en datasekretess eller användaravtal. Hoppa över det här avsnittet om du inte använder det [!UICONTROL Data Export Controls].

## Inställningar för datakälla {#settings}

[!UICONTROL Data Source Settings] -avsnittet innehåller flera alternativ, men dessa två är viktiga när du vill skapa en datakälla för olika enheter:

* **[!UICONTROL Use as Authenticated Profile]**: Med den här inställningen kan du skapa en [!UICONTROL Profile Merge Rule] med dina egna autentiserade data.

* **[!UICONTROL Use as a Device Graph]**: Den här kontrollen är bara tillgänglig för konton som listas som DataProvider. Om du markerar den här kryssrutan skapas datakällan som ett enhetsdiagram så att du kan dela den med andra [!DNL Audience Manager] kunder. Samarbeta med din [!DNL Audience Manager] konsult för att komma igång som dataleverantör och för att specificera vilka kunder detta [!UICONTROL Data Source] ska delas med. Din konsult kommer att tillhandahålla ditt konto och din enhets diagramdelning via en intern provisioneringsprocess.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Med den här kontrollen kan du ange datalagringsperioden för inaktiva kund-ID:n. Detta avgör hur länge Audience Manager behåller sina ID:n i vår databas efter att de senast sågs på Audience Manager-plattformen. Standardvärdet är 24 månader (720 dagar). Det minsta värde du kan ange är 1 månad och det högsta värdet är 5 år. Observera att vi räknar alla månader som 30 dagar. Audience Manager kör en process som tar bort inaktiva kund-ID:n en gång i veckan, i enlighet med den datalagring du anger för inaktiva kund-ID:n.

Med textfälten som är kopplade till de här inställningarna kan du byta namn på [!UICONTROL Data Source] med ett alias som visas i alternativen [för](merge-rule-definitions.md)profilkopplingsregel. Om du till exempel lägger till ett alias i **[!UICONTROL Use as Authenticated Profile]** visas namnet i [!UICONTROL Authenticated Profile Options] listan. Om du lägger till ett alias i **[!UICONTROL Use as a Device Graph]** visas namnet i [!UICONTROL Device Options] listan.

## Skapa en profilkopplingsregel {#create-profile-merge-rule}

Om du vill skapa en [!UICONTROL Profile Merge Rule]fil går du till **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** och slutför stegen som beskrivs här.

Du kan skapa upp till 3 kopplingsregler efter att du har konfigurerat en datakälla för olika enheter. Du får tillgång till en fjärde profilkopplingsregel ([!UICONTROL All Cross-Device Profiles]) om du registrerar dig för [personbaserade mål](../destinations/people-based-destinations-overview.md).

Administratörsbehörighet krävs för att skapa, redigera eller ta bort en regel. Alla användare kan visa och använda befintliga [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Förutsättningar:** Det krävs en datakälla för olika enheter för att skapa en [!UICONTROL Profile Merge Rule]. Se [Skapa en datakälla](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Se Alternativ för [profilkopplingsregel definierade](merge-rule-definitions.md) för beskrivningar av de olika kontrollerna.

## Grundläggande information {#basic-info}

Så här slutför du [!UICONTROL Basic Information] avsnittet:

1. Namnge [!UICONTROL Profile Merge Rule].
2. *(Valfritt)* Beskriv [!UICONTROL Profile Merge Rule]. En kortfattad beskrivning hjälper dig att definiera regelns roll eller syfte.
3. *(Valfritt)* Välj **[!UICONTROL Set as default]** om du vill göra det här till standard [!UICONTROL Profile Merge Rule]. Nya segment kopplas automatiskt till standardregeln.

## Dataexportkontroller {#data-export-controls}

[Dataexportkontroller](../data-export-controls.md) är valfria klassificeringsregler som du kan tillämpa på dina [!UICONTROL Profile Merge Rule]. De förhindrar dig från att skicka data till ett mål när den åtgärden bryter mot en datasekretess eller användaravtal. Hoppa över det här avsnittet om du inte använder det [!UICONTROL Data Export Controls].

## Inställningar för profilkopplingsregel {#profile-merge-rule-setup}

Så här slutför du [!UICONTROL Proflie Merge Rule Setup] avsnittet:

1. Välj en **[!UICONTROL Authenticated Option]**. Alternativen är:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Välj en **[!UICONTROL Authenticated Profile Option]** (upp till 3, maximalt). Detta är de datakällor [som du har skapat på olika](merge-rules-start.md) enheter tidigare.
3. Välj en **[!UICONTROL Device Option]**. Alternativen är:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Klicka på **[!UICONTROL Save]**.

## Konfigurera kopplingsregelkod {#configure-merge-rule-code}

Följ de här instruktionerna för att ställa in [!UICONTROL Adobe Experience Platform Identity Service]koden [!UICONTROL DIL]och den mobila [!DNL SDK] koden så att den fungerar med dina kopplingsregler.

<!-- merge-rules-configure-code.xml -->

### Förutsättningar

Du måste skapa en [datakälla](#create-data-source) för olika enheter och [profilkopplingsregler](#create-profile-merge-rule) *innan* du slutför dessa procedurer.

## För Adobe Experience Platform Identity Service-kunder {#id-service-customers}

Du bör använda [!UICONTROL Adobe Experience Platform Identity Service] och den senaste versionen av [DIL](../../dil/dil-overview.md) när du arbetar med [!UICONTROL Profile Merge Rules]. Du behöver dock inte använda funktionen [!UICONTROL Adobe Experience Platform Identity Service] för att arbeta med den här funktionen. Om du bara använder [!UICONTROL DIL]kan du läsa det [gamla DIL-avsnittet](#legacy-dil) nedan.

### Konfigurera funktionen Ange kundens ID

När du arbetar med [!UICONTROL Adobe Experience Platform Identity Service]filen skickar `setCustomerIDs` funktionen deklarerade ID:n till [!DNL Audience Manager]. Om du vill använda en profilkopplingsregel måste du ändra den så `setCustomerIDs` att integreringskoden som angavs när du skapade en datakälla mellan olika enheter används. Exempel: du har skapat en datakälla för olika enheter med integreringskoden `my_datasource_ic`. Om du vill skicka in ett deklarerat ID lägger du till integreringskoden i funktionen för besökar-ID enligt det ändrade kodexemplet nedan.

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

Mer information finns i [Skapa en datakälla](#create-data-source) för olika enheter samt [Kund-ID och autentiseringstillstånd](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html).

### Konfigurera `DIL.create` funktion

De senaste versionerna av hämtar [!UICONTROL DIL] nu automatiskt [!UICONTROL declared ID] från `visitorService` funktionen i `DIL.create` (se [Deklarerade ID-variabler](../declared-ids.md#declared-id-variables)). Kontrollera din `DIL.create` funktion för att se till att den är korrekt konfigurerad enligt exemplet nedan.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

I namnutrymmets nyckelvärdepar är `*`MCORG`*` -variabeln ditt [!DNL Experience Cloud] Organization ID. Om du inte har det här ID:t kan du hitta det i [!UICONTROL Administration] avsnittet på [!DNL Experience Cloud] instrumentpanelen. Du behöver administratörsbehörighet för att kunna visa den här instrumentpanelen. Se [Administration: Bastjänster](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Konfigurera SDK:er

Se avsnittet [Konfigurera SDK](#configure-sdks-legacy-dil) nedan.

## Äldre DIL {#legacy-dil}

Om du inte använder [!DNL Adobe Experience Platform Identity Service] än, så borde du verkligen göra det. Men vi förstår att en övergång till ny kod kräver noggranna genomgångar och tester. I så fall kontrollerar du att funktionen är korrekt konfigurerad enligt exemplet nedan. `DIL.create`

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Mer information finns i det äldre [!UICONTROL DIL] avsnittet i [Deklarerade ID-variabler](../declared-ids.md#declared-id-variables).

### Konfigurera SDK:er {#configure-sdks-legacy-dil}

Kontrollera de metoder i koden [!DNL SDK] som gör att du kan skicka [!UICONTROL declared IDs] från [!DNL Android] och [!DNL iOS] från mobila enheter. Variabelnamnen för [!DNL Android] - och [!DNL iOS] kodbiblioteken är desamma:

* `dpid`: ID för datakälla mellan enheter.
* `dpuuid`: The [!UICONTROL declared ID] (d.v.s. användar-ID).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Enhetstyp </th> 
   <th colname="col2" class="entry"> Metod </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntax:</b> </p> <p> <pre> public static void setDpidAndDpuid(String dpid, String dpuuid); </pre> </p> <p> <b>Exempel:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
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

Se även [Audience Manager Methods for Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) and [Audience Manager Methods for iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Skapa en datakälla](../manage-datasources.md#create-data-source)

