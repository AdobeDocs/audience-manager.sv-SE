---
description: Konfigurera en Google-grupp för att överföra dina Google Campaign Manager-datafiler till Audience Manager. Innehållet i det här avsnittet sammanfattar integrationsprocessen och ger dig länkar till Google Campaign Manager-resurser som hjälper dig att komma igång.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importera Google Campaign Manager-datafiler till Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Importera Google Campaign Manager-datafiler till Audience Manager {#import-dcm-data-files-into-audience-manager}

Konfigurera en [!DNL Google] grupp för att ta med [!DNL Google Campaign Manager] datafiler till Audience Manager. Innehållet i det här avsnittet sammanfattar integrationsprocessen och ger dig länkar till [!DNL Google Campaign Manager] resurser som hjälper dig att komma igång.

## Sammanfattning av integrering

[!DNL Google Campaign Manager] är [!DNL Google]:s ersättning för [!DNL DoubleClick for Advertisers] (DFA). Liknar DFA, [!DNL Google Campaign Manager] kan importera, visa och arbeta med sina data i [!DNL Audience Manager]. Men [!DNL Audience Manager] kan inte direkt komma åt och importera dina filer för [!UICONTROL Data Transfer] och [!UICONTROL Match Table]. Kunderna ansvarar i stor grad själva för import av dessa filer.

Inrättningsförfarandet är dock väl dokumenterat i [Dubbelklicka på Hjälp om Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Du kan också gå igenom stegen nedan för att komma igång.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] datafiler innehåller data för alla era annonsörer eller kunder. Om du behöver utesluta vissa klienter måste du redigera filerna innan du gör dem tillgängliga för [!DNL Audience Manager].

## Dataöverföringsfrekvens och -tillgänglighet

[!DNL Audience Manager] söker efter och överför data en gång om dagen. Data är vanligtvis tillgängliga i [!DNL Audience Manager] efter 24 timmar.

## Steg

1. [Skapa en grupp](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Grupper styr åtkomsten till [!DNL Google Campaign Manager] data. Så småningom kommer du att bjuda in och lägga till [!DNL Audience Manager] till den här gruppen.

1. [Verifiera din Google Cloud-lagringsstatus](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud-lagring innehåller den databassett som innehåller din [!UICONTROL Data Transfer] och [!UICONTROL Match Tables]. Du måste konfigurera en bucket eller se till att den nya gruppen har åtkomst till en befintlig datalagringsenhet.

1. [Hämta en URL för datafil](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Arbeta med dina [!DNL Google Campaign Manager] Account Manager eller Platform Solutions Consultant. De ger dig en URL till dina datafiler. [!DNL Google] kan ändra formatet för bucket och filnamn i framtida versioner. Arbeta med [!DNL Google Campaign Manager] Account Manager för att vara säker på att du använder rätt format.

1. [Ange bucketbehörigheter](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   The [!DNL Cloud Storage Manager] Med kan du styra delning av data och därmed få tillgång till dem. Ge gruppen läsåtkomst till den bucket som innehåller din [!UICONTROL Data Transfer] och [!UICONTROL Match Table] filer.

1. [Konfigurera datadelning](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Delad [!DNL Google Campaign Manager] användar-ID:n krypteras för att skydda sekretessen. Krypteringen lägger till två kolumner i slutet av dataöverföringsfilen, `PartnerId1` och `PartnerId2`. Dessa kolumner innehåller kodade användar-ID:n som är specifika för varje företag som tar emot filerna.

   Som auktoriserad tredje part [!DNL Audience Manager] kan ta emot [!DNL Google Campaign Manager] data, men det går inte att avkoda ID:n. På [!DNL Audience Manager] vi vet hur de kodade ID:n matchar våra ID:n. Det innebär att vi kan matcha och synkronisera användare med tillförsikt och precision.

   >[!NOTE]
   >Du kan inte importera [!DNL Google Campaign Manager] filer i [!DNL Audience Manager] om ni redan delar data med två andra tredjepartspartners.

1. Bjud in [!DNL Audience Manager] för att gå med i gruppen.

   När du har skapat en grupp och gett den åtkomst till en databucket kan du bjuda in [!DNL Audience Manager] för att gå med i gruppen. Skicka en inbjudan via e-post till dfaaam@adobe.com. Inkludera datafilens URL från steg 3. Våra interna team samarbetar med dig för att verifiera åtkomsten efter att ha godkänt inbjudan. 1. Konfigurera två datakällor för [!DNL Google Campaign Manager] data i [!DNL Audience Manager] Användargränssnitt.

   Namnge datakällorna `Advertiser Analytics: DCM Platform` och `Advertiser Analytics: AAM+DCM Platform`. I [Skapa datakällor](../../../features/manage-datasources.md#create-data-source) arbetsflöde, ange ID-typ till `Cookie`. Dela ID:n för de två nya datakällorna med våra interna team.

1. Du kan enkelt skapa egenskaper från [!DNL Google Campaign Manager] filer som du importerar till [!DNL Audience Manager]. Se [Åtgärdsbara loggfiler](../../../integration/media-data-integration/actionable-log-files.md) och fråga [!DNL Audience Manager] konsult eller kundtjänst för att aktivera funktionen åt dig.
