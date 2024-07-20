---
description: Audience Manager och Adobe Experience Platform identitetstjänst gör anrop till och tar emot data från demdex.net. Det kan verka som att Adobe arbetar med en ovanlig tredjepartsdomän, men så är inte fallet. I det här avsnittet beskrivs elementen i ett demdex.net.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Förstå anrop till Demdex-domänen
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 4%

---

# Förstå anrop till domänen [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] och [!DNL Adobe Experience Platform Identity Service] anropar och tar emot data från domänen `demdex.net`. Det kan verka som att [!DNL Adobe] arbetar med en ovanlig tredjepartsdomän, men så är inte fallet. I det här avsnittet beskrivs elementen i ett `demdex.net`-anrop.

| Samtalselement | Beskrivning |
|---|---|
| `demdex.net` | Det här är en äldre domän som styrs av [!DNL Adobe]. Det återspeglar det ursprungliga namnet på [!DNL Audience Manager] ([!DNL Demdex]) före förvärvet. [!DNL Adobe] förvärvades [!DNL Demdex] 2011 och företaget omprofilerades som [!DNL Audience Manager]. Det är svårt att ändra den här domänen eftersom den är djupt inskriven i [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service] och vår installerade användarbas. Du kan se andra prefix kopplade till äldre `demdex.net` anrop (t.ex. `dcs.demdex.net`, `fast.demdex.net` osv.). Oavsett prefixet är ett anrop till `something.demdex.net` alltid ett anrop till [!DNL Adobe] och inte till någon okänd eller misstänkt tredjepartsdomän. |
| `dpm` | [!DNL DPM] är en förkortning för [!DNL Data Provider Match]. Den meddelar interna [!DNL Adobe]-system att ett anrop från [!DNL Audience Manager] eller [!DNL Adobe Experience Cloud ID Service] skickas i kunddata för synkronisering eller för att begära ett ID. Det här är det vanligaste `demdex.net`-anropet du kan se från [!DNL Audience Manager] eller [!DNL Adobe Experience Cloud ID Service]. Grunderna för <br><br>[!DNL DPM]-samtal: <ul><li>[!DNL Audience Manager]: Ett [!DNL DPM] anrop från [!DNL Audience Manager] skickar data till [!DNL Data Collection Servers] och [!DNL Profile Cache Servers]. Se [Komponenter för datainsamling](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Ett [!DNL DPM] anrop från [!DNL Adobe Experience Cloud ID Service] är en begäran om ett besökar-ID. Se [Cookies och Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) och [How the Adobe Experience Platform Identity Service Requests and Sets IDs](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html).</li></ul><br>Obs! [!DNL Adobe Experience Cloud ID Service]-kunder kan ändra prefixet [!DNL DPM] i domännamnet. Se [målgruppshanteraren Server och målgruppshanterarenServersäkerhet](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform identitetstjänst](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Audience Manager Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)
