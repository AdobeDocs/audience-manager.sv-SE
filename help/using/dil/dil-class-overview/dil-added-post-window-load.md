---
description: Används för att meddela DIL att det läses in efter att fönstret har lästs in.
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---


# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av tillägget [!DNL Data Integration Library (DIL)] och [!DNL DIL].
>
>Befintliga kunder kan fortsätta använda sin [!DNL DIL]-implementering. Adobe kommer dock inte att utveckla [!DNL DIL] efter den här punkten. Kunder uppmuntras att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) för sin långsiktiga datainsamlingsstrategi.
>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) i stället.

Används för att meddela DIL att det läses in efter att fönstret har lästs in.

**Funktionssignatur:** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## Exempelkod

```
DIL.isAddedPostWindowLoad();
```
