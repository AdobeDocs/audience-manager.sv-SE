---
description: I den här artikeln beskrivs två funktioner som innehåller avancerade funktioner för Audience Lab Duplicate Allocation Template och Segment Holdout.
seo-description: I den här artikeln beskrivs två funktioner som innehåller avancerade funktioner för Audience Lab Duplicate Allocation Template och Segment Holdout.
seo-title: Avancerade funktioner i Audience Lab
solution: Audience Manager
title: Avancerade funktioner i Audience Lab
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] Avancerade funktioner {#audience-lab-advanced-functionality}

I den här artikeln beskrivs två funktioner som innehåller avancerade funktioner för [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] och [!DNL Segment Holdout].

## Duplicera allokeringsmall {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

I [!DNL Audience Lab]visas de olika [!DNL Allocation Template] val du gör när du skapar en testgrupp:

* Enheternas fördelning mellan testsegmenten.
* Mappning av testsegment till destinationer.
* Den eller de konverteringsegenskaper som du använder för en testgrupp;
* Datumintervallet som testgruppen publicerar på de valda målen.

Genom att duplicera en allokeringsmall kan du återanvända samma fördelning av testsegment och mål för ett annat bassegment i en ny testgrupp. Ett exempel på en allokeringsmall visas nedan. Bilden tas från [!UICONTROL Summary & Finalize] steget i arbetsflödet **Skapa testgrupp** .

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Använda duplicerad allokeringsmall

Skapa en inledande testgrupp och välj sedan **[!UICONTROL Duplicate Allocation Template]** för att återanvända samma inställningar i flera testgrupper. Du kan till exempel använda den här funktionen om du kör ett test där du vill avgöra effekten av flera mål för flera segment.

1. I huvudvyn för Audience Lab söker du efter den testgrupp vars allokeringsmall du vill återge i en ny testgrupp. In the drop-down box, select **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. I [!UICONTROL Create Test Group] guiden kan du ange ett bassegment och byta namn på testsegmenten om du vill.
3. Du *kan inte* ändra:

   * Enheternas fördelning mellan testsegmenten.
   * Konverteringsegenskaper.
   * Mappning av testsegment till mål. Du kan bara fylla i mappningsnyckeln för de mål som kräver en.
   * Datumintervallet som testgruppen publicerar på de valda målen.

4. Granska informationen som du lade till i föregående steg och välj **[!UICONTROL Finalize Group]**.

## Testa segmenthållout {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] är en avancerad funktion som aktiveras på kundens begäran. Kontakta [!DNL Customer Care] eller [!DNL Adobe Consulting] aktivera den här funktionen.

Använd den här funktionen för att hindra en del av publiken från att tas med i testet. Procentandelen som du väljer tas inte med i testet. På så sätt kan du mäta och jämföra antalet konverteringar från målgrupper (aktiverade på destinationer) och icke-målgrupper (utelämningsgrupper).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Använda testsegmentets hållpunkt

1. Skapa en ny testgrupp med hjälp av [!UICONTROL Create Test Group] guiden.
1. I **[!UICONTROL Allocate Test Segment]** steget kan du välja vilken del av publiken som inte ska testas.

   ![Listobjekt](assets/test-segment-holdout.png)

1. Använd skjutreglaget för att justera hur många enheter du vill hålla ut från testningen. Observera hur Test Segment 1 och Test Segment 2 nu bara genererar 70 % av det totala antalet enheter.

   ![](assets/test-segment-holdout-selected.png)

1. Gå igenom resten av stegen i **[!UICONTROL Create Test Group]** arbetsflödet och välj **[!UICONTROL Finalize Group]** när du är nöjd med ditt val. Nu har du en testgrupp där en del av publiken inte kan testas.
