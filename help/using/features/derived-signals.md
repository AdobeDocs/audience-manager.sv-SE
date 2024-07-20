---
description: En härledd signal kvalificerar besökare för ytterligare egenskaper baserat på det förlopp de redan har sett. Med andra ord kan ytterligare egenskaper härledas från en egenskap som för närvarande visas, även om en användare aldrig har sett den nya egenskapen tidigare.
seo-description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-title: Derived Signals
solution: Audience Manager
title: Härledda signaler
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Härledda signaler {#derived-signals}

En/ett [!UICONTROL derived signal] kvalificerar webbplatsbesökare för ytterligare egenskaper baserat på en egenskap som de redan har sett. Med andra ord kan ytterligare egenskaper härledas från en egenskap som för närvarande visas, även om en användare aldrig har sett den nya egenskapen tidigare.

<!-- c_tb_derived_signal.xml -->

## Syfte med härledda signaler

I [!DNL Audience Manager] kan du skapa en relation mellan signaler (eller trait-regler) som skickas under ett händelseanrop till andra, angivna signaler eller egenskaper. Anta till exempel att ett händelseanrop skickas i en signal som består av nyckelvärdet [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] ansluter signalen till alla andra som har skapats med verktyget [!UICONTROL derived signals]. Även om de associerade signalerna kan vara valfria nyckelvärden som du anger, är de mest användbara när de länkas till befintliga signaler som redan konfigurerats som [!UICONTROL Trait Builder]-regler. I bilden nedan kan du till exempel se att när en användaråtgärd utlöser signalen [!DNL "product = new car"] kan användaren även kvalificera sig för egenskaper som definieras av målnyckeln och värdesignalerna.

![](assets/derived_signal_example.png)

## Plats för härledda signaler

Skapa och hantera [!UICONTROL derived signals] i **[!UICONTROL Tools > Derived Signals]** från sidofältsnavigeringen.

## Skapa en härledd signal {#create}

<!-- t_tb_create_derived.xml -->

Så här skapar du en [!UICONTROL derived signal]:

1. Välj **[!UICONTROL Derived Signals]** på menyn [!UICONTROL Tools].
1. Ange en:
   * *(Valfritt)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Klicka på **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>Teckengränsen för fälten [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key] och [!UICONTROL Target Value] är 228 tecken.

## Redigera en härledd signal {#edit}

<!-- t_tb_edit_derived.xml -->

Så här redigerar du en [!UICONTROL derived signal]:

1. Hovra över signalen och klicka sedan på **[!UICONTROL Edit]**.
2. Gör önskade ändringar av kod, nyckel eller värde och klicka sedan på **[!UICONTROL Save]**.

## Ta bort en härledd signal {#delete}

<!-- t_tb_delete_derived.xml -->

Om du vill ta bort [!UICONTROL derived signal] håller du pekaren över signalen och klickar sedan på **[!UICONTROL Delete]**.
