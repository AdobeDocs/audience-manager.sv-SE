---
description: Vanliga frågor och problem som rör rapportering.
seo-description: Vanliga frågor och problem som rör rapportering.
seo-title: Vanliga frågor om rapportering
solution: Audience Manager
title: Vanliga frågor om rapportering
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 0%

---


# Vanliga frågor om rapportering{#reporting-faq}

Vanliga frågor och problem som rör rapportering.

<br> 

<!-- 

faq_reports.xml

 -->

**Varför visas siffror som är lägre än förväntat eller 0 för nya[!UICONTROL Trait Graph]embed-egenskaper?**

När du har överfört egenskaper visas ibland [!UICONTROL Trait Graph] inga resultat eller siffror som är lägre än förväntat. Detta inträffar när datavolymen som vi får är så stor att det inkommande bearbetningsjobbet inte kan slutföra inmatningen av informationen förrän efter rapportdatumet för den dagen.

Därför skickas dessa data till rapporteringssystemet sent och visas inte i det rapportintervall på 1 dag som används för att rita upp [!UICONTROL Trait Graph]. Du kan dock visa dessa data i rapportintervallen 7, 14, 30 och 60 dagar i en [trend](../reporting/trend-reports.md#trend-report-overview) - eller [General Report](../reporting/general-reports.md#general-reports-overview) följande dag.

<br> 

**Vissa segment saknas i en[!UICONTROL Overlap]rapport. Var är de?**

För att minska efterfrågan på data utelämnar dessa rapporter statistiskt obetydliga data från resultaten. Dina segment saknas inte, de tas bara bort eftersom de inte ger några meningsfulla resultat eller användbara grupper med användare som du kan rikta dig mot. Se även:

* [Rapporter och datainsamlingsmetoder](../reporting/report-sampling.md)
* [Räkna unika användare i Överlappning och Allmänna rapporter](../reporting/unique-user-counts.md).

<br> 

**Om jag kör en e-postmarknadsföringskampanj, hur kan jag avgöra om omdirigerade användare kommer till min webbplats från den kampanjen eller från andra källor?**

Lägg till en kampanjspecifik frågesträng i URL:en för det webbplatsavsnitt som du vill övervaka. Ställ sedan in en trait-regel för att hämta variabeln. Om URL:en till exempel skickar in ett kampanj-ID som detta `www.test123.com/electronics?campaign=123`skapar du en trait-regel som hämtar data från `h_referer` variabeln med en trait-regel som söker efter ett huvud som `h_referer = 'campaign=123'`).

<br> 

**Vad är skillnaden mellan antalet populationer i realtid och totalt antal segment?**

* **Realtid:** Antalet unika användare som är en del av segmentet och som är aktiva på dina egenskaper under en angiven tidsperiod (d.v.s. måste ha registrerat aktivitet för den användaren för den specifika tidsperioden). [!DNL Audience Manager]

* **Totalt antal segment:** En sammanställning av alla användare som för närvarande klassificeras i det segmentet.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Jag har ett segment som består av bara ett drag. När jag tittar på Rapporteringsstatistik stämmer inte deras antal överens. Varför det?**

Se [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**Jag har inkommande en fil och mitt inkommande kvitto visar ett stort antal poster som har bearbetats, men rapporteringen visar ett mycket lägre antal. Varför?**

I serverdelen kopplas inbäddade data endast till användare som fortfarande är aktiva i AAM (användaren måste ha haft senaste [!DNL DCS] aktivitet under de senaste 120 dagarna). Om du lägger in data för användare som redan har gått ut i [!DNL Audience Manager]kan det därför [!UICONTROL Inbound] tala om för dig att ett visst antal användarposter har registrerats, men om dessa användare inte har haft någon aktivitet nyligen, kommer dessa data att tas bort när de når oss [!UICONTROL User Profile Store] och rapporteringen kommer att visa detta.

<br> 

**Varför är de unika egenskaperna för min typ av butik mycket högre än det totala antalet onboardposter?**

Om du bäddar in en fil för en leverantör av data mellan olika enheter som är avstängd från kund-ID:t, utförs en sökning i Audience Manager för att hämta alla enhets-ID:n som är kopplade till varje kund-ID:n. Audience Manager tilldelar sedan de ingående egenskaperna till det enhets-ID som är kopplat till kund-ID:t.

Anta att du har 100 poster ombord. För vart och ett av dessa kund-ID har AAM i genomsnitt kopplat tre enhets-ID. Det innebär att det varumärke som introducerades tilldelas 300 enhets-ID:n.

Det finns två orsaker till varför ett enskilt kund-ID mellan olika enheter kan kopplas till flera enhets-ID:

* Användare loggar in på samma enhetskonto från flera datorer/webbläsare.
* Användare rensar sina cookies. Obs! &quot;Övergivna&quot; cookies tas bort efter 120 dagars inaktivitet.

<br> 

**Varför är[!UICONTROL Total Trait Realizations]mina onboaröda egenskaper alltid 0?**

[!UICONTROL Total Trait Realizations] motsvarar sidinläsning. [!UICONTROL Total Trait Realizations] Ange hur många gånger den specifika egenskapen har utlösts i realtid. Det här talet beräknas endast för regelbaserade egenskaper. Inbyggda traktioner visas alltid [!UICONTROL Total Trait Realizations] som 0.

<br> 

**Jag skapade en egenskap och den[!UICONTROL Trait Graph]visar ett större antal[!UICONTROL Unique Trait Realizations]än[!UICONTROL Total Trait Population]. Är det här normalt?**

Du ser detta eftersom det [!UICONTROL Unique Trait Realizations] är realtidsstatistik, men de rapporteringsjobb vi gör för att beräkna [!UICONTROL Total Trait Population] är inte realtidsdata. De [!UICONTROL Total Trait Population] ska vara större än [!UICONTROL Unique Trait Realizations] inom några dagar.
