---
description: Recommendations och användningsexempel för återmarknadsföring av segment och anpassade segmentkvalifikationer med enhetsdiagrammet Profile Link.
seo-description: Recommendations och användningsexempel för återmarknadsföring av segment och anpassade segmentkvalifikationer med enhetsdiagrammet Profile Link.
seo-title: Användningsexempel för enhetsdiagram för profillänk
solution: Audience Manager
title: Användningsexempel för enhetsdiagram för profillänk
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 9%

---


# Användningsexempel för enhetsdiagram för profillänk {#profile-link-device-graph-use-cases}

Recommendations och användningsexempel för återmarknadsföring av segment och anpassade segmentkvalifikationer med [!UICONTROL Profile Link Device Graph].

## Recommendations {#recommendations}

Ta en titt på enhetsdiagrammet [!UICONTROL Profile Link] för kampanjer som:

* Ha en hög autentiseringsnivå över alla digitala resurser. Använd ett [alternativ för externt enhetsdiagram](merge-rule-definitions.md#device-options) om du har ett litet antal autentiserade användare.
* Kräv korrekt målinriktning av kända målgrupper. [!UICONTROL Profile Link Device Graph] byggs med autentiserade data från första part.
* Rikta in er till kända målgrupper i autentiserade och oautentiserade lägen i realtid.

![](assets/merge-rule-triangle2.png)

## Målinriktning mellan enheter {#cross-device-personalization}

Låt oss säga att John äger tre enheter som han regelbundet använder för att söka efter semestererbjudanden: den här bärbara datorn ([!DNL Device 1]), hans smarttelefon ([!DNL Device 2]) och hans surfplatta ([!DNL Device 3]). John använder dock sina enheter för att söka efter olika objekt i paketerbjudandena:

* Han använder sin bärbara dator för att söka efter flyg,
* Han använder sin smarttelefon för att söka efter hotell,
* Han använder sin surfplatta för att söka efter guidade turer.

Även om John inte autentiseras på alla tre av de enheter som nämns ovan kan en semesterpaketleverantör associera dessa enheter med Johns autentiserade profil genom att använda regeln **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**, förutsatt att han var den sista personen som autentiserades på alla tre enheterna.

![last-device-graph](assets/last-device-graph.png)

Eftersom Audience Manager kvalificerar alla enhetsprofiler som ingår i profilsammanfogningen för ett segment segmenteras alla tre enhetsprofilerna. Med [!UICONTROL Profile Link Device Graph] kan Audience Manager titta på beteendet på alla tre enheterna och kvalificera alla enheter för ett segment som ingen enskild enhetsprofil kvalificerar sig för.

Med denna [!UICONTROL Profile Merge Rule] kan marknadsförare leverera en enhetlig upplevelse till alla enheter som ägs av en person, baserat på användaraktiviteten i stället för den enskilda enhetsaktiviteten.

![personalisering på olika enheter](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Användningsexempel för externt enhetsdiagram](external-graph-use-cases.md)
>* [Allmänna användningsexempel för regler för profilsammanslagning](merge-rule-targeting-options.md)
>* [Vanliga frågor om regler för profilsammanslagning](../../faq/faq-profile-merge.md)

