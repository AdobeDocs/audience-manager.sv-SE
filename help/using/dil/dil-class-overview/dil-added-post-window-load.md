---
description: Används för att meddela DIL att det läses in efter att fönstret har lästs in.
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 1%

---


# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av [!DNL Data Integration Library (DIL)] och [!DNL DIL] tillägg.
><br>
>Befintliga kunder kan fortsätta använda sina [!DNL DIL] implementering. Adobe kommer dock inte att utvecklas [!DNL DIL] bortom denna punkt. Kunder uppmanas att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) för deras långsiktiga strategi för datainsamling.
><br>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) i stället.

Används för att meddela DIL att det läses in efter att fönstret har lästs in.

**Funktionssignatur:** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## Exempelkod

```
DIL.isAddedPostWindowLoad();
```
