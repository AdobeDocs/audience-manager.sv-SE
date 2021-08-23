---
description: Med Audience Analytics kan ni skicka Audience Manager-segment till Analytics. Om du vill använda den här funktionen skapar du ett Analytics-mål och mappar segment till det i Audience Manager.
seo-description: Med Audience Analytics kan ni skicka Audience Manager-segment till Analytics. Om du vill använda den här funktionen skapar du ett Analytics-mål och mappar segment till det i Audience Manager.
seo-title: Konfigurera en Analytics-destination
solution: Audience Manager
title: Konfigurera en Analytics-destination
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 1%

---

# Konfigurera en Analytics-destination

## Krav {#requirements}

Om du vill konfigurera ett Analytics-mål måste Audience Manager-användaren ha administratörsbehörighet. Se [Skapa användare](/help/using/features/administration/administration-overview.md#create-users) i administrationshandboken. Observera att det inte räcker med jokerteckenbehörigheten `CREATE_DESTINATIONS` [för att skapa Analytics-mål.
](/help/using/features/administration/administration-overview.md#wild-card-permissions)
Mer information finns i Krav i [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Din standardanalysdestination och nya analysdestinationer

| Måltyp för analys | Beskrivning |
|---|---|
| Standard | Namnet på standardmålet är &quot;Adobe Analytics&quot;, som du kan redigera. Mappade ID:n för rapporteringsprogramsvit visas i mapplagringen för dina Audience Manager-egenskaper och -segment. <br>  Audience Manager skapar automatiskt ett mål om ditt konto har:  <br>  <ul><li>Uppfyll kraven som beskrivs i dokumentationen för [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html).</li><li>En [rapportserie](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) i Analytics.</li><li>[Mappade en rapportsvit till en organisation](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/report-suite-mapping.html).</li></ul> |
| Nytt | Om du vill skapa nya Analytics-mål går du till Målgruppsdata > Destinationer > Skapa nytt mål och följer stegen för varje avsnitt som beskrivs nedan. |

## Steg 1: Ange grundläggande information

Det här avsnittet innehåller fält och alternativ som startar processen att skapa Analytics-mål. Så här slutför du det här avsnittet:

1. Klicka på **Grundläggande information** för att visa kontrollerna.
2. Namnge målet. Undvik förkortningar och specialtecken.
3. *(Valfritt)* Beskriv målet. En kort beskrivning är ett effektivt sätt att definiera eller ange mer information om en destination.
4. *(Valfritt)* I  **** plattformslistan låter du standardinställningen vara  **Alla**. För närvarande gör dessa alternativ ingenting. De är utformade för att stödja funktioner som kan läggas till vid ett senare tillfälle.
5. I listan **Kategori** väljer du **Adobe Experience Cloud**.
6. I listan **Type** väljer du **Adobe Analytics**.
7. Klicka på **Spara** om du vill gå till konfigurationsinställningarna eller klicka på **Dataexportetiketter** om du vill använda exportkontroller på målet.

>[!NOTE]
>
>För ett analysmål är kryssrutan **Fyll i målmappning automatiskt** och **Segment-ID** markerat som standard. Du kan inte ändra de här inställningarna.

![grundläggande information](assets/basicinformation.png)

## Steg 2: Konfigurera dataexportkontroller

Det här avsnittet innehåller alternativ som tillämpar [dataexportkontroller](/help/using/features/data-export-controls.md) på ett Analytics-mål. Hoppa över det här steget om du inte använder dataexportkontroller. Så här slutför du det här avsnittet:

1. Klicka på **Dataexportkontroller** för att visa kontrollerna.
1. Välj en etikett som motsvarar den dataexportkontroll som används för målet (se [Lägg till dataexportetiketter till ett mål](/help/using/features/destinations/add-data-export-labels.md) ). För Analytics-mål är kryssrutan PII markerad som standard.
1. Klicka på **Spara**.

![exportkontroller](assets/exportControls.png)

## Steg 3: Kartrapportsviter

I avsnittet Konfiguration visas de analysrapportsviter som har aktiverats för vidarebefordran på serversidan. Om du har flera Analytics-destinationer kommer rapportsviterna som tilldelas dessa destinationer att utesluter varandra och tillämpas av Audience Manager. Så här slutför du det här avsnittet:

1. Klicka på **Konfiguration** för att visa kontrollerna.
1. Välj en (eller flera) rapportsviter som du vill skicka segment till.
1. Klicka på **Spara**.

![reportsuites](assets/reportSuites.png)

## Steg 4: Segmentmappningar

I det här avsnittet finns alternativ som gör att du kan mappa segment automatiskt eller manuellt.

| Mappningsalternativ | Beskrivning |
|---|---|
| Mappa automatiskt alla aktuella och framtida segment | Som standard skickas alla segment som en besökare kvalificerar för till Analytics. <br>  Om en besökare tillhör fler än 150 Audience Manager-segment i en enda träff skickas endast de 150 senast kvalificerade segmenten till Analytics, medan den återstående listan trunkeras. En extra flagga skickas till Analytics som anger att segmentlistan trunkerades. Den här åtgärden visas som&quot;Målgruppsgräns nådd&quot; i dimensionen Publiknamn och&quot;1&quot; i dimensionen Publikens ID. Mer information finns i [Vanliga frågor](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html). <br>  Det här alternativet påverkar även måltillgängligheten i  [Segment Builder](/help/using/features/segments/segment-builder.md). Om ett segment till exempel automatiskt mappas till ett Analytics-mål är det målet inte tillgängligt för markering i [målmappningarna](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) i Segment Builder. Analysmålet visas nedtonat och&quot;Analytics&quot; (Analyser) visas i kolumnen Type i målwebbläsaren. |
| Mappa segment manuellt | Det här alternativet visar sök- och bläddringskontroller där du kan välja vilka segment du vill skicka till Analytics. <br>  Så här söker du efter ett segment:  <br>  <ol><li>Skriv segmentnamnet eller ID:t i sökfältet.</li><li>Klicka på <b>Lägg till.</b></li><li>Fortsätt att söka efter och lägga till segment eller klicka på <b>Klar</b>.</li></ol><br>  Så här söker du efter ett segment: <ol><li>Klicka på <b>Bläddra bland alla segment</b>. Då visas en lista med tillgängliga segment.</li><li>Markera kryssrutan för det segment som du vill använda i listan och klicka på <b>Lägg till markerade segment</b>.</li><li>Klicka på <b>Spara</b> i fönstret Lägg till mappningar. Du kan inte ändra mappningar, start- eller slutdatum under betaversionen.</li><li>Fortsätt att bläddra och lägga till segment eller klicka på <b>Klar</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Nästa steg

När du har skapat och sparat ett mål kan du arbeta med dessa data i Analytics. Det kan dock ta några timmar innan data är tillgängliga i de rapportsviter du valt. Se [Använd målgruppsdata i Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).
