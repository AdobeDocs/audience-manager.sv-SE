---
description: Statusen för besöksautentisering i Audience Manager avgör om den nya trait-informationen skrivs till besökarens autentiserade profil eller till enhetsprofilen, där data samlades in från. Audience Manager hanterar autentiseringsstatusarna för besökar-ID UNKNOWN och LOGGED_OUT i händelseanrop på samma sätt.
keywords: dpm.demdex.net
seo-description: Statusen för besöksautentisering i Audience Manager avgör om den nya trait-informationen skrivs till besökarens autentiserade profil eller till enhetsprofilen, där data samlades in från. Audience Manager hanterar autentiseringsstatusarna för besökar-ID UNKNOWN och LOGGED_OUT i händelseanrop på samma sätt.
seo-title: Autentiseringstillstånd för besökare i Audience Manager
solution: Audience Manager
title: Autentiseringstillstånd för besökare i Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# Autentiseringstillstånd för besökare i Audience Manager{#visitor-authentication-states-in-audience-manager}

Statusen för besöksautentisering i Audience Manager avgör om den nya trait-informationen skrivs till besökarens autentiserade profil eller till enhetsprofilen, där data samlades in från. Audience Manager hanterar autentiseringsstatusarna för besökar-ID UNKNOWN och LOGGED_OUT i händelseanrop på samma sätt.

Från och med [!DNL Experience Cloud] ID-tjänsten v1.5+ innehåller metoden det valfria `setCustomerID` `AuthState` objektet. `AuthState` identifierar besökare utifrån deras [autentiseringsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] hanterar de realiserade egenskaperna på olika sätt, beroende på vilken autentiseringsstatus som skickas i anropet och vilken [profilkopplingsregel](../features/profile-merge-rules/merge-rules-dashboard.md) du använder för segmentering.

## Autentiseringsstatus: OKÄND {#auth-status-unknown}

| Begäranvärde | **Läs** information från den autentiserade profilen | **Skriv** nya egenskaper i den autentiserade profilen |
---------|----------|---------
| 0 | <ul><li>Ja, om kopplingsregeln för autentiserade alternativ = &quot;Senaste autentiserade profiler&quot;.</li><li>Nej, om kopplingsregeln för autentiserade alternativ = &quot;Aktuella autentiserade profiler&quot; eller &quot;Ingen autentiserad profil&quot;.</li></ul> | Nej, trait-data läggs till i enhetsprofilen. |


Exempelanrop (det begärandevärde som motsvarar autentiseringsstatusen markeras):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Autentiseringsstatus: AUTENTISERAD {#auth-status-authenticated}

| Begäranvärde | **Läs** information från den autentiserade profilen | **Skriv** nya egenskaper i den autentiserade profilen |
---------|----------|---------
| 1 | <ul><li>Ja, om kopplingsregeln för autentiserade alternativ = &quot;Aktuella autentiserade profiler&quot; eller &quot;Senaste autentiserade profiler&quot;.</li><li>Nej, om kopplingsregeln för autentiserade alternativ = &quot;Ingen autentiserad profil&quot;.</li></ul> | Ja, trait-data läggs till i den autentiserade profilen. |

Exempelanrop (det begärandevärde som motsvarar autentiseringsstatusen markeras):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Autentiseringsstatus: LOGGED_OUT {#auth-status-logged-out}

| Begäranvärde | **Läs** information från den autentiserade profilen | **Skriv** nya egenskaper i den autentiserade profilen |
---------|----------|---------
| 2 | <ul><li>Ja, om kopplingsregeln för autentiserade alternativ = &quot;Senaste autentiserade profiler&quot;</li><li>Nej, om kopplingsregeln för autentiserade alternativ = &quot;Aktuella autentiserade profiler&quot; eller &quot;Ingen autentiserad profil&quot;</li></ul> | Nej, trait-data skrivs till enhetsprofilen. |

Exempelanrop (det begärandevärde som motsvarar autentiseringsstatusen markeras):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] utför en ID-synkronisering mellan [CID och UUID](../reference/ids-in-aam.md) i alla tre fallen.

>[!MORELIKETHIS]
>
>* [Kund-ID:n och autentiseringstillstånd](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

