---
keywords: form-based experience composer;form-based composer;refinements
description: Med Adobe Target Form-Based Experience Composer kan man skapa upplevelser som inte är visuella.
title: Formulärbaserad Experience Composer
feature: Form-based Experience Composer
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 2%

---


# Formulärbaserad Experience Composer{#form-based-experience-composer}

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] är en icke-visuell upplevelse och erbjuder ett gränssnitt som är användbart när det gäller att skapa upplevelser som kan användas i A/B-tester, Experience Targeting, Automated Personalization och Recommendations när den visuella upplevelsedispositionen inte är tillgänglig eller praktisk att använda. Du kan till exempel använda den formulärbaserade dispositionen för att skapa upplevelser och erbjudanden för e-post, kioskdatorer och röstassistenter.

Om du skapar en Recommendations-aktivitet finns det inga upplevelser. Välj kriterier och design. Om du väljer flera kriterier eller designer genererar Target automatiskt upplevelserna.

1. Klicka på **[!UICONTROL Create Activity]** och välj sedan den typ av aktivitet som du vill skapa.

   Den formulärbaserade Experience Composer är tillgänglig för A/B-tester, Experience Targeting, Automated Personalization och Recommendations-aktiviteter.
1. Välj **[!UICONTROL Form-Based Experience Composer]** i dialogrutan [!UICONTROL New Activity].

   Formulärbaserad Experience Composer öppnas.

   ![](assets/location_refinements.png)

   Den här skärmen är annorlunda om du skapar en Recommendations-aktivitet. Recommendations verksamhet omfattar inte upplevelser.
1. Namnge aktiviteten.
1. Välj en plats.

   När du klickar i rutan [!UICONTROL Select Location] visas en lista med tillgängliga platser. Välj en av platserna. Välj &quot;target-global-mbox&quot; om du vill välja den globala plats som levereras via target.js.

   Du kan också ange en plats som inte finns med här. Detta kan vara användbart om mbox ännu inte har skapats eller visats på en sida. Skriv namnet på platsen. Var försiktig när du anger en plats som inte finns än. Om stavningen eller skiftläget inte stämmer överens med stavningen och skiftläget när mbox-anropet görs, kommer aktiviteten inte att levereras. Manuellt angivna platser sparas i listan över tillgängliga platser. Nästa gång du försöker välja en manuellt angiven plats blir den tillgänglig i listrutan [!UICONTROL Select Location] för den aktiviteten.

   >[!NOTE]
   >
   >Om du skapar en manuellt angiven plats när en aktivitet skapas skapas inte en ny plats automatiskt. Platsnamnet sparas bara i aktivitetens sammanhang. Platsen skapas när ett samtal om innehållsleverans sker. Efter den plats som skapas kommer den att vara tillgänglig för användning i andra aktiviteter, för att skapa målgrupper osv. från listrutan med tillgängliga platser.

1. Klicka på **[!UICONTROL Add Audience Refinements]** och välj sedan en eller flera [målgrupper](/help/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) för den här aktiviteten.

   ![](assets/location_refinements_2.png)

   I den formulärbaserade Experience Composer har förbättringarna ersatts med full målgruppsfunktionalitet. Förfiningar för befintliga aktiviteter har migrerats till [målgrupper som bara är aktiva](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).
1. Välj den typ av innehåll som du vill ska visas på den platsen.

   ![](assets/form_content.png)

1. Ange innehållet för den innehållstyp som du valde.

   **Ändra HTML-erbjudande:** Välj ett HTML-erbjudande.

   **Erbjudande om ändring av bild:** Välj en bild som sparats i innehållsbiblioteket i Target.

   Du kan också lägga till en länk till en bild (klickfrekvens, mål, landning osv.).

   1. Klicka på [!UICONTROL Change Image Offer].
   1. Markera önskad bild och klicka sedan på [!UICONTROL Edit Links].
   1. Ange önskad URL eller sida på platsen och klicka sedan på [!UICONTROL Update].

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

   För en Recommendations-aktivitet visas alternativet Lägg till rekommendation i listrutan Innehåll. Klicka på **[!UICONTROL Add Recommendation]** och välj sedan sidtyp. Följ sedan de vanliga stegen som definieras i gränssnittet för att [skapa en Recommendations-aktivitet](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   När du väljer Recommendations-villkor i den formulärbaserade Experience Composer finns det nu en direktlänk till det valda kriteriekortet så att du snabbt och enkelt kan redigera villkoren.

   ![](assets/change_criteria.png)

   Från målsidan i det guidade arbetsflödet i tre steg:

   ![](assets/change_criteria_2.png)

1. (Valfritt, för AB-aktiviteter, Automated Personalization och Experience Targeting) Om du vill upprepa den här processen för ytterligare platser klickar du på **[!UICONTROL Add Location]** och konfigurerar platsen och innehållet.
1. Klicka på **[!UICONTROL Next]** och slutför sedan stegen för att skapa aktiviteten som vanligt för din aktivitetstyp.

* [Skapa ett A/B-test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [Skapa en upplevelseinriktad aktivitet](/help/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Skapa en Recommendations-aktivitet](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Utbildningsvideo: Formulärbaserad disposition ![Tutorial badge](/help/assets/tutorial.png)

Den här videon innehåller en demonstration av den formulärbaserade dispositionen.

* Skapa en aktivitet med formulärbaserad Experience Composer
* Förstå när formulärbaserad Experience Composer ska användas jämfört med Visual Experience Composer
* Använd förfiningar för att ange en plats som mål

>[!VIDEO](https://video.tv.adobe.com/v/17390)