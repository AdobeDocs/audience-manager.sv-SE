---
description: Med reglerna för profilsammanslagning får du kontroll över de datauppsättningar som används för segmentering och kan rikta sig till en person exakt på flera enheter.
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: Regler för profilsammanslagning - översikt
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# [!UICONTROL Profile Merge Rules] - översikt {#profile-merge-rules-overview}

Med [!UICONTROL Profile Merge Rules] kan du styra vilka datauppsättningar som används för segmentering och rikta in användarna korrekt på flera enheter.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Datainsamling och målinriktning med anonyma och autentiserade profiler {#data-collection-targeting}

Vanligtvis bygger målgruppssegmentering och målgruppsanpassning på data som samlas in från alla användare på en enhet. Datainsamling och målinriktning baserat på data på enhetsnivå har vissa nackdelar. Du kan t.ex. inte skilja mellan flera användare som delar en enhet eller målar användare korrekt på flera enheter. Enhetscentrerad datainsamling räcker inte längre för digitala marknadsföringskampanjer eller målinriktning mellan olika enheter.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] ändrar i grunden hur [!DNL Audience Manager] samlar in data och segmentanvändare för målinriktning. Du kan arbeta med två olika typer av profiler, en enhetsprofil och en [autentiserad profil](../../reference/visitor-authentication-states.md).

| Profiltyp | Beskrivning |
|---|---|
| [!UICONTROL Device Profile] | Ett [!UICONTROL device profile] är kopplat till ett ID för en viss enhet, till exempel ett [!UICONTROL cookie] ID eller mobilenhets-ID.<br><br> Den innehåller:<ul><li>[!UICONTROL Rule-based traits] realiserades när en användare inte autentiseras.</li><li>[!UICONTROL Onboarded traits] är kopplat till ett enhets-ID, till exempel [!UICONTROL cookie-based], tredjepartsdata.</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile] är knuten till ett användar-ID som skickas när en person loggar in på din plats.<br><br>Den innehåller:<ul><li>[!UICONTROL Rule-based traits] samlas in mellan enheter när en användare autentiseras.</li><li>[!UICONTROL Onboarded traits] i en offlinefil som är länkad till samma användar-ID.</li></ul> |

Dessa olika profiler styr vilka data du kan använda för segmentering. Med till exempel en [autentiserad profil](../../reference/visitor-authentication-states.md) kan du skapa korrekt [!UICONTROL segments] baserat på data från flera enheter för en enskild användare. Detta innebär att ni kan leverera en enhetlig varumärkesupplevelse till kunder på flera enheter. [!DNL Audience Manager] uppnår detta genom att lagra mappningen av de olika enheter som en person använder för sina onlineaktiviteter till sin [autentiserade profil](../../reference/visitor-authentication-states.md). Dessa mappningar kallas [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Fördelar {#advantages}

Med [!UICONTROL Profile Merge Rules] kan du:

* Målanvändare baserat på [autentiserad profil](../../reference/visitor-authentication-states.md), anonyma profiler eller kombinationer av båda.
* Rikta in er till en viss kund på olika enheter.
* Skapa ett enhetsdiagram baserat på deterministiska data.
* Finjustera data i [!UICONTROL segments] baserat på olika profiler.
* Få ytterligare insikter om er målgrupp.
