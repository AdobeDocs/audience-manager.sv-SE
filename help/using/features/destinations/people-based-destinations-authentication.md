---
description: Den här sidan innehåller riktlinjer för hur du konfigurerar och hanterar integreringen mellan Audience Manager och personbaserade plattformar.
seo-description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms.
seo-title: Authentication with People-Based Platforms
solution: Audience Manager
title: Autentisering med personbaserade plattformar
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: 1809e9ee0b19a8ffb4bec38162f728d543d13701
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# Autentisering med personbaserade plattformar {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

Den här sidan innehåller riktlinjer om hur du kan konfigurera och hantera integreringen
mellan Audience Manager och personbaserade plattformar.

>[!NOTE]
>Detta är ett obligatoriskt steg för personbaserade destinationer, oavsett implementeringsscenario.

## Konfigurera personbaserad plattformsautentisering {#configure-authentication}

1. Logga in på ditt Audience Manager-konto och gå till **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Om du har en tidigare konfigurerad integrering med en social plattform bör du se den här sidan. I annat fall är sidan tom.
   ![Personbaserad integration](assets/pbd-config.png)
2. Klicka på **[!UICONTROL Add Account]**.
3. Använd listrutan **[!UICONTROL People-Based Platform]** för att välja den plattform som du vill konfigurera integreringen med.
   ![Personbaserad-plattform](assets/pbd-add.png)
4. Klicka på **[!UICONTROL Confirm]** om du vill omdirigeras till autentiseringssidan för den valda plattformen.
5. När du har autentiserat dig på ditt konto för sociala plattformar omdirigeras du till Audience Manager där du ska se dina associerade annonskonton. Välj det annonserarkonto som du vill använda och klicka på **[!UICONTROL Confirm]**.
6. Audience Manager visar ett meddelande högst upp på sidan för att tala om för dig om kontot har lagts till. I meddelandet kan du även lägga till en e-postadress för att få meddelanden från Adobe när autentiseringen för den sociala plattformen håller på att upphöra.

## Förfallotid för autentiseringstoken och meddelandehantering {#token-expiration-notification}

Audience Manager hanterar integreringen med sociala plattformar genom autentiseringstoken som upphör efter en viss tid. Giltighetstiden för token regleras av respektive social plattforms integreringsregler. När autentiseringstoken gått ut kan Audience Manager inte skicka målgruppssegment till ditt mål. För att undvika det här scenariot rekommenderar vi att du lägger till minst en e-postadress för kontakt i integreringen, så att du får ett meddelande så snart autentiseringstoken håller på att upphöra att gälla. När det inträffar kan ni autentisera er på nytt för att försäkra er om att målgruppen fortsätter att ta emot era målgruppssegment.

Så här lägger du till e-postadresser i befintliga integreringar:

1. Logga in på ditt Audience Manager-konto och gå till **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifiera den integrering som du vill få information om när token upphör att gälla för och klicka på ikonen **[!UICONTROL Edit]**.
1. Ange de e-postadresser som du vill ska ta emot meddelanden om utgångsdatum för token, avgränsade med kommatecken.
1. Klicka på **[!UICONTROL Save]**.

## Förnyelse av autentiseringstoken {#token-renewal}

När en autentiseringstoken upphör att gälla avbryts integreringen mellan Audience Manager och motsvarande sociala plattform, så Audience Manager kan inte längre skicka målgruppssegment till målet. På sidan [!UICONTROL Integrated Accounts] visas förfallostatusen för varje integrering i kolumnen [!UICONTROL Expiration], och du kan när som helst förnya autentiseringen.

Så här förnyar du en autentisering som har upphört att gälla eller som snart upphör att gälla:
1. Logga in på ditt Audience Manager-konto och gå till **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifiera den integrering som du behöver förnya autentiseringen för. Utgångna autentiseringar markeras som [!UICONTROL Expired], medan autentiseringar som snart upphör att gälla snart visar det återstående antalet autentiserade dagar.
1. Klicka på motsvarande **[!UICONTROL Renew]**-ikon i kolumnen [!UICONTROL Expiration]. Detta utlöser arbetsflödet **[!UICONTROL Renew Account]**, som tar dig tillbaka genom den sociala plattformens autentiseringssida. När du autentiserar förnyas token med det nya förfallodatumet.
   ![pbd-renew](assets/pbd-renew.png)
