---
description: Beskriver förhållandet mellan noggrannhet och räckvidd i algoritmiska egenskaper.
seo-description: Beskriver förhållandet mellan noggrannhet och räckvidd i algoritmiska egenskaper.
seo-title: Noggrannhet och räckvidd
solution: Audience Manager
title: Noggrannhet och räckvidd
uuid: d121e099-6642-4003-ad4f-507d21e478d8
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Noggrannhet och räckvidd {#accuracy-and-reach}

Beskriver förhållandet mellan noggrannhet och räckvidd i algoritmiska egenskaper.

<!-- c_accuracy_reach.xml -->

## Noggrannhet kontra räckvidd: Om

Det är viktigt att förstå relationen mellan noggrannhet och räckvidd när man arbetar med algoritmiska egenskaper. Noggrannheten representeras av ett poängsatt värde som visar hur lika användare är med baslinjen. Precisionsskalan varierar från 0 (minst korrekt) till 1 (mest korrekt). Reach är bara ett värde som representerar antalet unika användare som du vill inkludera i en egenskap. Räckvidd och noggrannhet är omvänt relaterade. Korrekta egenskaper når färre användare och egenskaper med större räckvidd är mindre exakta. Bilden nedan illustrerar detta koncept.

![](assets/Reach_v_Accuracy.png)

## Noggrannhet och räckvidd påverkar målgruppens storlek

Era verksamhetsmål bör hjälpa er att fatta rätt beslut om exakthet och räckvidd när ni arbetar med algoritmiska egenskaper. Om du strävar efter att uppnå exakt rätt bör du tänka på att en traits befolkning kan öka eller minska över modellkörningar. Populationsförändringar är resultatet av algoritmens beslutsfattande under varje utvärderingsperiod. Ibland hittar algoritmen fler kvalificerade användare under en bearbetningscykel och, under andra, kan den hitta färre. Resultaten avgörs av baslinjedata som används för att skapa modellen och nya besökare och trait-kvalifikationer som har kommit sedan den föregående modellkörningen. När användaren arbetar med räckvidd förblir däremot antalet ifyllningar konstant. Om du till exempel vill nå 10 000 användare ser algoritmen till att den alltid träffar numret för varje modellkörning.

## Allmänna användningsexempel för precision kontra räckvidd

Fokuset på precision och räckvidd beror på vad du vill uppnå med ett visst segment. Följande tabell kan hjälpa dig att utvärdera exakthet jämfört med räckvidd när du skapar en egenskap.

| Favoriter för varumärkesbeslut | Hjälper till att hitta |
|---|---|
| **Noggrannhet** | Användare som liknar baslinjekunder i din modell. Användbar för riktade kampanjer när ni vill nå en viss målgrupp. |
| **Räckvidd** | Ett visst antal användare för varje datakörning. Användbar för varumärkeskampanjer när ni är intresserade av att nå en viss målgrupp. |