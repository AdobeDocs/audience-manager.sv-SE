---
description: Med grupphanteringsverktygen kan du skapa och hantera flera objekt samtidigt med en enda åtgärd. Du kan använda grupphanteringsverktyg för att arbeta med datakällor, härledda signaler, destinationer, mappar, segment och egenskaper.
keywords: baaam;BAAAM;download baaam
seo-description: Med grupphanteringsverktygen kan du skapa och hantera flera objekt samtidigt med en enda åtgärd. Du kan använda grupphanteringsverktyg för att arbeta med datakällor, härledda signaler, destinationer, mappar, segment och egenskaper.
seo-title: Komma igång med masshantering
solution: Audience Manager
title: Komma igång med masshantering
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---


# Komma igång med masshantering{#getting-started-with-bulk-management}

Med den här funktionen kan du [!DNL Bulk Management Tools] skapa och hantera flera objekt samtidigt med en enda åtgärd. Du kan använda [!DNL Bulk Management Tools] för att arbeta med [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments]och [!UICONTROL traits].

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i [!DNL Audience Manager] användargränssnittet respekteras i [!UICONTROL Bulk Management Tools].

## Översikt {#overview}

Den här funktionen använder ett [!DNL Microsoft Excel] kalkylblad med makron som gör säkra, autentiserade anrop till [!DNL Audience Manager] API:erna. API:t innehåller metoder och tjänster som gör att du kan göra flera ändringar samtidigt. Du behöver inte veta hur du kodar eller arbetar med våra API:er för att kunna använda den. Kalkylbladet innehåller kolumnrubriker och flikar som utför specifika massändringsfunktioner. Om du vill göra satsvisa ändringar lägger du bara till de fördefinierade rubrikerna i specifika kalkylblad, anger den information som du vill ändra gruppvis och klickar på en åtgärdsknapp. Kalkylbladet och API:erna gör resten av arbetet åt dig.

## Hämta {#download}

Ladda ned det senaste kalkylbladet **[här](assets/BAAAM_V2_20200502.xlsm)**.

## Förutsättningar {#prereqs}

För att kunna använda [!DNL Bulk Management Tools]programmet behöver du följande:

* Din [!DNL Experience Cloud] inloggning. Som kund bör du redan ha dessa uppgifter.
* Kalkylbladet [!DNL Bulk Management Tools] . [Hämta kalkylbladet](assets/BAAAM_V2_20200502.xlsm) för att hämta den senaste versionen.
* [!DNL Microsoft Excel] som körs på [!DNL macOS] eller 64 bitar [!DNL Microsoft Windows]. Vi rekommenderar att du använder den senaste versionen av [!DNL Microsoft Excel].
* När du öppnar kalkylbladet måste du **aktivera makron** för [!DNL Bulk Management Tools] att det ska fungera.

## Autentiseringskrav och alternativ {#auth-reqs}

Massändringar kräver autentisering. Innan du utför någon åtgärd måste du logga in. Eftersom kalkylbladet gör API-anrop måste du konfigurera det så att det autentiseras i ditt användarkonto.

**Krav för API-autentisering**

Den andra versionen av [!DNL Bulk Management Tools]som släpptes i oktober 2019 förenklar autentiseringsprocessen. Autentiseringsstegen i den här versionen beskrivs nedan:

1. Öppna kalkylbladet och navigera till **[!UICONTROL Config]** kalkylbladet.
2. Följ stegen som beskrivs i kalkylbladet.
   ![](assets/baaam-authentication.png)
3. När du har slutfört stegen får du göra större ändringar.

När du gör större ändringar måste du fortfarande bekräfta att du har behörighet att göra ändringarna, men API-autentiseringen är automatisk.

**Alternativ för domänautentisering**

Domänautentisering ger dig möjlighet att testa massbegäranden eller tillämpa dem direkt på ditt produktionskonto. Om du gör större ändringar i betamiljön påverkas inte ditt produktionskonto. Produktionsändringarna träder i kraft omedelbart. Med bulkhanteringsbladet kan du arbeta i följande miljöer:

* Beta
* Produktion

## Åtgärder {#actions-ops}

Kalkylbladet består [!UICONTROL Bulk Management Tools] av autentiseringsknappar, åtgärdsflikar, åtgärdsknappar och en **[!UICONTROL Headers]** flik. Fliken innehåller de förformaterade kolumnrubriker som används av åtgärdsikonerna. **[!UICONTROL Headers]** Åtgärdsflikarna innehåller makron som utför den valda gruppåtgärden. Om du vill utföra en gruppåtgärd kopierar du en uppsättning rubriker till rätt åtgärdsflik, anger rubrikdata och klickar på en åtgärdsknapp.

När du har [autentiserat](#auth-reqs)klickar du på en åtgärdsknapp för att komma igång.

![](assets/baaam-worksheet.png)

Tabellen nedan visar de åtgärder du kan utföra och objekt som du kan ändra med [!UICONTROL Bulk Management Tools] kalkylbladen.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Åtgärder </th> 
   <th colname="col2" class="entry"> Objekt </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Massåtgärder visas på flikar längst ned i kalkylbladet och omfattar: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Begäranden </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Uppdatera </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Skapa </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Uppskattning </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Ta bort </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Objekten som du kan ändra gruppvis finns under fliken <b><span class="uicontrol"> Sidhuvuden</span></b> och innehåller: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Datakällor</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Härledda signaler</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> Mål</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> Modeller</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Skräddarsydda mappar</a> och segmentmappar </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> Segment</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> Traits</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exempel på gruppåtgärd**

Låt oss till exempel titta på hur man skapar flera egenskaper samtidigt. Så här skapar du flera egenskaper i en gruppåtgärd:

1. Klicka på **[!UICONTROL Headers]** fliken och kopiera alla etiketter under [!UICONTROL Create a Trait] alternativet.
2. Klicka på **[!UICONTROL Create]** fliken och klistra in etiketterna med början i rad 1, kolumn A.
3. Ange information för varje kolumnrubrik och klicka **[!UICONTROL Create Traits]**. Den här åtgärden uppmanar dig att bekräfta din autentisering. Ditt massjobb körs när du har bekräftat din autentisering. Kontrollera det nedre vänstra hörnet av kalkylbladet för att se om det finns ett jobbstatusmeddelande.


>[!NOTE]
>
>När du arbetar med stora begäranden kan kalkylbladet sluta svara och vara inaktivt. I de här fallen, lämna det bara ifred. Kalkylbladet kommer att bli responsivt när gruppbegäran är slutförd. Om kalkylbladet inte svarar under en längre tid kan du läsa [felsökningsavsnittet](../../reference/bulk-management-tools/bulk-troubleshooting.md).

