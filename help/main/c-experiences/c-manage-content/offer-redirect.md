---
keywords: omdirigeringserbjudande;skapa omdirigeringserbjudande;lägg till html-erbjudande;Skicka alla URL-parametrar vid omdirigering
description: Lär dig hur du skapar omdirigeringserbjudanden som hjälper webbläsare att hitta nya sidor.
title: Hur skapar jag omdirigeringserbjudanden?
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 0%

---

# Skapa omdirigeringserbjudanden

Lär dig hur du skapar omdirigeringserbjudanden som hjälper webbläsare att hitta nya sidor.

Det kan finnas två helt olika sidor att testa i stället för att bara ändra innehållsdelar på en sida. I det här fallet jämför ditt A/B-test sida A med sida B. Konfigurera en [!UICONTROL A/B Test]-aktivitet med två upplevelser: en som pekar på standardsida A och den andra som dirigeras om till sida B. Erbjudandet är konfigurerat för att dirigera om besökaren till en annan sida.

>[!NOTE]
>
> * Omdirigeringserbjudanden kan skapas på sidan [!UICONTROL Offers] > [!UICONTROL Code Offers] eller i [Forms-baserad Experience Composer](/help/main/c-experiences/form-experience-composer.md). Du kan inte skapa eller tillämpa omdirigeringserbjudanden i [!UICONTROL Visual Experience Composer] (VEC). Innehållet injiceras på [!DNL Target]-begärandeplatserna, så de här platserna passar troligtvis inte för en global [!DNL Target]-begäran.
>
>* Du kan inte använda omdirigeringserbjudanden i AJAX (`mboxUpdate`).
>
>* För omdirigeringserbjudanden i aktiviteter som använder [[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) måste implementeringen uppfylla vissa minimikrav. Dessutom finns det viktig information som du behöver känna till. Se [Omdirigeringserbjudanden - Vanliga frågor om A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Mer information om hur du konfigurerar en omdirigerad upplevelse finns i [Omdirigera till en URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

Omdirigeringserbjudandet verkställer JavaScript-kod för omdirigering av webbläsaren. Den använder metoden `window.location.replace();`, så sidan som besökaren omdirigeras från lagras inte i webbläsarhistoriken. På så sätt kan besökarna använda bakåtknappen i sina webbläsare.

>[!NOTE]
>
>Om du vill skicka referensvärdet för landningssidan ska du använda ett HTML-erbjudande i stället för ett omdirigeringserbjudande.

## Skapa ett omdirigeringserbjudande från sidan [!UICONTROL Code Offers]

1. Klicka på **[!UICONTROL Offers]** och välj sedan fliken **[!UICONTROL Code Offers]**.
1. Klicka på **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.
1. Ange ett beskrivande namn för erbjudandet.

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i biblioteket [!UICONTROL Assets].

1. (Villkorligt) Om du har ett [Target Premium-konto](/help/main/c-intro/intro.md#premium) väljer du önskad [arbetsyta](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. Ange URL:en för det unika innehåll eller mål som du vill omdirigera till. Denna URL måste vara en absolut URL.

   >[!NOTE]
   >
   >Omdirigeringserbjudanden resulterar i en oändlig slinga om omdirigerings-URL:en även kvalificerar användaren för samma aktivitet. Se till att användaren inte kvalificerar om sig för aktiviteten efter att ha omdirigerats.

1. Välj alternativ för att anpassa omdirigeringserbjudandet:

   * **[!UICONTROL Include all URL parameters]:** Aktivera det här alternativet om du vill att alla URL-parametrar som finns på föregående sida ska spridas till den omdirigerade sidan.

     Du vill t.ex. omdirigera personer direkt från en mäns sida till en mäns skjortkategorisida. Du vill också att de dynamiska parametrarna i URL:en ska skickas eftersom det är den här metoden som du spårar om någon har nått webbplatsen via e-post, banderollannons, sökannons eller organiskt. Genom att aktivera det här alternativet blir ditt omdirigeringserbjudande på sidan `https://www.mycompany.com/mens.html?emailId=123` automatiskt `https://www.mycompany.com/mensShirts.html?emailId=123` när allt du angav i URL-rutan var `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Pass mbox session ID]:** krävs för omdirigering till en annan domän. Aktivera det här alternativet genom att dra i reglaget om du vill att `sessionId` ska inkluderas automatiskt i omdirigeringen. Det här alternativet är endast obligatoriskt när du testar klickningar från ett e-postmeddelande eller klickar från en domän till en annan. `sessionId` matchar besökarens cookie så att besökaren kan fortsätta att spåras och rätt innehåll visas.

     Om du använder cookie-konfigurationen från första och tredje part behöver du inte skicka mbox-sessions-ID när du korsar domäner. Den är beständig på cookie-filen från tredje part, så den är inte nödvändig i URL-adressen.

1. Klicka på **[!UICONTROL Create]**.

>[!IMPORTANT]
>
>Fråga din implementeringskonsult innan du startar testerna.

## Skapa ett omdirigeringserbjudande med [!UICONTROL Form-Based Experience Composer]

1. När du skapar en aktivitet med [formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) väljer du platsen där avsnittet **[!UICONTROL Content]** ska visas.
1. Klicka på listrutan **[!UICONTROL Content]**, klicka på ikonen **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) och sedan på **[!UICONTROL Change Redirect Offer]**.
1. Klicka på **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.
1. Ange ett beskrivande namn för erbjudandet.

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i biblioteket [!UICONTROL Assets].

1. Ange URL:en för det unika innehåll eller mål som du vill omdirigera till. Denna URL måste vara en absolut URL.

   >[!NOTE]
   >
   >Omdirigeringserbjudanden resulterar i en oändlig slinga om omdirigerings-URL:en även kvalificerar användaren för samma aktivitet. Se till att användaren inte kvalificerar om sig för aktiviteten efter att ha omdirigerats.

1. Välj alternativ för att anpassa omdirigeringserbjudandet:

   * **[!UICONTROL Include all URL parameters]:** Aktivera det här alternativet genom att dra reglaget om du vill att alla URL-parametrar som finns på föregående sida ska spridas till den omdirigerade sidan.

     Du vill t.ex. omdirigera personer direkt från en mäns sida till en mäns skjortkategorisida. Du vill också att de dynamiska parametrarna i URL:en ska skickas eftersom det är den här metoden som du spårar om någon har nått webbplatsen via e-post, banderollannons, sökannons eller organiskt. Genom att aktivera det här alternativet blir ditt omdirigeringserbjudande på sidan `https://www.mycompany.com/mens.html?emailId=123` automatiskt `https://www.mycompany.com/mensShirts.html?emailId=123` när allt du angav i URL-rutan var `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Pass mbox session ID]:** krävs för omdirigering till en annan domän. Aktivera det här alternativet genom att dra i reglaget om du vill att `sessionId` ska inkluderas automatiskt i omdirigeringen. Det här alternativet är endast obligatoriskt när du testar klickningar från ett e-postmeddelande eller klickar från en domän till en annan. `sessionId` matchar besökarens cookie så att besökaren kan fortsätta att spåras och rätt innehåll visas.

     Om du använder cookie-konfigurationen från första och tredje part behöver du inte skicka mbox-sessions-ID när du korsar domäner. Den är beständig på cookie-filen från tredje part, så den är inte nödvändig i URL-adressen.

1. Klicka på **[!UICONTROL Create]**.

>[!IMPORTANT]
>
>Fråga din implementeringskonsult innan du startar testerna.

## Använd omdirigeringserbjudanden i aktiviteter

Använd omdirigeringserbjudanden med [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md). Du kan för närvarande inte tillämpa omdirigeringserbjudanden med [!UICONTROL Visual Experience Composer] (VEC).

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] är en icke-visuell upplevelse och erbjuder ett gränssnitt för att skapa upplevelser som är användbara när det gäller att skapa upplevelser som kan användas i [!UICONTROL A/B Tests]-, [!UICONTROL Experience Targeting] (XT)-, [!UICONTROL Automated Personalization] (AP)- och [!UICONTROL Recommendations]-aktiviteter när [!UICONTROL Visual Experience Composer] inte är tillgänglig eller praktiskt att använda. Du kan till exempel använda [!UICONTROL Form-Based Experience Composer] för att skapa upplevelser som använder omdirigeringserbjudanden.

1. Skapa eller redigera en aktivitet i [!UICONTROL Form-Based Experience Composer].

   I [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) finns detaljerade stegvisa instruktioner.

1. Ange önskad plats och lägg till eventuella målgruppsförbättringar efter behov.

1. Klicka på listrutan **[!UICONTROL Content]**, klicka på ikonen **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) och sedan på **[!UICONTROL Change Redirect Offer]**.
1. Välj önskat omdirigeringserbjudande i dialogrutan [!UICONTROL Select Redirect Offer] och klicka sedan på **[!UICONTROL Add]**.
1. Slutför konfigurationen av aktiviteten.
