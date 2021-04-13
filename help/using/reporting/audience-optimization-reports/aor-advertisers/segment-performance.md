---
description: I rapporten Segment Performance jämförs mappade och omappade segment med visningar och konverteringsgrader. Ett mappat segment är ett segment som du skapar och skickar till ett mål för målanpassning. Ett omappat segment är ett segment som du har skapat men inte skickat till ett mål för målgruppsanpassning. Genom att jämföra dessa olika segmenttyper inom och mellan rapporter kan ni optimera befintliga kampanjer och hitta förbisedda segment som ni kanske vill skicka till en målgrupp för målinriktning.
seo-description: I rapporten Segment Performance jämförs mappade och omappade segment med visningar och konverteringsgrader. Ett mappat segment är ett segment som du skapar och skickar till ett mål för målanpassning. Ett omappat segment är ett segment som du har skapat men inte skickat till ett mål för målgruppsanpassning. Genom att jämföra dessa olika segmenttyper inom och mellan rapporter kan ni optimera befintliga kampanjer och hitta förbisedda segment som ni kanske vill skicka till en målgrupp för målinriktning.
seo-title: Resultatrapport för segment
solution: Audience Manager
title: Resultatrapport för segment
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization-rapporter
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# Resultatrapport för segment{#segment-performance-report}

I [!UICONTROL Segment Performance]-rapporten jämförs mappade och omappade segment med visningar och konverteringsgrader. Ett mappat segment är ett segment som du skapar och skickar till ett mål för målanpassning. Ett omappat segment är ett segment som du har skapat men inte skickat till ett mål för målgruppsanpassning. Genom att jämföra dessa olika segmenttyper inom och mellan rapporter kan ni optimera befintliga kampanjer och hitta förbisedda segment som ni kanske vill skicka till en målgrupp för målinriktning.

## Så här läser du mappade segmentresultat {#read-mapped-segment-results}

Den mappade [!UICONTROL Segment Performance]-rapporten visar alla segment som du har skapat och skickat till ett mål för målinriktning. Positionen för dina mappade segment i en rapport kan vara bra att veta vilka segment som fungerar och var du kan behöva göra några justeringar.

Om du vill läsa rapporten kan du dela upp resultaten i fyra avsnitt med imaginära rader (i rött) och de kategorier som visas i exempelrapporten nedan.

![](assets/mapped-segment-performance.png)

Etiketterna i exemplet och följande tabell kan hjälpa dig att förstå segmentets prestanda och hur du ska svara på dessa resultat.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Placement Indicates </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Övre vänster</b> </p> </td> 
   <td colname="col2"> <p>Bra konverteringsgrader. </p> <p>Du kanske kan få fler konverteringar genom att öka intrycket. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nederst till vänster</b> </p> </td> 
   <td colname="col2"> <p>Låga konverteringsgrader. </p> <p>Du kanske vill undvika att rikta in dessa segment. Segmenten i det här avsnittet är bra att jämföra med segmenten i det omappade segmentresultatet. Vissa av dina omappade segment kanske fungerar bättre än de segment som du redan har som mål. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Övre höger</b> </p> </td> 
   <td colname="col2"> <p>Starka prestanda. Lämna de här segmenten ifred. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nederst till höger</b> </p> </td> 
   <td colname="col2"> <p>Låg konverteringsgrad och höga intryck. </p> <p>Segmenten i det här avsnittet fungerar inte bra. Du kanske vill flytta budgeten bort från dessa segment och till segment i rapportens övre vänstra kvadrant. Detta minskar intrycket och kan bidra till att förbättra konverteringsgraden för segment i det nedre högra avsnittet. Jämför även dessa mappade segment med dina omappade segment. Vissa av dina omappade segment kanske fungerar bättre än de segment som du redan har som mål. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Så här läser du omappade segmentresultat {#read-unmapped-segment-results}

Att titta på omappade segment i en [!UICONTROL Segment Performance]-rapport är ett bra sätt att hitta nya segment som du inte har tänkt dig som målinriktning. Vissa av dessa segment kanske överträffar dina mappade segment. Detta beror på att ett omappat segment måste uppfylla en uppsättning kvalificeringskriterier som ska ingå i den här rapporten. För att kunna inkluderas i den här rapporten måste ett omappat segment:

* Har konverteringar som är större än genomsnittet för alla mappade segment.
* Var i de 100 övre omappade segmenten efter konverteringsgrad.

Om du vill läsa den här rapporten kan du dela upp resultaten i fyra avsnitt med imaginära rader (i rött) och kategorier som visas i exempelrapporten nedan.

![](assets/unmapped-segment-performance.png)

I den här rapporten vill du bara fokusera på de omappade segmenten i det övre vänstra avsnittet. Dessa omappade segment har hög konverteringsgrad för en låg nivå av visningar jämfört med segment i de övriga tre avsnitten.

>[!NOTE]
>
>7-dagars och 30-dagars summeringsperioder är bara tillgängliga för söndag **[!UICONTROL Date Through]**-datum.
