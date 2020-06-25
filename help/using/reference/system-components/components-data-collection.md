---
description: Datainsamlingskomponenterna omfattar datainsamlingsservrar, DIL API, inkommande överföring av data från server till server samt loggfiler.
seo-description: Datainsamlingskomponenterna omfattar datainsamlingsservrar, DIL API, inkommande överföring av data från server till server samt loggfiler.
seo-title: Datainsamlingskomponenter
solution: Audience Manager
title: Datainsamlingskomponenter
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 0%

---


# Datainsamlingskomponenter{#data-collection-components}

Datainsamlingskomponenterna omfattar datainsamlingsservrar, DIL API, inkommande överföring av data från server till server samt loggfiler.

<!-- 

c_compcollect.xml

 -->

Audience Manager innehåller följande datainsamlingskomponenter:

* [Datainsamlingsservrar (DCS) och profilcacheservrar (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Dataintegreringsbibliotek (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Inkommande server-till-server](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Loggfiler](../../reference/system-components/components-data-collection.md#log-files)

## Datainsamlingsservrar (DCS) och profilcacheservrar (PCS) {#dcs-pcs}

DCS och PCS fungerar tillsammans och tillhandahåller separat tjänster som är relaterade till kundanpassning, målgruppssegmentering och datalagring.

**[!UICONTROL Data Collection Servers (DCS)] -funktion **

I [!DNL Audience Manager]DCS:

* Tar emot och utvärderar trait-data från ett händelseanrop. Detta inkluderar information som används för segmentering i realtid och data som skickas in enligt schemalagda intervaller av server-till-server-överföringar.
* Segmentera användare baserat på deras realiserade egenskaper och de kvalificeringsregler du skapar med [Segment Builder](../../features/segments/segment-builder.md).
* Skapar och hanterar enhets-ID och autentiserade profil-ID:n. Detta inkluderar identifierare som DataProvider ID, användar-ID, deklarerade ID:n, integreringskoder osv.
* Kontrollerar om det finns ytterligare egenskaper hos PCS som en användare redan har uppnått före ett händelsesamtal i realtid. På så sätt kan DCS-användarna kvalificera sig baserat på realtidsdata och historiska data.
* Skriver loggfiler och skickar dem till analyssystem för lagring och bearbetning.

**[!DNL DCS]Hanterar efterfrågan via[!UICONTROL Global Server Load Balancing (GSLB)]**

Systemet [!DNL DCS] är ett geografiskt fördelat och lastbalanserat system. Detta innebär att [!DNL Audience Manager] kan dirigera förfrågningar till och från ett regionalt datacenter baserat på den geografiska platsen för en besökare. Denna strategi hjälper till att förbättra svarstiderna eftersom ett svar går direkt till ett datacenter som innehåller information om besökaren. [!DNL DCS] [!UICONTROL GSLB] gör vårt system effektivt eftersom relevanta data cachas i servrar som ligger närmast användaren.

>[!IMPORTANT]
>
>Den identifierar [!DNL DCS] bara webbtrafik som kommer från enheter som använder IPv4.

I ett händelseanrop hämtas geografisk plats i ett nyckelvärdepar som returneras i en större mängd JSON-data. Detta nyckelvärdepar är `"dcs_region": region ID` parametern.

![](assets/dcs-map.png)

Som kund interagerar ni med det [!DNL DCS] indirekt via vår datainsamlingskod. Du kan också arbeta direkt med [!DNL DCS] via en uppsättning API:er. Se API-metoder och kod [för](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)Data Collection Server (DCS).

**[!UICONTROL Profile Cache Servers (PCS)]**

Det [!UICONTROL PCS] är en stor databas (i stort sett en stor cookie på serversidan). Den lagrar data som tas emot för aktiva användare från server till server-överföringar och [!DNL DCS]. [!UICONTROL PCS] data består av enhets-ID, autentiserade profil-ID:n och tillhörande egenskaper. När användaren [!DNL DCS] får ett realtidssamtal kontrolleras [!UICONTROL PCS] om användaren har andra egenskaper som han/hon kan tillhöra eller vara berättigad till. Och om en egenskap läggs till i ett segment vid ett senare tillfälle läggs dessa trait-ID:n till i [!UICONTROL PCS] och användarna kan kvalificera sig för det segmentet automatiskt, utan att besöka en viss webbplats eller app. Detta [!UICONTROL PCS] bidrar till att fördjupa [!DNL Audience Manager]förståelsen för era användare eftersom det kan matcha och segmentera användare i realtid eller bakom kulisserna med nya och historiska traits-data. Detta beteende ger en mer fullständig och korrekt bild av era användare än bara med realtidskvalifikationer.

Det finns inga gränssnittskontroller som gör att våra kunder kan arbeta direkt med [!UICONTROL PCS]. Kundåtkomst till [!UICONTROL PCS] är indirekt genom sin roll som datalager och dataöverföringar. De [!UICONTROL PCS] springer på Apache Cassandra.

**Tar bort inaktiva ID:n från[!UICONTROL PCS]**

Som tidigare nämnts [!UICONTROL PCS] lagras trait ID:n för aktiva användare. En aktiv användare är en användare som har setts av [edge-dataservrarna](../../reference/system-components/components-edge.md) från valfri domän under de senaste 14 dagarna. Dessa anrop till [!UICONTROL PCS] att hålla en användare i aktivt tillstånd:

* [!DNL /event] samtal
* [!DNL /ibs] anrop (ID-synk)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Tömningarna [!UICONTROL PCS] går om de är inaktiva i 17 dagar. De här egenskaperna går dock inte förlorade. De är lagrade i Hadoop. Om användaren visas igen vid ett senare tillfälle kommer Hadoop att återföra alla sina egenskaper till [!UICONTROL PCS]datorn, vanligtvis inom 24 timmar.

**Andra[!UICONTROL DCS/PCS]processer: Avanmäl dig till sekretess**

Dessa serversystem hanterar förfrågningar om sekretess och avanmälan av användare. Information om användarens cookie samlas inte in i loggfilen om en användare har avanmält sig från datainsamlingen. Mer information om vår sekretesspolicy finns i [Adobes sekretesscenter](https://www.adobe.com/privacy/advertising-services.html).

## Dataintegreringsbibliotek (DIL) {#dil}

[!UICONTROL DIL] är kod som du placerar på sidan för datainsamling. Mer information om tillgängliga tjänster och metoder finns i [DIL API](../../dil/dil-overview.md) .

## Inkommande server-till-server {#inbound-outbound-server}

Detta är system som tar emot data som skickas in av olika server-till-server-integreringar med våra klienter. Mer information finns i dokumentationen om hur du [skickar målgruppsdata](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) .

## Loggfiler {#log-files}

Data [!UICONTROL PCS] skapas och skrivs till loggfilerna. Dessa skickas till andra databassystem för bearbetning, rapportering och lagring.

>[!MORELIKETHIS]
>
>* [Adobes sekretesscenter](https://www.adobe.com/privacy.html)

