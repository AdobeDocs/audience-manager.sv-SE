---
description: Vanliga frågor och problem som rör rapportering.
seo-description: Vanliga frågor och problem som rör rapportering.
seo-title: Vanliga frågor om rapportering
solution: Audience Manager
title: Vanliga frågor om rapportering
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
feature: Reporting Reference
exl-id: 1e6531b2-bb39-4056-9d5e-164f50955f99
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 99%

---

# Vanliga frågor om rapportering {#reporting-faq}

Vanliga frågor och problem som rör rapportering.

<br>

<!-- 

faq_reports.xml

 -->

**Varför visas siffror som är lägre än förväntat eller 0 för nya registrerade traits i [!UICONTROL Trait Graph]?**

När du har överfört traits visas ibland inga resultat eller värden som är lägre än förväntat i [!UICONTROL Trait Graph]. Det inträffar när datavolymen som vi får är så stor att det inkommande bearbetningsjobbet inte kan mata in informationen förrän efter tidsgränsen för rapportering den dagen.

Dessa data skickas till rapporteringssystemet sent och visas inte i det rapportintervall på 1 dag som används för att beräkna [!UICONTROL Trait Graph]. Du kan visa dessa data i rapportintervallen för 7, 14, 30 och 60 dagar i en [trendrapport](../reporting/trend-reports.md#trend-report-overview) eller [allmän rapport](../reporting/general-reports.md#general-reports-overview) dagen därpå.

<br> 

**Vissa segment saknas i en [!UICONTROL Overlap]-rapport. Var är de?**

För att minska beräkningsbelastningen utelämnas statistiskt insignifikanta data från resultaten i dessa rapporter. Dina segment saknas inte, de utelämnas bara eftersom de inte ger några meningsfulla resultat eller användbara användargrupper som du kan rikta dig mot. Se även:

* [Metoder för rapportering och datainsamling](../reporting/report-sampling.md)
* [Räkna unika användare i överlappande och allmänna rapporter](../reporting/unique-user-counts.md).

<br> 

**Om jag kör en e-postmarknadsföringskampanj, hur kan jag avgöra om omdirigerade användare kommer till min webbplats från den kampanjen eller andra källor?**

Lägg till en kampanjspecifik frågesträng i webbadressen för det webbplatsavsnitt som du vill övervaka. Ställ sedan in en trait-regel som samlar in variabeln. Om till exempel webbadresen innehåller ett kampanj-ID som detta `www.test123.com/electronics?campaign=123`, kan du skapa en trait-regel som hämtar data från `h_referer`-variabeln med en trait-regel som söker efter ett sidhuvud som `h_referer = 'campaign=123'`).

<br> 

**Vad är skillnaden mellan antalet segmentpopulationer i realtid och totalt?**

* **Realtid:** Antalet unika användare som är en del av segmentet och som är aktiva på dina tillgångar under en angiven tidsperiod (d.v.s. [!DNL Audience Manager] måste registrera aktivitet för den användaren under den specifika tidsperioden).

* **Total segmentpopulation:** En sammanställning av alla användare som för närvarande klassificeras i det segmentet.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Jag har ett segment som bara består av ett trait. När jag tittar på rapportmätvärdena så stämmer inte antalen överens. Varför det?**

Se [Trait- och segmentpopulationsdata i Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**Jag har en inkommande fil och mitt kvitto för inkommande visar ett stort antal poster som har bearbetats, men rapporterna visar ett mycket lägre antal. Varför?**

I serverdelen kopplas registrerade data endast till användare som fortfarande är aktiva i AAM (användaren måste ha haft [!DNL DCS]-aktivitet under de senaste 120 dagarna). Om du lägger in data för användare som redan har gått ut i [!DNL Audience Manager] kan [!UICONTROL Inbound] meddela att ett visst antal användarposter har registrerats, men om dessa användare inte har haft någon aktivitet nyligen, kommer dessa data att tas bort när de når vår [!UICONTROL User Profile Store] och rapporteringen kommer att visa detta.

<br> 

**Varför är unika traits för registrerade enhetövergripande traits mycket högre än det totala antalet registrerade poster?**

Om du registrerar en fil för en enhetsövergripande dataleverantör som baseras på kund-ID, utförs en sökning i Audience Manager för att hämta alla enhets-ID:n som är kopplade till dessa kund-ID:n. Audience Manager tilldelar sedan registrerade traits till det enhets-ID som är kopplat till det kund-ID:t.

Anta att du har 100 registrerade poster. För vart och ett av dessa kund-ID:n har AAM i genomsnitt kopplat tre enhets-ID:n. Det innebär att det trait som registrerades tilldelas 300 enhets-ID:n.

Det finns två orsaker till varför ett enskilt enhetsövergripande kund-ID kan kopplas till flera enhets-ID:n:

* Användare loggar in på samma enhetsövergripande konto från flera datorer/webbläsare.
* Användare rensar sina cookies. Obs! Övergivna cookies tas bort efter 120 dagars inaktivitet.

<br> 

**Varför är mina registrerade traits alltid 0 i [!UICONTROL Total Trait Realizations]?**

[!UICONTROL Total Trait Realizations] motsvarar sidinläsningar. [!UICONTROL Total Trait Realizations] anger hur många gånger ett specifikt trait har utlösts i realtid. Antalet beräknas bara för regelbaserade traits. Registrerade traits visas alltid som 0 i [!UICONTROL Total Trait Realizations].

<br> 

**Jag skapade ett trait och [!UICONTROL Trait Graph] visar ett större antal [!UICONTROL Unique Trait Realizations] än [!UICONTROL Total Trait Population]. Är det normalt?**

Du ser detta eftersom det är realtidsstatistik i [!UICONTROL Unique Trait Realizations], men rapporteringsjobben som görs för att beräkna [!UICONTROL Total Trait Population] är inte i realtid. [!UICONTROL Total Trait Population] bör vara större än [!UICONTROL Unique Trait Realizations] inom några dagar.
