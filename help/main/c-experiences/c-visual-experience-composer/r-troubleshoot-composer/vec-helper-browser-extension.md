---
keywords: vec;Visual experience composer; vec;iframe;extension;browser
description: Upptäck varför vissa webbplatser kanske inte kan öppnas på ett tillförlitligt sätt i Visual Experience Composer (VEC). Med webbläsartillägget VEC Helper kan du läsa in webbplatser tillförlitligt i VEC.
title: Hur använder jag hjälptillägget Visual Experience Composer (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 3456da329e25f3d8e8f591fce0b851580d385455
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 0%

---

# Hjälptillägg för Visual Experience Composer

The [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) Med webbläsartillägget Helper för Google Chrome kan du läsa in webbplatser tillförlitligt i VEC för att snabbt skapa och skapa QA-webbupplevelser.

VEC Helper-webbläsaren är ett Chrome-tillägg. Det här tillägget är inte nödvändigt när du använder Mozilla Firefox.

>[!IMPORTANT]
>
>Aktuell [!DNL Target] Tillägget VEC Helper som beskrivs i den här artikeln skapades med Manifest v2. Google har nyligen meddelat att nya tillägg som skapats med Manifest v2 inte längre tillåts.
>
>Det befintliga tillägget fungerar fortfarande i Google Chrome. I framtiden [!DNL Adobe] tar bort hjälptillägget som beskrivs i det här avsnittet och kräver att kunderna går över till det nyare [Hjälptillägg för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). Du meddelas via versionsinformation och text i den här artikeln när det här tillägget slutar fungera. På grund av säkerhetsförbättringar i manifestet v3, [!DNL Adobe] rekommenderar att du hämtar det nya tillägget för att fortsätta att visuellt skapa dina webbplatser i [!DNL Target].

## Orsaker till att vissa webbplatser kanske inte öppnas som de ska i VEC

* Webbplatsen har strikta säkerhetsprinciper.
* Webbplatsen ligger i en iframe.
* at.js-biblioteket är ännu inte implementerat på webbplatsen.
* Kundens QA- eller stage-sajt är inte tillgänglig för omvärlden (webbplatsen är intern).
* Det finns vissa begränsningar när du försöker använda VEC för att öppna en webbplats som använder [Servicearbetare](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API){target=_blank} (SW).

En SWF-fil är en webbteknik som kan användas för att avlyssna begäranden för den domän som de är installerade på av en webbsida. Programvaran överlever sidbesöket och aktiverar sig själv vid efterföljande besök. Svartvyn avgör vilka förfrågningar som går igenom och vilka som fångas upp och hanteras från ett cacheminne istället.

Programvaran kan styra cachningen. kan cachelagra själva webbsidan, statiska resurser som JS, CSS, IMG, AJAX, deras innehåll och deras svarshuvuden, inklusive de som [VEC Helper-tillägg för mål](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) försöker ta bort, som X-Frame-Options: SAMEORIGIN, CSP (Content-Security-Policy) eller Set-Cookie.

Tyvärr tar Chrome-tilläggets API:er som fångar upp webbförfrågningar inte emot förfrågningar som fångats upp och hanterats av en SWF-fil. Tillägget kan därför inte åtgärda sidhuvuden och cookies om webbsidesbegäran hanterades från ett cacheminne av en SWF-fil eftersom webbsidan inte läses in i VEC på grund av X-Frame-Options eller CSP-rubriker som också cache-lagrades.

Som en möjlig tillfällig lösning kan du inaktivera Service Workers på fliken Chrome Developer Tools > Application (Verktyg för Chrome-utvecklare) och sedan aktivera kryssrutan&quot;Bypass for network&quot; (Kringgå för nätverk) under avsnittet Service Workers (Servicearbetare).

* Du använder Google Chrome 80+ med förbättrade principer för att framtvinga cookies för samma webbplats. Mer information finns i [Hur påverkar de nyligen meddelade reglerna för tillämpning av cookie-standarden Google Chrome SameSite de VEC och EEC?](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

Webbläsartillägget VEC Helper för Chrome löser problem med webbplatsinläsning som kunderna nu är beroende av [!DNL Target] [Förbättrad Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) eller tillägg från tredje part, till exempel Uppriktigt.

## Fördelar med att använda VEC Helper-tillägget

* Alla iframe-rubriker, som X-Frame-Options och Content-Security-Policy, tas implicit bort från webbplatsen. Du behöver inte längre skapa komplicerade regler.
* Om en webbsida ännu inte innehåller [!DNL Target] at.js JavaScript-bibliotek kan du använda tillägget för att mata in biblioteket så att du kan skapa upplevelser för webbplatsen. Du kan sedan skapa aktiviteter och köra frågor och svar med hjälp av förhandsgranskningslänkar.

   Observera att tillägget inte injicerar at.js med Enhanced Experience Composer (EEC), men funktionen SameSite Cookie finns fortfarande kvar. Om du vill mata in at.js på webbsidan stänger du av EEC.

* [Mobilvisningsrutor](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) stöds även utan [!UICONTROL Enhanced Experience Composer] (EEG).
* Kunder som är nybörjare på [!DNL Target] kan använda tillägget för att experimentera med [!DNL Target] även om deras IT-utvecklare ännu inte har implementerat [!DNL Target] på deras webbplatser.
* Partners som betjänar flera kunders webbplatser och [!DNL Target] konton har nu en enkel mekanism som stöder VEC-inläsning, i stället för att hantera flera regler i tredjepartsverktyg.

## Hämta och installera VEC Helper-webbläsartillägget

1. Navigera till [Webbläsartillägget Adobe Target VEC Helper i Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Klicka på **[!UICONTROL Add to Chrome > Add Extension]**.
1. Öppna VEC i [!DNL Target].
1. Om du vill använda tillägget klickar du på ikonen för VEC Helper-webbläsartillägget ( ![VEC Helper: ikon](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ) i webbläsarens verktygsfält i Chrome när du arbetar i VEC eller [QA-läge](/help/main/c-activities/c-activity-qa/activity-qa.md).
1. (Villkorligt) Skjut upp **[!UICONTROL Inject Target Libraries]** växla till&quot;på&quot;-positionen om webbsidan ännu inte innehåller [!DNL Target] at.js JavaScript-bibliotek.

   Följande bild visar VEC Helper med [!UICONTROL Inject Target Libraries] aktiverad inställning:

   ![VEC-hjälp 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   Följande bild visar VEC Helper där du tillfrågas om du vill att den ska injiceras [!DNL Target] bibliotek på sidan för att aktivera redigering:

   ![VEC-hjälp 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Villkorligt) Skjut upp **[!UICONTROL Cookies]** växla till&quot;på&quot;-positionen för att automatiskt lägga till `SameSite=None` åtgärda attributwebbläsare.

   ![Cookies i VEC-hjälptillägget](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Mer information om `SameSite=None` korrigering av attributwebbläsare, se&quot;Hur påverkar de nyligen meddelade reglerna för tillämpning av cookies i Google Chrome SameSite hur VEC och EEC fungerar?&quot; in [Felsökning av problem relaterade till Visual Experience Composer och Enhanced Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Anteckningar

* The [!UICONTROL Inject Target libraries] -flaggan i tillägget är som standard AV. Du kan aktivera den här flaggan om du vill använda VEC på en webbplats som ännu inte har implementerats för [!DNL Target].

   Den här flaggan är en global inställning. Flaggan är aktiverad eller inaktiverad för alla webbplatser som öppnas i VEC. Om du till exempel anger att flaggan ska vara&quot;on&quot; och öppna en webbplats som redan har implementerats med at.js, får du ett meddelande om att at.js redan har lästs in. Adobe räknar med att de flesta kunder redan har at.js implementerat på sina sidor och använder standardinställningen&quot;off&quot;.

* Tillägget läser in den senaste versionen av at.js som är tillgänglig från [!DNL Target UI] in [!UICONTROL Administration > Implementation].
* När tillägget används för att injicera at.js i [QA-läge](/help/main/c-activities/c-activity-qa/activity-qa.md)måste du ha en annan flik i Chrome öppen. Denna Chrome-flik måste autentiseras till samma [!DNL Adobe Experience Cloud] Organisationen som du skapade aktiviteten i.
* Följande meddelanden hjälper dig att hålla dig informerad:

   * Om du försöker läsa in en webbplats med VEC som inte kan läsas in visas ett meddelande om att du har installerat webbläsartillägget VEC Helper.
   * Om at.js ännu inte har implementerats på webbplatsen visas ett meddelande i VEC om att du har installerat tillägget.
   * Om tillägget är aktiverat och aktiverar inläsningen visas meddelanden när tillägget injicerar at.js-biblioteket (om det behövs) eller hjälper till att öppna webbplatsen på ett tillförlitligt sätt i VEC.
