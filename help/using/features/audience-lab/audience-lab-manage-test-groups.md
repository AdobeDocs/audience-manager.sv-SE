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

Den här proceduren vägleder dig genom de steg som krävs för att skapa, redigera eller ta bort en testgrupp i [!UICONTROL Audience Lab].

## Skapa segmenttestgrupper {#create-test-groups}

### Förutsättningar

<!-- create-test-group.xml -->

* Du måste ha konfigurerat minst en **konverteringsegenskap**. Du kan ställa in konverteringsegenskaper i [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md) genom att välja **conversion** som händelsetyp. Mer information om vilka konverteringsegenskaper som är och hur du konfigurerar dem finns i [videon](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html).

  >[!IMPORTANT]
  >
  >[Mappegenskaper](../../features/traits/about-folder-traits.md) stöds **inte** av [!UICONTROL Audience Lab]. Om du ställer in [händelsetypen](../../features/traits/create-onboarded-rule-based-traits.md) för ett mappträtt till **conversion** genereras inga data i [!UICONTROL Audience Lab] för den specifika mappegenskapen.

* För företag som använder [rollbaserad åtkomstkontroll](../../features/administration/administration-overview.md): Tilldela [!UICONTROL Audience Lab] [jokerteckenbehörighet](../../features/administration/administration-overview.md#wild-card-permissions) till **[!UICONTROL User Groups]** för att ge åtkomst. Med den här behörigheten kan användaren skapa och visa resultatet av ett test. En användare kan bara använda segment från en datakälla som de har behörighet för **read** och **mappa till mål**. Användaren kan bara använda konverteringsegenskaper från en datakälla för vilken han/hon har **&quot;läs&quot;**-behörighet. Användaren kan bara se destinationer som han/hon har åtkomst till. Innan du lägger till jokerteckenbehörigheten [!DNL Audience Lab] i en grupp måste gruppen alltså ha:
   * Tillgång till läsning av relevanta konverteringsegenskaper.
   * Tillgång till att läsa och kartlägga relevanta segment för provningar.
   * Tillgång till relevanta destinationer.

Så här skapar du en ny [!UICONTROL Segment Test Group]:

1. Välj **[!UICONTROL Create New Test Group]** på kontrollpanelen [!UICONTROL Audience Lab] för att starta guiden.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Fyll i en **[!UICONTROL Test Group Name]** och en **[!UICONTROL Description]**.
   * Välj **[!UICONTROL Base Segment]** antingen genom att navigera i filläsaren eller genom att skriva i sökfältet, bekräfta genom att trycka på **[!UICONTROL Choose Segment.]**
   * Du kan spara testgruppen som ett utkast och fortsätta arbeta med den senare.
   * En varning visas om bassegmentet du valde redan används i andra testgrupper. Om du använder bassegmentet två gånger kan konverteringsresultatet för båda testerna förvrängas.

1. **[!UICONTROL Allocate Test Segments]**

   * Du kan skapa **upp till 15 testsegment** och dela procentandelen enheter som du vill.
   * Du kan redigera namnet på testsegmenten genom att klicka på dem.
   * Procentsatserna divideras automatiskt jämnt till 100 % när nya testsegment tilldelas. Du kan sedan redigera procentsatserna manuellt. Klicka i kryssrutan när du har redigerat procentsatserna och kontrollera att de är upp till 100 %. I annat fall kan du inte fortsätta till nästa steg.

1. **[!UICONTROL Set a Control Segment]**

   * Markera ett kontrollsegment om du vill ta bort en viss del av segmentet som ska användas som kontrollgrupp. Med kontrollgrupper kan du se effekten av de testsegment som du skapade jämfört med ett test.
   * Du kan välja ett testsegment som kontrollsegment i listrutan eller så kan du välja **[!UICONTROL None]** utan kontroll.
   * Klicka på **[!UICONTROL Next]** när du är klar.

1. **[!UICONTROL Select Conversion Traits]**

   * Lägg till konverteringsegenskaper genom att skriva i fönstret för konverteringsegenskaper. Detta är ett **obligatoriskt** steg och du kan inte fortsätta till nästa steg om du inte lägger till minst en konverteringsegenskap.
   * Du kan lägga till upp till 5 konverteringsegenskaper om du vill.
   * En varning visas om du väljer en konverteringsegenskap som redan används för andra testgrupper.
   * Observera att Audience Manager inte stöder användning av [mappegenskaper](/help/using/features/traits/about-folder-traits.md) som konverteringsegenskaper. Om du väljer ett mappdrag som konverteringsegenskap visas 0 aggregat- och trendrapporter i testet.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Ange önskade mål i sökfältet eller använd listrutepilen. [!UICONTROL Audience Lab] testsegment kan skickas till URL, cookie eller server-till-server-mål.
   * Dra och släpp segment till mål.
   * När du har släppt ett segment i ett mål fyller du i **[!UICONTROL Destination Mapping Value]** i den blinda.
   * Du kan skicka samma testsegment till flera mål och du kan lägga till flera testsegment till ett enda mål.
   * Destinationer är nedtonade om de inte är tillgängliga för ett visst testsegment baserat på [dataexportkontroller](../../features/data-export-controls.md).
   * Användarna kan bara se de mål de har åtkomst till baserat på den [RBAC-användargrupp](../../features/administration/administration-overview.md) de tillhör.
   * Slutligen måste du välja ett startdatum för testgruppen. Det här datumet är början på den period då testgruppen kommer att publiceras till destinationer. Välj **Inget slutdatum** om du vill ha en oändlig jämförelse av testsegmenten.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] med en autentiserad profil stöds bara i realtidsmål. Om ett testsegment med en profilsammanfogningsregel i den konfigurationen skickas till ett filbaserat server-till-server-mål, kanske målgrupperna inte fylls i.

   Klicka på **[!UICONTROL Next]** om du vill granska och slutföra testgruppen.

1. **[!UICONTROL Summary & Finalize]**

   * Granska informationen som du lade till i föregående steg och välj **[!UICONTROL Finalize Group]**.
   * Kom ihåg att när du är klar med en testgrupp kan den dupliceras eller tas bort, men inte redigeras.

   >[!NOTE]
   >* Du kan spara testgrupperna när som helst under skapandet och gå tillbaka till guiden vid ett senare tillfälle. Testgruppens status blir **[!UICONTROL Draft]** och testgruppen skickar inga data till destinationer förrän du slutför segmentets testgrupp.
   >* För utkast av tester kan du gå tillbaka och redigera testgrupperna genom att klicka på **[!UICONTROL Edit]** i testgruppskortet i huvudvyn för [!UICONTROL Audience Lab].

## Redigera segmenttestgrupper {#edit-test-groups}

I [!UICONTROL Audience Lab] kan du bara redigera utkasttestgrupper. I guiden [!UICONTROL Create Segment Test Group] kan du spara testgruppen som ett utkast och fortsätta arbeta med den senare.

1. Navigera till huvudvyn för [!UICONTROL Audience Lab].
1. Sök efter dina utkasttestgrupper och välj kontrollen **[!UICONTROL Edit]** på testgruppskortet.
1. Återuppta guiden [Skapa testgrupp för segment](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) och välj **[!UICONTROL Finalize Group]** när du är klar.

## Ta bort segmenttestgrupper {#delete-test-groups}

1. Navigera till huvudvyn för [!UICONTROL Audience Lab].
1. Hitta den testgrupp som du vill ta bort. Du kan antingen:

   * tryck på kontrollen **[!UICONTROL Delete]** på testgruppskortet, eller
   * Tryck på testgruppens titel på testgruppskortet för att gå till vyn [Testgruppsinformation](../../features/audience-lab/audience-lab-information-view.md) och tryck på kontrollen **[!UICONTROL Delete]** i namnlisten.

1. För [slutförda testsegment](../../features/audience-lab/audience-lab.md#status) visas en varning om att du ska hämta CSV-filen för att spara rapporteringen om du vill.
