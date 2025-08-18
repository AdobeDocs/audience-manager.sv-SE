---
description: Rekommendationer och användningsexempel för återannonsering av segment och anpassade segmentkvalifikationer med enhetsdiagrammet Profile Link.
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: Användningsexempel för profillänkens enhetsdiagram
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 3%

---

# Användningsexempel för profillänkens enhetsdiagram {#profile-link-device-graph-use-cases}

Rekommendationer och användningsexempel för återmarknadsföring av segment och personliga segmentkvalifikationer med [!UICONTROL Profile Link Device Graph].

## Rekommendationer {#recommendations}

Titta på enhetsdiagrammet [!UICONTROL Profile Link] för kampanjer som:

* Ha en hög autentiseringsnivå över alla digitala resurser. Använd ett [alternativ för externt enhetsdiagram](merge-rule-definitions.md#device-options) om du har ett litet antal autentiserade användare.
* Kräv korrekt målinriktning av kända målgrupper. [!UICONTROL Profile Link Device Graph] har skapats med autentiserade data från första part.
* Rikta in er till kända målgrupper i autentiserade och oautentiserade lägen i realtid.

![](assets/merge-rule-triangle2.png)

## Målinriktning mellan olika enheter {#cross-device-personalization}

Låt oss säga att John äger tre enheter som han använder regelbundet för att söka efter erbjudanden om semesterpaket: hans bärbara dator ([!DNL Device 1]), hans smarttelefon ([!DNL Device 2]) och hans surfplatta ([!DNL Device 3]). John använder dock sina enheter för att söka efter olika objekt i paketerbjudandena:

* Han använder sin bärbara dator för att söka efter flyg,
* Han använder sin smarttelefon för att söka efter hotell,
* Han använder sin surfplatta för att söka efter guidade turer.

Även om John inte autentiseras på alla tre av de enheter som nämns ovan, med regeln **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**, kan en semesterpaketleverantör associera dessa enheter med Johns autentiserade profil, under förutsättning att han var den sista personen att autentisera på alla tre enheterna.

![last-device-graph](assets/last-device-graph.png)

Eftersom Audience Manager kvalificerar alla enhetsprofiler som deltar i profilsammanfogningen för ett segment segmenteras alla tre enhetsprofilerna. Med [!UICONTROL Profile Link Device Graph] kan Audience Manager undersöka beteendet på alla tre enheter och kvalificera alla enheter för ett segment som ingen enskild enhetsprofil kvalificerar sig för.

Med [!UICONTROL Profile Merge Rule] kan marknadsförare leverera en enhetlig upplevelse till alla enheter som ägs av en person, baserat på användaraktiviteten i stället för den enskilda enhetsaktiviteten.

![personalisering mellan olika enheter](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Användningsexempel för externt enhetsdiagram](external-graph-use-cases.md)
>* [Allmänna användningsexempel för regler för profilsammanslagning](merge-rule-targeting-options.md)
>* [Regler för profilsammanslagning - frågor och svar](../../faq/faq-profile-merge.md)
