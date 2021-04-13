---
description: Audience Manager och Adobe Experience Platform identitetstjänst anropar och tar emot data från domänen demdex.net. Det kan verka som att Adobe arbetar med en ovanlig tredjepartsdomän, men så är inte fallet. I det här avsnittet beskrivs elementen i ett demdex.net-anrop.
seo-description: Audience Manager och Adobe Experience Platform identitetstjänst anropar och tar emot data från domänen demdex.net. Det kan verka som att Adobe arbetar med en ovanlig tredjepartsdomän, men så är inte fallet. I det här avsnittet beskrivs elementen i ett demdex.net-anrop.
seo-title: Förstå anrop till Demdex-domänen
solution: Audience Manager
title: Förstå anrop till Demdex-domänen
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: 'Referens '
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 15%

---

# Förstå anrop till [!DNL Demdex]-domänen {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] och  [!DNL Adobe Experience Platform Identity Service] anropar och tar emot data från  `demdex.net` domänen. Det kan verka som att [!DNL Adobe] arbetar med en ovanlig tredjepartsdomän, men så är inte fallet. I det här avsnittet beskrivs elementen i ett `demdex.net`-anrop.

| Samtalselement | Beskrivning |
|---|---|
| `demdex.net` | Detta är en äldre domän som styrs av [!DNL Adobe]. Det återspeglar det ursprungliga namnet på [!DNL Audience Manager] ([!DNL Demdex]) före förvärvet. [!DNL Adobe] förvärvades [!DNL Demdex] 2011 och företaget omprofilerades som [!DNL Audience Manager]. Det är svårt att ändra den här domänen eftersom den är djupt inskriven med [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service] och vår installerade användarbas. Du kan se andra prefix som är kopplade till äldre `demdex.net`-anrop (t.ex. `dcs.demdex.net`, `fast.demdex.net`). Oavsett prefixet är ett anrop till `something.demdex.net` alltid ett anrop till [!DNL Adobe] och inte till någon okänd eller misstänkt tredjepartsdomän. |
| `dpm` | [!DNL DPM] är en förkortning för  [!DNL Data Provider Match]. Den talar om för interna [!DNL Adobe]-system att ett anrop från [!DNL Audience Manager] eller [!DNL Adobe Experience Cloud ID Service] skickar kunddata för synkronisering eller begär ett ID. Det här är det vanligaste `demdex.net`-anropet du kan se från [!DNL Audience Manager] eller [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] Grunderna för samtal: <ul><li>[!DNL Audience Manager]: Ett  [!DNL DPM] anrop från  [!DNL Audience Manager] skickar data till  [!DNL Data Collection Servers] och  [!DNL Profile Cache Servers]. Se [Komponenter för datainsamling](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Ett  [!DNL DPM] anrop från användaren  [!DNL Adobe Experience Cloud ID Service] är en begäran om besökar-ID. Se [Cookies och Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/sv-SE/id-service/using/intro/cookies.html) och [How the Adobe Experience Platform Identity Service Requests and Sets IDs](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Obs!  [!DNL Adobe Experience Cloud ID Service] -kunder kan ändra  [!DNL DPM] prefixet i domännamnet. Se [auditionManager Server och auditionManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Audience Manager Cookies](https://docs.adobe.com/content/help/sv-SE/core-services/interface/ec-cookies/cookies-am.html)

