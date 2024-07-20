---
description: Hjälpmedel är en serie funktioner som gör en programprodukt användbar, med så lite ansträngning som möjligt från användare med olika funktionshinder, som visuell, auditiv, kognitiv, motor eller andra typer.
seo-description: Accessibility refers to a series of features that make a software product usable, with as little effort as possible from users with various disabilities, such as visual, auditory, cognitive, motor, or other kind.
seo-title: Accessibility in Audience Manager
solution: Audience Manager
title: Tillgänglighet i Audience Manager
feature: Overview
exl-id: 45fd53e6-b8e1-49b4-99a3-c78adc90c707
source-git-commit: 15e36d2847627b5e5ccef11f8073ce5124f14815
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---

# Tillgänglighet i Audience Manager {#accessibility}

## Översikt {#overview}

Hjälpmedel är en serie funktioner som gör en programprodukt användbar, med så lite ansträngning som möjligt från användare med olika funktionshinder, som visuell, auditiv, kognitiv, motor eller andra typer.

Adobe är branschledande inom tillgänglighet och stöder skapandet av enastående webbupplevelser genom att uppmuntra utvecklare att producera engagerande innehåll som är tillgängligt för alla användare. Mer information om tillgänglighetsåtaganden i Adobe finns i [hjälpmedel för Adobe](https://www.adobe.com/accessibility.html).

De vanligaste hjälpmedelsfunktionerna i programvaror är: tangentbordsnavigering, semantisk struktur, tillräcklig kontrast mellan förgrundselement och bakgrundselement, stöd för hjälpfunktioner, etiketter för tydliga element osv.

För att göra [!DNL Audience Manager] enklare att använda för alla har vi utvecklat stöd för flera tillgänglighetsfunktioner.

## Tangentbordsnavigering {#keyboard-navigation}

[!DNL Audience Manager] har stöd för fullständig tangentbordstillgänglighet:

* `Tab`-tangenten och pilarna rör sig mellan enskilda element i användargränssnittet.

  ![Accesibility-highlight](assets/accesibility-highlight.png)

* Nycklarna `Return` (`Enter`) och `Space` aktiverar det markerade objektet.

## Tillgänglig tabellsortering {#table-sorting}

Tabellrubriker kan markeras när du navigerar med tangenten `Tab`, och du kan ändra sorteringsordningen genom att trycka på `Space`.

![accessibility-table-headers](assets/accessibility-table-headers.png)

## Stöd för hjälpfunktioner {#assistive-technologies}

Genom att använda semantisk kod och [ARIA](https://www.w3.org/WAI/standards-guidelines/aria/) innehåller interaktiva element i [!DNL Audience Manager] -användargränssnittet motsvarande etiketter, hjälpmedelsnamn och roller som identifierar både deras syfte och det aktuella läget.

Detta garanterar att hjälpmedelstekniker, som skärmläsare, kan läsa upp etiketter och annan information för användarna så att de enkelt kan interagera med programkontrollerna.

Alla interaktiva element i användargränssnittet i Audience Manager innehåller motsvarande etiketter. Detta garanterar att hjälpmedelstekniker, som skärmläsare, kan läsa upp etiketterna för användarna.

## Färger och kontrast {#colors-contrast}

Användargränssnittet [!DNL Audience Manager] strävar efter att ge tillräckligt med kontrast i programmet för att se till att användare med nedsatt syn eller färgbrister får en lättillgänglig visningsupplevelse.

Inläsningsskärmar kan till exempel innehålla en inläsande snurra inuti en vit modal ruta, allt ovanpå en mörkgrå övertäckning.

![hjälpmedelsinläsning](assets/accessibility-loading.png)

## Ytterligare läsning {#further-reading}

[!DNL Audience Manager] strävar efter att tillhandahålla en allt större grad av tillgänglighet, vilket gör produkten enkel att använda för alla.

Vi rekommenderar att du använder formuläret [Återkoppling om tillgänglighet för Adobe](https://www.adobe.com/accessibility/feedback.html) för att skicka förbättringsförslag och tillgänglighetsproblem som du stöter på. Vi tar gärna hänsyn till din feedback och förbättrar [!DNL Audience Manager].
