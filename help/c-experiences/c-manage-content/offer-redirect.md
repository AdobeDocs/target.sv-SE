---
keywords: redirect offer;create redirect offer;add html offer;Pass all URL parameters in redirect;Pass mboxSessionId in redirect (only needed when the redirect is going to a different domain)
description: Kan jag använda omdirigeringserbjudanden för att få en webbläsare att dirigera om till en ny sida?
title: Skapa omdirigeringserbjudanden
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 15eb3050b4263358d0747b09a8afd2b4c102294c
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 0%

---


# Skapa omdirigeringserbjudanden

Omdirigeringserbjudanden i [!DNL Adobe Target] gör att en webbläsare dirigerar om till en ny sida.

Det kan finnas två helt olika sidor att testa i stället för att bara ändra innehållsdelar på en sida. I det här fallet jämför ditt A/B-test sidan A med sida B. Skapa en A/B-testaktivitet med två upplevelser: den ena pekar på standardsidan A och den andra på sidan B. Erbjudandet är konfigurerat för att dirigera om besökaren till en annan sida.

>[!NOTE]
>
> * Omdirigeringserbjudanden kan skapas på sidan [!UICONTROL Offers] > [!UICONTROL Code Offers] eller i [Forms-baserad Experience Composer](/help/c-experiences/form-experience-composer.md). Du kan inte skapa eller använda omdirigeringserbjudanden i Visual Experience Composer (VEC). Innehållet kommer att injiceras på förfrågningsplatserna för [!DNL Target], så de passar troligtvis inte för en global [!DNL Target]-begäran.
   >
   >
* Du kan inte använda omdirigeringserbjudanden i jaxrutor (`mboxUpdate`).
   >
   >
* För omdirigeringserbjudanden i aktiviteter som använder A4T måste implementeringen uppfylla vissa minimikrav. Dessutom finns det viktig information som du behöver känna till. Mer information finns i [Omdirigeringserbjudanden - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
   >
   >
* Mer information om hur du konfigurerar en omdirigerad upplevelse finns i [Omdirigera till en URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).


Omdirigeringserbjudandet kör JavaScript-kod för att dirigera om webbläsaren. Den använder metoden `window.location.replace();`, så sidan som besökaren omdirigeras från lagras inte i webbläsarhistoriken. På så sätt kan besökaren fortfarande använda bakåtknappen i sin webbläsare.

>[!NOTE]
>
>Om du vill skicka referensvärdet för landningssidan rekommenderar vi att du använder ett HTML-erbjudande i stället för ett omdirigeringserbjudande.

## Skapa ett omdirigeringserbjudande från sidan Koderbjudanden

1. Klicka på **[!UICONTROL Offers]** och välj sedan fliken **[!UICONTROL Code Offers]**.

   ![Fliken Koderbjudanden](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Skapa omdirigeringserbjudande, dialogruta](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Ange ett beskrivande namn för erbjudandet.

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i Assets-biblioteket.

1. Ange URL:en för det unika innehåll eller mål som du vill omdirigera till. Det här måste vara en absolut URL.

   >[!NOTE]
   >
   >Omdirigeringserbjudanden resulterar i en oändlig slinga om omdirigerings-URL:en även kvalificerar användaren för samma aktivitet. Du bör se till att användaren inte omkvalificerar sig för aktiviteten efter att ha omdirigerats.

1. Välj alternativ för att anpassa omdirigeringserbjudandet:

   * **Inkludera alla URL-parametrar:** Skjut växlingsknappen för att aktivera det här alternativet om du vill att alla URL-parametrar som finns på föregående sida ska spridas till den omdirigerade sidan.

      Du vill t.ex. omdirigera personer direkt från en mäns sida till en mäns skjortkategorisida. Du vill också att de dynamiska parametrarna i URL:en ska skickas eftersom det är så här du spårar om någon har nått webbplatsen via e-post, banderollannons, sökannons eller organiskt. Genom att aktivera det här alternativet kommer ditt omdirigeringserbjudande på sidan `https://www.mycompany.com/mens.html?emailId=123` automatiskt att bli `https://www.mycompany.com/mensShirts.html?emailId=123` när allt du angav i URL-rutan var `https://www.mycompany.com/mensShirts.html`.

   * **Sessions-ID för lösenordssession:** Krävs för omdirigering till en annan domän. Aktivera det här alternativet genom att dra i reglaget om du vill att `sessionId` automatiskt ska inkluderas i omdirigeringen. Detta är endast nödvändigt när du testar klickningar från ett e-postmeddelande eller klickar från en domän till en annan. `sessionId` matchar besökarens cookie så att besökaren kan fortsätta att spåras och rätt innehåll visas.

      Om du använder cookie-konfigurationen från första och tredje part behöver du inte skicka mbox-sessions-ID när du korsar domäner. Den är beständig på cookie-filen från tredje part, så den är inte nödvändig i URL-adressen.

1. Klicka på **[!UICONTROL Save]**.

>[!NOTE]
>
>Fråga din implementeringskonsult innan du startar dessa tester.

## Skapa ett omdirigeringserbjudande med formulärbaserad Experience Composer

1. När du skapar en aktivitet med [formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md) väljer du den plats där avsnittet **[!UICONTROL Content]** ska visas.

   ![Innehållsavsnitt i formulärbaserad Experience Composer](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. Klicka på listrutan **[!UICONTROL Default Content]** och klicka sedan på **[!UICONTROL Change Redirect Offer]**.

   ![Ändra alternativ för omdirigeringserbjudande](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Skapa omdirigeringserbjudande, dialogruta](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Ange ett beskrivande namn för erbjudandet.

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i Assets-biblioteket.

1. Ange URL:en för det unika innehåll eller mål som du vill omdirigera till. Det här måste vara en absolut URL.

   >[!NOTE]
   >
   >Omdirigeringserbjudanden resulterar i en oändlig slinga om omdirigerings-URL:en även kvalificerar användaren för samma aktivitet. Du bör se till att användaren inte omkvalificerar sig för aktiviteten efter att ha omdirigerats.

1. Välj alternativ för att anpassa omdirigeringserbjudandet:

   * **Inkludera alla URL-parametrar:** Skjut växlingsknappen för att aktivera det här alternativet om du vill att alla URL-parametrar som finns på föregående sida ska spridas till den omdirigerade sidan.

      Du vill t.ex. omdirigera personer direkt från en mäns sida till en mäns skjortkategorisida. Du vill också att de dynamiska parametrarna i URL:en ska skickas eftersom det är så här du spårar om någon har nått webbplatsen via e-post, banderollannons, sökannons eller organiskt. Genom att aktivera det här alternativet kommer ditt omdirigeringserbjudande på sidan `https://www.mycompany.com/mens.html?emailId=123` automatiskt att bli `https://www.mycompany.com/mensShirts.html?emailId=123` när allt du angav i URL-rutan var `https://www.mycompany.com/mensShirts.html`.

   * **Sessions-ID för lösenordssession:** Krävs för omdirigering till en annan domän. Aktivera det här alternativet genom att dra i reglaget om du vill att `sessionId` automatiskt ska inkluderas i omdirigeringen. Detta är endast nödvändigt när du testar klickningar från ett e-postmeddelande eller klickar från en domän till en annan. `sessionId` matchar besökarens cookie så att besökaren kan fortsätta att spåras och rätt innehåll visas.

      Om du använder cookie-konfigurationen från första och tredje part behöver du inte skicka mbox-sessions-ID när du korsar domäner. Den är beständig på cookie-filen från tredje part, så den är inte nödvändig i URL-adressen.

1. Klicka på **[!UICONTROL Save]**.

>[!NOTE]
>
>Fråga din implementeringskonsult innan du startar dessa tester.

## Använd omdirigeringserbjudanden i aktiviteter

Du måste tillämpa omdirigeringserbjudanden med [!UICONTROL Form-Based Experience Composer]. Du kan för närvarande inte använda omdirigeringserbjudanden med VEC.

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] är ett gränssnitt för icke-visuell upplevelse och erbjuder skapandegränssnitt som är användbart när du skapar upplevelser som kan användas i aktiviteterna [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Recommendations] när den visuella upplevelsedispositionen inte är tillgänglig eller praktisk att använda. Du kan till exempel använda [!UICONTROL Form-Based Experience Composer] för att skapa upplevelser som använder omdirigeringserbjudanden.

1. Skapa eller redigera en aktivitet i [!UICONTROL Form-Based Experience Composer].

   I [Formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md) finns detaljerade stegvisa instruktioner.

1. Ange önskad plats och lägg till eventuella målgruppsförbättringar efter behov.

1. Klicka på listrutan i avsnittet **[!UICONTROL Content]** och klicka sedan på **[!UICONTROL Change Redirect Offer]**.

   ![Ändra alternativ för omdirigeringserbjudande](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Välj önskat omdirigeringserbjudande i dialogrutan [!UICONTROL Select Remote Offer] och klicka sedan på **[!UICONTROL Done]**.

1. Slutför konfigurationen av aktiviteten.

## Utbildningsvideo: The Content Repository (4:56) ![Overview badge](/help/assets/overview.png)

Den här videon innehåller information om hur du hanterar innehåll.

* Anslutning mellan [Experience Cloud-resursbiblioteket](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) och målinnehållsbiblioteket
* Anpassade HTML-erbjudanden
* Anpassat HTML-erbjudande i Visual Experience Composer

>[!VIDEO](https://video.tv.adobe.com/v/17387)
