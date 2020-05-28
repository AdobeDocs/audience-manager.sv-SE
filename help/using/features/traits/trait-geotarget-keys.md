---
description: Beskriver de vanliga nyckelvärdepar på plattformsnivå som du kan använda för att rikta in användare med geografiska variabler i alla egenskaper i ditt Audience Manager-konto.
seo-description: Beskriver de vanliga nyckelvärdepar på plattformsnivå som du kan använda för att rikta in användare med geografiska variabler i alla egenskaper i ditt Audience Manager-konto.
seo-title: Geogeting med tangenter på plattformsnivå
solution: Audience Manager
title: Geogeting med tangenter på plattformsnivå
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
translation-type: tm+mt
source-git-commit: 8959e0023f7663d7a20080aaf130d469ed8a4313
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# Geogeting med tangenter på plattformsnivå {#geotargeting-with-platform-level-keys}

Beskriver de vanliga nyckelvärdepar på plattformsnivå som du kan använda för att rikta in användare med geografiska variabler i alla egenskaper i ditt Audience Manager-konto.

<!-- c_tb_platform_vars.xml -->

## Syfte med variabler på plattformsnivå {#platform-variables}

Med plattformsnivåvariabler kan ni ta data som skickas från en viss webbplats och göra dem tillgängliga för målinriktning i alla egenskaper i ert [!DNL Audience Manager] konto. Variablerna formateras med [nyckelvärdepar](../../reference/key-value-pairs-explained.md) med nyckeln som prefixeras av `d_` enligt nedan.

## Lägga till värden i plattformsnivånycklar {#adding-values}

För vissa tangenter på plattformsnivå kan du ange värdet själv. Med andra kopplas nycklarna till motsvarande [!DNL IP] adresser som skickas i ett händelseanrop. I båda fallen måste du fortfarande ange värdet när du skapar egenskaper i [!UICONTROL Trait Builder].

## Användardefinierade tangenter på plattformsnivå {#user-defined-keys}

Du anger värdet när du skapar egenskaper med dessa nyckelvärdepar:

| Nyckel | För målinriktning |
|---|---|
| `d_zx` | Postnummer (t.ex. `d_zx=10022`). |

## Tangenter på plattformsnivå definierade av IP-adress {#keys-ip-address}

Vi arbetar med [Digital Envoy](https://www.digitalenvoy.com/) för att få och uppdatera demografiska och geografiska data för nycklarna nedan. Värdena för de här nycklarna bestäms av matchande [!DNL IP] adresser till motsvarande geografiska och demografiska data. Du måste dock fortfarande ange parametern value när du skapar nyckelvärdepar i [!UICONTROL Trait Builder].

| Nyckel | För målinriktning |
|--- |--- |
| d_area_code | [Nordamerika riktnummer](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Exempel: <ul><li>**Fack**:  d_area_code=801</li><li>**Trait Name**: Utah</li></ul> |
| _Ort | Städer och städer. Ladda ned [stadslistan](assets/d_city.txt).  Exempel: <ul><li>Fack:  d_city=bonn</li><li>Trait Name: Bonn</li></ul> **Tips**: Du kan använda `d_city` tillsammans med för `d_country` att vara säker på att du inte riktar in dig på två städer med samma namn i olika länder. Ni kan vara ännu mer specifika när det gäller er målinriktning genom att använda `d_postal_code`. |
| d_country | Värdena motsvarar ISO-landskoder. En sökbar lista med koder finns i [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>  Det enda specialfall som inte följer ISO 3166 är inriktat på Förenade kungariket. Du bör använda&quot;UK&quot; i stället för&quot;GB&quot; för målinriktning i Storbritannien.  För att rikta sig till Nederländska Antillerna har koden&quot;AN&quot; tagits bort sedan 2010. Området har upplösts till fem separata territoriella enheter. Konsekvensen är att ni inte bör använda&quot;AN&quot; för målinriktning i Nederländska Antillerna, utan en kombination av landskoderna för&quot;CW&quot;,&quot;SX&quot; och&quot;BQ&quot;.  Till exempel:  <br>  Fack:  d_country=CZ <br>Trait Name: Tjeckien <br>Trait:  d_country=UK <br>Trait Name: United Kingdom <br>Trait:  d_country=CW OR d_country=SX OR d_country=BQ <br>Trait Name: Nederländska Antillerna |
| d_dma_code | Metropolitan area DMA codes. Hämta [DMA-regionlistan](assets/DMAregions.csv) (.csv-format).  Exempel: <ul><li>Fack:  d_dma_code=807</li><li>Trait Name: San Francisco</li></ul> |
| d_lat | Latitud (t.ex. d_lat=40.75). Ladda ned [latitudlistan](assets/d_lat.txt). |
| d_long | Longitud (t.ex. d_long=73.98). Ladda ned [longitudlistan](assets/d_long.txt). |
| d_mail_code | Postnummer (utelämna den utökade +4-koden). Ladda ned [postkodslistan](assets/d_postal_code.txt).  Exempel: <ul><li>Fack:  d_mail_code=84004 </li><li>Trait Name: Alfa</li></ul> |
| d_state | Förkortning med två tecken för ett amerikanskt läge. Hämta [tillståndskodlistan](assets/d_state.txt).  Exempel: <ul><li>Fack:  d_state=NY </li><li>Trait Name: New York</li></ul>d_state innehåller upprepade värden för olika lägen i olika länder. d_state == &quot;on&quot; matchar flera lägen: Ontario (i Kanada), Ondo (i Nigeria), Oshana (i Namibia). Vi rekommenderar att du kopplar den här signalen med andra som d_country för mer specifik geolokalisering. |
| d_region | Regionala alfanumeriska ID:n. Hämta [regionlistan](assets/Country_RegionCodes_City.csv).  Sedan kan du använda den här listan för att matcha region-ID:n med regionnamn. |
| d_isp | Internetleverantör/organisation. Ladda ned [ISP-listan](assets/d_isp.txt). |

Förteckningen över [alla platsbaserade signaler](assets/all.txt) omfattar alla signaler ovan, i följande ordning: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Prefixkrav för nyckelvariabler](../../features/traits/trait-variable-prefixes.md)

