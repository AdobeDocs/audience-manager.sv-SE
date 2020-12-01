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

En [!UICONTROL folder trait] skapas automatiskt när du skapar en ny mapp i taxonomin.

<!-- create-folder-trait.xml -->

1. Gå till **[!UICONTROL Audience Data > Traits]** för att navigera till kontrollpanelen **Traits**.
1. Håll muspekaren över i fönstret [!UICONTROL Trait Storage]:

   * &quot;All Traits&quot; om du vill lägga till en ny rotnivåmapp.
   * En befintlig överordnad mapp som lägger till en ny underordnad mapp.

   ![](assets/folder_traits_create.PNG)

1. Klicka på ikonen + för att skapa mappen. Tänk på att du kan skapa högst 2 000 mappar i taxonomin. Mer information finns i dokumentationen om [användningsbegränsningar](../../features/administration/usage-limits.md).
1. Namnge mappen och klicka på **Spara**. En mapp med namnet Electronics kommer till exempel att ha en mappegenskap med namnet &quot;Electronics Folder Trait&quot;. Du kan visa och välja den nya mappegenskapen på kontrollpanelen för egenskaper.
1. Det nya mappfältet tilldelas automatiskt till den [!DNL Audience Manager]-genererade datakällan. Dina användare med lämpliga [!UICONTROL Role-Based Access Control]-behörigheter ([!DNL RBAC]) kan ändra datakällan i arbetsflödet för redigeringsmappens egenskaper. Se [Redigera en mappstruktur](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Redigera en mappegenskap {#edit-folder-trait}

Beskriver hur du kan redigera en [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. Håll markören över kolumnen **[!UICONTROL Actions]** på kontrollpanelen [!UICONTROL Traits] för mappegenskapen som du vill redigera.
1. Klicka på pennan för att redigera tecknet.

   ![](assets/folder_traits_edit_border.png)

1. Med arbetsflödet **[!UICONTROL Edit]** kan du ändra datakällan för mappegenskaper. Välj önskad datakälla och klicka på **[!UICONTROL Save]**. Datakällor sorteras numeriskt med [!DNL DPID] i listrutan.

   Om ditt företag använder [!UICONTROL Role-Based Access Rights (RBAC)] behöver du eller dina användare [åtkomstbehörighet](../../features/traits/about-folder-traits.md#role-based-access-controls) för att kunna anpassa datakällor.

>[!NOTE]
>
>Du kan inte byta namn direkt på en mappegenskap. [Byt namn på den associerade ](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) lagringsmappen för att ändra namnet på mappens egenskaper.

## Ta bort en mappegenskap {#delete-folder-trait}

Ta bort en mappegenskap genom att ta bort den lagringsmapp som egenskapen tillhör.

<!-- delete-folder-trait.xml -->

1. **Audience Data >** Traitstys för att navigera till  **** Traitsdashboard.
1. I fönstret [!UICONTROL Trait Storage] tar du bort en mapp genom att hålla markören över den och klicka på X-ikonen.

   ![Stegresultat](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Du kan inte ta bort en mappegenskap om den används i ett segmentuttryck. Navigera till avsnittet [trait view](../../features/traits/trait-details-page.md) för att se vilka segment som använder mappegenskapen. Klicka sedan på segmentnamnet för att öppna den [segmentsammanfattningsvyn](../../features/segments/segment-summary-view.md) där du kan ta bort egenskaper från segmentuttryck.
