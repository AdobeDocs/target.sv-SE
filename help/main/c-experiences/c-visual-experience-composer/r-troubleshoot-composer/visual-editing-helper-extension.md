---
keywords: vec;Visual experience composer; vec;iframe;extension;browser;faq
description: Upptäck varför vissa webbplatser inte kan öppnas på ett tillförlitligt sätt i [!UICONTROL Visual Experience Composer] (VEC). The [!UICONTROL Visual Editing Helper] Med webbläsartillägg kan du läsa in webbplatser på ett tillförlitligt sätt i VEC.
title: Hur jag använder [!UICONTROL Visual Editing Helper] Tillägget?
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: 30ad6712d9722854384721ca20d38a605930c4d7
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# [!UICONTROL Visual Editing Helper] extension

The [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] webbläsartillägg för Google Chrome gör att du kan läsa in webbplatser tillförlitligt i [!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) för att snabbt skapa och skapa QA-webbupplevelser.

>[!IMPORTANT]
>
>Det nya tillägget ersätter det föregående [Webbläsartillägg för målets VEC-hjälp](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md). Se viktig text högst upp i den artikeln.

## Orsaker till att vissa webbplatser kanske inte öppnas som de ska i VEC

* Webbplatsen har strikta säkerhetsprinciper.
* Webbplatsen ligger i en iframe.
* Kundens QA- eller stage-sajt är inte tillgänglig för omvärlden (webbplatsen är intern).

The [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] webbläsartillägg för Chrome löser problem med inläsning av webbplatser som kunderna nu förlitar sig på [!DNL Target] [Förbättrad Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) eller tillägg från tredje part, till exempel Uppriktigt.

## Fördelar med att använda [!UICONTROL Visual Editing Helper] extension

* Alla iframe-busting-rubriker, som `X-Frame-Options` och `Content-Security-Policy`, tas implicit bort från webbplatsen. Du behöver inte skapa komplicerade regler för att få rätt.
* Om en webbsida ännu inte innehåller [!DNL Target] at.js-biblioteket kan du använda tillägget för att mata in biblioteket så att du kan skapa upplevelser för webbplatsen. Du kan sedan skapa aktiviteter och köra frågor och svar med hjälp av förhandsgranskningslänkar.

   Använda [Förbättrad Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec), inkluderar tillägget inte at.js, men funktionen SameSite Cookie finns fortfarande. Om du vill mata in at.js på webbsidan stänger du av EEC.

* [Mobilvisningsrutor](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) stöds även utan [!UICONTROL Enhanced Experience Composer] (EEG).
* Kunder som är nybörjare på [!DNL Target] kan använda tillägget för att experimentera med [!DNL Target] även om deras IT-utvecklare ännu inte har implementerat [!DNL Target] på deras webbplatser.
* Partners som betjänar flera kunders webbplatser och [!DNL Target] konton har nu en enkel mekanism som stöder VEC-inläsning, i stället för att hantera flera regler i tredjepartsverktyg.

## Hämta och installera [!UICONTROL Visual Editing Helper] webbläsartillägg

1. Navigera till [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] webbläsartillägg i Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Klicka på **[!UICONTROL Add to Chrome]** > **[!UICONTROL Add Extension]**.
1. Öppna VEC i [!DNL Target].
1. Om du vill använda tillägget klickar du på [!UICONTROL Visual Editing Helper] ikon för webbläsartillägg ( ![Ikon för tillägg för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) i webbläsarens verktygsfält i Chrome när du är i VEC- eller QA-läge.

   The [!UICONTROL Visual Editing Helper] aktiveras automatiskt när en webbplats öppnas i [!UICONTROL Target] VEC för framtagning av material. Tillägget har inga villkorsinställningar. Tillägget hanterar alla inställningar automatiskt, inklusive inställningarna för cookies för samma plats.

   Mer information om `SameSite=None` korrigering av attributwebbläsare, se&quot;Hur påverkar de nyligen meddelade reglerna för tillämpning av cookies i Google Chrome SameSite hur VEC och EEC fungerar?&quot; in [Felsökning av problem relaterade till Visual Experience Composer och Enhanced Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Anteckningar

* För [!DNL Target]läser tillägget in den senaste versionen av at.js som är tillgänglig från [!DNL Target] Användargränssnitt i [!UICONTROL Administration] > [!UICONTROL Implementation] och at.js hämtar redigeringsbiblioteken.
* När tillägget används för att injicera at.js i [QA-läge](/help/main/c-activities/c-activity-qa/activity-qa.md)måste du ha en annan flik i Chrome öppen. Denna Chrome-flik måste autentiseras till samma [!DNL Adobe Experience Cloud] organisation där du skapade aktiviteten.
* Följande meddelanden hjälper dig att hålla dig informerad:

   * Om du försöker att läsa in en webbplats med VEC som inte kan läsas in visas ett meddelande om att du har installerat [!UICONTROL Visual Editing Helper] webbläsartillägg.
   * Om at.js eller alloy.js ännu inte har implementerats på webbplatsen visas ett meddelande i VEC om att du har installerat tillägget.
* Om du försöker använda det nya tillägget går du tillbaka till [gammalt tillägg](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) och [!DNL Target] kan inte läsa in webbplatsen, rensa alla webbläsardata och inaktivera det nya tillägget.

## Vanliga frågor

### Gör tillägget, när det är aktivt, något när det används utanför [!DNL Adobe Target] eller [!UICONTROL Adobe Journey Optimizer] (AJO)?

Tillägget aktiveras bara när webbplatsen i fråga läses in inuti en iFrame i [!DNL Adobe] produkter ([!DNL Target], [!DNL AJO]). Utanför det här flödet försöker tillägget inte lägga till, ta bort eller ändra några rubriker och tillägget försöker inte att mata in någon kod inuti webbplatsen.

### Vad gör tillägget när det är aktivt i [!DNL Adobe Target] VEC?

När en webbplats läses in inuti en iFrame in [!DNL Adobe] produkter ([!DNL Target], [!DNL AJO]) infogar tillägget kod (medföljer tillägget) på webbplatsen och hämtar hjälpfiler från [!DNL Adobe] CDN för visuell redigering.
