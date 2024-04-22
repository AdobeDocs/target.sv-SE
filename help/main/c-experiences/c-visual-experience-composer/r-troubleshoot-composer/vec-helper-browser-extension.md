---
keywords: vec;visual experience disposition; vec;iframe;extension;browser
description: Upptäck varför vissa webbplatser inte kan öppnas på ett tillförlitligt sätt i [!UICONTROL Visual Experience Composer] (VEC) Med webbläsartillägget VEC Helper kan du läsa in webbplatser tillförlitligt i VEC.
title: Hur jag använder [!UICONTROL Visual Experience Composer] (VEC) Hjälptillägg?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 8edae6a197a3ac82b85fcce4d99c8b0d5f45c712
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer] hjälptillägg

The [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) Hjälpwebbläsartillägg för [!DNL Google Chrome] Med kan du läsa in webbplatser tillförlitligt i VEC för att snabbt skapa och skapa QA-webbupplevelser.

VEC Helper-webbläsaren är en [!DNL Chrome] tillägg. Det här tillägget behövs inte när du använder [!DNL Mozilla Firefox].

>[!IMPORTANT]
>
>Aktuell [!DNL Target] Tillägget VEC Helper som beskrivs i den här artikeln skapades med Manifest v2. Google meddelade nyligen att man inte längre kommer att tillåta nya tillägg som skapats med Manifest v2 från och med juni 2024. Mer information finns i [Manifest V2 support timeline notification](https://developer.chrome.com/docs/extensions/develop/migrate/mv2-deprecation-timeline){target=_blank} från [!DNL Google] på *Chrome för utvecklare* webbplats.
>
>Det befintliga tillägget fungerar fortfarande i Google Chrome. med början i juni 2024, [!DNL Adobe] kommer att börja inaktivera hjälptillägget som beskrivs i det här avsnittet och kräva att kunderna går över till det nyare [Hjälptillägg för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).
>
Du kommer att meddelas via versionsinformation, ett meddelande i produkten och text i den här artikeln när det här tillägget inte längre fungerar. På grund av säkerhetsförbättringar i manifestet v3, [!DNL Adobe] hämtar det nya tillägget för att fortsätta att visuellt skapa dina webbplatser i [!DNL Target].

## Orsaker till att vissa webbplatser kanske inte öppnas som de ska i VEC

* Webbplatsen har strikta säkerhetsprinciper.
* Webbplatsen ligger i en iframe.
* at.js-biblioteket är ännu inte implementerat på webbplatsen.
* Kundens QA- eller stage-sajt är inte tillgänglig för omvärlden (webbplatsen är intern).
* Det finns vissa begränsningar när du försöker använda VEC för att öppna en webbplats som använder [Servicearbetare](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API){target=_blank} (SW).

En SWF-fil är en webbteknik som kan användas för att avlyssna begäranden för den domän som de är installerade på av en webbsida. Programvaran överlever sidbesöket och aktiverar sig själv vid efterföljande besök. Svartvyn avgör vilka förfrågningar som går igenom och vilka som fångas upp och hanteras från ett cacheminne istället.

SW kan styra cachelagringen; kan cachelagra själva webbsidan, statiska resurser som JS, CSS, IMG, AJAX, deras innehåll och deras svarshuvuden, inklusive de som [VEC Helper-tillägg för mål](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) försöker ta bort, som X-Frame-Options: SAMEORIGIN, CSP (Content-Security-Policy) eller Set-Cookie.

Tyvärr tar Chrome-tilläggets API:er som fångar upp webbförfrågningar inte emot förfrågningar som fångats upp och hanterats av en SWF-fil. Tillägget kan därför inte åtgärda sidhuvuden och cookies om webbsidesbegäran hanterades från ett cacheminne av en SWF-fil eftersom webbsidan inte läses in i VEC på grund av X-Frame-Options eller CSP-rubriker som också cache-lagrades.

Som en möjlig tillfällig lösning kan du inaktivera Service Workers på fliken Chrome Developer Tools > Application (Verktyg för Chrome-utvecklare) och sedan aktivera kryssrutan&quot;Bypass for network&quot; (Kringgå för nätverk) under avsnittet Service Workers (Servicearbetare).

* Du använder Google Chrome 80+ med förbättrade principer för att framtvinga cookies för samma webbplats. Mer information finns i [Hur påverkar de nyligen meddelade reglerna för tillämpning av cookie-standarden Google Chrome SameSite de VEC?](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

Webbläsartillägget VEC Helper för Chrome löser problem med webbplatsinläsning som kunderna nu är beroende av [!DNL Target] [Förbättrad Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) eller tillägg från tredje part, till exempel Uppriktigt.

## Fördelar med att använda VEC Helper-tillägget

* Alla iframe-rubriker, som X-Frame-Options och Content-Security-Policy, tas implicit bort från webbplatsen. Du behöver inte längre skapa komplicerade regler.
* Om en webbsida ännu inte innehåller [!DNL Target] at.js JavaScript-bibliotek kan du använda tillägget för att mata in biblioteket så att du kan skapa upplevelser för webbplatsen. Du kan sedan skapa aktiviteter och köra frågor och svar med hjälp av förhandsgranskningslänkar.

  Observera att tillägget inte injicerar at.js med Enhanced Experience Composer (EEC), men funktionen SameSite Cookie finns fortfarande kvar. Om du vill mata in at.js på webbsidan stänger du av EEC.

* [Mobilvisningsrutor](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) stöds även utan [!UICONTROL Enhanced Experience Composer] (EEG).
* Kunder som inte är tidigare [!DNL Target] kan experimentera med [!DNL Target] även om deras IT-utvecklare ännu inte har implementerat [!DNL Target] på deras webbplatser.
* Partners som betjänar flera kunders webbplatser och [!DNL Target] konton har nu en enkel mekanism som stöder VEC-inläsning, i stället för att hantera flera regler i tredjepartsverktyg.

## Hämta och installera VEC Helper-webbläsartillägget

1. Navigera till [Webbläsartillägget Adobe Target VEC Helper i Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Klicka på **[!UICONTROL Add to Chrome > Add Extension]**.
1. Öppna VEC i [!DNL Target].
1. Klicka på ikonen för VEC Helper-webbläsartillägget ( ![VEC Helper: ikon](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ) i webbläsarens verktygsfält i Chrome när du arbetar i VEC eller [QA-läge](/help/main/c-activities/c-activity-qa/activity-qa.md).
1. (Villkorligt) Skjut upp **[!UICONTROL Inject Target Libraries]** växla till&quot;på&quot;-positionen om webbsidan ännu inte innehåller [!DNL Target] at.js JavaScript-bibliotek.

   Följande bild visar VEC Helper med [!UICONTROL Inject Target Libraries] aktiverad inställning:

   ![VEC-hjälp 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   Följande bild visar hur VEC Helper frågar om du vill att den ska injiceras [!DNL Target] bibliotek på sidan för att aktivera redigering:

   ![VEC-hjälp 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Villkorligt) Skjut upp **[!UICONTROL Cookies]** växla till&quot;på&quot;-positionen för att automatiskt lägga till `SameSite=None` korrigering av attributwebbläsare.

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
