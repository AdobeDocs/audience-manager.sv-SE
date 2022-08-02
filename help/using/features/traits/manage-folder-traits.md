---
description: Skapa, redigera och ta bort mappegenskaper.
keywords: Mappegenskaper;Mappegenskaper;mappegenskaper;mappegenskaper
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: Hantera mapp-traits
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: f7a4478589f4af1d467f1045a97dbb7f5cd6f9e5
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 5%

---

# Hantera mapp-traits {#manage-folder-traits}

Skapa, redigera och ta bort mappegenskaper.

## Skapa en mappegenskap {#create-folder-trait}

A [!UICONTROL folder trait] skapas automatiskt när du skapar en ny mapp i din taxonomi.

<!-- create-folder-trait.xml -->

1. Gå till **[!UICONTROL Audience Data > Traits]** för att navigera till **Traits** kontrollpanel.
1. I [!UICONTROL Trait Storage] fönster, hovra över:

   * &quot;All Traits&quot; om du vill lägga till en ny rotnivåmapp.
   * En befintlig överordnad mapp som lägger till en ny underordnad mapp.

   ![](assets/folder_traits_create.PNG)

1. Klicka på ikonen + för att skapa mappen. Observera att du kan skapa högst 2 000 mappar i din taxonomi. Mer information finns i dokumentationen om [användningsbegränsningar](../../features/administration/usage-limits.md).
1. Namnge mappen och klicka på **Spara**. En mapp med namnet Electronics kommer till exempel att ha en mappegenskap med namnet &quot;Electronics Folder Trait&quot;. Du kan visa och välja den nya mappegenskapen på kontrollpanelen för egenskaper.
1. Det nya mappfältet tilldelas automatiskt till [!DNL Audience Manager] genererad datakälla. Dina användare med lämplig [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) kan ändra datakällan i arbetsflödet för redigering av mappegenskaper. Se [Redigera en mappegenskap](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Redigera en mappegenskap {#edit-folder-trait}

Beskriver hur du kan redigera en [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. I [!UICONTROL Traits] kontrollpanel, hovra över **[!UICONTROL Actions]** -kolumnen för mappegenskapen som du vill redigera.
1. Klicka på pennan för att redigera tecknet.

   ![](assets/folder_traits_edit_border.png)

1. The **[!UICONTROL Edit]** arbetsflödet gör att du kan ändra datakällan för mappegenskaper. Välj önskad datakälla och klicka på **[!UICONTROL Save]**. Datakällor sorteras numeriskt efter [!DNL DPID]i listrutan.

   Om ditt företag använder [!UICONTROL Role-Based Access Rights (RBAC)], du eller dina användare behöver [åtkomstbehörigheter](../../features/traits/about-folder-traits.md#role-based-access-controls) för att anpassa datakällor.

>[!NOTE]
>
>Du kan inte byta namn direkt på en mappegenskap. [Byt namn på den associerade lagringsmappen](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) om du vill ändra namnet på mappens egenskaper.

## Ta bort en mappegenskap {#delete-folder-trait}

Ta bort en mappegenskap genom att ta bort den lagringsmapp som egenskapen tillhör.

<!-- delete-folder-trait.xml -->

1. **Målgruppsdata > Traits** för att navigera till **Traits** kontrollpanel.
1. I [!UICONTROL Trait Storage] tar du bort en mapp genom att hålla markören över den och klicka på X-ikonen.

   ![Stegresultat](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Du kan inte ta bort en mappegenskap om den används i ett segmentuttryck. Navigera till [trait view](../../features/traits/trait-details-page.md) för att se vilka segment som använder mappegenskapen. Klicka sedan på segmentnamnet för att öppna [segmentsammanfattningsvy](../../features/segments/segment-summary-view.md), som gör att du kan ta bort egenskaper från segmentuttryck.
