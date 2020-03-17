---
keywords: redirect offer;create redirect offer;add html offer;Pass all URL parameters in redirect;Pass mboxSessionId in redirect (only needed when the redirect is going to a different domain)
description: Information om omdirigeringserbjudanden i Adobe Target som gör att en webbläsare dirigerar om till en ny sida.
title: Skapa omdirigeringserbjudanden
topic: Standard
uuid: 54336965-a26e-47c3-b3bc-079d3573502a
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Skapa omdirigeringserbjudanden{#create-redirect-offers}

Omdirigeringserbjudandet gör att en webbläsare dirigerar om till en ny sida.

Det kan finnas två helt olika sidor att testa i stället för att bara ändra innehållsdelar på en sida. I det här fallet jämför ditt A/B-test sidan A med sida B. Skapa en A/B-testkampanj med två upplevelser: den ena pekar på standardsidan A och den andra på sidan B. Erbjudandet är konfigurerat för att dirigera om besökaren till en annan sida.

>[!NOTE] {class=&quot;- topic/note &quot;
>
>Du kan inte använda omdirigeringserbjudanden i aximbox ( `mboxUpdate`).
>
>För omdirigeringserbjudanden i aktiviteter som använder A4T måste implementeringen uppfylla vissa minimikrav. Dessutom finns det viktig information som du behöver känna till. Mer information finns i [Omdirigeringserbjudanden - A4T Frågor och svar](../../c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).

Mer information om hur du konfigurerar en upplevelse som dirigeras om finns i [Omdirigera till en URL](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

Omdirigeringserbjudandet kör JavaScript-kod för att dirigera om webbläsaren. Den använder `window.location.replace();` metoden, så sidan som besökaren omdirigeras från lagras inte i webbläsarhistoriken. På så sätt kan besökaren fortfarande använda bakåtknappen i sin webbläsare.

>[!NOTE] {class=&quot;- topic/note &quot;
>
>Om du vill skicka referensvärdet för landningssidan rekommenderar vi att du använder ett HTML-erbjudande i stället för ett omdirigeringserbjudande.

**Så här skapar du ett omdirigeringserbjudande:**

1. Klicka på **[!UICONTROL Offers]** och välj sedan fliken **[!UICONTROL Code Offers]**.
1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.
1. Skriv ett erbjudandenamn.
1. Ange URL:en för det unika innehåll eller mål som du vill omdirigera till. Det här måste vara en absolut URL.

   >[!NOTE]
   >
   >Omdirigeringserbjudanden resulterar i en oändlig slinga om omdirigerings-URL:en även kvalificerar användaren för samma aktivitet. Du bör se till att användaren inte omkvalificerar sig för aktiviteten efter att ha omdirigerats.

1. Välj alternativ för att anpassa omdirigeringserbjudandet:

* **Inkludera alla URL-parametrar:** Markera den här rutan om du vill att alla URL-parametrar som finns på föregående sida ska spridas till den omdirigerade sidan.

   Du vill t.ex. omdirigera personer direkt från en mäns sida till en menys kategorisida. Du vill också att de dynamiska parametrarna i URL:en ska skickas eftersom det är så här du spårar om någon har nått webbplatsen via e-post, banderollannons, sökannons eller organiskt. Genom att markera den här rutan [!DNL `https://www.mycompany.com/mens.html?emailId=123`] blir omdirigeringserbjudandet automatiskt [!DNL `https://www.mycompany.com/mensShirts.html?emailId=123`] när allt du har angett i URL-rutan [!DNL `https://www.mycompany.com/mensShirts.html`].

* **Sessions-ID för lösenordsruta (krävs för omdirigering till en annan domän):** Markera den här rutan om du vill att omdirigeringen ska inkluderas automatiskt `sessionId` . Detta är endast nödvändigt när du testar klickningar från ett e-postmeddelande eller klickar från en domän till en annan. Den `sessionId` matchar besökarens cookie så att besökaren kan fortsätta att spåras och rätt innehåll visas.

   Om du använder cookie-konfigurationen från första och tredje part behöver du inte skicka mbox-sessions-ID när du korsar domäner. Den är beständig på cookie-filen från tredje part, så den är inte nödvändig i URL-adressen.

>[!NOTE] {class=&quot;- topic/note &quot;
>
>Fråga din implementeringskonsult innan du startar dessa tester.

## Utbildningsvideo: Märket Innehållsdatabas (4:56) - ![översikt](/help/assets/overview.png)

Den här videon innehåller information om hur du hanterar innehåll.

* Anslutning mellan [Experience Cloud-resursbiblioteket](https://docs.adobe.com/content/help/en/core-services/interface/assets/creative-cloud.html) och målinnehållsbiblioteket
* Anpassade HTML-erbjudanden
* Anpassat HTML-erbjudande i Visual Experience Composer

>[!VIDEO](https://video.tv.adobe.com/v/17387)
