---
description: Konfigurera en Google-grupp för att överföra dina DCM-datafiler (DoubleClick Campaign Manager) till Audience Manager. Innehållet i det här avsnittet sammanfattar integrationsprocessen och ger dig länkar till DCM-resurser som hjälper dig att komma igång.
seo-description: Konfigurera en Google-grupp för att överföra dina DCM-datafiler (DoubleClick Campaign Manager) till Audience Manager. Innehållet i det här avsnittet sammanfattar integrationsprocessen och ger dig länkar till DCM-resurser som hjälper dig att komma igång.
seo-title: Importera DCM-datafiler till Audience Manager
solution: Audience Manager
title: Importera DCM-datafiler till Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Importera DCM-datafiler till Audience Manager {#import-dcm-data-files-into-audience-manager}

Konfigurera en Google-grupp för att överföra dina DCM-datafiler (DoubleClick Campaign Manager) till Audience Manager. Innehållet i det här avsnittet sammanfattar integrationsprocessen och ger dig länkar till DCM-resurser som hjälper dig att komma igång.

## Sammanfattning av integrering

DCM är [!DNL Google]:s ersättning för [!DNL DoubleClick for Advertisers] (DFA). DCM-kunder kan importera, visa och arbeta med data i [!DNL Audience Manager] ungefär på samma sätt som med DFA. Men [!DNL Audience Manager] kan inte direkt komma åt och importera dina filer för [!UICONTROL Data Transfer] och [!UICONTROL Match Table]. Kunderna ansvarar i stor grad själva för import av dessa filer.

Konfigurationsproceduren är dock väl dokumenterad i hjälpen [för](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456)DoubleClick Campaign Manager. Du kan också gå igenom stegen nedan för att komma igång.

>[!CAUTION]
>
>DCM-datafiler innehåller data för alla annonsörer och kunder. Om du behöver utesluta vissa klienter måste du redigera filerna innan du gör dem tillgängliga för [!DNL Audience Manager].

## Dataöverföringsfrekvens och -tillgänglighet

[!DNL Audience Manager] söker efter och överför data en gång om dagen. Data är vanligtvis tillgängliga inom [!DNL Audience Manager] 24 timmar.

## Steg

1. [Skapa en grupp](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Grupper styr åtkomsten till dina DCM-data. Så småningom kommer du att bjuda in och lägga [!DNL Audience Manager] till den här gruppen.

1. [Verifiera din Google Cloud-lagringsstatus](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud-lagring innehåller den databaket som innehåller din [!UICONTROL Data Transfer] och [!UICONTROL Match Tables]. Du måste konfigurera en bucket eller se till att den nya gruppen har åtkomst till en befintlig datalagringsenhet.

1. [Hämta en URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456)för datafil.

   Arbeta med er DCM-kontoansvarige eller Platform Solutions Consultant. De ger dig en URL till dina datafiler. [!DNL Google] kan ändra formatet för bucket och filnamn i framtida versioner. Arbeta med DCM-kontohanteraren för att vara säker på att du använder rätt format.

1. [Ange bucketbehörigheter](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   Med [!DNL Cloud Storage Manager] den kan du styra datadelning och därmed få tillgång till hakparenteser. Ge gruppen läsåtkomst till den bucket som innehåller dina [!UICONTROL Data Transfer] och [!UICONTROL Match Table] dina filer.

1. [Konfigurera datadelning](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Delade användar-ID för DCM krypteras för att skydda sekretessen. Krypteringen lägger till två kolumner i slutet av dataöverföringsfilen, `PartnerId1` och `PartnerId2`. Dessa kolumner innehåller kodade användar-ID:n som är specifika för varje företag som tar emot filerna.

   Som auktoriserad tredje part [!DNL Audience Manager] kan ta emot DCM-data, men kan inte avkoda ID:n. Å andra [!DNL Audience Manager] sidan vet vi hur de kodade ID:n matchar våra ID:n. Det innebär att vi kan matcha och synkronisera användare med tillförsikt och precision.

   >[!NOTE]
   >Du kan inte importera DCM-filer till [!DNL Audience Manager] om du redan delar data med två andra tredjepartspartners.

1. Bjud in [!DNL Audience Manager] att gå med i gruppen.

   När du har skapat en grupp och gett den åtkomst till en databucket bjuder du in [!DNL Audience Manager] att gå med i gruppen. Skicka en inbjudan via e-post till DFA-AAM@adobe.com. Inkludera datafilens URL från steg 3. Våra interna team samarbetar med dig för att verifiera åtkomsten efter att ha godkänt inbjudan. 1. Konfigurera två datakällor för DCM-data i [!DNL Audience Manager] användargränssnittet.

   Namnge datakällorna `Advertiser Analytics: DCM Platform` och `Advertiser Analytics: AAM+DCM Platform`. I arbetsflödet [Skapa datakällor](../../../features/manage-datasources.md#create-data-source) anger du ID-typen till `Cookie`. Dela ID:n för de två nya datakällorna med våra interna team.

1. Du kan enkelt skapa egenskaper från de DCM-filer du importerar till [!DNL Audience Manager]. Se [Loggfiler](../../../integration/media-data-integration/actionable-log-files.md) som kan användas och fråga din [!DNL Audience Manager] konsult eller kundtjänst om du vill aktivera funktionen.
