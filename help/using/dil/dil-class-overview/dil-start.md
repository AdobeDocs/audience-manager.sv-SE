---
description: Beskriver autentiseringskrav och textformatering som används i DIL-dokumentationen på klassnivå.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Komma igång med DIL API:er på klassnivå
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 8%

---

# Komma igång med DIL API:er på klassnivå{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av [!DNL Data Integration Library (DIL)] och [!DNL DIL] tillägg.
>
>Befintliga kunder kan fortsätta använda sina [!DNL DIL] implementering. Adobe kommer dock inte att utvecklas [!DNL DIL] bortom denna punkt. Kunder uppmanas att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) för deras långsiktiga strategi för datainsamling.
>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) i stället.

Med DIL API:erna på klassnivå kan du programmässigt skapa och arbeta med Audience Manager-objekt. Klassnivå-API:erna fungerar med andra instansnivåfunktioner för att ange värden eller returnera data.

## Komma igång med DIL API:er på klassnivå {#get-started}

Beskriver autentiseringskrav och textformatering som används på klassnivå [!UICONTROL DIL] dokumentation.

<!-- 

c_class_start.xml

 -->

När du arbetar med klassnivån [!UICONTROL DIL] API:

* Åtkomst kräver ett partnernamn och ett behållar-ID (NSID). Kontakta din kontoansvarige på Audience Manager för att få denna information.
* Ersätt valfritt exempel *kursiv* text i API-dokumentationen med värde, ID eller annan variabel som krävs för den metod du arbetar med.
* [!UICONTROL DIL] skriver kodade data till en målcookie. Blanksteg kodas till exempel som `%20` och semikolon `%3B`.
