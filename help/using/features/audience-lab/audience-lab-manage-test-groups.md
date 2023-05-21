---
description: Den här proceduren vägleder dig genom de steg som behövs för att skapa, redigera eller ta bort en testgrupp i Audience Lab
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: Hantera testgrupper
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# Hantera testgrupper {#manage-test-groups}

Den här proceduren vägleder dig genom de steg som behövs för att skapa, redigera eller ta bort en testgrupp i [!UICONTROL Audience Lab].

## Skapa segmenttestgrupper {#create-test-groups}

### Förutsättningar

<!-- create-test-group.xml -->

* Du måste ha minst en **konverteringsegenskap** konfigurera. Du kan ange konverteringsegenskaper i dialogrutan [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md)genom att välja **konvertering** som händelsetyp. För mer information om vilka konverteringsegenskaper som är och hur de är konfigurerade har vi tagit fram en [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) för dig.

   >[!IMPORTANT]
   >
   >[Mappegenskaper](../../features/traits/about-folder-traits.md) är **stöds inte** av [!UICONTROL Audience Lab]. Ange [Händelsetyp](../../features/traits/create-onboarded-rule-based-traits.md) av en mappegenskap till **konvertering** genererar inga data i [!UICONTROL Audience Lab] för den specifika mappegenskapen.

* För företag som använder [Rollbaserad åtkomstkontroll](../../features/administration/administration-overview.md): Tilldela [!UICONTROL Audience Lab] [behörighet för jokertecken](../../features/administration/administration-overview.md#wild-card-permissions) till **[!UICONTROL User Groups]** för att ge åtkomst. Med den här behörigheten kan användaren skapa och visa resultatet av ett test. En användare kan bara använda segment från en datakälla som han/hon har **read** och **mappa till mål** behörighet för. Användaren kan bara använda konverteringsegenskaper från en datakälla som han/hon har **&quot;read&quot;** behörigheter. Användaren kan bara se destinationer som han/hon har åtkomst till. Så innan du lägger till [!DNL Audience Lab] behörighet att lägga till jokertecken i en grupp, kontrollera att gruppen har:
   * Tillgång till läsning av relevanta konverteringsegenskaper.
   * Tillgång till att läsa och kartlägga relevanta segment för provningar.
   * Tillgång till relevanta destinationer.

Skapa en ny [!UICONTROL Segment Test Group]:

1. Välj **[!UICONTROL Create New Test Group]** i [!UICONTROL Audience Lab] kontrollpanelen för att starta guiden.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Fyll i en **[!UICONTROL Test Group Name]** och **[!UICONTROL Description]**.
   * Välj **[!UICONTROL Base Segment]** antingen genom att navigera i filläsaren eller genom att skriva i sökfältet, bekräfta genom att trycka på **[!UICONTROL Choose Segment.]**
   * Du kan spara testgruppen som ett utkast och fortsätta arbeta med den senare.
   * En varning visas om bassegmentet du valde redan används i andra testgrupper. Om du använder bassegmentet två gånger kan konverteringsresultatet för båda testerna förvrängas.

1. **[!UICONTROL Allocate Test Segments]**

   * Du kan skapa **upp till 15 testsegment** och dela upp procentandelen enheter som du vill.
   * Du kan redigera namnet på testsegmenten genom att klicka på dem.
   * Procentsatserna divideras automatiskt jämnt till 100 % när nya testsegment tilldelas. Du kan sedan redigera procentsatserna manuellt. Klicka i kryssrutan när du har redigerat procentsatserna och kontrollera att de är upp till 100 %. I annat fall kan du inte fortsätta till nästa steg.

1. **[!UICONTROL Set a Control Segment]**

   * Markera ett kontrollsegment om du vill ta bort en viss del av segmentet som ska användas som kontrollgrupp. Med kontrollgrupper kan du se effekten av de testsegment som du skapade jämfört med ett test.
   * Du kan välja ett testsegment som kontrollsegment i listrutan eller välja **[!UICONTROL None]** utan kontroll.
   * Klicka **[!UICONTROL Next]** när du är klar.

1. **[!UICONTROL Select Conversion Traits]**

   * Lägg till konverteringsegenskaper genom att skriva i fönstret för konverteringsegenskaper. Det här är en **obligatoriskt** går det inte att fortsätta till nästa steg om du inte lägger till minst en konverteringsegenskap.
   * Du kan lägga till upp till 5 konverteringsegenskaper om du vill.
   * En varning visas om du väljer en konverteringstjänst som redan används för andra testgrupper.
   * Observera att Audience Manager inte stöder användning av [mappegenskaper](/help/using/features/traits/about-folder-traits.md) som konverteringsegenskaper. Om du väljer ett mappdrag som konverteringsegenskap visas 0 aggregat- och trendrapporter i testet.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Ange önskade mål i sökfältet eller använd listrutepilen. [!UICONTROL Audience Lab] testsegment kan skickas till URL, cookie eller server-till-server-mål.
   * Dra och släpp segment till mål.
   * När du har släppt ett segment i ett mål fyller du i **[!UICONTROL Destination Mapping Value]** i de blinda.
   * Du kan skicka samma testsegment till flera mål och du kan lägga till flera testsegment till ett enda mål.
   * Destinationer är nedtonade om de inte är tillgängliga för ett visst testsegment baserat på [Dataexportkontroller](../../features/data-export-controls.md).
   * Användarna kan bara se de mål de har åtkomst till baserat på [RBAC-användargrupp](../../features/administration/administration-overview.md) de tillhör.
   * Slutligen måste du välja ett startdatum för testgruppen. Det här datumet är början på den period då testgruppen kommer att publiceras till destinationer. Välj **Inget slutdatum** för en obegränsad jämförelse av testsegmenten.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] med en autentiserad profil stöds bara i realtid. Om ett testsegment med en profilsammanfogningsregel i den konfigurationen skickas till ett filbaserat server-till-server-mål, kanske målgrupperna inte fylls i.

   Klicka **[!UICONTROL Next]** för att granska och slutföra testgruppen.

1. **[!UICONTROL Summary & Finalize]**

   * Granska informationen som du lade till i föregående steg och välj **[!UICONTROL Finalize Group]**.
   * Kom ihåg att när du är klar med en testgrupp kan den dupliceras eller tas bort, men inte redigeras.

   >[!NOTE]
   >* Du kan spara testgrupperna när som helst under skapandet och gå tillbaka till guiden vid ett senare tillfälle. Testgruppens status blir **[!UICONTROL Draft]** och testgruppen skickar inga data till destinationer förrän du slutför segmenttestgruppen.
   >* För utkast av tester kan du gå tillbaka och redigera testgrupperna genom att klicka på **[!UICONTROL Edit]** i testgruppskortet i [!UICONTROL Audience Lab] vy.


## Redigera segmenttestgrupper {#edit-test-groups}

I [!UICONTROL Audience Lab]kan du bara redigera utkasttestgrupper. I [!UICONTROL Create Segment Test Group] kan du spara testgruppen som ett utkast och fortsätta arbeta med den senare.

1. Navigera till [!UICONTROL Audience Lab] huvudvyn.
1. Sök efter dina utkasttestgrupper och välj **[!UICONTROL Edit]** kontroll i testgruppskortet.
1. Återuppta [Skapa segmenttestgrupp](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) guide och välj **[!UICONTROL Finalize Group]** när du är klar.

## Ta bort segmenttestgrupper {#delete-test-groups}

1. Navigera till [!UICONTROL Audience Lab] huvudvyn.
1. Hitta den testgrupp som du vill ta bort. Du kan antingen:

   * tryck på **[!UICONTROL Delete]** kontroll på testgruppskortet, eller
   * tryck på testgruppens titel på testgruppskortet för att gå till [Information om testgrupp](../../features/audience-lab/audience-lab-information-view.md) visa och trycka på **[!UICONTROL Delete]** i namnlisten.

1. För [slutförda testsegment](../../features/audience-lab/audience-lab.md#status)visas ett varningsmeddelande om du vill ladda ned CSV-filen och spara rapporten.
