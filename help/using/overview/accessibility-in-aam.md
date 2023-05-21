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
source-wordcount: '417'
ht-degree: 0%

---

# Tillgänglighet i Audience Manager {#accessibility}

## Översikt {#overview}

Hjälpmedel är en serie funktioner som gör en programprodukt användbar, med så lite ansträngning som möjligt från användare med olika funktionshinder, som visuell, auditiv, kognitiv, motor eller andra typer.

Adobe är branschledande inom tillgänglighet och stöder skapandet av enastående webbupplevelser genom att uppmuntra utvecklare att producera engagerande innehåll som är tillgängligt för alla användare. Mer information om tillgänglighetsåtaganden i Adobe finns på [Tillgänglighet för Adobe](https://www.adobe.com/accessibility.html).

De vanligaste hjälpmedelsfunktionerna i programprodukterna är: tangentbordsnavigering, semantisk struktur, tillräcklig kontrast mellan förgrundselement och bakgrundselement, stöd för hjälpmedelsteknik, etiketter för tydliga element osv.

Att göra [!DNL Audience Manager] enklare att använda för alla har vi utvecklat stöd för flera tillgänglighetsfunktioner.

## Tangentbordsnavigering {#keyboard-navigation}

[!DNL Audience Manager] har stöd för fullständig tangentbordstillgänglighet:

* The `Tab` tangenten och pilarna flyttas mellan de enskilda elementen i användargränssnittet.

   ![tillgänglighet - framhävning](assets/accesibility-highlight.png)

* The `Return` (`Enter`) och `Space` aktiverar det markerade objektet.

## Tillgänglig tabellsortering {#table-sorting}

Tabellrubriker kan markeras vid navigering via `Tab` och du kan ändra sorteringsordningen genom att trycka på `Space`.

![accessibility-table-headers](assets/accessibility-table-headers.png)

## Stöd för hjälpfunktioner {#assistive-technologies}

Genom användningen av semantisk kod och [ARIA](https://www.w3.org/WAI/standards-guidelines/aria/), interaktiva element i [!DNL Audience Manager] -användargränssnittet innehåller motsvarande etiketter, hjälpmedelsnamn och roller som identifierar både deras syfte och det aktuella läget.

Detta garanterar att hjälpmedelstekniker, som skärmläsare, kan läsa upp etiketter och annan information för användarna så att de enkelt kan interagera med programkontrollerna.

Alla interaktiva element i användargränssnittet i Audience Manager innehåller motsvarande etiketter. Detta garanterar att hjälpmedelstekniker, som skärmläsare, kan läsa upp etiketterna för användarna.

## Färger och kontrast {#colors-contrast}

The [!DNL Audience Manager] användargränssnittet strävar efter att ge tillräcklig kontrast i programmet för att ge en lättillgänglig visningsupplevelse för användare med nedsatt syn eller färgbrist.

Inläsningsskärmar kan till exempel innehålla en inläsande snurra inuti en vit modal ruta, allt ovanpå en mörkgrå övertäckning.

![hjälpmedelsinläsning](assets/accessibility-loading.png)

## Ytterligare läsning {#further-reading}

[!DNL Audience Manager] strävar efter att ge en allt större grad av tillgänglighet, vilket gör produkten enkel att använda för alla.

Vi rekommenderar att du använder [Feedback-formulär för Adobe](https://www.adobe.com/accessibility/feedback.html) för att skicka förbättringsförslag och tillgänglighetsfrågor som du stöter på. Vi tar gärna hänsyn till dina synpunkter och förbättrar [!DNL Audience Manager].
