---
description: Beskriver de vanliga nyckelvärdepar på plattformsnivå som du kan använda för att rikta in användare med geografiska variabler i alla egenskaper i ditt Audience Manager-konto.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting med tangenter på plattformsnivå
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 2de7aba53e3c88d31270f2acb4fa29389f940312
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# Geotargeting med tangenter på plattformsnivå {#geotargeting-with-platform-level-keys}

Beskriver de vanliga nyckelvärdepar på plattformsnivå som du kan använda för att rikta in användare med geografiska variabler i alla egenskaper i ditt Audience Manager-konto.

<!-- c_tb_platform_vars.xml -->

## Syfte med variabler på plattformsnivå {#platform-variables}

Med plattformsnivåvariabler kan du ta data som skickas från en viss webbplats och göra dem tillgängliga för målinriktning för alla egenskaper i ditt [!DNL Audience Manager]-konto. Variablerna är formade med [nyckel/värde-par](../../reference/key-value-pairs-explained.md) med nyckeln prefix av `d_` enligt nedan.

## Lägga till värden i tangenter på plattformsnivå {#adding-values}

För vissa tangenter på plattformsnivå kan du ange värdet själv. Med andra är nycklarna associerade med motsvarande [!DNL IP] adresser som skickats i ett händelseanrop. I båda fallen måste du fortfarande ange värdet när du skapar egenskaper i [!UICONTROL Trait Builder].

## Användardefinierade tangenter på plattformsnivå {#user-defined-keys}

Om du redan har, eller skapar, en process för att definiera och samla in nyckelvärdepar, ska du använda det här alternativet. Om du vill använda nycklar som är fördefinierade av IP-adressen fortsätter du till nästa avsnitt. När det gäller användardefinierade tangenter anger du värdet när du skapar egenskaper med dessa nyckelvärdepar:

| Nyckel | För målinriktning |
|---|---|
| `d_zx` | Postnummer (t.ex. `d_zx=10022`). |

## Tangenter på plattformsnivå definierade av IP-adress {#keys-ip-address}

Vi arbetar med [Digital Envoy](https://www.digitalenvoy.com/) för att hämta och uppdatera demografiska och geografiska data för nycklarna nedan. Värdena för de här nycklarna bestäms genom att matcha [!DNL IP] adresser med motsvarande geografiska och demografiska data. Du måste dock fortfarande ange parametern value när du skapar nyckelvärdepar i [!UICONTROL Trait Builder].

| Nyckel | För målinriktning |
|--- |--- |
| d_area_code | [Nordamerika riktnummer](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Exempel: <ul><li>**Trait**: d_area_code=801</li><li>**Trait Name**: Utah</li></ul> |
| _Ort | Städer och städer. Hämta listan [orter](assets/d_city.txt).  Exempel: <ul><li>Trait: d_city=bonn</li><li>Trait Name: Bonn</li></ul> **Tips**: Du kan använda `d_city` i kombination med `d_country` för att vara säker på att du inte anger två städer med samma namn i olika länder som mål. Du kan vara ännu mer specifik i din målinriktning genom att använda `d_postal_code`. |
| d_country | Värdena motsvarar ISO-landskoder. En sökbar lista med koder finns i [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>  Det enda specialfall som inte följer ISO 3166 är inriktat på Förenade kungariket. Du bör använda&quot;UK&quot; i stället för&quot;GB&quot; för målinriktning i Storbritannien.  För att rikta sig till Nederländska Antillerna har koden&quot;AN&quot; tagits bort sedan 2010. Området har upplösts till fem separata territoriella enheter. Konsekvensen är att ni inte bör använda AN för målinriktning i Nederländska Antillerna, utan en kombination av landskoderna för CW, SX och BQ.  Till exempel: <br>  Trait: d_country=CZ <br>  Trait Name: Czech Republic <br>  Trait: d_country=UK <br>  Trait Name: United Kingdom <br>  Trait: d_country=CW OR d_country=SX OR d_country=BQ <br>  Trait Name: Nederländska Antillerna |
| d_dma_code | Metropolitan area DMA codes. Hämta [DMA-regionlistan](assets/DMAregions.csv) (.csv-format).  Exempel: <ul><li>Trait: d_dma_code=807</li><li>Trait Name: San Francisco</li></ul> |
| d_lat | Latitud (t.ex. d_lat=40.75). Hämta [latitudlistan](assets/d_lat.txt). |
| d_long | Longitud (t.ex. d_long=73.98). Hämta [longitudlistan](assets/d_long.txt). |
| d_mail_code | Postnummer (utelämna den utökade +4-koden). Hämta listan [med postnummer](assets/d_postal_code.txt).  Exempel: <ul><li>Trait: d_mail_code=84004 </li><li>Trait Name: Alpine</li></ul> |
| d_state | Förkortning med två tecken för ett amerikanskt läge. Hämta [lägeskodslistan](assets/d_state.txt).  Exempel: <ul><li>Trait: d_state=NY </li><li>Trait Name: New York</li></ul>d_state innehåller upprepade värden för olika lägen i olika länder. d_state ==&quot;on&quot; matchar flera lägen: Ontario (i Kanada), Ondo (i Nigeria), Oshana (i Namibia). Vi rekommenderar att du kopplar den här signalen med andra som d_country för mer specifik geolokalisering. |
| d_region | Regionalt alfanumeriskt ID. Hämta [regionlistan](assets/Country_RegionCodes_City.csv).  Sedan kan du använda den här listan för att matcha region-ID:n med regionnamn. |
| d_isp | Internetleverantör/organisation. Hämta [ISP-listan](assets/d_isp.txt). |

Listan med [alla platsbaserade signaler](assets/all.txt) innehåller alla signaler ovan, i följande ordning: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Prefixkrav för nyckelvariabler](../../features/traits/trait-variable-prefixes.md)

