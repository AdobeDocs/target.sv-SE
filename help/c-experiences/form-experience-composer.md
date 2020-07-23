---
keywords: form-based experience composer;form-based composer;refinements
description: Med den formulärbaserade Experience Composer kan du skapa upplevelser som inte är visuella.
title: Formulärbaserad Experience Composer
topic: Standard
uuid: 6791ed6f-69d0-4ec4-9ea4-47aa92b2a4c9
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 2%

---


# Formulärbaserad Experience Composer{#form-based-experience-composer}

Den formulärbaserade Experience Composer är en icke-visuell upplevelse och erbjuder ett gränssnitt som är användbart när det gäller att skapa upplevelser som kan användas i A/B-tester, Experience Targeting, Automated Personalization och Recommendations när den visuella upplevelsedispositionen inte är tillgänglig eller praktisk att använda. Du kan till exempel använda den formulärbaserade dispositionen för att skapa upplevelser och erbjudanden för e-post, kioskdatorer och röstassistenter.

Om du skapar en rekommendationsaktivitet finns det inga upplevelser. Välj kriterier och design. Om du väljer flera kriterier eller designer genererar Target automatiskt upplevelserna.

1. Klicka **[!UICONTROL Create Activity]** och välj sedan den typ av aktivitet som du vill skapa.

   Den formulärbaserade Experience Composer är tillgänglig för A/B-tester, Experience Targeting, Automated Personalization och Recommendations.
1. Välj **[!UICONTROL Form-Based Experience Composer]** i [!UICONTROL New Activity]dialogrutan.

   Formulärbaserad Experience Composer öppnas.

   ![](assets/location_refinements.png)

   Den här skärmen är annorlunda om du skapar en rekommendationsaktivitet. Rekommendationsaktiviteter omfattar inte upplevelser.
1. Namnge aktiviteten.
1. Välj en plats.

   När du klickar i [!UICONTROL Select Location] rutan visas en lista med tillgängliga platser. Välj en av platserna. Välj &quot;target-global-mbox&quot; om du vill välja den globala plats som levereras via target.js.

   Du kan också ange en plats som inte finns med här. Detta kan vara användbart om mbox ännu inte har skapats eller visats på en sida. Skriv namnet på platsen. Var försiktig när du anger en plats som inte finns än. Om stavningen eller skiftläget inte stämmer överens med stavningen och skiftläget när mbox-anropet görs, kommer aktiviteten inte att levereras. Manuellt angivna platser sparas i listan över tillgängliga platser. Nästa gång du försöker välja en manuellt angiven plats blir den tillgänglig i [!UICONTROL Select Location] listrutan för den aktiviteten.

   >[!NOTE]
   >
   >Om du skapar en manuellt angiven plats när en aktivitet skapas skapas inte en ny plats automatiskt. Platsnamnet sparas bara i aktivitetens sammanhang. Platsen skapas när ett samtal om innehållsleverans sker. Efter den plats som skapas kommer den att vara tillgänglig för användning i andra aktiviteter, för att skapa målgrupper osv. från listrutan med tillgängliga platser.

1. Klicka **[!UICONTROL Add Audience Refinements]** och välj sedan en eller flera [målgrupper](../c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) för aktiviteten.

   ![](assets/location_refinements_2.png)

   I den formulärbaserade Experience Composer har förbättringarna ersatts med full målgruppsfunktionalitet. Förfiningar av befintliga aktiviteter har migrerats till målgrupper som bara är [aktiva](../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).
1. Välj den typ av innehåll som du vill ska visas på den platsen.

   ![](assets/form_content.png)

1. Ange innehållet för den innehållstyp som du valde.

   **Ändra HTML-erbjudande:** Välj ett HTML-erbjudande.

   **Ändra bilderbjudande:** Välj en bild som har sparats i innehållsbiblioteket i Target.

   Du kan också lägga till en länk till en bild (klickfrekvens, mål, landning osv.).

   1. Klicka på [!UICONTROL Change Image Offer].
   1. Markera önskad bild och klicka sedan på [!UICONTROL Edit Links].
   1. Ange önskad URL eller sida på webbplatsen och klicka sedan på [!UICONTROL Update].

   **Ändra JSON-erbjudande:** Välj ett json-erbjudande.

   **Ändra upplevelsefragment:** Välj en upplevelsefragment.

   **Ändra omdirigeringserbjudande:** Välj ett omdirigeringserbjudande.

   **Ändra fjärrerbjudande:** Välj ett fjärrerbjudande.

   **Skapa HTML-erbjudande:**

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

   För en rekommendationsaktivitet visas alternativet Lägg till rekommendation i listrutan Innehåll. Klicka **[!UICONTROL Add Recommendation]** och välj sedan sidtyp. Följ sedan de vanliga stegen som definieras i gränssnittet för att [skapa en Rekommendationer-aktivitet](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   När du väljer rekommendationskriterier i den formulärbaserade Experience Composer finns det nu en direktlänk till det valda kriteriekortet så att du snabbt och enkelt kan redigera villkoren.

   ![](assets/change_criteria.png)

   Från målsidan i Target trestegsbaserade guidade arbetsflöde:

   ![](assets/change_criteria_2.png)

1. (Valfritt, för AB-aktiviteter, Automated Personalization och Experience Targeting) Om du vill upprepa den här processen för ytterligare platser klickar du på **[!UICONTROL Add Location]** och konfigurerar platsen och innehållet.
1. Klicka **[!UICONTROL Next]** och slutför sedan stegen för att skapa aktiviteten som vanligt för din aktivitetstyp.

* [Skapa ett A/B-test](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
* [Skapa en upplevelseinriktad aktivitet](../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Skapa en rekommendationsaktivitet](../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Utbildningsvideo: Formulärbaserad ![självstudiekurs för disposition](/help/assets/tutorial.png)

Den här videon innehåller en demonstration av den formulärbaserade dispositionen.

* Skapa en aktivitet med formulärbaserad Experience Composer
* Förstå när formulärbaserad Experience Composer ska användas jämfört med Visual Experience Composer
* Använd förfiningar för att ange en plats som mål

>[!VIDEO](https://video.tv.adobe.com/v/17390)