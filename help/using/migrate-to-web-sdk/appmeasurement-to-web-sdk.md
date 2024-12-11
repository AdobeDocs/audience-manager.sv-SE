---
title: Uppdatera ditt datainsamlingsbibliotek för Audience Manager från AppMeasurement JavaScript-biblioteket till Web SDK JavaScript-biblioteket.
description: Lär dig hur du uppdaterar ditt datainsamlingsbibliotek för Audience Manager från AppMeasurement JavaScript-biblioteket till Web SDK JavaScript-biblioteket.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: 3ba980e97763866d82bdf94109068f1f1f8f63d2
workflow-type: tm+mt
source-wordcount: '2398'
ht-degree: 0%

---


# Uppdatera ditt datainsamlingsbibliotek för Audience Manager från AppMeasurement JavaScript-biblioteket till Web SDK JavaScript-biblioteket

## Målgrupp {#intended-audience}

Den här sidan är till för Audience Manager och Adobe Analytics-kunder som använder JavaScript-biblioteket [!DNL AppMeasurement] för att skicka webbdata till Audience Manager.

I tabellen nedan finns anvisningar om hur du migrerar till Web SDK, beroende på vilken datainsamlingsmetod du använder.

| Din befintliga datainsamlingsmetod | Instruktioner för Web SDK-migrering |
|---------|----------|
| JavaScript-bibliotek för [!DNL AppMeasurement] | Följ instruktionerna i den här handboken. |
| [!DNL Audience Manager] [taggtillägg](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Följ anvisningarna i [Uppdatera ditt datainsamlingsbibliotek från taggtillägget Audience Manager till Web SDK-taggtillägget](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] JavaScript-bibliotek + [!DNL Audience Manager] [DIL-bibliotek](../dil/dil-overview.md) | Följ anvisningarna i [Uppdatera ditt datainsamlingsbibliotek från taggtillägget Audience Manager till Web SDK-taggtillägget](dil-extension-to-web-sdk.md). |

## Migreringsöversikt {#overview}

Migrering från [!DNL AppMeasurement] till [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) är i första hand en Adobe Analytics-migrering. För Audience Manager-kunder omfattar migreringen även Audience Manager. Båda måste migreras tillsammans. Om du huvudsakligen arbetar med Audience Manager måste du se till att Analytics-teamet deltar i migreringen.

Om du använder [!DNL AppMeasurement] för datainsamling från Audience Manager använder du för närvarande [!DNL Server-side Forwarding (SSF)]-metoden för att skicka Analytics-data till Audience Manager. I den här konfigurationen vidarebefordras begäran om insamling av analysdata till Audience Manager, som även hanterar Audience Manager svar på sidan.

Detta har varit standardmetoden i många år och är sannolikt din nuvarande konfiguration. Om ditt [!DNL AppMeasurement]-bibliotek innehåller modulen `AudienceManagement` och dina datainsamlingsanrop innehåller sökvägen `/10/` i begäran (`/b/ss/examplereportsuite/10/`) är den här handboken till dig.

## Dataflöden för SSF (Server-side Forwarding) jämfört med Web SDK {#data-flows}

För instruktionerna nedan är det viktigt att förstå dataflödesskillnaderna mellan Analytics och Audience Manager när man går över till Web SDK (och Edge Network).

Med vidarebefordran på serversidan samlar den regionala datainsamlingsnoden för Analytics in data, omvandlar dem till en signal som accepteras av Audience Manager, skickar den till Audience Manager och returnerar svaret från Audience Manager till sidan. Modulen [!DNL AudienceManagement] i biblioteket [!DNL AppMeasurement] hanterar sedan svaret (t.ex. att cookies släpps, URL-mål skickas). Den här processen kallas för vidarebefordran på serversidan eftersom Analytics vidarebefordrar data till Audience Manager med hjälp av Adobe-servrar.

Med Web SDK skickar Edge Network data till Analytics och Audience Manager i olika åtgärder. Web SDK är ett enda bibliotek som skickar data till alla lösningar, och Edge Network omvandlar lösningsbaserade datapunkter till lösningsspecifika format.

I det nya dataflödet skickas alla data till en [datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview) i Edge Network, som du kan [konfigurera](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) att skicka data till Adobe-lösningar efter behov. Om du aktiverar tjänsten Audience Manager på datastream för Audience Manager omvandlas [!DNL XDM]- och Analytics-data till signaler som accepteras av Audience Manager. Edge Network returnerar också Audience Manager svar till sidan, där Web SDK hanterar svaret, på liknande sätt som [!DNL AppMeasurement] och [!DNL AudienceManagement]-modulen gjorde.

## Överföring av taggar jämfört med andra taggar {#tags-vs-non-tags}

Oavsett om du använder taggar med tillägget [!DNL AppMeasurement], biblioteket [!DNL AppMeasurement] i ett annat tagghanteringssystem eller placerar [!DNL AppMeasurement] direkt på sidan är stegen för att migrera Audience Manager till Web SDK desamma. Eftersom Audience Manager-migreringen är beroende av Analytics-migreringen bestäms stegen för att migrera från [!DNL AppMeasurement] till Web SDK under Analytics-migreringen.

Den informationen beskrivs i Analytics-dokumentationen för [Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)- eller [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)-baserade implementeringar.

## XDM och `data.__adobe.`-noderna {#xdm-data-nodes}

En av huvudfunktionerna i [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) är att skicka data till [Real-time Customer Data Platform (RTCDP)](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home). För att uppnå detta och fortfarande samla in data för andra Experience Cloud-lösningar utan en fullständig omimplementering, delas lösningsspecifika data upp i datainsamlingsserveranropet. Det här anropet använder ett standardiserat JSON-schema som kallas [Experience Data Model (XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)

Lösningsagnostiska element, som information om webbläsaren och enheten, skickas till Edge Network i en förbestämd XDM-struktur. Edge Network omvandlar dessa data till lösningsspecifika format. Data som är specifika för Target, Analytics och Audience Manager lagras dock i en dedikerad `data.__adobe`-nod i XDM-nyttolasten.

Exempel:

* Analysvariabeln `s.eVar1` representeras i XDM-nyttolasten som `data.__adobe.analytics.evar1`.
* En Target-parameter som är relaterad till kundlojalitetsstatusen lagras som `data.__adobe.target.loyaltyStatus`.

Data i noden `__adobe` skickas till respektive lösningar (som Analytics och Audience Manager) utan att skickas till Experience Platform, även om Experience Platform-tjänsten är aktiverad på datastream. Det innebär att du kan behålla dina nuvarande konfigurationer för Analytics och Audience Manager samtidigt som du kan mappa nödvändiga dataelement till XDM-schemaelement för användning i realtid i Experience Platform med [Dataprep för datainsamling](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep).

Strängen Analytics `s.products`, som används för att rapportera kundvagnens innehåll under utcheckningen, kan till exempel fortfarande skickas till Analytics och Audience Manager i det ursprungliga formatet. Samtidigt kan du använda elementen i den här strängen för att skapa mer intuitiva XDM-kundvagnsscheman för Experience Platform.

Eftersom de flesta Audience Manager-implementeringar förlitar sig på analysdata som vidarebefordras till Audience Manager, är många av dina Audience Manager-uttryck troligen baserade på analysvariabler (`c_evar#`, `c_prop#` och `c_events`). För att undvika att återskapa trait-uttryck med XDM-format under migreringen är Edge Network som standard konfigurerat att omvandla alla Analytics-variabler som finns i noden `data.__adobe.analytics` till Audience Manager-signaler. Den här processen liknar arbetsflödet för vidarebefordran på serversidan.

Edge Network kan utföra den här omvandlingen eftersom ett enda datainsamlingsanrop från sidan skickas till en enda datastream som matar flera Adobe-lösningar. Därför kommer de flesta migreringar från [!DNL AppMeasurement] till Web SDK för både Analytics och Audience Manager främst att använda noden `data.__adobe.analytics`.

Edge Network omvandlar enhets- och webbläsardata från XDM-nyttolasten och pakethuvuden till Audience Manager-signaler. Detta gör att du kan fortsätta använda `h_` och `d_` plattformstangenter i Audience Manager-uttryck.

## Noden `data.__adobe.audiencemanager` {#data-note}

Noden `data.__adobe.audiencemanager` används för Audience Manager-implementeringar som inte är beroende av Analytics. Det lagrar anpassade nyckelpar/värdepar för Audience Manager som tidigare skickats via biblioteket [DIL,](../dil/dil-overview.md), vilket beskrivs i [migreringsguiden för taggtillägg](dil-extension-to-web-sdk.md).

Även om noden `data.__adobe.audiencemanager` inte behövs för den migrering som beskrivs i den här guiden, tillåter det nya dataflödet som beskrivs här att data skickas till Audience Manager utan att registreras i Analytics.

Om du behöver skicka ett anpassat nyckel/värde-par till Audience Manager utan att inkludera det i Analytics, kan du använda noden `data.__adobe.audiencemanager`. Alla datauppsättningar i den här noden läggs till i Analytics-data som omvandlats av Audience Manager i datainsamlingsserveranropet.

## Fördelar och nackdelar med implementeringsvägen

Att använda den här migreringsmetoden har både fördelar och nackdelar. Väg noga in varje alternativ för att avgöra vilken metod som är bäst för er organisation.

| Fördelar | Nackdelar |
| --- | --- |
| <ul><li>**Använder din befintliga implementering**: Även om den här metoden kräver vissa implementeringsändringar krävs ingen helt ny implementering från början. Du kan använda ditt befintliga datalager och kod med minimala ändringar av implementeringslogiken.</li><li>**Kräver inget schema**: För den här migreringsfasen till Web SDK behövs inget XDM-schema. I stället kan du fylla i objektet `data`, som skickar data direkt till Audience Manager. När migreringen till Web SDK är klar kan du skapa ett schema för din organisation och använda datastream-mappning för att fylla i tillämpliga XDM-fält. Om det krävs ett schema i det här skedet av migreringsprocessen måste din organisation använda ett Audience Manager XDM-schema. Om du använder det här schemat blir det svårare för din organisation att använda ditt eget schema i framtiden.</li></ul> | <ul><li>**Implementering av teknisk skuld**: Eftersom den här metoden använder en modifierad form av din befintliga implementering, kan det vara svårare att spåra implementeringslogik och utföra ändringar i framtiden vid behov.</li><li>**Kräver mappning för att skicka data till plattformen**: När din organisation är redo att använda Real-Time CDP måste du skicka data till en datauppsättning i Adobe Experience Platform. Den här åtgärden kräver att alla fält i objektet `data` är en post i datastream-mappningsverktyget som tilldelar det till ett XDM-schemafält. Mappning behöver bara göras en gång för det här arbetsflödet, och implementeringen behöver inte ändras. Det är dock ett extra steg som inte krävs när du skickar data i ett XDM-objekt.</li></ul> |

Adobe rekommenderar att du följer den här implementeringsvägen i följande scenarier:

* Du har en befintlig implementering som använder Adobe Analytics AppMeasurement JavaScript-biblioteket. Om du har en implementering med taggtillägget Audience Manager följer du i stället [Migrera från taggtillägget Audience Manager till Web SDK-taggtillägget](dil-extension-to-web-sdk.md).
* Du avser att använda Real-Time CDP i framtiden, men vill inte ersätta din Audience Manager-implementering med en Web SDK-implementering från grunden. Att ersätta implementeringen från grunden i Web SDK kräver mest arbete, men erbjuder även den mest livskraftiga långsiktiga implementeringsarkitekturen. Om din organisation är beredd att använda en ren Web SDK-implementering kan du läsa [dokumentationen för Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) för mer information.

## Steg som krävs för att migrera till Web SDK

Följ stegen nedan för att migrera din datainsamlingsintegrering till Web SDK.

+++**1. Migrera din Analytics-implementering**.

Arbeta med ert Analytics-team för att följa stegen för Analytics-migrering i de [Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)- eller [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)-baserade implementeringarna. När du har migrerat din Analytics-implementering fortsätter du till följande steg.

+++

+++**2. Lägg till tjänsten Audience Manager i datastream**

Lägg till tjänsten Audience Manager i datastream som du skapade under steg 1.

1. Navigera till [experience.adobe.com](https://experience.adobe.com) och logga in med dina autentiseringsuppgifter.
1. Använd hemsidan eller produktväljaren i det övre högra hörnet för att navigera till **[!UICONTROL Data Collection]**.
1. Välj **[!UICONTROL Datastreams]** i den vänstra navigeringen.
1. Välj den datastream som du skapade som en del av din Analytics-migrering i steg 1.
1. Välj **[!UICONTROL Add Service]**.
1. Välj **[!UICONTROL Audience Manager]** på den nedrullningsbara menyn för tjänster.
1. Kontrollera alternativen **[!UICONTROL Cookie Destinations Enabled]** och **[!UICONTROL URL Destinations Enabled]**. Med dessa alternativ kan Edge Network returnera dessa måltyper för Audience Manager till sidan.
1. Kontrollera att **[!UICONTROL Enable XDM Flattened Fields]** är inaktiverad. Med det här alternativet inaktiveras den automatiska omformningen av Analytics-variabler till Audience Manager-signaler. Det här alternativet är utformat för att behålla bakåtkompatibilitet för användare som migrerade till Web SDK innan Edge Network automatiskt omvandlade Analytics-data till Audience Manager-signaler.

   >[!NOTE]
   >
   >Om du migrerar till Web SDK med alternativet **[!UICONTROL Enabled XDM Flattened Fields]** aktiverat måste alla data som behövs i Audience Manager formaterat som XDM och alla Audience Manager-egenskaper med hjälp av props, eVars eller händelser uppdateras för att i stället söka efter XDM-formaterade data. Adobe rekommenderar att du lämnar det här alternativet inaktiverat.


   ![Lägg till tjänsten Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

1. Välj **[!UICONTROL Save]** om du vill spara dataströmskonfigurationen.

Din datastream är nu redo att ta emot och skicka data till Audience Manager. Observera dataStream ID, eftersom detta ID krävs när du konfigurerar Web SDK i koden.

+++

+++**3. Aktivera synkronisering av tredjeparts-ID och ange Audience Manager-behållar-ID**

1. Navigera till [experience.adobe.com](https://experience.adobe.com) och logga in med dina autentiseringsuppgifter.
1. Använd hemsidan eller produktväljaren i det övre högra hörnet för att navigera till **[!UICONTROL Data Collection]**.
1. Välj **[!UICONTROL Datastreams]** i den vänstra navigeringen.
1. Välj den datastream som du skapade som en del av din Analytics-migrering i steg 1.
1. Välj **[!UICONTROL Edit]** i det övre högra hörnet på konfigurationssidan för datastream.
1. Expandera listrutan **[!UICONTROL Advanced Options]** och aktivera funktionen **[!UICONTROL Third Party ID Sync]** om den inte redan är aktiverad. Det här alternativet innebär att Edge Network returnerar Partner ID-synkroniseringar för datapartner i Audience Manager och Experience Platform.

   ![Aktivera synkronisering av ID från tredje part.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. I de flesta fall kan du lämna fältet **[!UICONTROL Third Party ID Sync Container ID]** tomt. Standardvärdet är `0`. Om du däremot föredrar att se till att rätt behållar-ID används följer du de här stegen:
   * Öppna ett webbläsarfönster i inkodat eller privat läge och navigera till en sida som är en del av migreringen.
   * Använd webbläsarens utvecklarverktyg för att filtrera efter nätverksanropet till `dpm.demdex.net/id`. Det här samtalet utlöses endast på första sidan av ett första besök, och därför behövs en inkognito eller en privat webbläsare.
   * Visa nyttolasten för begäran. Om parametern `d_nsid` inte är noll kopierar du den till fältet **[!UICONTROL Third Party ID Sync Container ID]**.

1. Välj **[!UICONTROL Save]**.

Din datastream är nu redo att både skicka data till Audience Manager och skicka Audience Manager svar till Web SDK.

+++

## Konfigurera vidarebefordran på serversidan och Audience Analytics i gränssnittet för Analytics Report Suite Manager {#configure-ssf-analytics}

Om du känner till funktionen [Vidarebefordran](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) på serversidan i Analytics *kan du undra: Ska jag inaktivera inställningen för vidarebefordran på serversidan i gränssnittet i Analytics Report Suite Manager för att förhindra att Analytics-data skickas till Audience Manager två gånger?*&quot;.

Svaret är nej, du bör inte inaktivera den här inställningen. Här är varför:

När den här inställningen är aktiverad och modulen [!DNL AudienceManagement] läggs till i biblioteket [!DNL AppMeasurement] på sidan, kommer alla data som skickas till den rapportsviten också att flöda till Audience Manager.

För att uppfylla GDPR:s sekretessbestämmelser finns det scenarier där data kan samlas in i Analytics men inte i Audience Manager. Dessutom finns det fall som omfattar globala rapportsviter och regionspecifika användningsfall där vissa datainsamlingsanrop inte ska skickas till Audience Manager. För att lösa detta introducerade Adobe en knapp för att vidarebefordra på serversidan.

Som förklaras på [Analytics- och GDPR-kompatibilitetssidan som fokuserar på vidarebefordran på serversidan](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr), förhindrar tillägg av `cm.ssf=1`-kontextvariabeln till en Analytics-datainsamlingsserver att datainsamlingsanrop vidarebefordras till Audience Manager.

Det finns två skäl till att du inte bör inaktivera den här inställningen.

1. När Audience Manager-tjänsten är aktiverad på en datastream, lägger Edge Network till variabeln `cm.ssf` till alla datainsamlingsbegäranden som skickas till Analytics. Detta förhindrar även att analysdata skickas till Audience Manager. Eventuella Assurance-loggar som används för att validera Analytics-migreringen visar variabeln `cm.ssf=1` när tjänsten Audience Manager är aktiverad på datastream.
1. Den här inställningen aktiverar även dataflödet för [!DNL Audience Analytics]-integreringen. Som beskrivs i [Audience Analytics-översikten](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam) krävs vidarebefordran på serversidan för den här integreringen eftersom Audience Manager-svaret på analysdatainsamlingsservern läggs till i Analytics-träffen före bearbetningen. En liknande process sker i Edge Network. När vidarebefordran på serversidan är aktiverat lägger Edge Network till de nödvändiga segmenten från Audience Manager-svaret till data som skickas till Analytics.

Sammanfattningsvis är det viktigt att den här inställningen är aktiverad så att Audience Analytics fortsätter att fungera med en Web SDK-implementering och att inga data räknas dubbelt i Audience Manager.
