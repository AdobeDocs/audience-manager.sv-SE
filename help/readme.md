---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# Instruktioner

**Obs! Den här sidan (eller någon Viktigt.md-sida) kommer inte att publicera till kundens motstående dokumentation**

## Innehåll

+ `TOC.md` i roten av användarhandboken innehåller information om hur du organiserar de ämnen som finns i handboken för den här lösningen.
+ Varje användarhandbok har sin egen `TOC.md`, där du kan ordna alla sidor/ämnen efter behov.
+ Den första sidan i alla användarhandböcker är `overview.md`.

## Användarhandbok

+ Introduktionen till användarhandboken kallas `overview.md`
+ Varje avsnitt i användarhandboken har en egen separat katalog.
   + Om det finns ett ämne i guiden som heter *Implementering*, är motsvarande katalog `/implementation`
+ Alla bildresurser lagras i `/assets` i roten av användarhandboken.
   + Alla bilder i `/assets` kommer att lokaliseras.
   + Alla bilder i `/no-localize` kommer inte att lokaliseras (det kommer en överraskning!). Detta kan användas för att i lokala versioner säkerställa att specifika resurser inte reproduceras i onödan.

## Metadata för användarhandboksnivå

+ Metadata som beskriver användarhandboken lagras i `TOC.md`. Det inkluderar:
   + product - product/capabilities.
   + cloud - molnet som den här produkten tillhör.
   + målgrupp - målgrupp eller arketyp som guiden riktar sig till.
   + användarhandbok - namn på användarhandboken.

## Metadata för sidnivå

+ Metadata som krävs för att beskriva ett dokument lagras som en del av varje enskild sida. Det inkluderar:
   + title - sidans titel.
   + description - description of page.
   + seo-title - seo alternativ titel.
   + seo-description - alternativ titel för SEO-ändamål.
   + short-title - (valfritt fält).
   + index - ja/nej - kommer sidan att indexeras av Adobe sökplattform.
   + translate - yes / no - will this page be localized.
   + version - används främst för AEM och Campaign för att ange produktversionen.
   + private-feature-pack - används främst för AEM.
   + beta - är den här produkten i betaversion?
   + omdirigering - kan användas för att skapa en referens till en ny sida om det skulle behövas.
   + doc-type: referens (standard) / felsökning / utvecklare / självstudiekurs / kb / whitepaper.

## Mer information

Mer publiceringsanvisningar, stilguider, exempel och andra resurser finns på [Dokumentationsrapport för samarbete](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
