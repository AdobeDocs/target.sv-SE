---
keywords: vec;visual experience disposition; vec;iframe;extension;browser
description: Identifiera varför vissa webbplatser kanske inte kan öppnas på ett tillförlitligt sätt i [!UICONTROL Visual Experience Composer] (VEC). Med webbläsartillägget VEC Helper kan du läsa in webbplatser tillförlitligt i VEC.
title: Hur använder jag hjälptillägget [!UICONTROL Visual Experience Composer] (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 6f4fd14a46f06c1366c02cfaf5a0cee5edbb00c4
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 0%

---

# Hjälptillägg för [!UICONTROL Visual Experience Composer]

Med webbläsartillägget [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) Helper för [!DNL Google Chrome] kan du läsa in webbplatser tillförlitligt i VEC för att snabbt skapa och skapa QA-webbupplevelser.

VEC Helper-webbläsaren är ett [!DNL Chrome]-tillägg. Det här tillägget är inte nödvändigt när [!DNL Mozilla Firefox] används.

>[!IMPORTANT]
>
>* Det äldre VEC Helper-tillägget [!DNL Target] som beskrivs i den här artikeln skapades med Manifest V2. [!DNL Google] meddelade att tillägg som skapats med Manifest V2 inte längre tillåts från och med juni 2024. Mer information finns i [Manifest V2 support timeline notification](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank} from [!DNL Google] på webbplatsen *Chrome for Developers*.
>
>* Från och med juni 2024 börjar [!DNL Google] inaktivera tillägg som skapats med Manifest V2, inklusive det tillägg som beskrivs i det här avsnittet. [!DNL Adobe] rekommenderar att kunderna går över till det nyare [hjälptillägget för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) så snart som möjligt.

## Orsaker till att vissa webbplatser kanske inte öppnas som de ska i VEC

* Webbplatsen har strikta säkerhetsprinciper.
* Webbplatsen ligger i en iframe.
* at.js-biblioteket är ännu inte implementerat på webbplatsen.
* Kundens QA- eller stage-sajt är inte tillgänglig för omvärlden (webbplatsen är intern).
* Det finns för närvarande vissa begränsningar när du försöker använda VEC för att öppna en webbplats som använder [Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API){target=_blank} (SW).

En SWF-fil är en webbteknik som kan användas för att avlyssna begäranden för den domän som de är installerade på av en webbsida. Programvaran överlever sidbesöket och aktiverar sig själv vid efterföljande besök. Svartvyn avgör vilka förfrågningar som går igenom och vilka som fångas upp och hanteras från ett cacheminne istället.

SWF-filen kan styra cachelagringen. Den kan cachelagra själva webbsidan, statiska resurser som JS, CSS, IMG, AJAX-begäranden, deras innehåll och deras svarshuvuden, inklusive de som tas bort av [måltillägget för VEC-hjälp](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), som X-Frame-Options: SAMEORIGIN, CSP (Content-Security-Policy) eller Set-Cookie.

Tyvärr får de Chrome-API:er för tillägg som fångar upp webbförfrågningar inte de förfrågningar som fångats upp och hanterats av en SWF-fil. Tillägget kan därför inte åtgärda sidhuvuden och cookies om webbsidesbegäran hanterades från ett cacheminne av en SWF-fil eftersom webbsidan inte läses in i VEC på grund av X-Frame-Options eller CSP-rubriker som också cache-lagrades.

Du kan komma runt problemet genom att inaktivera Service Workers på fliken Chrome Developer Tools > Application och sedan aktivera kryssrutan&quot;Bypass for network&quot; under Service Workers.

* Du använder Google Chrome 80+ med förbättrade principer för tillämpning av cookie-filer på samma webbplats. Mer information finns i [Hur påverkar den nyligen lanserade policyn för tillämpning av cookies i Google Chrome SameSite VEC och EEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

VEC Helper-webbläsartillägget för Chrome löser problem med webbplatsinläsning som kunderna nu förlitar sig på [!DNL Target] [Förbättrad Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) eller tillägg från tredje part, som Request.

## Fördelar med att använda VEC Helper-tillägget

* Alla iframe-rubriker, som X-Frame-Options och Content-Security-Policy, tas implicit bort från webbplatsen. Du behöver inte längre skapa komplicerade regler.
* Om en webbsida ännu inte innehåller JavaScript-biblioteket [!DNL Target] at.js kan du använda tillägget för att mata in biblioteket så att du kan skapa upplevelser för webbplatsen. Du kan sedan skapa aktiviteter och köra frågor och svar med hjälp av förhandsgranskningslänkar.

  Observera att tillägget inte injicerar at.js med Enhanced Experience Composer (EEC), men funktionen SameSite Cookie finns fortfarande kvar. Om du vill mata in at.js på webbsidan stänger du av EEC.

* [Mobila visningsrutor](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) stöds även utan [!UICONTROL Enhanced Experience Composer] (EEC).
* Kunder som är nya i [!DNL Target] kan använda tillägget för att experimentera med [!DNL Target], även om deras IT-utvecklare ännu inte har implementerat [!DNL Target] på sina webbplatser.
* Partners som betjänar flera kunders webbplatser och [!DNL Target]-konton har nu en enkel mekanism som stöder VEC-inläsning, i stället för att hantera flera regler i tredjepartsverktyg.

## Hämta och installera VEC Helper-webbläsartillägget

1. Navigera till webbläsartillägget [Adobe Target VEC Helper i Chrome Web Store](https://chromewebstore.google.com/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca).
1. Klicka på **[!UICONTROL Add to Chrome > Add Extension]**.
1. Öppna VEC i [!DNL Target].
1. Om du vill använda tillägget klickar du på ikonen för VEC Helper-webbläsartillägget ( ![VEC Helper-ikonen ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ) i verktygsfältet i din Chrome-webbläsare i VEC- eller [QA-läge](/help/main/c-activities/c-activity-qa/activity-qa.md) .
1. (Villkorligt) Skjut växeln **[!UICONTROL Inject Target Libraries]** till&quot;on&quot;-positionen om webbsidan ännu inte innehåller JavaScript-biblioteket [!DNL Target] at.js.

   I följande bild visas VEC Helper med inställningen [!UICONTROL Inject Target Libraries] aktiverad:

   ![VEC-hjälp 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   Följande bild visar VEC Helper där du tillfrågas om du vill att [!DNL Target] bibliotek ska injiceras på sidan för att det ska gå att skapa:

   ![VEC-hjälp 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Villkorligt) Dra **[!UICONTROL Cookies]**-växeln till&quot;på&quot;-positionen för att automatiskt lägga till webbläsarkorrigeringen för `SameSite=None`-attributet.

   ![Växla cookies i VEC-hjälplägget](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Mer information om korrigeringen för attributwebbläsaren `SameSite=None` finns i&quot;Hur påverkar den nyligen lanserade policyn för tillämpning av cookies i Google Chrome SameSite?&quot; i [Felsökning av problem relaterade till Visual Experience Composer och Enhanced Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Anteckningar

* Flaggan [!UICONTROL Inject Target libraries] i tillägget är inaktiverad som standard. Du kan aktivera den här flaggan om du vill använda VEC på en webbplats som ännu inte har implementerats för [!DNL Target].

  Den här flaggan är en global inställning. Flaggan är aktiverad eller inaktiverad för alla webbplatser som öppnas i VEC. Om du till exempel anger att flaggan ska vara&quot;on&quot; och öppna en webbplats som redan har implementerats med at.js, får du ett meddelande om att at.js redan har lästs in. Adobe räknar med att de flesta kunder redan har at.js implementerat på sina sidor och använder standardinställningen&quot;off&quot;.

* Tillägget läser in den senaste versionen av at.js som är tillgänglig från [!DNL Target UI] i [!UICONTROL Administration > Implementation].
* När du använder tillägget för att injicera at.js i [QA Mode](/help/main/c-activities/c-activity-qa/activity-qa.md) måste du ha en annan Chrome-flik öppen. Den här Chrome-fliken måste autentiseras i samma [!DNL Adobe Experience Cloud]-organisation som du skapade aktiviteten i.
* Följande meddelanden hjälper dig att hålla dig informerad:

   * Om du försöker läsa in en webbplats med VEC som inte kan läsas in visas ett meddelande om att du har installerat webbläsartillägget VEC Helper.
   * Om at.js ännu inte har implementerats på webbplatsen visas ett meddelande i VEC om att du har installerat tillägget.
   * Om tillägget är aktiverat och aktiverar inläsningen visas meddelanden när tillägget injicerar at.js-biblioteket (om det behövs) eller hjälper till att öppna webbplatsen på ett tillförlitligt sätt i VEC.
