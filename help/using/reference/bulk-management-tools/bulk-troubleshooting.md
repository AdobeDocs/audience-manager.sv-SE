---
description: Vad du ska göra när kalkylbladen returnerar ett fel eller när gruppbegäran misslyckas.
seo-description: Vad du ska göra när kalkylbladen returnerar ett fel eller när gruppbegäran misslyckas.
seo-title: Felsökningstips för verktygen för masshantering
solution: Audience Manager
title: Felsökningstips för verktygen för masshantering
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# Felsökningstips för verktygen för masshantering{#troubleshooting-tips-for-bulk-management-tools}

Vad du ska göra när kalkylbladen returnerar ett fel eller när gruppbegäran misslyckas.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i [!DNL Audience Manager] användargränssnittet respekteras i [!UICONTROL Bulk Management Tools].

Faktorer som hög nätverkstrafik, serveranvändning och stora datauppsättningar kan göra att en gruppbegäran misslyckas eller tar slut. Om ett problem uppstår slutar kalkylbladet att skriva data och ett felmeddelande visas. När detta händer bör du:

* Läs felmeddelandet.
* Åtgärda problemet.
* Ta bort alla rader som redan har uppdaterats.
* Försök med gruppbegäran igen.

## Autentiseringsfel, långa fördröjningar eller beteenden som inte svarar {#delays-behavior}

I följande tabell visas några vanliga problem som du kan stöta på när du gör satsvisa begäranden med kalkylbladen. Försök att åtgärda dessa problem med de rekommenderade lösningarna. Om de rekommenderade lösningarna inte löser problemet bör du spara ditt arbete, starta om datorn och försöka utföra begäran igen utan att starta eller arbeta med andra program.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problem </th> 
   <th colname="col2" class="entry"> Lösning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Autentiseringsfel</b> </td> 
   <td colname="col2"> 
    <b>Uppdatera till den senaste versionen av Microsoft Excel</b>: När en ny version av Microsoft Excel släpps och du använder en äldre version kan du råka ut för ett autentiseringsfel i kalkylbladet för grupphantering. Uppdatera till den senaste versionen av Microsoft Excel för att lösa autentiseringsfelet.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Långa förseningar</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Inaktivera kompatibilitetsläge</b>: Kontrollera om andra kalkylblad är öppna i kompatibilitetsläget för Microsoft Excel. Kompatibilitetsläget kan öka körningsmiljöerna. Stäng eventuella öppna kalkylblad i det här läget och försök utföra gruppbegäran igen. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Systemresurser</b>: Begränsade systemresurser leder till långa förseningar. Stäng alla andra program innan du gör en gruppbegäran. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Inget svar</b> </td> 
   <td colname="col2">Om du klickar på en åtgärdsknapp händer ingenting: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Kontrollera att du har rätt rubrikuppsättning för markeringsåtgärden. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Kontrollera att du använder rätt kalkylblad för de kopierade rubrikerna. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Kontrollera positionen för de data som du vill använda i en gruppåtgärd. Alla rubriker börjar i kolumn A, rad 1. Alla data placeras i motsvarande rubriker med början i kolumn A, rad 2 (direkt under rubrikerna). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Felmeddelanden

Ibland kan du få felmeddelanden när du gör gruppändringar. Mer information om hur du tolkar felmeddelandet finns i [Svarskoder definierade](/help/using/api/rest-api-main/aam-api-getting-started.md) i API-dokumentationen.

