---
keywords: formulärbaserad upplevelsedisposition;formulärbaserad disposition;förbättringar
description: Lär dig använda Adobe [!DNL Target] Formulärbaserad Experience Composer för att skapa icke-visuella upplevelser. Använd den här dispositionen när VEC inte är tillgängligt eller inte är praktiskt att använda.
title: Hur använder jag den formulärbaserade Experience Composer?
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: fb9c9e4d2a3d0cf330724dfd02e329fedc388f01
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 2%

---

# Formulärbaserad Experience Composer

The [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] är en icke-visuell upplevelse och erbjuder ett gränssnitt som är användbart när det gäller att skapa upplevelser som ska användas i [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization]och [!UICONTROL Recommendations] verksamhet när [!UICONTROL Visual Experience Composer] (VEC) är inte tillgängligt eller praktiskt att använda. Du kan till exempel använda den formulärbaserade Experience Composer för att skapa upplevelser och erbjudanden för e-post, kioskdatorer och röstassistenter.

Om du skapar en [!UICONTROL Recommendations] aktivitet, det finns inga upplevelser. Välj kriterier och design. Om du väljer flera villkor eller designer [!UICONTROL Target] skapar upplevelserna automatiskt.

1. Klicka **[!UICONTROL Create Activity]** väljer du sedan den typ av aktivitet som du vill skapa.

   The [!UICONTROL Form-Based Experience Composer] är tillgängligt för [!UICONTROL A/B Test], [!UICONTROL Experience Targeting], [!UICONTROL Automated Personalization]och [!UICONTROL Recommendations] verksamhet.

1. Välj **[!UICONTROL Form]** från [!UICONTROL Create Activity] -dialogrutan.

1. (Villkorligt) Välj en arbetsyta och en egenskap.

1. Klicka på **[!UICONTROL Next]**.

   The [!UICONTROL Form-Based Experience Composer] öppnas.

   ![](assets/location_refinements.png)

   Den här skärmen är annorlunda om du skapar en [!UICONTROL Recommendations] aktivitet. [!UICONTROL Recommendations] aktiviteter omfattar inte upplevelser.

1. Namnge aktiviteten genom att klicka på &quot;[!UICONTROL Untitled Activity].&quot;
1. Välj en plats.

   När du klickar på [!UICONTROL Select Location] visas en lista med tillgängliga platser. Välj en av platserna.

   Du kan också ange en plats som inte finns med här. Detta kan vara användbart om mbox ännu inte har skapats eller visats på en sida. Skriv namnet på platsen. Var försiktig när du anger en plats som inte finns än. Om stavningen eller skiftläget inte stämmer överens med stavningen och skiftläget när mbox-anropet görs, kommer aktiviteten inte att levereras. Manuellt angivna platser sparas i listan över tillgängliga platser. Nästa gång du försöker välja en manuellt angiven plats blir den tillgänglig på [!UICONTROL Select Location] nedrullningsbar lista för den aktiviteten.

   >[!NOTE]
   >
   >Om du skapar en manuellt angiven plats när en aktivitet skapas skapas inte en ny plats automatiskt. Platsnamnet sparas bara i aktivitetens sammanhang. Platsen skapas när ett samtal om innehållsleverans sker. Efter den plats som skapas kommer den att vara tillgänglig för användning i andra aktiviteter, för att skapa målgrupper osv. från listrutan med tillgängliga platser.

1. Klicka **[!UICONTROL Add Audience Refinements]** väljer du en eller flera [publik](/help/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) för den här aktiviteten klickar du på **[!UICONTROL Done]**.

   ![](assets/location_refinements_2.png)

   I [!UICONTROL Form-based Experience Composer], har finjusteringarna ersatts med full målgruppsfunktionalitet. Förfiningar för befintliga aktiviteter har migrerats till [målgrupper endast för aktivitet](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. Välj den typ av innehåll som du vill ska visas på den platsen.

   ![](assets/form_content.png)

1. Ange innehållet för den innehållstyp som du valde.

   **Erbjudande om byte av HTML:** Välj ett HTML-erbjudande.

   **Ändra bilderbjudande:** Välj en bild som har sparats i innehållsbiblioteket i Target.

   Du kan också lägga till en länk till en bild (klickfrekvens, mål, landning osv.).

   1. Klicka på [!UICONTROL Change Image Offer].
   1. Markera önskad bild och klicka sedan på [!UICONTROL Edit Links].
   1. Ange önskad URL eller sida på webbplatsen och klicka sedan på [!UICONTROL Update].

   **Ändra JSON-erbjudande:** Välj ett json-erbjudande.

   **Ändra upplevelsefragment:** Välj en upplevelsefragment. Mer information finns i [Experience Fragment](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

   **Ändra omdirigeringserbjudande:** Välj ett omdirigeringserbjudande. Mer information finns i [Skapa omdirigeringserbjudanden](/help/c-experiences/c-manage-content/offer-redirect.md).

   **Ändra fjärrerbjudande:** Välj ett fjärrerbjudande. Mer information finns i [Skapa fjärrerbjudanden](/help/c-experiences/c-manage-content/about-remote-offers.md).

   **Skapa HTML:**

   1. Klicka på [!UICONTROL Offers] och välj sedan fliken [!UICONTROL Code Offers].
   1. Klicka på [!UICONTROL Create] > [!UICONTROL HTML Offer].
   1. Skriv ett erbjudandenamn.
   1. Skriv eller klistra in HTML-koden i rutan Kod.
   1. Klicka på [!UICONTROL Save].

   **Skapa JSON-erbjudande:**

   1. Klicka på [!UICONTROL Offers] och välj sedan fliken [!UICONTROL Code Offers].
   1. Klicka på [!UICONTROL Create] > [!UICONTROL JSON Offer].
   1. Skriv ett erbjudandenamn.
   1. Skriv eller klistra in JSON-koden i rutan Kod.
   1. Klicka på [!UICONTROL Save].

   **Lägg till rekommendation:**

   När det gäller en Recommendations-aktivitet kan du använda listrutan Innehåll till att [!UICONTROL Add Recommendation] alternativ. Klicka **[!UICONTROL Add Recommendation]** väljer du sedan sidtyp. Följ sedan de vanliga stegen som definieras i gränssnittet för att [skapa en Recommendations-aktivitet](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   När du väljer Recommendations-villkor i den formulärbaserade Experience Composer finns det nu en direktlänk till det valda kriteriekortet så att du snabbt och enkelt kan redigera villkoren.

   ![](assets/change_criteria.png)

   Från målsidan i det guidade arbetsflödet i tre steg:

   ![](assets/change_criteria_2.png)

   **Beslut om att lägga till erbjudande:**

   Lägg till ett erbjudande som skapats i [!DNL Adobe Journey Optimizer] (AJO) till en [!DNL Adobe Target] aktivitet för att presentera det bästa dynamiska erbjudandet och upplevelsen för besökarna på er webbplats eller mobilwebbplats med hjälp av offer decisioning. Det här alternativet är tillgängligt för manuell [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] (XT) endast aktiviteter.

   Mer information finns i [Använd offertbeslut](/help/c-integrating-target-with-mac/ajo/offer-decision.md).

1. (Valfritt, för [!UICONTROL A/B Test], [!UICONTROL Automated Personalization]och [!UICONTROL Experience Targeting] aktiviteter) Om du vill upprepa den här processen för ytterligare platser klickar du på **[!UICONTROL Add Location]** och konfigurera platsen och innehållet.
1. Klicka **[!UICONTROL Next]** slutför du stegen för att skapa aktiviteten som vanligt för din aktivitetstyp.

* [Skapa ett A/B-test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [Skapa en upplevelseinriktad aktivitet](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Skapa en Recommendations-aktivitet](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Utbildningsvideo: Formulärbaserad disposition ![Självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller en demonstration av den formulärbaserade dispositionen.

* Skapa en aktivitet med formulärbaserad Experience Composer
* Förstå när formulärbaserad Experience Composer ska användas jämfört med Visual Experience Composer
* Använd förfiningar för att ange en plats som mål

>[!VIDEO](https://video.tv.adobe.com/v/17390)
