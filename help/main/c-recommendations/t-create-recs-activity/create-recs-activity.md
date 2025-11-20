---
keywords: skapa rekommendationer;rekommendationsaktivitet;nya rekommendationer;rekommendationer översikt
description: Lär dig hur du använder  [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC) för att skapa en [!DNL Recommendations] aktivitet.
title: Hur skapar jag en [!DNL Recommendations] aktivitet?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: c83073d5-f852-4f09-8343-e4658fbf6f43
source-git-commit: 32b3a93b30c6ca6f7576be5dbb25b476167b33b7
workflow-type: tm+mt
source-wordcount: '1201'
ht-degree: 0%

---

# Skapa en [!DNL Recommendations]-aktivitet

Använd [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC) för att skapa en [!DNL Recommendations]-aktivitet direkt på en [!DNL Target]-aktiverad sida och för att ändra delar av sidan i [!DNL Target].

1. Klicka på **[!UICONTROL Activities]** > **[!UICONTROL Create Activity]** > **[!UICONTROL Recommendations]**.

1. Välj **[!UICONTROL Visual]** om det behövs.

   Om du föredrar att använda [!UICONTROL Form-Based Experience Composer] väljer du [!UICONTROL Form]. Mer information finns i [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md).

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer] erbjuder [!DNL Target] VEC:n [!UICONTROL Single Page Application]. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/main/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsökning av Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md) om du har problem.

1. (Villkorligt) Välj en [arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Ange en aktivitets-URL och klicka sedan på **[!UICONTROL Create]**.

   >[!NOTE]
   >
   >[!DNL Target] skiljer inte mellan URL-protokoll ( [!DNL https] och [!DNL http]). Därför matchar både [!DNL `http://www.adobe.com`] och [!DNL `https://wwww.adobe.com`].

   Aktivitets-URL:en är sidan där rekommendationerna visas.

   När du klickar på [!UICONTROL Create] öppnas VEC och din sida visas. Du kan ersätta ett aktuellt element med rekommendationer eller infoga rekommendationer.

1. Klicka på ett element på sidan och klicka sedan på **[!UICONTROL Replace w/ Recommendations]**, **[!UICONTROL Insert Recommendations Before]** eller **[!UICONTROL Insert Recommendations After]** om det finns rekommendationer för var elementet finns.

   >[!NOTE]
   >
   >[!UICONTROL Recommendations] aktiviteter stöder endast en ändring/rekommendation åt gången. För flera rekommendationer kan du antingen skapa flera [!DNL Recommendations]-aktiviteter eller använda A/B- eller XT-testning.

   Besökare på webbplatsen kan bara se det rekommenderade innehållet om de är berättigade till rekommendationen. Besökare som inte är kvalificerade för rekommendationen kommer att se standardinnehållet.

   ![Rekommendationsalternativ](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   * **[!UICONTROL Replace w/ Recommendations]**: Om du ersätter ett element med rekommendationer tas det aktuella innehållet bort och ersätts med dina rekommendationer. När besökare besöker din webbplats och är kvalificerade för rekommendationen, ser de rekommenderade objekten i det angivna området i stället för det befintliga innehållet.
   * **[!UICONTROL Insert Recommendations Before]**: Om du infogar rekommendationer före det valda elementet placeras det rekommenderade innehållet före det elementet. Beroende på hur sidan är uppbyggd visas rekommendationen ovanför eller till vänster om det markerade elementet.
   * **[!UICONTROL Insert Recommendations After]**: Om du infogar rekommendationer efter det valda elementet placeras det rekommenderade innehållet efter det elementet. Beroende på hur sidan är uppbyggd visas rekommendationen nedanför eller till höger om det markerade elementet.

   Med alternativet **[!UICONTROL Expand Selection]** kan du expandera den valda platsen (överordnad behållare) så att du enklare kan identifiera och ta med de önskade sidelementen.

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

   ![Välj sidtypsalternativ](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. Välj ett eller flera [villkor](/help/main/c-recommendations/c-algorithms/algorithms.md).

   Kriterierna visas som kort som visar information om varje villkor. Som standard visar skärmen [!UICONTROL Select Criteria] villkor som är kompatibla med din vertikala bransch och den sidtyp du valde i föregående steg. Du kan ändra de här alternativen om du vill visa andra villkor.

   >[!NOTE]
   >
   >Alla villkor fungerar inte korrekt på alla sidor. Sidan eller mbox måste skickas `entity.id` eller `entity.categoryId` för att aktuella rekommendationer för objekt/aktuell kategori ska vara kompatibla. I allmänhet är det bäst att bara visa kompatibla villkor. Om du vill att inkompatibla villkor ska vara tillgängliga för aktiviteten avmarkerar du kryssrutan **[!UICONTROL Compatible]**. Alternativet [!UICONTROL Compatible] kanske inte visas, beroende på dina rekommendationer ( **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** > **[!UICONTROL Filter Incompatible Criteria]**). Mer information finns i [Inställningar](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}.

   ![Dialogrutan Välj villkor](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   Om du väljer flera villkor delas trafiken jämnt mellan de valda villkoren. Om du till exempel har valt två villkor och din aktivitet är utformad för att visa standardinnehåll för 20 % av aktivitetsinspelarna, så ser 40 % av aktivitetsinspelarna rekommendationerna som styrs av respektive villkor. Det finns inget alternativ för att ändra procentsatserna för varje villkor.

   * Om du vill söka efter ett befintligt villkor (till exempel om ett stort antal villkorskort visas) skriver du i sökfältet tills de önskade villkoren visas, markerar villkoren och klickar sedan på **[!UICONTROL Next]**.

     Vissa villkor ingår i [!DNL Recommendations]. Du och ditt team kan också skapa egna kriterier.

   * Om du vill skapa ett nytt villkor klickar du på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]** och fyller sedan i informationen för det nya villkoret. Mer information om hur du skapar nya villkor finns i [Skapa villkor](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).
   * Du kan också gruppera villkor i sekvenser. Om du vill skapa en ny villkorssekvens klickar du på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. Mer information finns i [Skapa villkorssekvens](/help/main/c-recommendations/c-algorithms/create-criteria-sequence.md).

1. Klicka på **[!UICONTROL Next]**.
1. Välj en [design](/help/main/c-recommendations/c-design-overview/design-overview.md).

   En design är en mall som bestämmer utseendet på platserna på sidan. [!DNL Target] innehåller flera förkonfigurerade designer. Du kan också skapa egna designer. Mer information finns i [Skapa en design](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14) och [Anpassa en design](/help/main/c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59).

   ![Dialogrutan Välj design](/help/main/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   Varje design visar en grafisk representation av hur den kommer att se ut, och ikoner som visar hur många av dina aktiva och inaktiva aktiviteter som för närvarande använder den designen.

   * Om du vill markera en eller flera befintliga designer klickar du på dem och sedan på **[!UICONTROL Next]**.

     Om du har valt flera villkor kan du bara välja en design.

   * Om du vill skapa en anpassad design klickar du på **[!UICONTROL Create Design]** och fyller sedan i namnet och koden för den nya designen. Klicka på **[!UICONTROL Next]**, markera eller överför en bild och klicka på **[!UICONTROL Done]** > **[!UICONTROL Done]**. Mer information om hur du skapar en ny design finns i [Skapa en design](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Klicka på **[!UICONTROL Next]**.

   Du kan lägga till kampanjer i dina rekommendationer. Mer information om hur du lägger till kampanjer på framsidan och baksidan finns i [Lägga till kampanjer](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Klicka på **[!UICONTROL Save]**.

   VEC-skärmen visar rekommendationsdesignen på din sida.

1. (Valfritt) Klicka på **[!UICONTROL Preview]** för att se hur aktiviteten kommer att se ut för besökarna.

   I [!UICONTROL Preview]-läget kan du interagera med dina rekommendationer, precis som en besökare skulle göra.

   När du har förhandsgranskat dina rekommendationer klickar du på **[!UICONTROL Compose]**.

1. Granska din rekommendation i VEC och klicka sedan på **[!UICONTROL Next]**.

1. Granska din [!DNL Recommendations]-aktivitet i flödesdiagrammet och gör nödvändiga ändringar.

   ![Rekommendationsflödesdiagram](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   Flödesdiagrammet leder dig genom stegen för att välja målgrupp för aktiviteten, skapa upplevelser och specificera framgångsmått.

   I flödesdiagrammet kan du göra följande:

   * Ändra målgruppen som ska se rekommendationerna

     >[!NOTE]
     >
     >Förutom att välja en befintlig målgrupp kan du [skapa en målgrupp som bara är aktiv](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) eller [kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) för att skapa ad hoc-målgrupper i stället för att skapa en ny målgrupp.

     Som standard ser alla användare rekommendationerna. Men ni kan rikta rekommendationen till en viss målgrupp.

     För en [!DNL Recommendations]-aktivitet ser kontrollgruppen sidan utan några rekommendationer.

   * Visa villkoren
   * Ändra samlingen (bredvid etiketten [!UICONTROL Criteria])
   * Ändra procentandelen deltagare som ser kontrollen
   * Visa designkoden
   * Ändra eller ta bort en design

1. Klicka på **[!UICONTROL Next]** när du är klar.
1. Ange dina aktivitetsinställningar.

   Skriv till exempel ett namn (obligatoriskt) och mål (valfritt) för aktiviteten. Mer information om inställningarna finns i [Rekommendationer för aktivitetsinställningar](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB).

   >[!NOTE]
   >
   >Om du anger ett [!DNL Recommendation]-aktivitetsnamn som redan finns för en annan aktivitet i [!DNL Recommendations Classic] synkroniseras den nya aktiviteten med ett nytt namn. Det nya namnet är det ursprungliga namnet som har lagts till med en tidsstämpel för att göra det unikt. Det nya namnet visas både i [!DNL Target Standard/Premium] och [!DNL Recommendations Classic].

1. När du är klar klickar du på **[!UICONTROL Save & Close]**.

   En översikt över din aktivitet visas.

   Från sidan [!UICONTROL Overview] kan du:

   * Aktivera aktiviteten
   * Redigera aktiviteten
   * Dela aktiviteten med din Experience Cloud-feed
   * Fråga aktiviteten
   * Visa dina upplevelse-URL:er
   * Hämta data
   * Ändra procentandelen aktivitetsdeltagare som ser kontrollupplevelsen
   * Visa eller dölj villkorsinformation
   * Visa koden för dina designer

1. (Valfritt) Öppna sidan [!UICONTROL Reports] om du vill visa rapporten som visar prestanda för din [!DNL Recommendations]-aktivitet.

1. (Valfritt) Öppna sidan [!UICONTROL Collisions] om du vill visa eventuella [aktivitetskonflikter](/help/main/c-experiences/c-visual-experience-composer/activity-collisions.md) som kan uppstå.

   Aktivitetskonflikter inträffar när flera aktiviteter är inställda på att leverera innehåll till samma sida, vilket kan göra att oväntat innehåll visas.

## Utbildningsvideo: Skapa en rekommendationsaktivitet (7:15) ![Självstudiekurs](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/27688)
