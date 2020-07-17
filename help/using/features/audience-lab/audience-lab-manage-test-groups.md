---
description: Den här proceduren vägleder dig genom de steg som behövs för att skapa, redigera eller ta bort en testgrupp i Audience Lab
seo-description: Den här proceduren vägleder dig genom de steg som behövs för att skapa, redigera eller ta bort en testgrupp i Audience Lab
seo-title: Hantera testgrupper
solution: Audience Manager
title: Hantera testgrupper
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 0%

---


# Hantera testgrupper {#manage-test-groups}

Den här proceduren vägleder dig genom de steg som behövs för att skapa, redigera eller ta bort en testgrupp i [!UICONTROL Audience Lab].

## Skapa segmenttestgrupper {#create-test-groups}

### Förutsättningar

<!-- create-test-group.xml -->

* Du måste ha minst en **konverteringsegenskap** inställd. Du kan ange konverteringsegenskaper i [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md)genom att välja **konvertering** som händelsetyp. Mer information om konverteringsegenskaper och hur du ställer in dem finns i [videon](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) .

   >[!IMPORTANT]
   >
   >[Mappegenskaper](../../features/traits/about-folder-traits.md) stöds **** inte av [!UICONTROL Audience Lab]. Om du anger [händelsetypen](../../features/traits/create-onboarded-rule-based-traits.md) för en mappegenskap till **konvertering** genereras inga data i [!UICONTROL Audience Lab] för den specifika mappegenskapen.

* För företag som använder [rollbaserad åtkomstkontroll](../../features/administration/administration-overview.md): Tilldela [!UICONTROL Audience Lab] jokerteckenbehörigheten [att](../../features/administration/administration-overview.md#wild-card-permissions) **[!UICONTROL User Groups]** ge åtkomst. Med den här behörigheten kan användaren skapa och visa resultatet av ett test. En användare kan bara använda segment från en datakälla som han/hon har **läs** - och **mappa till målbehörighet** för. Användaren kan bara använda konverteringsegenskaper från en datakälla som han/hon har **&quot;läsbehörighet&quot;** för. En användare kan bara se destinationer som de har åtkomst till. Innan du lägger till [!DNL Audience Lab] jokerteckenbehörigheten i en grupp måste gruppen alltså ha:
   * Tillgång till läsning av relevanta konverteringsegenskaper.
   * Tillgång till att läsa och kartlägga relevanta segment för provningar.
   * Tillgång till relevanta destinationer.

To create a new [!UICONTROL Segment Test Group]:

1. Starta guiden genom att välja **[!UICONTROL Create New Test Group]** i [!UICONTROL Audience Lab] kontrollpanelen.
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
   * Du kan välja ett testsegment som kontrollsegment i den nedrullningsbara listan eller välja **[!UICONTROL None]** att inte använda någon kontroll.
   * Klicka **[!UICONTROL Next]** när du är klar.

1. **[!UICONTROL Select Conversion Traits]**

   * Lägg till konverteringsegenskaper genom att skriva i fönstret för konverteringsegenskaper. Detta är ett **obligatoriskt** steg och du kan inte fortsätta till nästa steg om du inte lägger till minst en konverteringsegenskap.
   * Du kan lägga till upp till 5 konverteringsegenskaper om du vill.
   * En varning visas om du väljer en konverteringstjänst som redan används för andra testgrupper.
   * Observera att Audience Manager inte har stöd för att använda [mappegenskaper](/help/using/features/traits/about-folder-traits.md) som konverteringsegenskaper. Om du väljer ett mappdrag som konverteringsegenskap visas 0 aggregat- och trendrapporter i testet.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Ange önskade mål i sökfältet eller använd listrutepilen. [!UICONTROL Audience Lab] testsegment kan skickas till URL, cookie eller server-till-server-mål.
   * Dra och släpp segment till mål.
   * När du har släppt ett segment i en destination fyller du i det **[!UICONTROL Destination Mapping Value]** i blinda.
   * Du kan skicka samma testsegment till flera mål och du kan lägga till flera testsegment till ett enda mål.
   * Destinationer är nedtonade om de inte är tillgängliga för ett visst testsegment baserat på [dataexportkontroller](../../features/data-export-controls.md).
   * Användarna kan bara se de mål de har åtkomst till baserat på den [RBAC-användargrupp](../../features/administration/administration-overview.md) de tillhör.
   * Slutligen måste du välja ett startdatum för testgruppen. Det här datumet är början på den period då testgruppen kommer att publiceras till destinationer. Välj **Inget slutdatum** för en obestämd jämförelse av testsegmenten.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] med en autentiserad profil stöds bara i realtid. Om ett testsegment med en profilsammanfogningsregel i den konfigurationen skickas till ett filbaserat server-till-server-mål, kanske målgrupperna inte fylls i.

   Klicka **[!UICONTROL Next]** för att granska och slutföra testgruppen.

1. **[!UICONTROL Summary & Finalize]**

   * Granska informationen som du lade till i föregående steg och välj **[!UICONTROL Finalize Group]**.
   * Kom ihåg att när du är klar med en testgrupp kan den dupliceras eller tas bort, men inte redigeras.

   >[!NOTE]
   >* Du kan spara testgrupperna när som helst under skapandet och gå tillbaka till guiden vid ett senare tillfälle. Testgruppens status blir **[!UICONTROL Draft]** och testgruppen skickar inga data till destinationerna förrän du slutför segmentets testgrupp.
   >* För utkast av tester kan du gå tillbaka och redigera testgrupperna genom att klicka **[!UICONTROL Edit]** på testgruppskortet i [!UICONTROL Audience Lab] huvudvyn.


## Redigera segmenttestgrupper {#edit-test-groups}

I [!UICONTROL Audience Lab]kan du bara redigera utkasttestgrupper. I [!UICONTROL Create Segment Test Group] guiden kan du spara testgruppen som ett utkast och fortsätta arbeta med den senare.

1. Navigera till [!UICONTROL Audience Lab] huvudvyn.
1. Sök efter dina utkast till testgrupper och välj **[!UICONTROL Edit]** kontrollen på testgruppskortet.
1. Återuppta guiden [Skapa testgrupp](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) för segment och välj **[!UICONTROL Finalize Group]** när du är klar.

## Ta bort segmenttestgrupper {#delete-test-groups}

1. Navigera till [!UICONTROL Audience Lab] huvudvyn.
1. Hitta den testgrupp som du vill ta bort. Du kan antingen:

   * tryck på **[!UICONTROL Delete]** kontrollen i testgruppskortet, eller
   * Tryck på testgruppens titel på testgruppskortet för att gå till vyn [Testgruppsinformation](../../features/audience-lab/audience-lab-information-view.md) och tryck på **[!UICONTROL Delete]** kontrollen i namnlisten.

1. För [slutförda testsegment](../../features/audience-lab/audience-lab.md#status)visas en varning om att du ska hämta CSV-filen för att spara rapporteringen om du vill.
