---
description: Statusen för besöksautentisering i Audience Manager avgör om den nya trait-informationen skrivs till besökarens autentiserade profil eller till enhetsprofilen, där data samlades in från. Audience Manager hanterar autentiseringsstatusarna för besökar-ID UNKNOWN och LOGGED_OUT i händelseanrop på samma sätt.
keywords: dpm.demdex.net
seo-description: Statusen för besöksautentisering i Audience Manager avgör om den nya trait-informationen skrivs till besökarens autentiserade profil eller till enhetsprofilen, där data samlades in från. Audience Manager hanterar autentiseringsstatusarna för besökar-ID UNKNOWN och LOGGED_OUT i händelseanrop på samma sätt.
seo-title: Autentiseringstillstånd för besökare i Audience Manager
solution: Audience Manager
title: Autentiseringstillstånd för besökare i Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: 'Referens '
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
translation-type: tm+mt
source-git-commit: c3c829ef1335d1e073b719f8252103fa578bb4e6
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 6%

---

# Autentiseringstillstånd för besökare i Audience Manager{#visitor-authentication-states-in-audience-manager}

Statusen för besöksautentisering i Audience Manager avgör om den nya trait-informationen skrivs till besökarens autentiserade profil eller till enhetsprofilen, där data samlades in från. Audience Manager hanterar autentiseringsstatusarna för besökar-ID UNKNOWN och LOGGED_OUT i händelseanrop på samma sätt.

Från och med [!DNL Experience Cloud] ID-tjänst v1.5+ inkluderar metoden `setCustomerID` det valfria `AuthState`-objektet. `AuthState` identifierar besökare utifrån deras  [autentiseringsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] hanterar de realiserade egenskaperna på olika sätt, beroende på vilken autentiseringsstatus som skickas i anropet och vilken  [profilkopplingsregel ](../features/profile-merge-rules/merge-rules-dashboard.md) du använder för segmentering.

## Autentiseringsstatus: OKÄND {#auth-status-unknown}

| Begäranvärde | Läs information från den autentiserade profilen | Skriv nya egenskaper till den autentiserade profilen |
|---|---|---|
| 0 | <ul><li>Ja, om [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Nej, om [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] eller [!UICONTROL No Authenticated Profile].</li></ul> | Nej, trait-data läggs till i enhetsprofilen. |

Exempelanrop (det begärandevärde som motsvarar autentiseringsstatusen markeras):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Autentiseringsstatus: AUTENTISERAD {#auth-status-authenticated}

| Begäranvärde | Läs information från den autentiserade profilen | Skriv nya egenskaper till den autentiserade profilen |
|---|---|---|
| 1 | <ul><li>Ja, om [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] eller [!UICONTROL Last Authenticated Profiles].</li><li>Nej, om [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Ja, trait-data läggs till i den autentiserade profilen. |

Exempelanrop (det begärandevärde som motsvarar autentiseringsstatusen markeras):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Autentiseringsstatus: LOGGED_OUT {#auth-status-logged-out}

| Begäranvärde | Läs information från den autentiserade profilen | Skriv nya egenskaper till den autentiserade profilen |
|---|---|---|
| 2 | <ul><li>Ja, om [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Nej, om [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] eller [!UICONTROL No Authenticated Profile].</li></ul> | Nej, trait-data skrivs till enhetsprofilen. |

Exempelanrop (det begärandevärde som motsvarar autentiseringsstatusen markeras):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] utför en ID-synkronisering mellan  [CID och ](../reference/ids-in-aam.md) UID i alla tre fallen.

>[!MORELIKETHIS]
>
>* [Kund-ID:n och autentiseringstillstånd](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

