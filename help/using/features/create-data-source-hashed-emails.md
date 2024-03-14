---
title: Konfigurera en datakälla för hash-kodade e-postarbetsflöden
description: Lär dig hur du skapar en datakälla för att lagra hash-kodade e-postmeddelanden för hash-kodade e-postarbetsflöden.
solution: Audience Manager
feature: Data Sources
source-git-commit: b88f180808ec9723a2a5324441733f6383f6302d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---


# Konfigurera en datakälla för hash-kodade e-postarbetsflöden

Hash-kodade e-postarbetsflöden, t.ex. personbaserade mål, kräver att du skapar en datakälla för att lagra de hashkodade e-postadresserna.

Följ stegen nedan för att skapa och konfigurera en datakälla för hashad e-post.

1. Logga in på ditt Audience Manager-konto och gå till **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** och klicka **[!UICONTROL Add New]**.
1. Ange en **[!UICONTROL Name]** och **[!UICONTROL Description]** för din nya datakälla.
1. I **[!UICONTROL ID Type]** nedrullningsbar meny, välja **[!UICONTROL Cross Device]**.
   ![Audience Manager-gränssnittsbild som visar avsnittet med information om datakällan.](../features/assets/create-hashed-email-data-source.png)
1. I **[!UICONTROL Data Source Settings]** väljer du båda **[!UICONTROL Inbound]** och **[!UICONTROL Outbound]** och aktivera **[!UICONTROL Share associated cross-device IDs in people-based destinations]** alternativ.
1. Använd listrutan för att välja **[!UICONTROL Emails(SHA256, lowercased)]** -etikett för den här datakällan.

   >[!IMPORTANT]
   >
   >Med det här alternativet anges endast att datakällan innehåller data som har hash-kodats med den specifika algoritmen. Audience Manager hash-kodar inte data i det här steget. Kontrollera att de e-postadresser som du planerar att lagra i den här datakällan redan är hashas med [!DNL SHA256] algoritm. I annat fall kan du inte använda den för hashad e-postarbetsflöden.

   ![Audience Manager-gränssnittsbild som visar avsnittet med inställningar för datakälla.](../features/assets/data-source-settings.png)


