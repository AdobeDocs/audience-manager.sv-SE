---
description: Skapa, redigera och ta bort mappegenskaper.
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: Skapa, redigera och ta bort mappegenskaper.
seo-title: Hantera mapp-traits
solution: Audience Manager
title: Hantera mapp-traits
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
translation-type: tm+mt
source-git-commit: 4ea5ba4ebd8cd4c13c99c8272f4b5733ab5fa125
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 9%

---


# Hantera mapp-traits {#manage-folder-traits}

Skapa, redigera och ta bort mappegenskaper.

## Skapa en mappegenskap {#create-folder-trait}

En mapp [!UICONTROL folder trait] skapas automatiskt när du skapar en ny mapp i din taxonomi.

<!-- create-folder-trait.xml -->

1. Gå **[!UICONTROL Audience Data > Traits]** till kontrollpanelen **Traits** .
1. Håll markören över i [!UICONTROL Trait Storage] fönstret:

   * &quot;All Traits&quot; om du vill lägga till en ny rotnivåmapp.
   * En befintlig överordnad mapp som lägger till en ny underordnad mapp.

   ![](assets/folder_traits_create.PNG)

1. Klicka på ikonen + för att skapa mappen. Tänk på att du kan skapa högst 2 000 mappar i taxonomin. Mer information finns i dokumentationen om [användningsbegränsningar](../../features/administration/usage-limits.md).
1. Namnge mappen och klicka på **Spara**. En mapp med namnet Electronics kommer till exempel att ha en mappegenskap med namnet &quot;Electronics Folder Trait&quot;. Du kan visa och välja den nya mappegenskapen på kontrollpanelen för egenskaper.
1. Det nya mappfältet tilldelas automatiskt till den [!DNL Audience Manager] genererade datakällan. Dina användare med rätt [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) behörighet kan ändra datakällan i arbetsflödet för redigeringsmappens egenskaper. Se [Redigera en mappstruktur](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Redigera en mappegenskap {#edit-folder-trait}

Beskriver hur du kan redigera en [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. Håll markören över kolumnen för den mappegenskap som du vill redigera på [!UICONTROL Traits] kontrollpanelen **[!UICONTROL Actions]** .
1. Klicka på pennan för att redigera tecknet.

   ![](assets/folder_traits_edit_border.png)

1. Med hjälp av arbetsflödet kan du ändra datakällan för mappegenskaper. **[!UICONTROL Edit]** Välj önskad datakälla och klicka på **[!UICONTROL Save]**. Datakällor sorteras numeriskt efter [!DNL DPID]i listrutan.

   Om ditt företag använder [!UICONTROL Role-Based Access Rights (RBAC)]måste du eller dina användare ha [åtkomstbehörighet](../../features/traits/about-folder-traits.md#role-based-access-controls) för att kunna anpassa datakällor.

>[!NOTE]
>
>Du kan inte byta namn direkt på en mappegenskap. [Byt namn på den associerade lagringsmappen](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) för att ändra namnet på mappens egenskaper.

## Ta bort en mappegenskap {#delete-folder-trait}

Ta bort en mappegenskap genom att ta bort den lagringsmapp som egenskapen tillhör.

<!-- delete-folder-trait.xml -->

1. **Målgruppsdata > Traits** för att navigera till kontrollpanelen **Traits** .
1. I [!UICONTROL Trait Storage] fönstret tar du bort en mapp genom att hålla markören över den och klicka på X-ikonen.

   ![Stegresultat](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Du kan inte ta bort en mappegenskap om den används i ett segmentuttryck. Navigera till avsnittet [Vyn](../../features/traits/trait-details-page.md) för att se vilka segment som använder mappegenskapen. Klicka sedan på segmentnamnet för att öppna [segmentsammanfattningsvyn](../../features/segments/segment-summary-view.md), där du kan ta bort egenskaper från segmentuttryck.
