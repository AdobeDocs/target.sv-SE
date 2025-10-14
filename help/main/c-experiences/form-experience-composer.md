---
keywords: formulärbaserad upplevelsedisposition;formulärbaserad disposition;förbättringar
description: Lär dig hur du använder den formulärbaserade Adobe [!DNL Target] Experience Composer för att skapa upplevelser som inte är visuella. Använd den här dispositionen när VEC inte är tillgängligt eller inte kan användas.
title: Hur använder jag den formulärbaserade Experience Composer?
feature: Form-based Experience Composer
exl-id: d06a271b-f058-4c83-af75-da2a29774967
source-git-commit: 2f86c9ee89b4e1698180f6b3dc9df393733eb780
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 1%

---

# Formulärbaserad Experience Composer

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] är en icke-visuell upplevelse och erbjuder ett gränssnitt som är användbart när det gäller att skapa upplevelser som ska användas i [!UICONTROL A/B Test]-, [!UICONTROL Experience Targeting]-, [!UICONTROL Automated Personalization]- och [!UICONTROL Recommendations]-aktiviteter när [!UICONTROL Visual Experience Composer] (VEC) inte är tillgängligt eller praktiskt för användning. Du kan till exempel använda den formulärbaserade Experience Composer för att skapa upplevelser och erbjudanden för e-post, kioskdatorer och röstassistenter.

Om du skapar en [!UICONTROL Recommendations]-aktivitet finns det inga upplevelser. Välj kriterier och design. Om du väljer flera kriterier eller designer genererar [!UICONTROL Target] automatiskt upplevelserna.

1. Klicka på **[!UICONTROL Create Activity]** och välj sedan den typ av aktivitet som du vill skapa.

   [!UICONTROL Form-Based Experience Composer] är tillgängligt för [!UICONTROL A/B Test]-, [!UICONTROL Experience Targeting]-, [!UICONTROL Automated Personalization]- och [!UICONTROL Recommendations]-aktiviteter.

1. Välj **[!UICONTROL Form]** i dialogrutan [!UICONTROL Create Activity].

1. (Villkorligt) Om du är [Target Premium-kund](/help/main/c-intro/intro.md#premium) väljer du en **[!UICONTROL Choose Workspace]** arbetsyta[&#x200B; i listrutan &#x200B;](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) .

   Alternativet [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) är en [&#x200B; Target Premium](/help/main/c-intro/intro.md)-funktion och kanske inte visas om din organisation har en [!UICONTROL Target Standard]-licens.

1. Välj en egenskap.

1. Klicka på **[!UICONTROL Create]**.

   [!UICONTROL Form-Based Experience Composer] öppnas.

   Den här skärmen är annorlunda om du skapar en [!UICONTROL Recommendations]-aktivitet. [!UICONTROL Recommendations] aktiviteter inkluderar inte upplevelser.

1. &#x200B;
   1. Klicka på ikonen **[!UICONTROL Rename]** ( ![Byt namn &#x200B;](/help/main/assets/icons/MoreSmallListVert.svg) ), klicka på **[!UICONTROL Rename]**, ange ett namn för aktiviteten och klicka sedan på **[!UICONTROL Save]**.

   Aktivitetsnamnet får inte börja med något av följande tecken:

   | Tecken | Beskrivning |
   |--- |--- |
   | `=` | Lika med |
   | `+` | Plus |
   | `-` | Minus |
   | `@` | Vid tecken |

   Aktivitetsnamnet får inte innehålla någon av följande teckensekvenser:

   | Teckensekvens | Beskrivning |
   |--- |--- |
   | ;= | Semikolon, lika med |
   | ;+ | Semikolon, Plus |
   | ;- | Semikolon, minus |
   | ;@ | Semikolon, tecken |
   | ,= | Komma, motsvarar |
   | ,+ | komma, plus |
   | ,- | Komma, Minus |
   | ,@ | Komma, Vid tecken |
   | `[`&quot; | Öppen hakparentes, dubbla citattecken |
   | &quot;`]` | Dubbla citattecken, avslutande hakparentes |

1. Välj en plats.

   När du klickar i rutan [!UICONTROL Select Location] visas en lista med tillgängliga platser. Välj en av platserna.

   Du kan också ange en plats som inte finns med här. Detta kan vara användbart om mbox ännu inte har skapats eller visats på en sida. Skriv namnet på platsen. Var försiktig när du anger en plats som inte finns än. Om stavningen eller skiftläget inte stämmer överens med stavningen och skiftläget när mbox-anropet görs, kommer aktiviteten inte att levereras. Manuellt angivna platser sparas i listan över tillgängliga platser. Nästa gång du försöker välja en manuellt angiven plats blir den tillgänglig i listrutan [!UICONTROL Select Location] för den aktiviteten.

   >[!NOTE]
   >
   >Om du skapar en manuellt angiven plats när en aktivitet skapas skapas inte en ny plats automatiskt. Platsnamnet sparas bara i aktivitetens sammanhang. Platsen skapas när ett samtal om innehållsleverans sker. Efter den plats som skapas kommer den att vara tillgänglig för användning i andra aktiviteter, för att skapa målgrupper osv. från listrutan med tillgängliga platser.

1. Klicka på **[!UICONTROL Add Audience Refinements]**, välj en eller flera [målgrupper](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) för den här aktiviteten och klicka sedan på **[!UICONTROL Done]**.

   I [!UICONTROL Form-based Experience Composer] har förbättringarna ersatts med funktioner för fullständig målgrupp. Förfiningar för befintliga aktiviteter har migrerats till [målgrupper som bara är aktiva](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

1. Välj den typ av innehåll som du vill ska visas på den platsen.

1. Ange innehållet för den innehållstyp som du valde.

   **Ändra HTML-erbjudande:** Välj ett HTML-erbjudande.

   **Erbjudande om ändring av bild:** Välj en bild som har sparats i innehållsbiblioteket i Target.

   Du kan också lägga till en länk till en bild (klickfrekvens, mål, landning osv.).

   1. Klicka på [!UICONTROL Change Image Offer].
   1. Markera bilden och klicka sedan på [!UICONTROL Edit Links].
   1. Ange önskad URL eller sida på webbplatsen och klicka sedan på [!UICONTROL Update].

   **Ändra JSON-erbjudande:** Välj ett json-erbjudande.

   **Ändra upplevelsefragment:** Välj en upplevelsefragment. Mer information finns i [Experience Fragment](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

   **Ändra omdirigeringserbjudande:** Välj ett omdirigeringserbjudande. Mer information finns i [Skapa omdirigeringserbjudanden](/help/main/c-experiences/c-manage-content/offer-redirect.md).

   **Ändra fjärrerbjudande:** Välj ett fjärrerbjudande. Mer information finns i [Skapa fjärrerbjudanden](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

   **Skapa HTML-erbjudande:**

   1. Klicka på [!UICONTROL Offers] och välj sedan fliken [!UICONTROL Code Offers].
   1. Klicka på [!UICONTROL Create] > [!UICONTROL HTML Offer].
   1. Skriv ett erbjudandenamn.
   1. Skriv eller klistra in din HTML-kod i rutan Kod.
   1. Klicka på [!UICONTROL Save].

   **Skapa JSON-erbjudande:**

   1. Klicka på [!UICONTROL Offers] och välj sedan fliken [!UICONTROL Code Offers].
   1. Klicka på [!UICONTROL Create] > [!UICONTROL JSON Offer].
   1. Skriv ett erbjudandenamn.
   1. Skriv eller klistra in JSON-koden i rutan Kod.
   1. Klicka på [!UICONTROL Save].

   **Lägg till rekommendation:**

   För en rekommendationsaktivitet ger listrutan Innehåll alternativet [!UICONTROL Add Recommendation]. Klicka på **[!UICONTROL Add Recommendation]** och välj sedan sidtyp. Följ sedan de vanliga stegen som definierats i gränssnittet för att [skapa en rekommendationsaktivitet](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).

   När du väljer rekommendationskriterier i den formulärbaserade Experience Composer finns det nu en direktlänk till det valda kriteriekortet så att du snabbt och enkelt kan redigera villkoren.

   Från sidan [!UICONTROL Targeting] i det guidade arbetsflödet i [!DNL Target] tre steg:

   **Beslut om att lägga till erbjudande:**

   Lägg till ett erbjudande som skapats i [!DNL Adobe Journey Optimizer] (AJO) till en [!DNL Adobe Target]-aktivitet för att presentera det bästa dynamiska erbjudandet och upplevelsen för besökarna på din webbplats eller på din mobilwebbplats med hjälp av offertbeslut. Det här alternativet är endast tillgängligt för manuella [!UICONTROL A/B Test]- och [!UICONTROL Experience Targeting] (XT)-aktiviteter.

   Mer information finns i [Använda offertbeslut](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

1. (Valfritt för [!UICONTROL A/B Test]-, [!UICONTROL Automated Personalization]- och [!UICONTROL Experience Targeting]-aktiviteter) Om du vill upprepa den här processen för ytterligare platser klickar du på **[!UICONTROL Add Location]** och konfigurerar platsen och innehållet.
1. Klicka på **[!UICONTROL Next]** och slutför sedan stegen för att skapa aktiviteten som vanligt för din aktivitetstyp.

* [Skapa ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)
* [Skapa en aktivitet för målinriktad upplevelse](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
* [Skapa en rekommendationsaktivitet](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

## Utbildningsvideo: Formulärbaserad disposition ![Tutorial badge](/help/main/assets/tutorial.png)

Den här videon innehåller en demonstration av den formulärbaserade dispositionen.

* Skapa en aktivitet med formulärbaserad Experience Composer
* Förstå när formulärbaserad Experience Composer ska användas jämfört med Visual Experience Composer
* Använd förfiningar för att ange en plats som mål

>[!VIDEO](https://video.tv.adobe.com/v/17390)
