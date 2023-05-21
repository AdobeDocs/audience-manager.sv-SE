---
description: Audience Manager och Adobe Experience Platform identitetstjänst anropar och tar emot data från domänen demdex.net. Det kan verka som att Adobe arbetar med en ovanlig tredjepartsdomän, men så är inte fallet. I det här avsnittet beskrivs elementen i ett demdex.net-anrop.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Förstå anrop till Demdex-domänen
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 7%

---

# Om samtal till [!DNL Demdex] Domän {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] och [!DNL Adobe Experience Platform Identity Service] ringa och ta emot data från `demdex.net` domän. Det här kan verka som [!DNL Adobe] arbetar med en ovanlig tredjepartsdomän, men så är inte fallet. I det här avsnittet beskrivs elementen i en `demdex.net` ring.

| Samtalselement | Beskrivning |
|---|---|
| `demdex.net` | Detta är en äldre domän som styrs av [!DNL Adobe]. Det återspeglar det ursprungliga namnet på [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] förvärvades [!DNL Demdex] 2011 och företaget omprofilerades som [!DNL Audience Manager]. Det är svårt att ändra den här domänen eftersom den är starkt kopplad till [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service]och vår installerade användarbas. Du kan se andra prefix som är kopplade till äldre `demdex.net` samtal (t.ex. `dcs.demdex.net`, `fast.demdex.net`, osv.). Oberoende av prefixet kan du anropa `something.demdex.net` är alltid ett anrop till [!DNL Adobe] och inte till någon okänd eller misstänkt tredjepartsdomän. |
| `dpm` | [!DNL DPM] är en förkortning för [!DNL Data Provider Match]. Den talar internt, [!DNL Adobe] system som [!DNL Audience Manager] eller [!DNL Adobe Experience Cloud ID Service] skickar kunddata för synkronisering eller begär ett ID. Det här är det vanligaste `demdex.net` ring dig från [!DNL Audience Manager] eller [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] Grunderna för samtal: <ul><li>[!DNL Audience Manager]: A [!DNL DPM] ring från [!DNL Audience Manager] skickar data till [!DNL Data Collection Servers] och [!DNL Profile Cache Servers]. Se [Komponenter för datainsamling](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: A [!DNL DPM] ring från [!DNL Adobe Experience Cloud ID Service] är en begäran om besökar-ID. Se [Cookies och Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) och [Hur Adobe Experience Platform identitetstjänst begär och anger ID:n](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html).</li></ul><br>Obs! [!DNL Adobe Experience Cloud ID Service] kunderna kan ändra [!DNL DPM] i domännamnet. Se [auditionManager Server och auditionManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Audience Manager Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)

