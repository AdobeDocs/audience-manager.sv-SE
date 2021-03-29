---
description: Audience Manager får enorma mängder data varje dag. Detta påverkar hur lång tid det tar att bearbeta dina data och generera rapportresultat. Innehållet i det här avsnittet beskriver hur dessa tidsintervall påverkar ditt Audience Manager-konto. Dessutom är de tidsramar och scheman som beskrivs här endast allmänna riktlinjer. Dessa scheman utgör inte serviceavtal (SLA) eller åtaganden som rör dataleverans. Adobe förbehåller sig rätten att när som helst ändra tidsramar och tidsplaner utan föregående meddelande.
seo-description: Audience Manager får enorma mängder data varje dag. Detta påverkar hur lång tid det tar att bearbeta dina data och generera rapportresultat. Innehållet i det här avsnittet beskriver hur dessa tidsintervall påverkar ditt Audience Manager-konto. Dessutom är de tidsramar och scheman som beskrivs här endast allmänna riktlinjer. Dessa scheman utgör inte serviceavtal (SLA) eller åtaganden som rör dataleverans. Adobe förbehåller sig rätten att när som helst ändra tidsramar och tidsplaner utan föregående meddelande.
seo-title: Hur dataleverans och filbearbetningstider påverkar rapporter
solution: Audience Manager
title: Hur dataleverans och filbearbetningstider påverkar rapporter
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: referens
translation-type: tm+mt
source-git-commit: a696bc03e430e25e2752d84905009645c625d762
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 5%

---


# Hur dataleverans och filbearbetningstider påverkar rapporter{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager får enorma mängder data varje dag. Detta påverkar hur lång tid det tar att bearbeta dina data och generera rapportresultat. Innehållet i det här avsnittet beskriver hur dessa tidsintervall påverkar ditt Audience Manager-konto. Dessutom är de tidsramar och scheman som beskrivs här endast allmänna riktlinjer. Dessa scheman utgör inte serviceavtal (SLA) eller åtaganden som rör dataleverans. Adobe förbehåller sig rätten att när som helst ändra tidsramar och tidsplaner utan föregående meddelande.

## Rapportnummer {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

I följande tabell visas och beskrivs tidsintervallen i våra allmänna rapporter och realtidsrapporter.


| Datatyper | Beskrivning |
|---|---|
| Realtidsdata | Dagens realtidsnummer är för timmarna 00:00 till 23:59:59 UTC från igår. |
| Allmänna rapportdata | Data i [Allmänna rapporter](../reporting/general-reports.md#general-reports-overview) är beroende av att andra jobbprocesser har slutförts och mängden data som har tagits emot för en viss dag. För det mesta bör [!UICONTROL General Report]-data uppdateras med 18:00 UTC varje dag. |

## Inkommande och utgående filöverföringar {#inbound-outbound-file-transfers}

[!DNL Audience Manager] bearbetar och skickar inkommande och utgående  [!UICONTROL Server-to-Server (S2S)] filöverföringar enligt de scheman som beskrivs i detta avsnitt. Med tanke på dessa tidsplaner och bryttider kan det finnas skillnader mellan segmentens realtids- och sluttider.

| Filtyp | Beskrivning |
|---|---|
| Inkommande filinmatning (offlinedata) | Filbearbetning utförs två gånger per dag. Dessa procedurer importerar data och förbereder dem för leverans. Filleveranstiderna varierar eftersom de påverkas av den totala mängden kunddata som behöver bearbetas. Du kan förvänta dig en maximal fördröjning på 48 timmar mellan den tidpunkt då filen överförs i Audience Manager och tills data finns tillgängliga för rapportering och aktivering. |
| Utgående (export) filer | Filbearbetning och leverans sker en gång om dagen, kl. 14:00 UTC. Tänk på att bearbetningen och leveransen påverkas av det totala antalet filer och deras storlek. I vissa fall kan det dröja så länge som 24 timmar. När detta inträffar skickar Audience Manager två filer för en viss dag i stället för 1. Vi kommer att meddela våra kunder i de sällsynta fall där Audience Manager måste sluta bearbeta en fil helt och hållet. Med tanke på dessa förhållanden är det svårt att uppskatta leveranstider för utgående data. Om du vill ta reda på om du har fått en komplett uppsättning filer kontrollerar du tidsstämpeln och letar efter eventuella saknade dagar. Det här är en 13-siffrig UNIX UTC-tidsstämpel som registrerar tidpunkten när filen skapades. Se [Utgående dataöverföringar i realtid](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Loggfiler för annonsserver | Filbearbetning utförs i nära realtid för att importera loggfilsposter när timfilerna är klara. Processen att förbereda filerna för rapportering utförs en gång om dagen. Filleveranstiderna varierar eftersom de påverkas av den totala mängden kunddata som behöver bearbetas. Du kan förvänta dig en maximal fördröjning på 48 timmar mellan den tidpunkt då du överför filen till Audience Manager och den tidpunkt då informationen är tillgänglig för rapportering och aktivering. |

>[!MORELIKETHIS]
>
>* [Vanliga frågor om inmatning av inkommande kunddata](../faq/faq-inbound-data-ingestion.md)

