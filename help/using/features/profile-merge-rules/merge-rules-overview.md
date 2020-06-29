---
description: Med reglerna för profilsammanslagning får du kontroll över de datauppsättningar som används för segmentering och kan rikta sig till en person exakt på flera enheter.
seo-description: Med reglerna för profilsammanslagning får du kontroll över de datauppsättningar som används för segmentering och kan rikta sig till en person exakt på flera enheter.
seo-title: Regler för profilsammanslagning - översikt
solution: Audience Manager
title: Regler för profilsammanslagning - översikt
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 0%

---


# [!UICONTROL Profile Merge Rules] Översikt {#profile-merge-rules-overview}

Med [!UICONTROL Profile Merge Rules] hjälp av kan ni styra vilka datauppsättningar som används för segmentering och rikta in er på rätt sätt till användarna på flera enheter.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Datainsamling och målinriktning med anonyma och autentiserade profiler {#data-collection-targeting}

Vanligtvis bygger målgruppssegmentering och målgruppsanpassning på data som samlas in från alla användare på en enhet. Datainsamling och målinriktning baserat på data på enhetsnivå har vissa nackdelar. Du kan t.ex. inte skilja mellan flera användare som delar en enhet eller målar användare korrekt på flera enheter. Enhetscentrerad datainsamling räcker inte längre för digitala marknadsföringskampanjer eller målinriktning mellan olika enheter.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] förändrar i grunden hur data och segment [!DNL Audience Manager] samlas in för målinriktning. Du kan arbeta med två olika typer av profiler, en enhetsprofil och en [autentiserad profil](../../reference/visitor-authentication-states.md).

| Profiltyp | Beskrivning |
|---|---|
| [!UICONTROL Device Profile] | A [!UICONTROL device profile] är knutet till ett ID för en viss enhet, till exempel ett [!UICONTROL cookie] ID eller mobilenhets-ID.<br><br> Den innehåller följande uppgifter:<ul><li>[!UICONTROL Rule-based traits] realiseras när en användare inte autentiseras.</li><li>[!UICONTROL Onboarded traits] kopplat till ett enhets-ID, t.ex. [!UICONTROL cookie-based]tredjepartsdata.</li></ul> |
| [!UICONTROL Authenticated Profile] | Detta [!UICONTROL authenticated profile] är kopplat till ett användar-ID som skickas när en person loggar in på din plats.<br><br>Den innehåller följande uppgifter:<ul><li>[!UICONTROL Rule-based traits] samlas in mellan olika enheter när en användare autentiseras.</li><li>[!UICONTROL Onboarded traits] i en offlinefil som är länkad till samma användar-ID.</li></ul> |

Dessa olika profiler styr vilka data du kan använda för segmentering. Om du till exempel har en [autentiserad profil](../../reference/visitor-authentication-states.md)kan du skapa korrekta [!UICONTROL segments] utifrån data från flera enheter för en enskild användare. Detta innebär att ni kan leverera en enhetlig varumärkesupplevelse till kunder på flera enheter. [!DNL Audience Manager] uppnår detta genom att lagra mappningen av de olika enheter som en person använder för sina onlineaktiviteter till sin [autentiserade profil](../../reference/visitor-authentication-states.md). De här mappningarna kallas [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Fördelar {#advantages}

Med [!UICONTROL Profile Merge Rules] dig kan du

* Target-användare baserat på [autentiserad profil](../../reference/visitor-authentication-states.md), anonyma profiler eller kombinationer av båda.
* Target är en specifik kund på alla deras enheter.
* Skapa ett enhetsdiagram baserat på deterministiska data.
* Finjustera data i dina [!UICONTROL segments] bilder baserat på olika profiler.
* Få ytterligare insikter om er målgrupp.
