---
description: Statusen för besöksautentisering i Audience Manager avgör om den nya trait-informationen skrivs till besökarens autentiserade profil eller till enhetsprofilen, där data samlades in från. Audience Manager hanterar autentiseringsstatusarna för besökar-ID UNKNOWN och LOGGED_OUT i händelseanrop på samma sätt.
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Autentiseringstillstånd för besökare i Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# Autentiseringstillstånd för besökare i Audience Manager{#visitor-authentication-states-in-audience-manager}

Statusen för besöksautentisering i Audience Manager avgör om den nya trait-informationen skrivs till besökarens autentiserade profil eller till enhetsprofilen, där data samlades in från. Audience Manager hanterar autentiseringsstatusarna för besökar-ID UNKNOWN och LOGGED_OUT i händelseanrop på samma sätt.

Börja med [!DNL Experience Cloud] ID-tjänsten v1.5+, `setCustomerID` metoden innehåller det valfria `AuthState` -objekt. `AuthState` identifierar besökare utifrån deras [autentiseringsstatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] hanterar de realiserade egenskaperna på olika sätt, beroende på vilken autentiseringsstatus som skickas i anropet och vilka [Sammanfogningsregel för profil](../features/profile-merge-rules/merge-rules-dashboard.md) som används för segmentering.

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
>[!DNL Audience Manager] utför en ID-synkronisering mellan [CID och UUID](../reference/ids-in-aam.md) i samtliga tre fall.

>[!MORELIKETHIS]
>
>* [Kund-ID:n och autentiseringstillstånd](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)

