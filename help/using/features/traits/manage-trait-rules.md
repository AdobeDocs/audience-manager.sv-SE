---
description: I Trait Builder kan du med Expression Builder skapa och testa regler som fastställer krav för målgruppskvalifikation. Regler består av nyckelvärdepar som "color == blue" eller "price > 100". Jämförelseoperatorer upprättar relationen mellan nycklar och värden. Booleska uttryck bestämmer relationen mellan regelgrupper.
seo-description: I Trait Builder kan du med Expression Builder skapa och testa regler som fastställer krav för målgruppskvalifikation. Regler består av nyckelvärdepar som "color == blue" eller "price > 100". Jämförelseoperatorer upprättar relationen mellan nycklar och värden. Booleska uttryck bestämmer relationen mellan regelgrupper.
seo-title: Hantera trait-regler
solution: Audience Manager
title: Hantera trait-regler
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 1%

---


# Hantera trait-regler {#managing-trait-rules}

I [!UICONTROL Trait Builder]kan ni [!UICONTROL Expression Builder] skapa och testa regler som fastställer krav på målgruppskvalifikation. Regler består av nyckelvärdepar som `color == blue` eller `price > 100`. Jämförelseoperatorer upprättar relationen mellan nycklar och värden. [!DNL Boolean] uttryck bestämmer relationen mellan regelgrupper.

<!-- c_tb_rules.xml -->

## Funktioner för huvudsignalregler beskrivs

![](assets/manage-trait-rules.png)

1. På **[!UICONTROL Expression Builder]** - eller **[!UICONTROL Code View]** -flikarna visas en översikt över reglerna i ditt varumärke. På fliken **[!UICONTROL Expression Builder]** kan du skapa regler med fält och nedrullningsbara menyer. Med **[!UICONTROL Code View]** den här funktionen kan du skapa regler genom att skriva dessa uttryck manuellt som kod. Bilden ovan visar ett enkelt drag som består av en signal som utvärderar data för ett kvalificerande villkor där en produktnyckel är lika med ett visst värde, i det här fallet `color == "blue"`.

1. Med fälten och kontrollerna i det här avsnittet kan du skapa signaler från nyckelvärdepar och ange relationen mellan dem och en jämförelseoperator. Nyckel, operator och värde krävs.
1. Med den här funktionen kan du [!UICONTROL Data Explorer Options] fylla i trait-realisationer för dina signaler baklänges.
   >[!NOTE]
   >
   >Det här alternativet är endast tillgängligt för [!UICONTROL Data Explorer] kunder. Kontakta din Adobe-konsult för mer information.
1. I det här avsnittet visas en uppskattning av trait-realisationer för de senaste 7 dagarna, för de signaler som definieras i [!UICONTROL Expression Builder], för bakåtfyllda och icke-bakåtfyllda egenskaper.
   >[!NOTE]
   >
   >Det här alternativet är endast tillgängligt för [!UICONTROL Data Explorer] kunder. Kontakta din Adobe-konsult för mer information.
1. Med testfälten kan du validera kombinationer av signalregler eller de [!DNL URL]som du vill använda när du skickar data till Audience Manager.

## Skapa en svällningsregel {#create-trait-rule}

Regler (eller uttryck) består av enskilda eller grupper av nyckelvärdepar. Jämförelseoperatorer anger relationen mellan nyckelvärdepar. Om du vill skapa en regel anger du en nyckel, ett värde, väljer en operator och klickar på **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Fyll i de obligatoriska fälten i **[!UICONTROL Basic Information]** avsnittet *innan* du skapar anpassade regler.

1. Expandera **[!UICONTROL Trait Expression]** avsnittet och ange ett nyckel- och värdenamn. Detta skapar en *`signal`* bild.
   >[!NOTE]
   >
   >Inkludera `c_` prefixet (eller någon annan namnkonvention) för nyckelvariabeln om dina händelseanrop skickar data till [!DNL Audience Manager] med den syntaxen.
1. Välj en [jämförelseoperator](../../features/traits/trait-comparison-operators.md) i **[!UICONTROL Operator]** listrutan. Jämförelseoperatorn utvärderar relationen mellan elementen i en signal.
   >[!NOTE]
   >
   >Operatorn [!DNL Boolean][!UICONTROL OR] upprättar relationen mellan flera signaler *inom* en grupp och kan inte ändras.
1. Klicka på **[!UICONTROL Add Rule]**. Den sparade regeln visas på arbetsytan för egenskaper ovanför datainmatningsfälten.

### Exempel på {#example-trait-rule}

I exemplet nedan har en användare skapat en ny trait-regel baserat på produkt-ID:t. För att skapa den här regeln tillhandahöll användaren nyckeln `productkey` som är länkad med en likhetsoperator ( `==`) till värdet `2093`.
![](assets/tb_sample_rule1.png)

Om du klickar **[!UICONTROL Add Rule]** sparas och flyttas EGENSKAPEN till [!UICONTROL Expression Builder] arbetsytan.

![](assets/tb_sample_rule2.png)

## Skapa en ny regelgrupp {#create-rule-group}

I den här proceduren beskrivs hur du skapar en ny regelgrupp.

<!-- t_tb_new_rule_group.xml -->

Ditt varumärke måste innehålla minst två regler innan du kan skapa en ny regelgrupp.

1. Flytta markören över den regel du vill flytta för att markera den.
1. Hovra över den markerade regelkanten.
Då separeras regeln automatiskt från den aktuella gruppen och flyttas till en ny grupp.
   >[!NOTE]
   >
   >Dra tillbaka en regel till den ursprungliga gruppen om du vill flytta den oavsiktligt.
1. Välj en [!DNL Boolean] operator ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) i listrutan för att ange relationen mellan regelgrupperna.

## Flytta regler mellan grupper {#move-rules-between-groups}

Om du vill flytta en regel klickar du på den och drar den till en annan grupp.

## Redigera ett spår {#edit-trait}

I den här proceduren beskrivs hur du redigerar en egenskap.

<!-- t_tb_edit.xml -->

1. Håll markören över kolumnen för den egenskap som du vill redigera på [!UICONTROL Traits] kontrollpanelen **[!UICONTROL Actions]** . Detta öppnar upp ikonerna för trait-hantering.
1. Klicka på pennan för att redigera tecknet.

   ![](assets/tb_edit_trait.png)

## Ta bort en dragningsregel {#delete-trait}

I den här proceduren beskrivs hur du tar bort en trait-regel.

<!-- t_tb_delete_rule.xml -->

1. Håll markören över kolumnerna för den egenskap du vill redigera på [!UICONTROL Traits] [!UICONTROL Actions] kontrollpanelen och klicka på pennikonen. Detta öppnar upp ikonerna för trait-hantering.
1. Expandera avsnittet [!UICONTROL Trait Expression].
1. Håll pekaren över den linje som du vill ta bort och klicka på X-ikonen. Regeln tas bort omedelbart.

>[!MORELIKETHIS]
>
>* [Skapa en ny regelgrupp](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Flytta regler mellan grupper](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Skapa en svällningsregel](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Ta bort en dragningsregel](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Flytta regler mellan grupper](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

