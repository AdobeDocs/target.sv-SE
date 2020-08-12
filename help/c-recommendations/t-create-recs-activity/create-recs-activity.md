---
keywords: create recommendations;recommendations activity;new recommendations;recommendations overview
description: Använd Target Visual Experience Composer (VEC) för att skapa en Recommendations-aktivitet direkt på en Target-aktiverad sida och för att ändra delar av sidan i Target.
title: Skapa en Recommendations-aktivitet
feature: null
uuid: c3f22cce-204a-4509-92c4-8fec43fbaebe
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Skapa en Recommendations-aktivitet{#create-a-recommendations-activity}

Använd Target Visual Experience Composer (VEC) för att skapa en Recommendations-aktivitet direkt på en Target-aktiverad sida och för att ändra delar av sidan i Target.

1. Klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL Recommendations]**.

   ![Skapa Recommendations-aktivitet](/help/c-recommendations/t-create-recs-activity/assets/Menu_CreateActivity.png)

1. Välj **[!UICONTROL Visual (Default)]** vid behov.

   ![Skapa Recommendations Activity (dialogruta)](/help/c-recommendations/t-create-recs-activity/assets/DB_NewRecAct.png)

   Om du föredrar att använda formulärbaserad Experience Composer väljer du [!UICONTROL Form]. Mer information finns i [Formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md) .

   >[!NOTE]
   >
   >Förutom VEC och Form-Based Experience Composer erbjuder Target Single Page Application VEC och VEC for Mobile Apps. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsökning i Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)om det uppstår problem.
   >
   >Alternativet [!UICONTROL [Choose Workplace](/help/administrating-target/c-user-management/property-channel/property-channel.md) i föregående bild är en [Target Premium](/help/c-intro/intro.md) -funktion. Din organisation har en Target Standard-licens om du inte ser det här alternativet.]

1. (Villkorligt) Om du är [Target Premium-kund](/help/c-intro/intro.md#premium)väljer du en [arbetsyta](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Ange en aktivitets-URL och klicka sedan på **[!UICONTROL Next]**.

   >[!NOTE]
   >
   >[!DNL Target] skiljer inte mellan URL-protokoll ( [!DNL https] och [!DNL http]). Resultatet blir att [!DNL `http://www.adobe.com`] och [!DNL `https://wwww.adobe.com`] båda matchar.

   Aktivitets-URL är den sida där rekommendationerna ska visas.

   När du klickar [!UICONTROL Next]öppnas VEC och sidan visas. Du kan ersätta ett aktuellt element med rekommendationer eller infoga rekommendationer.

1. Klicka på ett element på sidan och om det finns rekommendationer för var elementet finns klickar du på **[!UICONTROL Replace w/ Recommendations]**, **[!UICONTROL Insert Recommendations Before]** eller **[!UICONTROL Insert Recommendations After]**.

   ![Recommendations](/help/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   Om du ersätter ett element med rekommendationer tas det aktuella innehållet bort och ersätts med dina rekommendationer.

1. Välj en sidtyp.

   Sidtyper kan vara:

   * Kundsida
   * Kategorisida
   * Hemsida
   * Landningssida
   * Produktsida
   * Sökresultatsida
   * Tack
   * Övriga

   ![Välj alternativ för sidtyp](/help/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. Markera ett eller flera [villkor](/help/c-recommendations/c-algorithms/algorithms.md).

   Kriterierna visas som kort som visar information om varje villkor. Som standard visas villkor som är kompatibla med vertikalt i branschen och den sidtyp som du har valt på skärmen. [!UICONTROL Select Criteria] Du kan ändra de här alternativen om du vill visa andra villkor.

   >[!NOTE]
   >
   >Alla villkor fungerar inte korrekt på alla sidor. Sidan eller mbox måste skickas `entity.id` eller `entity.categoryId` för att aktuella artikel/aktuella kategorirekommendationer ska vara kompatibla. I allmänhet är det bäst att bara visa kompatibla villkor. Om du vill att inkompatibla villkor ska vara tillgängliga för aktiviteten avmarkerar du **[!UICONTROL Compatible]** kryssrutan. Det [!UICONTROL Compatible] här alternativet kanske inte visas beroende på dina Recommendations-inställningar ( **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** > **[!UICONTROL Filter Incompatible Criteria]**). Mer information finns i [Inställningar](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84).

   ![Välj villkor, dialogruta](/help/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   Om du väljer flera villkor delas trafiken jämnt mellan de valda villkoren. Om du till exempel har valt två villkor och din aktivitet är utformad för att visa standardinnehåll för 20 % av aktivitetsinspelarna, så ser 40 % av aktivitetsinspelarna rekommendationerna som styrs av respektive villkor. Det finns inget alternativ för att ändra procentsatserna för varje villkor.

   * Om du vill söka efter ett befintligt villkor (t.ex. om ett stort antal villkorskort visas) skriver du i sökfältet tills det önskade villkoret visas, markerar villkoret och klickar sedan på **[!UICONTROL Next]**.

      Vissa villkor ingår [!DNL Recommendations]. Du och ditt team kan också skapa egna kriterier.

   * Om du vill skapa ett nytt villkor klickar du på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]** och fyller sedan i informationen för det nya villkoret. Mer information om hur du skapar nya villkor finns i [Skapa villkor](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).
   * Du kan också gruppera villkor i sekvenser. Om du vill skapa en ny villkorssekvens klickar du på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. Mer information finns i [Skapa villkorssekvenser](../../c-recommendations/c-algorithms/create-criteria-sequence.md#task_8A9CB465F28D44899F69F38AD27352FE) .

1. Klicka på **[!UICONTROL Next]**.
1. Välj en [design](/help/c-recommendations/c-design-overview/design-overview.md).

   En design är en mall som bestämmer utseendet på platserna på sidan. [!DNL Target] innehåller flera förkonfigurerade designer. Du kan också skapa egna designer. Mer information finns i [Skapa en design](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14) och [Anpassa en design](../../c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59).

   ![Välj design, dialogruta](/help/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   Varje design visar en grafisk representation av hur den kommer att se ut, och ikoner som visar hur många av dina aktiva och inaktiva aktiviteter som för närvarande använder den designen.

   * Om du vill markera en eller flera befintliga designer klickar du på dem och sedan på **[!UICONTROL Next]**.

      Om du har valt flera villkor kan du bara välja en design.

   * Om du vill skapa en egen design klickar du på **[!UICONTROL Create Design]** och fyller sedan i namnet och koden för den nya designen. Klicka **[!UICONTROL Next]**, markera eller överför en bild och klicka på **[!UICONTROL Done]** > **[!UICONTROL Done]**. Mer information om hur du skapar en ny design finns i [Skapa en design](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Klicka på **[!UICONTROL Next]**.

   Du kan lägga till kampanjer i dina rekommendationer. Mer information om att lägga till kampanjer framför och under finns i [Lägga till kampanjer](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14).
1. Klicka på **[!UICONTROL Save]**.

   VEC-skärmen visar rekommendationsdesignen på din sida.

1. (Valfritt) Klicka **[!UICONTROL Preview]** för att se hur aktiviteten kommer att se ut för besökarna.

   [!UICONTROL Preview] Med det här läget kan du interagera med dina rekommendationer, precis som en besökare skulle göra.

   När du är klar med förhandsgranskningen av dina rekommendationer klickar du på **[!UICONTROL Compose]**.

1. Granska din rekommendation i VEC och klicka sedan på **[!UICONTROL Next]**.

1. Granska din [!DNL Recommendations] aktivitet i flödesdiagrammet och gör nödvändiga ändringar.

   ![Recommendations-flödesdiagram](/help/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   Flödesdiagrammet leder dig genom stegen för att välja målgrupp för aktiviteten, skapa upplevelser och specificera framgångsmått.

   I flödesdiagrammet kan du göra följande:

   * Ändra målgruppen som ska se rekommendationerna

      >[!NOTE]
      >
      >Förutom att välja en befintlig målgrupp kan ni [skapa en målgrupp](../../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) som bara är aktiv eller [kombinera flera målgrupper](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp.

      Som standard ser alla användare rekommendationerna. Men ni kan rikta rekommendationen till en viss målgrupp.

      För en [!DNL Recommendations] aktivitet ser kontrollgruppen sidan utan några rekommendationer.

   * Visa villkoren
   * Ändra samlingen (bredvid [!UICONTROL Criteria] etiketten)
   * Ändra procentandelen deltagare som ser kontrollupplevelsen
   * Visa designkoden
   * Ändra eller ta bort en design

1. Klicka **[!UICONTROL Next]** när du är klar.
1. Ange dina aktivitetsinställningar.

   Skriv till exempel ett namn (obligatoriskt) och mål (valfritt) för aktiviteten. Mer information om inställningarna finns i [Recommendations aktivitetsinställningar](../../c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB).

   >[!NOTE]
   >
   >Om du anger ett [!DNL Recommendation] aktivitetsnamn som redan finns för en annan aktivitet i [!DNL Recommendations Classic]synkroniseras den nya aktiviteten med ett nytt namn. Det nya namnet är det ursprungliga namnet som har lagts till med en tidsstämpel för att göra det unikt. Det nya namnet visas både i [!DNL Target Standard/Premium] och [!DNL Recommendations Classic].

1. När du är klar klickar du på **[!UICONTROL Save & Close]**.

   En översikt över din aktivitet visas.

   Från [!UICONTROL Overview] sidan kan du:

   * Aktivera aktiviteten
   * Redigera aktiviteten
   * Fäst aktiviteten på ditt Experience Cloud-bord
   * Visa dina upplevelse-URL:er
   * Hämta data
   * Ändra procentandelen aktivitetsdeltagare som ser kontrollupplevelsen
   * Visa eller dölja villkorsinformation
   * Visa koden för dina designer

1. (Valfritt) Öppna [!UICONTROL Reports] sidan om du vill visa rapporten som visar hur din [!DNL Recommendations] aktivitet fungerar.
1. (Valfritt) Öppna [!UICONTROL Collisions] sidan om du vill visa [aktivitetskonflikter](/help/c-experiences/c-visual-experience-composer/activity-collisions.md) som kan uppstå.

   Aktivitetskonflikter inträffar när flera aktiviteter är inställda på att leverera innehåll till samma sida, vilket kan göra att oväntat innehåll visas.

## Utbildningsvideo: Skapa en Recommendations-aktivitet (7:15) - ![självstudiemärke](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/27688)