---
description: Formatera innehållet i metadatafilen för målgruppsoptimering enligt dessa specifikationer.
seo-description: Formatera innehållet i metadatafilen för målgruppsoptimering enligt dessa specifikationer.
seo-title: Innehållsformat för metadatafiler
solution: Audience Manager
title: Innehållsformat för metadatafiler
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---


# Innehållsformat för metadatafiler{#content-format-for-metadata-files}

Formatera innehållet i metadatafilen för målgruppsoptimering enligt dessa specifikationer.

## Syntax {#syntax}

Följande syntax definierar strukturen för välformaterat innehåll i en metadatafil. Obs! *Kursiv* anger en variabelplatshållare.

**Syntax:**  *innehålls-ID* | *namn* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

Den tredje kolumnen **-1** är tekniskt sett överordnat ID, som är ett äldre fält. Värdet ska alltid anges som **-1**.

>[!NOTE]
>
>Observera att en metadatafil per dimension behövs, så att flera metadatafiler förväntas i haken. Dimensionerna listas i artikeln [Namngivningskonventioner för metadatafil](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Separata filposter med ^a (kontroll-A eller ASCII 001)**

Använd `^a` (control-A eller ASCII 001) för att separera innehåll i metadatafilerna. Eftersom det här är tecken som inte skrivs ut visas ett vertikalstreck (|) endast i visningssyfte i syntaxexemplet ovan.

Vid behov kan du hämta exempelfilen - [20181105_0_1](assets/20181105_0_1.zip). Zippa upp den och redigera den i valfri redigerare och justera den efter det faktiska metadatainnehållet eftersom den redan innehåller den avgränsare som krävs.

>[!IMPORTANT]
>
>Lägg inte till rubrikrader i metadatafiler.

## Exempel {#examples}

Låt oss titta på hur du strukturerar innehåll i en metadatafil. En del av den här strukturen beror på dimensionen. Dimensionerna listas i artikeln [Namngivningskonventioner för metadatafil](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

I det här exemplet är filtiteln 20180921_0_1 och de tre kolumnerna i filen är: Kampanj-ID, namn och överordnat ID.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Kreativ**

I det här exemplet är filtiteln 20180827_0_2 och de tre kolumnerna i filen är: Creative ID, Name och Parent ID.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Plats**

I det här exemplet är filtiteln 20180921_0_5 och de tre kolumnerna i filen är: Plats-ID, namn och överordnat ID.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
