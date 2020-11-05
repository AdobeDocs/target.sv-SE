---
description: Använd det här alternativet när du vill skicka besökaren till en annan sida i stället för att visa innehåll på samma sida.
title: Omdirigera till en URL
feature: vec
subtopic: Multivariate Test
topic: Standard
uuid: e6515279-8a6e-4265-aa2d-700ee81eb143
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 0%

---


# Omdirigera till en URL{#redirect-to-a-url}

Använd det här alternativet när du vill skicka besökaren till en annan sida i stället för att visa innehåll på samma sida.

Det kan finnas två helt olika sidor att testa i stället för att bara ändra innehållsdelar på en sida. I det här fallet jämför ditt A/B-test sidan A med sida B. Skapa en A/B-testkampanj med två upplevelser: den ena pekar på standardsidan A och den andra på sidan B. Välj **[!UICONTROL Redirect to URL]** och ange URL:en för sida B på menyn Experience Action (Experience Action), som du hittar genom att klicka på etiketten för upplevelsen. Erbjudandet är konfigurerat för att dirigera om besökaren till en annan sida.

Omdirigeringserbjudandet kör JavaScript-kod för att dirigera om webbläsaren. Den använder `window.location.replace();`metoden, så sidan som besökaren omdirigeras från lagras inte i webbläsarhistoriken. På så sätt kan besökaren fortfarande använda bakåtknappen i sin webbläsare.

Omdirigeringserbjudanden har några begränsningar:

* För omdirigeringserbjudanden i aktiviteter som använder A4T måste implementeringen uppfylla vissa minimikrav. Dessutom finns det viktig information som du behöver känna till. Mer information finns i [Omdirigeringserbjudanden - A4T Frågor och svar](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* När du använder den formulärbaserade Experience Composer ska omdirigeringserbjudanden inte användas i rutor som är en del av sidan. Ett omdirigeringserbjudande får endast användas från en script-tagg som är en del av HTML-koden `<head>`. Du bör alltid använda autoskapa och ange omdirigeringserbjudandet för den globala mbox.

>[!NOTE]
>
>Om du vill skicka referensvärdet för landningssidan rekommenderar vi att du använder ett HTML-erbjudande i stället för ett omdirigeringserbjudande.

Så här skapar du ett omdirigeringserbjudande:

1. Skapa en upplevelse.
1. Håll muspekaren över en upplevelse och klicka sedan på ikonen Omdirigera till URL (![](assets/icon_redirect_url.png)).

   ![](assets/exp_actions.png)

1. Ange URL-adressen.
1. Om du vill kan du välja att inkludera aktuella frågeparametrar.

   Om det här alternativet är markerat, något efter ? i besökarens URL läggs till i omdirigerings-URL:en vid tidpunkten för omdirigeringen.

   Det här alternativet är markerat som standard.
1. (Valfritt) Skapa ytterligare regler.

   Ytterligare regler kan baseras på något av följande:

   * URL
   * Domän
   * Bana
   * Hash-fragment (#)
   * Fråga
   * mbox-parameter
   Ytterligare regler kan kopplas till aktivitets-URL:en med AND eller OR. Alla regler som du lägger till utvärderas mot varandra med AND.
