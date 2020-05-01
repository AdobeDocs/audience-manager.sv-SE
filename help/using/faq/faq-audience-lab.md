---
description: Frågor och svar om Audience Lab-funktionen.
seo-description: Frågor och svar om Audience Lab-funktionen.
seo-title: Vanliga frågor om Audience Lab
solution: Audience Manager
title: Vanliga frågor om Audience Lab
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Vanliga frågor om Audience Lab{#audience-lab-faq}

Frågor och svar om Audience Lab-funktionen.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**Har testsegmenten som skapas i testgrupperna olika segment-ID? Hur mappar jag ID:n till olika destinationer?**

Ja, testsegmenten har olika segment-ID. För destinationer med [!UICONTROL Auto-fill Destination Mapping] eller segment som skickas till [!DNL Google][!UICONTROL Audience Lab] hanteras mappningsvärdena på samma sätt som de mål som normalt används.

<br> 

**Kan samma konverteringsegenskap kopplas till flera testgrupper?**

Ja, det är tillåtet. Tänk på ett fall av ett test med ett manligt segment som är associerat med konvertering X och ett test med ett honsegment som är associerat med konvertering X. Det spelar ingen roll att båda testerna genererar konverteringar eftersom de testar två olika målgrupper.

<br> 

**Låt oss säga att en testgrupp använder en autentiserad profil för delning av testsegment. Den autentiserade profilen är länkad till fyra[Audience Manager UUID](../reference/ids-in-aam.md). När besökaren uppvisar en konverteringsegenskap från någon av de fyra UUID:n, räknas[!UICONTROL Audience Lab]detta som en eller fyra konverteringar?**

I det här fallet räknas [!UICONTROL Audience Lab] bara en konvertering.

<br> 

**Vad händer om besökaren från fallet ovan först uppvisar konverteringsegenskapen från en av de fyra UUID:n som är länkade till deras autentiserade profil och sedan också uppvisar konverteringsegenskapen från två andra UUID:n som är länkade till den autentiserade profilen? Räknas det här fallet som en eller tre konverteringar?**

I det här fallet [!UICONTROL Audience Lab] räknas tre konverteringar, en för varje enhet som har visat verifieringsegenskapen.

<br> 

**Kan en användare ha[!UICONTROL Segment: Read-Only]åtkomst, men även åtkomst för att[!UICONTROL Audience Lab]testa att skapa segment?**

Mer information om hur du använder [med](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) behörigheter finns i [!UICONTROL Audience Lab] Skapa segmenttestgrupp [!UICONTROL RBAC] .

**Kan jag använda[!UICONTROL Audience Lab]tillsammans med[!UICONTROL Profile Link Device Graph]och externa enhetsdiagram ([Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html), Tapad Device Graph, Liveramp Device Graph)?**

För närvarande [!UICONTROL Audience Lab] kan bara dela upp segmentpopulationer med enheter som är anslutna till en kvalificerande enhet när du använder [!UICONTROL Profile Link Device Graph]. Vi arbetar med att lägga till stöd i [!UICONTROL Audience Lab] för andra enhetsdiagram och kommer att meddela när vi gör det.
