---
title: Konfigurera en datakälla för hash-kodade e-postarbetsflöden
description: Lär dig hur du skapar en datakälla för att lagra hash-kodade e-postmeddelanden för hash-kodade e-postarbetsflöden.
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
source-git-commit: d55dbc4f9630e3d22dfb988f6725f33993229c48
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Konfigurera en datakälla för hash-kodade e-postarbetsflöden

Hash-kodade e-postarbetsflöden, t.ex. personbaserade mål, kräver att du skapar en datakälla för att lagra de hashkodade e-postadresserna.

Följ stegen nedan för att skapa och konfigurera en datakälla för hashad e-post.

1. Logga in på ditt Audience Manager-konto, gå till **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** och klicka på **[!UICONTROL Add New]**.
1. Ange **[!UICONTROL Name]** och **[!UICONTROL Description]** som ny datakälla.
1. Välj **[!UICONTROL ID Type]** i listrutan **[!UICONTROL Cross Device]**.
   ![Audience Manager-gränssnittsbild som visar avsnittet med information om datakällan.](../features/assets/create-hashed-email-data-source.png)
1. I avsnittet **[!UICONTROL Data Source Settings]** markerar du både alternativen **[!UICONTROL Inbound]** och **[!UICONTROL Outbound]** och aktiverar alternativet **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Använd listrutan för att välja etiketten **[!UICONTROL Emails(SHA256, lowercased)]** för den här datakällan.

   >[!IMPORTANT]
   >
   >Med det här alternativet anges endast att datakällan innehåller data som har hash-kodats med den specifika algoritmen. Audience Manager hash-kodar inte data i det här steget. Kontrollera att e-postadresserna som du planerar att lagra i den här datakällan redan har hash-kodats med algoritmen [!DNL SHA256]. I annat fall kan du inte använda den för hashad e-postarbetsflöden.

   ![Audience Manager-gränssnittsbild som visar avsnittet med inställningar för datakälla.](../features/assets/data-source-settings.png)
