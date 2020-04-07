---
description: En allmän rapport returnerar resultatdata för egenskaper, segment och mål.
seo-description: En allmän rapport i Audience Manager returnerar prestandadata för egenskaper, segment och mål.
seo-title: Allmänna rapporter i Audience Manager
solution: Audience Manager
title: Allmänna rapporter
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# Allmänna rapporter{#general-reports}

En [!UICONTROL General] rapport returnerar resultatdata för egenskaper, segment och mål.

## Översikt {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] använder [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) för att utöka användargruppsbehörigheter till [!UICONTROL General] rapporter. Användarna kan bara se de egenskaper och segment i rapporter som de har behörighet att visa. [!UICONTROL RBAC] kan ni styra vilka rapportdata som interna team kan visa. En byrå som till exempel hanterar olika annonsörkonton kan konfigurera användargruppbehörigheter så att ett team som hanterar Advertiser A:s konto inte kan se annonsörens B:s rapportdata.

Kör en [!UICONTROL General] rapport när du behöver:

* Granska prestanda efter egenskaper, segment eller mål.
* Spåra visningar (totalt och unikt) med 1, 7, 14, 30, 60 och 90 dagars intervall.
* Granska totalt och unikt lastantal.
* Jämför egenskaper och segmentprestanda.
* Identifiera starka eller dåliga prestationsegenskaper och segment, analysera efterfrågan eller jämför lastnings-/branddata med tredjepartsrapporter.
* Exportera data (.csv-format) för vidare analys och delning.

Följande bild ger en översikt på hög nivå över viktiga element i [!UICONTROL General] rapporten.

![](assets/general_reports.png)

1. Konfigurera följande alternativ:

   * **Typ av rapportering:** Välj önskad rapporttyp (Trait, Segment eller Destination).

   * **Till:** Ange rapportens datumintervall.

2. Sök efter ett varumärke, segment eller mål efter namn eller ID.
3. I mapplistan drar och släpper du de egenskaper, segment eller mål som du vill rapportera till [!UICONTROL Selections] panelen till höger.
4. Generera rapporten som ska visas i en exporterbar rapport.

## Kör en allmän rapport {#run-general-report}

I det här avsnittet beskrivs hur du kör en [!UICONTROL General] rapport och anger tid och andra prestandaalternativ.

<!-- 

t_run_general_report.xml

 -->

1. Klicka på på **[!UICONTROL Analytics]** kontrollpanelen **[!UICONTROL General Reports]**.
1. Välj önskad typ i **[!UICONTROL Report Type]** listrutan: Trait, Segment eller Destination.
1. *Villkorligt* Klicka i datumrutan för att visa en kalender och välj sedan rapportens slutdatum om du vill ange ett annat datum än dagens.
1. Sök efter ett varumärke, segment eller mål efter namn eller ID.
1. I mapplistan drar och släpper du de egenskaper, segment eller mål som du vill rapportera till [!UICONTROL Selections] panelen till höger.
1. Klicka på **[!UICONTROL Run Report]**.

   Resultaten visas i en tabell som kan exporteras. Klicka på kolumnrubrikerna för att sortera resultaten i stigande eller fallande ordning.
1. Välj önskad alternativknapp längst upp i rapporten om du vill filtrera data efter prestanda ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]eller [!UICONTROL Total Trait Population]) eller efter tid (1, 7, 14, 30, 60 eller 90-dagarsintervall).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] beräknas [!UICONTROL Rule-based Traits] endast för.

1. *Valfritt* klick **[!UICONTROL Export to CSV]**. Detta exporterar [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]och [!UICONTROL Total Trait Population] för alla dagintervall.

## Allmänna rapportresultat förklaras {#general-reports-explained}

Siffrorna i [!UICONTROL General Reports] genereras direkt från vår [!UICONTROL User Profile Store]. Resultaten avspeglar antalet användare som finns i serverdelen vid den tidpunkt då dessa rapporteringsnummer genererades [!DNL Audience Manager] .

* Dessa siffror inkluderar inte besökar-ID:n med mycket trafik. Trafik från bottar filtreras innan den når vårt serverdelssystem. Dessutom ignoreras viss robottrafik under en veckas rensningsjobb som körs i serverdelen.
* Om du bäddar in data via inkommande bearbetning som är avaktiverad för [!DNL Audience Manager] UID, och dessa ID:n innehåller användare som inte längre är aktiva i vårt system, kommer dessa inaktiva [!DNL Audience Manager] UID:n aldrig att nå [!UICONTROL User Profile Store] och rapporteras inte.
* [!UICONTROL Total Trait Realizations] beräknas [!UICONTROL Rule-based Traits] endast för.

## Resultat av allmänna rapporter för egenskaper {#general-report-results-traits}

Måtten nedan är tillgängliga när du kör en allmän rapport och väljer **[!UICONTROL Trait]** som rapporttyp:

**Unika kundrelationer**

Det här måttet representerar det unika antalet [Audience Manager-unika användar-ID (UUID)](../reference/ids-in-aam.md) som är kvalificerade för egenskapen i det valda tidsintervallet. Om en användare till exempel besökte din hemsida tre gånger den 10/1 skulle du se en Unik Trait Realization.

**Totalt antal anpassningar**

Det här måttet representerar den totala mängden trait som utlöses för trait i det valda tidsintervallet. Om en användare till exempel besökte din hemsida och sedan navigerade till dina tekniska nyheter och dina sportnyheter, skulle de visas i den allmänna rapporten som tre kompletta trait-implementeringar och en unik trait-implementering.

**Population för totalt fack**

Det här måttet representerar den totala mängden UUID för Audience Manager som för närvarande är kvalificerade för egenskapen. Använd det här numret för att förstå hur många användare du kan använda för segmentering och målinriktning. Vanligtvis ingår användare i ett varumärke i [120 dagar](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). En användare som till exempel besöker din hemsida tre gånger idag och aldrig återvänder efteråt, blir kvar som användare i den här befolkningen varje dag till 120 dagar från och med nu. Vid 120 dagars markering skulle de tas bort från befolkningen. Läs vår referens [för](../features/traits/trait-and-segment-qualification-reference.md) Trait and Segment Qualification om du vill ha fler exempel på skillnaden mellan Unique Trait Realizations och Total Trait Population.

Bilden nedan visar resultatet av att köra en allmän rapport för rapporttypen Trait.

![](assets/general_reports_metrics.png)

## Resultat av allmänna rapporter för segment {#general-report-results-segments}

Måtten nedan är tillgängliga när du kör en allmän rapport och väljer **[!UICONTROL Segment]** som rapporttyp:

**Segmentpopulering i realtid**

Det här måttet visar det faktiska antalet unika besökare som har setts i realtid i det angivna tidsintervallet och som var kvalificerade för segmentet när de sågs av Audience Manager.

**Total segmentpopulation**

Det här måttet representerar det totala antalet Audience Manager UUID:n som är kvalificerade för segmentet under den summeringsperiod som du valde. Den totala segmentpopulationen på en dag representerar den mest korrekta användarbasen för målinriktning.

>[!NOTE]
>
>Välj **[!UICONTROL Include Destination Mappings]** om du vill se en uppdelning av segmentpopulationen för aktiverade destinationer.

Bilden nedan visar resultatet av att köra en allmän rapport för rapporttypen Segment.

![](assets/general_reports_segment_metrics.png)

## Resultat av allmänna rapporter för destinationer {#general-report-results-destinations}

Måtten nedan är tillgängliga när du kör en allmän rapport och väljer **[!UICONTROL Destination]** som rapporttyp:

**Segmentpopulering i realtid**

Det här måttet visar det faktiska antalet unika besökare som har setts i realtid i det angivna tidsintervallet och som var kvalificerade för segmentet när de sågs av Audience Manager.

**Total segmentpopulation**

Det här måttet representerar det totala antalet Audience Manager UUID som tillhör ett segment inom summeringsperioden och som skickades till ett mål.

Bilden nedan visar resultatet av att köra en allmän rapport för rapporttypen Destinationer.

![](assets/general_reports_destinations.png)
