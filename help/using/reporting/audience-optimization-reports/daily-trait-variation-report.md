---
description: Den här rapporten returnerar en lista över egenskaper som har realiserats minst 10 000 gånger under de 30 dagarna före det valda datumet/datumen och som har en standardavvikelse som är större eller lika med 1,7 i båda riktningarna under samma tidsintervall. Rapporten hjälper er att utvärdera hur antalet visningar från unika användare i en egenskap varierar över tiden.
seo-description: Den här rapporten returnerar en lista över egenskaper som har realiserats minst 10 000 gånger under de 30 dagarna före det valda datumet/datumen och som har en standardavvikelse som är större eller lika med 1,7 i båda riktningarna under samma tidsintervall. Rapporten hjälper er att utvärdera hur antalet visningar från unika användare i en egenskap varierar över tiden.
seo-title: Daglig rapport över trait-variationer
solution: Audience Manager
title: Daglig rapport över trait-variationer
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---


# Daglig rapport över trait-variationer {#daily-trait-variation-report}

Den här rapporten returnerar en lista över egenskaper som har realiserats minst 10 000 gånger under de 30 dagarna före det valda datumet/datumen och som har en standardavvikelse som är större eller lika med 1,7 i båda riktningarna under samma tidsintervall. Rapporten hjälper er att utvärdera hur antalet visningar från unika användare i en egenskap varierar över tiden.

>[!NOTE]
>
>Rapporten Daily Trait Variation i Audience Manager följer RBAC-principerna. Du kan bara se egenskaper från datakällor som du har åtkomst till baserat på [RBAC-användargruppen](/help/using/features/administration/administration-overview.md) som du tillhör.

Standardavvikelsen mäter mängden variation eller spridning från medelvärdet (eller genomsnittligt/förväntat värde). En låg standardavvikelse indikerar att datapunkterna tenderar att vara mycket nära medelvärdet. En hög standardavvikelse anger att datapunkterna är spridda över ett stort värdeintervall.

![](assets/daily_trait_variation.png)

Använd listan [!UICONTROL Date] för att välja ett eller flera datum för rapporten. Ett färgkodat stapeldiagram visas längst ned i listan som ger en visuell representation av intervallet för standardavvikelsen för alla egenskaper för alla valda datum. Den svarta lodräta linjen anger medelvärdet.

Mittkolumnen innehåller en lista med egenskaper som identifieras av [!UICONTROL Trait ID] och [!UICONTROL Trait Name]. Klicka på ett spår för att öppna en popup-dialogruta där du kan välja bland följande alternativ:

* **Behåll endast:** Tar bort alla andra egenskaper från rapporten och visar endast data för den här egenskapen.
* **Exkludera:** Tar bort den här egenskapen från rapporten och visar data för alla andra egenskaper. Du kan utesluta flera egenskaper.
* **Visa data:** Här kan du visa data för den raden. Du kan även hämta alla rader som en textfil.

Kolumnen [!UICONTROL Standard Deviation] visar färgkodade stapeldiagram som visar standardavvikelsen för varje egenskap under det valda intervallet. Röda fält anger egenskaper med en negativ standardavvikelse (datapunkterna tenderar att vara under medelvärdet). Gröna fält anger egenskaper med en positiv standardavvikelse (datapunkterna tenderar att ligga över medelvärdet). Om du för musen över ett fält visas en popup-dialogruta med mer information och alternativ för att behålla eller exkludera den egenskapen och visa mer information.

Ikoner visas längst ned i rapporten, där du kan exportera data i olika format, återställa ändringar som du har gjort i rapporten (t.ex. utelämna egenskaper), aktivera eller inaktivera automatiska uppdateringar och uppdatera rapportens data. Se [Ikoner och verktyg för rapport](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Använd fall {#use-cases}

**Exempel 1**: den här rapporten kan vara mycket användbar i situationer där du har egenskaper med hög säsongsnivå. Anta att din webbutik testar säsongskampanjer av olika typer och priser. Följande egenskaper har definierats i [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Anta att du kör [!UICONTROL Daily Trait Variation]-rapporten den 20 december och du märker en positiv avvikelse för ovanstående egenskaper under de senaste 30 dagarna. Detta kan tyda på att besökarna letar efter de produkter som nämns i din säsongskampanj. Om ni vill dra nytta av den här trenden kan ni sedan satsa mer på att rikta in er på kreatörer för just den produktkategorin på besökare som är intresserade av dem.

**Exempel 2**: den här rapporten kan hjälpa dig att identifiera målavvikelser relaterade till taggningsproblem eller felaktiga egenskaper. Tänk dig att du har definierat följande egenskaper baserat på kategorierna i din onlinebutik:

* `productPage == "smartphones"`

På grund av en omkonfiguration av din butik delar du upp smarttelefonsidan i flera sidor, baserat på varumärkesnamn. Du glömmer dock att uppdatera de egenskaper som definierats i [!DNL Audience Manager].

En månad senare kör du [!UICONTROL Daily Trait Variation]-rapporten och märker en stor negativ avvikelse på `productPage == "smartphones"`-egenskapen, även om besökarnumret har ökat enligt webbplatsanalysen. Baserat på den här informationen inser du att du inte har uppdaterat egenskaperna i [!DNL Audience Manager] för dina nya produktsidor, så du vet att du måste skapa följande egenskaper:

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

När du gjort det ser du att din målgrupp är berättigad till de nya egenskaperna.
