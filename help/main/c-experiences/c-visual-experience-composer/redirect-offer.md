---
kewords: redirect;redirect url;send to different page
description: Lär dig hur du använder alternativet Omdirigera till URL i Adobe [!DNL Target] när du vill skicka besökaren till en annan sida i stället för att visa innehåll på samma sida.
title: Kan jag dirigera om en sida till en annan URL?
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
source-git-commit: b0bf54d47ac44afc3597f308ea38fd479c54026d
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Omdirigera till en URL

Använd alternativet [!UICONTROL Redirect to URL] i [!DNL Adobe Target] när du vill skicka besökaren till en annan sida i stället för att visa innehåll på samma sida.

Det kan finnas två helt olika sidor att testa i stället för att bara ändra innehållsdelar på en sida. I det här fallet jämför ditt A/B-test sida A med sida B. Konfigurera en A/B-testkampanj med två upplevelser: en som pekar på standardsida A och den andra som dirigeras till sida B. Välj **[!UICONTROL Redirect to URL]** och ange URL:en för sida B på menyn Experience Action (Experience Action), som du hittar genom att klicka på etiketten för upplevelsen. Erbjudandet är konfigurerat för att dirigera om besökaren till en annan sida.

Omdirigeringserbjudandet verkställer JavaScript-kod för omdirigering av webbläsaren. Den använder metoden `window.location.replace();`, så sidan som besökaren omdirigeras från lagras inte i webbläsarhistoriken. På så sätt kan besökaren fortfarande använda bakåtknappen i sin webbläsare.

Omdirigeringserbjudanden har några begränsningar:

* För omdirigeringserbjudanden i aktiviteter som använder A4T måste implementeringen uppfylla vissa minimikrav. Dessutom finns det viktig information som du behöver känna till. Mer information finns i [Omdirigeringserbjudanden - A4T - frågor och svar](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* När du använder den formulärbaserade Experience Composer ska omdirigeringserbjudanden inte användas i rutor som är en del av sidan. Ett omdirigeringserbjudande får endast användas från en skripttagg som är en del av HTML `<head>`. Du bör alltid använda autoskapa och ange omdirigeringserbjudandet för den globala mbox.

>[!NOTE]
>
>Om du vill skicka referensvärdet för landningssidan rekommenderar vi att du använder ett HTML-erbjudande i stället för ett omdirigeringserbjudande.

Så här skapar du ett omdirigeringserbjudande:

1. Skapa en upplevelse.
1. Håll muspekaren över en upplevelse och klicka sedan på ikonen Omdirigera till URL (![icon_redirect_url-bild](assets/icon_redirect_url.png)).

   ![exp_actions, bild](assets/exp_actions.png)

1. Skriv URL-adressen.
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

## Kända fel

* Omdirigeringsaktiviteter i at.js-implementeringar kan få URL:en för förhandsgranskning att gå in i en loop (erbjudandet levereras upprepade gånger). Du kan använda [QA-läge](/help/main/c-activities/c-activity-qa/activity-qa.md) i stället för att utföra förhandsgranskning och QA. Problemet påverkar inte den faktiska leveransen av erbjudandet. (TGT-23019)
