---
description: Frågor och svar om Audience Lab-funktionen.
seo-description: Frågor och svar om Audience Lab-funktionen.
seo-title: Vanliga frågor om Audience Lab
solution: Audience Manager
title: Vanliga frågor om Audience Lab
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 100%

---


# Vanliga frågor om Audience Lab {#audience-lab-faq}

Frågor och svar om Audience Lab-funktionen.

<!-- 

audience-lab-faq.xml

 -->

<br>

**Har testsegmenten som skapas i testgrupperna olika segment-ID? Hur mappar jag ID:n till olika destinationer?**

Ja, testsegmenten har olika segment-ID. För destinationer med [!UICONTROL Auto-fill Destination Mapping] eller segment som skickas till [!DNL Google] hanteras mappningsvärdena i [!UICONTROL Audience Lab] på samma sätt som destinationerna gör i vanliga fall.

<br> 

**Kan samma konverteringstrait kopplas till flera testgrupper?**

Ja, det är tillåtet. Tänk dig ett test med ett manligt segment som är associerat med konvertering X och ett test med ett kvinnligt segment som är associerat med konvertering X. Det spelar ingen roll att båda testerna genererar konverteringar eftersom de testar två olika målgrupper.

<br> 

**Låt oss säga att en testgrupp använder en autentiserad profil för delning av testsegment. Den autentiserade profilen är länkad till fyra [Audience Manager UUID](../reference/ids-in-aam.md). När en besökare har ett konverteringstrait från någon av dessa fyra UUID:n, räknas det som en eller fyra konverteringar i [!UICONTROL Audience Lab]?**

I det här fallet räknas det bara som en konvertering i [!UICONTROL Audience Lab].

<br> 

**Vad händer om besökaren från exemplet ovan först har ett konverteringstrait från en av de fyra UUID:n som är länkade till hens autentiserade profil och sedan har ett konverteringstrait från två andra UUID:n som är länkade till den autentiserade profilen? Räknas det som en eller tre konverteringar?**

I det här fallet räknas det som tre konverteringar i [!UICONTROL Audience Lab], en för varje enhet som har ett autentiserings-trait.

<br> 

**Kan en användare ha åtkomst till [!UICONTROL Segment: Read-Only] och samtidigt ha åtkomst för att skapa [!UICONTROL Audience Lab]-testsegment?**

Mer information om hur du använder [!UICONTROL Audience Lab] med [!UICONTROL RBAC]- behörigheter finns i [Skapa testgrupp för segment](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups).

**Kan jag använda [!UICONTROL Audience Lab] tillsammans med [!UICONTROL Profile Link Device Graph] och externa enhetsdiagram ([Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/sv-SE/device-co-op/using/home.html), Tapad Device Graph, Liveramp Device Graph)?**

För närvarande kan [!UICONTROL Audience Lab] bara dela upp segmentpopulationer efter enheter som är anslutna till en kvalificerande enhet när du använder [!UICONTROL Profile Link Device Graph]. Vi arbetar med att lägga till stöd i [!UICONTROL Audience Lab] för andra enhetsdiagram och kommer att meddela när vi gör det.
