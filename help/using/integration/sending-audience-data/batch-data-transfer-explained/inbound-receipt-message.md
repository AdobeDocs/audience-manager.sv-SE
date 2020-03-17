---
description: Varje gång en inkommande Server-till-Server-fil bearbetas skickas ett kvitto via e-post till partnerlösningar och, om detta är konfigurerat, till partnern.
seo-description: Varje gång en inkommande Server-till-Server-fil bearbetas skickas ett kvitto via e-post till partnerlösningar och, om detta är konfigurerat, till partnern.
seo-title: Exempelmeddelande till partners efter inkommande bearbetning
solution: Audience Manager
title: Exempelmeddelande till partners efter inkommande bearbetning
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Exempelmeddelande till partners efter inkommande bearbetning{#sample-message-to-partners-after-inbound-processing}

När en inkommande [!UICONTROL Server-to-Server] fil bearbetas skickas ett kvitto via e-post till partnerlösningar och, om konfigurationen är konfigurerad, till partnern.

<!-- r_inbound_message.xml -->

Följande exempel är ett exempel på ett e-postmeddelande. Tabellen under meddelandet beskriver de olika raderna i meddelandet.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Från: aam-noreply@adobe.com </b> </p> <p> <b>Ämne: Bearbetningsresultat för Adobe Audience Manager Server-to-Server:</b> </p> <p> <b>Bästa Adobe-partner: (ID:7)</b><b></b> </p> <p> <b>Vi har tagit emot din filleverans från Adobe Audience Manager Server till server</b> </p> <p> <b>Filnamn:</b> <i></i> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>Mottagna poster: 40669900</b> </p> <p><b>Formatfel: 0</b> </p> <p> <b>Ogiltigt AAM-ID: 112 </b> </p> <p> <b>Inget matchande AAM-ID: 0 </b> </p> <p> <b>Inget fack realiserat: 26730823 </b> </p> <p> <b>Bearbetade poster: 40669900 </b> </p> <p> <b>Lagrade poster: 13938958 </b> </p> <p> <b>Totalt antal enheter: 21 </b> </p> <p> <b>Totalt antal signaler: 918878926 </b> </p> <p> <b>Totalt antal oanvända signaler: 660348376 </b> </p> <p> <b>Totalt antal realiserade egenskaper: 258086908 </b> </p> <p> <b>Totalt antal borttagna egenskaper: 0 </b> </p> <p> <b>Totalt antal traits misslyckades vid validering: 0 </b> </p> <p> <b>Totalt antal användare som har egenskaper som inte kunde valideras: 0 </b> </p> <p> <b>Jobbstarttid: 2018-05-17 18:07:49 </b> </p> <p> <b>Jobbsluttid: 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

Följande tabell innehåller rader som motsvarar rader i det mottagna e-postmeddelandet.

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linje </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Filnamn </td> 
   <td colname="col2"> <p>Lista över alla inkommande filer som Adobe har tagit emot för den här partnern och som har bearbetats tillsammans. I det föregående exempelmeddelandet är partner-ID 7 och dataägar-ID 901. </p> <p>Slutnumret (1,2,3...) är det uppdelade nummer som lagts till antingen av kunden eller av den inkommande distributören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mottagna poster </td> 
   <td colname="col2"> <p>Totalt antal poster som Adobe tagit emot över alla filer. I de flesta fall bör detta vara det totala antalet rader i inkommande filer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formatfel </td> 
   <td colname="col2"> <p>Antal rader som inte matchade det förväntade formatet. Dessa rader kunde inte identifieras av det inkommande jobbet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ogiltigt AAM-ID </td> 
   <td colname="col2"> <p>Antal Audience Manager UUID:n som inte matchar det förväntade 38-siffriga formatet. Eller så är Audience Manager UUID:n som skickas i filen inte siffror. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inget matchande AAM-ID </td> 
   <td colname="col2"> <p>Totalt antal användare för vilka Audience Manager inte kunde hitta ett matchande UUID. Dessa filer har inte synkroniserats med ID, så Audience Manager kan inte slå upp UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inget fack realiserat </td> 
   <td colname="col2"> <p>Antal poster där ingen av signalerna på linjen kopplas till en Audience Manager-egenskap. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bearbetade poster </td> 
   <td colname="col2"> <p>Totalt antal poster Audience Manager har bearbetats. I de flesta fall bör det här numret vara samma som"Mottagna poster". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lagrade poster </td> 
   <td colname="col2"> <p>Antal poster som resulterar i data som ska läsas in i systemet = Bearbetade poster - Formatfel - Ogiltiga AAM-ID:n - Inget matchande AAM-ID - Inget spår realiserat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totalt antal enheter </td> 
   <td colname="col2"> <p>Antal enheter för vilka data lästes in i systemet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totalt antal signaler </td> 
   <td colname="col2"> <p> Totalt antal signaler för alla användare i alla inkommande filer (totalt antal nyckel-/värdepar i de bearbetade posterna). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totalt antal oanvända signaler </td> 
   <td colname="col2"> <p>Totalt antal oanvända signaler för alla användare i alla inkommande filer (nyckel/värde-par som inte mappades till Audience Manager-egenskaper). I de flesta fall innebär det att Audience Manager inte har definierade regler för signalen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totala realiserade egenskaper </td> 
   <td colname="col2"> <p>Antal Audience Manager-egenskaper för alla användare i alla inkommande filer baserat på signalerna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totalt antal borttagna egenskaper </td> 
   <td colname="col2"> <p> Totalt antal borttagna egenskaper för alla användare i alla inkommande filer. För fullständig synkronisering händer detta om användaren har egenskapen i en tidigare körning men inte i den aktuella körningen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totalt antal traits som inte kunde valideras </td> 
   <td colname="col2"> <p>Representerar antalet egenskaper som inte tillhör den datakälla som deklarerats i filnamnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totalt antal användare som har egenskaper som inte kunde valideras </td> 
   <td colname="col2"> <p>Antalet poster som hade egenskaper som inte kunde valideras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Jobbstarttid </td> 
   <td colname="col2"> <p>Den tidpunkt då det inkommande jobbet startar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Jobbsluttid </td> 
   <td colname="col2"> <p>Den tidpunkt då det inkommande jobbet avslutas. </p> </td> 
  </tr> 
 </tbody> 
</table>