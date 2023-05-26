---
keywords: omdirigeringserbjudande;skapa omdirigeringserbjudande;lägg till html-erbjudande;Skicka alla URL-parametrar i omdirigering;Pass mboxSessionId i omdirigering (behövs endast när omdirigeringen går till en annan domän)
description: Lär dig hur du skapar omdirigeringserbjudanden i Adobe [!DNL Target] för att få en webbläsare att dirigera om till en ny sida.
title: Hur skapar jag omdirigeringserbjudanden?
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 0%

---

# Skapa omdirigeringserbjudanden

Omdirigera erbjudanden i [!DNL Adobe Target] gör att en webbläsare dirigerar om till en ny sida.

Det kan finnas två helt olika sidor att testa i stället för att bara ändra innehållsdelar på en sida. I det här fallet jämför ditt A/B-test sidan A med sida B. Skapa en A/B-testaktivitet med två upplevelser: den ena pekar på standardsidan A och den andra på sidan B. Erbjudandet är konfigurerat för att dirigera om besökaren till en annan sida.

>[!NOTE]
>
> * Omdirigeringserbjudanden kan skapas på [!UICONTROL Offers] > [!UICONTROL Code Offers] eller på [Forms-baserad Experience Composer](/help/main/c-experiences/form-experience-composer.md). Du kan inte skapa eller använda omdirigeringserbjudanden i Visual Experience Composer (VEC). Innehållet kommer att injiceras i [!DNL Target] begärandeplatser, så dessa passar troligtvis inte för en global [!DNL Target] begäran.
>
>* Du kan inte använda omdirigeringserbjudanden i vaxrutor (`mboxUpdate`).
>
>* För omdirigeringserbjudanden i aktiviteter som använder A4T måste implementeringen uppfylla vissa minimikrav. Dessutom finns det viktig information som du behöver känna till. Mer information finns i [Omdirigeringserbjudanden - Vanliga frågor om A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Mer information om hur du skapar en omdirigerad upplevelse finns i [Omdirigera till en URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).


Omdirigeringserbjudandet kör JavaScript-kod för att dirigera om webbläsaren. Den använder `window.location.replace();` så att sidan som besökaren omdirigeras från inte lagras i webbläsarhistoriken. På så sätt kan besökaren fortfarande använda bakåtknappen i sin webbläsare.

>[!NOTE]
>
>Om du vill skicka referensvärdet för landningssidan rekommenderar vi att du använder ett HTML-erbjudande i stället för ett omdirigeringserbjudande.

## Skapa ett omdirigeringserbjudande från sidan Koderbjudanden

1. Klicka på **[!UICONTROL Offers]** och välj sedan fliken **[!UICONTROL Code Offers]**.

   ![Fliken Koderbjudanden](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Skapa omdirigeringserbjudande, dialogruta](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Ange ett beskrivande namn för erbjudandet.

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i Assets-biblioteket.

1. Ange URL:en för det unika innehåll eller mål som du vill omdirigera till. Det här måste vara en absolut URL.

   >[!NOTE]
   >
   >Omdirigeringserbjudanden resulterar i en oändlig slinga om omdirigerings-URL:en även kvalificerar användaren för samma aktivitet. Du bör se till att användaren inte omkvalificerar sig för aktiviteten efter att ha omdirigerats.

1. Välj alternativ för att anpassa omdirigeringserbjudandet:

   * **Inkludera alla URL-parametrar:** Aktivera det här alternativet genom att dra reglaget om du vill att alla URL-parametrar som finns på föregående sida ska spridas till den omdirigerade sidan.

      Du vill t.ex. omdirigera personer direkt från en mäns sida till en mäns skjortkategorisida. Du vill också att de dynamiska parametrarna i URL:en ska skickas eftersom det är så här du spårar om någon har nått webbplatsen via e-post, banderollannons, sökannons eller organiskt. Genom att aktivera det här alternativet kan du skicka ditt omdirigeringserbjudande på sidan `https://www.mycompany.com/mens.html?emailId=123` automatiskt `https://www.mycompany.com/mensShirts.html?emailId=123` när allt du angav i URL-rutan var `https://www.mycompany.com/mensShirts.html`.

   * **Sessions-ID för lösenordsruta:** Krävs för omdirigering till en annan domän. Aktivera det här alternativet genom att dra reglaget om du vill att `sessionId` som automatiskt kommer att ingå i omdirigeringen. Detta är endast nödvändigt när du testar klickningar från ett e-postmeddelande eller klickar från en domän till en annan. The `sessionId` matchar besökarens cookie så att besökaren kan fortsätta att spåras och rätt innehåll visas.

      Om du använder cookie-konfigurationen från första och tredje part behöver du inte skicka mbox-sessions-ID när du korsar domäner. Den är beständig på cookie-filen från tredje part, så den är inte nödvändig i URL-adressen.

1. Klicka på **[!UICONTROL Save]**.

>[!NOTE]
>
>Fråga din implementeringskonsult innan du startar dessa tester.

## Skapa ett omdirigeringserbjudande med formulärbaserad Experience Composer

1. När du skapar en aktivitet med [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md)väljer du den plats där du vill visa **[!UICONTROL Content]** -avsnitt.

   ![Innehållsavsnitt i formulärbaserad Experience Composer](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Klicka på **[!UICONTROL Default Content]** nedrullningsbar lista och klicka sedan på **[!UICONTROL Change Redirect Offer]**.

   ![Ändra alternativ för omdirigeringserbjudande](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Skapa omdirigeringserbjudande, dialogruta](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Ange ett beskrivande namn för erbjudandet.

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i Assets-biblioteket.

1. Ange URL:en för det unika innehåll eller mål som du vill omdirigera till. Det här måste vara en absolut URL.

   >[!NOTE]
   >
   >Omdirigeringserbjudanden resulterar i en oändlig slinga om omdirigerings-URL:en även kvalificerar användaren för samma aktivitet. Du bör se till att användaren inte omkvalificerar sig för aktiviteten efter att ha omdirigerats.

1. Välj alternativ för att anpassa omdirigeringserbjudandet:

   * **Inkludera alla URL-parametrar:** Aktivera det här alternativet genom att dra reglaget om du vill att alla URL-parametrar som finns på föregående sida ska spridas till den omdirigerade sidan.

      Du vill t.ex. omdirigera personer direkt från en mäns sida till en mäns skjortkategorisida. Du vill också att de dynamiska parametrarna i URL:en ska skickas eftersom det är så här du spårar om någon har nått webbplatsen via e-post, banderollannons, sökannons eller organiskt. Genom att aktivera det här alternativet kan du skicka ditt omdirigeringserbjudande på sidan `https://www.mycompany.com/mens.html?emailId=123` automatiskt `https://www.mycompany.com/mensShirts.html?emailId=123` när allt du angav i URL-rutan var `https://www.mycompany.com/mensShirts.html`.

   * **Sessions-ID för lösenordsruta:** Krävs för omdirigering till en annan domän. Aktivera det här alternativet genom att dra reglaget om du vill att `sessionId` som automatiskt kommer att ingå i omdirigeringen. Detta är endast nödvändigt när du testar klickningar från ett e-postmeddelande eller klickar från en domän till en annan. The `sessionId` matchar besökarens cookie så att besökaren kan fortsätta att spåras och rätt innehåll visas.

      Om du använder cookie-konfigurationen från första och tredje part behöver du inte skicka mbox-sessions-ID när du korsar domäner. Den är beständig på cookie-filen från tredje part, så den är inte nödvändig i URL-adressen.

1. Klicka på **[!UICONTROL Save]**.

>[!NOTE]
>
>Fråga din implementeringskonsult innan du startar dessa tester.

## Använd omdirigeringserbjudanden i aktiviteter

Du måste tillämpa omdirigeringserbjudanden med [!UICONTROL Form-Based Experience Composer]. Du kan för närvarande inte använda omdirigeringserbjudanden med VEC.

The [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] är en icke-visuell upplevelse och erbjuder ett gränssnitt som är användbart när det gäller att skapa upplevelser som ska användas i [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP), och [!UICONTROL Recommendations] aktiviteter när den visuella upplevelsedispositionen inte är tillgänglig eller praktisk att använda. Du kan till exempel använda [!UICONTROL Form-Based Experience Composer] för att skapa upplevelser som använder omdirigeringserbjudanden.

1. Skapa eller redigera en aktivitet i [!UICONTROL Form-Based Experience Composer].

   Se [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) för detaljerade steg-för-steg-instruktioner.

1. Ange önskad plats och lägg till eventuella målgruppsförbättringar efter behov.

1. Klicka på listrutan i dialogrutan **[!UICONTROL Content]** -avsnittet och klicka sedan på **[!UICONTROL Change Redirect Offer]**.

   ![Ändra alternativ för omdirigeringserbjudande](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Välj önskat omdirigeringserbjudande från [!UICONTROL Select Remote Offer] och sedan klicka på **[!UICONTROL Done]**.

1. Slutför konfigurationen av aktiviteten.

## Utbildningsvideo: Formulärbaserad disposition ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller en demonstration av den formulärbaserade dispositionen, som du kan använda för att skapa omdirigeringserbjudanden.

* Skapa en aktivitet med formulärbaserad Experience Composer
* Förstå när formulärbaserad Experience Composer ska användas jämfört med Visual Experience Composer
* Använd förfiningar för att ange en plats som mål

>[!VIDEO](https://video.tv.adobe.com/v/17390)
