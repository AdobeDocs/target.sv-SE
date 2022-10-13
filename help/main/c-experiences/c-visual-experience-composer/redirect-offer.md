---
kewords: redirect;redirect url;send to different page
description: Lär dig hur du använder alternativet Omdirigera till URL i Adobe [!DNL Target] när du vill skicka besökaren till en annan sida i stället för att visa innehåll på samma sida.
title: Kan jag dirigera om en sida till en annan URL?
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
source-git-commit: b0bf54d47ac44afc3597f308ea38fd479c54026d
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# Omdirigera till en URL

Använd [!UICONTROL Redirect to URL] alternativ i [!DNL Adobe Target] när du vill skicka besökaren till en annan sida i stället för att visa innehåll på samma sida.

Det kan finnas två helt olika sidor att testa i stället för att bara ändra innehållsdelar på en sida. I det här fallet jämför ditt A/B-test sidan A med sida B. Skapa en A/B-testkampanj med två upplevelser: den ena pekar på standardsidan A och den andra på sidan B. På menyn Experience Action (Upplevelseåtgärd), som du hittar genom att klicka på bokstavsetiketten för upplevelsen, väljer du **[!UICONTROL Redirect to URL]** och ange webbadressen till sidan B. Erbjudandet är konfigurerat för att dirigera om besökaren till en annan sida.

Omdirigeringserbjudandet kör JavaScript-kod för att dirigera om webbläsaren. Den använder `window.location.replace();`så att sidan som besökaren omdirigeras från inte lagras i webbläsarhistoriken. På så sätt kan besökaren fortfarande använda bakåtknappen i sin webbläsare.

Omdirigeringserbjudanden har några begränsningar:

* För omdirigeringserbjudanden i aktiviteter som använder A4T måste implementeringen uppfylla vissa minimikrav. Dessutom finns det viktig information som du behöver känna till. Mer information finns i [Omdirigeringserbjudanden - Vanliga frågor om A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* När du använder den formulärbaserade Experience Composer ska omdirigeringserbjudanden inte användas i rutor som är en del av sidan. Ett omdirigeringserbjudande får endast användas från en script-tagg som är en del av HTML `<head>`. Du bör alltid använda autoskapa och ange omdirigeringserbjudandet för den globala mbox.

>[!NOTE]
>
>Om du vill skicka referensvärdet för landningssidan rekommenderar vi att du använder ett HTML-erbjudande i stället för ett omdirigeringserbjudande.

Så här skapar du ett omdirigeringserbjudande:

1. Skapa en upplevelse.
1. Håll muspekaren över en upplevelse och klicka sedan på ikonen Omdirigera till URL (![icon_redirect_url-bild](assets/icon_redirect_url.png)).

   ![exp_actions, bild](assets/exp_actions.png)

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

## Kända fel

* Omdirigeringsaktiviteter i at.js-implementeringar kan få URL:en för förhandsgranskning att gå in i en loop (erbjudandet levereras upprepade gånger). Du kan använda [QA-läge](/help/main/c-activities/c-activity-qa/activity-qa.md) i stället för att utföra förhandsgranskning och kvalitetskontroll. Problemet påverkar inte den faktiska leveransen av erbjudandet. (TGT-23019)
