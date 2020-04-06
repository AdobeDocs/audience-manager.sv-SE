---
description: Rapportering om aktivitetsanvändning hjälper dig att visa och spåra aktivitetsanvändningen för din Audience Manager-instans, så att du kan jämföra den faktiska användningen med ditt avtalsenliga åtagande.
keywords: activity, usage, reporting, commitment
seo-description: Rapportering om aktivitetsanvändning hjälper dig att visa och spåra aktivitetsanvändningen för din Audience Manager-instans, så att du kan jämföra den faktiska användningen med ditt avtalsenliga åtagande.
seo-title: Aktivitetsanvändningsrapportering
solution: Audience Manager
title: Aktivitetsanvändningsrapportering
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# Aktivitetsanvändningsrapportering

## Översikt {#overview}

Med det här verktyget [!UICONTROL Activity Usage Report] kan du visa och spåra aktivitetsanvändningen för din Audience Manager-instans, vilket ger dig en tydlig uppfattning om hur din aktivitetsanvändning ser ut jämfört med ditt avtalsåtagande.

Dessutom kan du ladda ned [!UICONTROL Activity Usage Report] vid behov för att lagra och göra egna analyser.

## Överväganden {#considerations}

Den [!UICONTROL Activity Usage Report] är tillgänglig för alla Audience Manager-användare med [administratörsbehörighet](edit-account-settings.md).

>[!IMPORTANT]
>
>Här [!UICONTROL Activity Usage Report] visas aktivitetsanvändningsstatistik för din Audience Manager-instans. Kontakta din Adobe-representant om du har faktureringsfrågor som rör din aktivitetsanvändning.

## Användningsexempel {#use-cases}

Det finns två huvudsakliga användningsområden för [!UICONTROL Activity Usage Report]:

* **Spåra faktisk instansaktivitetsanvändning mot din aktivitetsanvändning**: De flesta kunder har ett uppskattat aktivitetsåtagande per månad per Audience Manager-instans, som sedan kumuleras till ett årsmedlemskap för aktivitet i alla instanser. Även om den här rapporten inte är en faktureringsrapport kan den ge användbar vägledning om du överskrider den allokerade aktivitetsanvändningen.
* **Validering av implementeringsändringar**: Om du nyligen har uppdaterat implementeringen, till exempel konfigurerat vidarebefordran på Analytics-serversidan eller ändrat inställningarna för Target-serveranropet, kan den här rapporten hjälpa dig att kontrollera om den nya aktivitetsvolymen är i linje med den förväntade aktivitetsvolymen.

## Använda rapporten om aktivitetsanvändning {#using}

Om du vill se [!UICONTROL Activity Usage Report]det loggar du in på ditt Audience Manager-konto och går till **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Använd sedan **[!UICONTROL Reporting Interval]** filtret för att välja tidsintervall för att generera rapporten. Du kan välja mellan 30, 60, 90 dagar eller ett anpassat datumintervall.

När rapporten har lästs in kan du se en beskrivning av den valda perioden [!UICONTROL Activities] .

[!UICONTROL Activities] Definiera den sammanlagda summan av alla interaktioner på plats och utanför webbplatsen med Audience Manager, uppdelat i följande kategorier:

* **[!UICONTROL Server Calls]**: Alla datainsamlings- och hämtningshändelser som skickas till Audience Manager från webbplatser, servrar, e-post, mobilappar eller andra system.
* **[!UICONTROL Pixel Calls](tidigare kallat[!UICONTROL Impression Server Calls])**: Data som samlats in från annonser (t.ex. visningsvolym från en målinriktningsplattform) eller e-postvisningsanrop till Audience Manager. Dessa kräver att parametern finns i`d_event`frågesträngen.
* **[!UICONTROL On-Boarded Records]**: Unika poster som hämtas från ditt eget CRM-system eller andra offlinedatafiler, t.ex. kundtjänstposter, enhets-ID:n och anpassade dataflöden från externa dataleverantörer.
* **[!UICONTROL Log File Records]**: Unika poster från loggfiler som hämtats till Audience Manager från en målplattform.

>[!NOTE]
>
>En unik post definierar varje enskild datapost i en fil som lagras av Adobe för en Audience Manager-kunds räkning.

Dessutom kan du använda diagramtyperna för att växla mellan två typer av diagram [!UICONTROL Activity Usage Trends] .

![aur-ui-graphs](assets/aur-ui-graphs.png)

Du kan också hålla markören över ett visst datum på tidslinjen för att se hur det datumet används i detalj.

![aur-hover](assets/aur-hover.png)

## Exporterar användningsrapporter för aktivitet {#export}

Om du vill få en bättre överblick över din nivå för aktivitetsanvändning i Audience Manager kan du exportera den [!UICONTROL Activity Usage Report] baserat på vilken typ av poster du vill inkludera.

![aur-export](assets/aur-export.png)

Rapporterna **[!UICONTROL Onboarded Records Breakdown]** och **[!UICONTROL Onsite Server Calls Breakdown]** rapporterna ger den mest detaljerade insikten om källdata som finns tillgängliga för dessa aktiviteter. Den volym som tilldelas dessa uppdelningar baseras på implementeringen.

### Uppdelning av onboardade poster {#onboarded-breakdown}

Den här rapporten innehåller onboardade poster uppdelade efter datakälla.

### Serveranrop på plats, uppdelning {#onsite-breakdown}

Den här rapporten innehåller en uppdelning av serveranrop från tre källor: [!UICONTROL Analytics], [!UICONTROL Target]och [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Detta är fakturerbara serversamtal som skickas från alla Adobe Analytics-instanser till Audience Manager, inklusive vidarebefordran på serversidan. Sekundära serveranrop eller dubblettserveranrop (som vid vidarebefordran på serversidan från flera rapportsviter) är inte fakturerbara aktiviteter, så de ingår inte i den här uppdelningen.
* **[!UICONTROL Target]**: Det här är anrop från Adobe Target till Audience Manager på serversidan, för att hämta segmentdata från Audience Manager som en del av en server-till-server-integrering.
* **[!UICONTROL Other]**: Inkluderar samtal från andra webbplatser eller system (partnerwebbplatser, direktsamtal till servrar osv.), mobilwebbläsare/appsamtal via [!DNL SDK], [!DNL DIL]händelsesamtal och [!DNL DCS] samtal. Inkluderar även anrop från [!DNL Target] om de har konfigurerats som en cookie-integrering (i stället för server-till-server).
