---
keywords: vec;visual experience disposition; vec;iframe;extension;browser;faq
description: Identifiera varför vissa webbplatser kanske inte kan öppnas på ett tillförlitligt sätt i [!UICONTROL Visual Experience Composer] (VEC). Med webbläsartillägget [!UICONTROL Visual Editing Helper] kan du läsa in webbplatser tillförlitligt i VEC.
title: Hur använder jag [!UICONTROL Visual Editing Helper]-tillägget?
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: c41580bcbecf2eb2c14f13ce8e66e854c655d059
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---

# [!UICONTROL Visual Editing Helper]-tillägg

Med webbläsartillägget [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] för [!DNL Google Chrome] kan du läsa in webbplatser tillförlitligt i [!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) för att snabbt skapa och skapa QA-webbupplevelser.

>[!IMPORTANT]
>
>* Det här nya tillägget ersätter det tidigare [VEC Helper-webbläsartillägget &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md). Se viktig text högst upp i den artikeln. På grund av säkerhetsförbättringar i manifest v3, kräver [!DNL Adobe] att det nya tillägget hämtas för att du ska kunna fortsätta att redigera dina webbplatser visuellt i [!DNL Target].

## Orsaker till att vissa webbplatser kanske inte öppnas som de ska i VEC

* Webbplatsen har strikta säkerhetsprinciper.
* Webbplatsen ligger i en iframe.
* Kundens QA- eller stage-sajt är inte tillgänglig för omvärlden (webbplatsen är intern).

Webbläsartillägget [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] för att lösa problem med webbplatsinläsning som kunderna nu förlitar sig på [!DNL Target] [Förbättrad Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) eller tillägg från tredje part, som TrueÄrligt.

## Fördelar med att använda tillägget [!UICONTROL Visual Editing Helper]

* Alla iframe-busting-huvuden, som `X-Frame-Options` och `Content-Security-Policy`, tas implicit bort från webbplatsen. Du behöver inte skapa komplicerade regler för att få rätt.
* Om en webbsida ännu inte innehåller biblioteket [!DNL Target] at.js kan du använda tillägget för att mata in biblioteket så att du kan skapa upplevelser för webbplatsen. Du kan sedan skapa aktiviteter och köra frågor och svar med hjälp av förhandsgranskningslänkar.

  Med [Förbättrad Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) injiceras inte at.js i tillägget, men funktionen SameSite Cookie finns fortfarande. Om du vill mata in at.js på webbsidan stänger du av EEC.

* [Mobila visningsrutor](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) stöds även utan [!UICONTROL Enhanced Experience Composer] (EEC).
* Kunder som är nya i [!DNL Target] kan använda tillägget för att experimentera med [!DNL Target], även om deras IT-utvecklare ännu inte har implementerat [!DNL Target] på sina webbplatser.
* Partners som betjänar flera kunders webbplatser och [!DNL Target]-konton har nu en enkel mekanism som stöder VEC-inläsning, i stället för att hantera flera regler i tredjepartsverktyg.

## Hämta och installera webbläsartillägget [!UICONTROL Visual Editing Helper]

1. Navigera till webbläsartillägget [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] i Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Klicka på **[!UICONTROL Add to Chrome]** > **[!UICONTROL Add Extension]**.
1. Öppna VEC i [!DNL Target].
1. Om du vill använda tillägget klickar du på ikonen [!UICONTROL Visual Editing Helper] för webbläsartillägg ( ![&#x200B; ikonen för visuell redigeringstillägg &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) i Chrome webbläsares verktygsfält när du är i VEC- eller QA-läge.

   [!UICONTROL Visual Editing Helper] aktiveras automatiskt när en webbplats öppnas i VEC:n [!UICONTROL Target] så att den kan användas för redigering. Tillägget har inga villkorsinställningar. Tillägget hanterar alla inställningar automatiskt, inklusive inställningarna för cookies för samma plats.

   Mer information om korrigeringen för attributwebbläsaren `SameSite=None` finns i&quot;Hur påverkar den nyligen lanserade policyn för tillämpning av cookies i Google Chrome SameSite?&quot; i [Felsökning av problem relaterade till Visual Experience Composer och Enhanced Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Anteckningar

* För [!DNL Target] läser tillägget in den senaste versionen av at.js som är tillgänglig från [!DNL Target] användargränssnittet i [!UICONTROL Administration] > [!UICONTROL Implementation] och at.js hämtar redigeringsbiblioteken.
* När du använder tillägget för att injicera at.js i [QA Mode](/help/main/c-activities/c-activity-qa/activity-qa.md) måste du ha en annan Chrome-flik öppen. Den här Chrome-fliken måste autentiseras i samma [!DNL Adobe Experience Cloud]-organisation som du skapade aktiviteten i.
* Följande meddelanden hjälper dig att hålla dig informerad:

   * Om du försöker läsa in en webbplats med VEC som inte kan läsas in visas ett meddelande om att du har installerat webbläsartillägget [!UICONTROL Visual Editing Helper].
   * Om at.js eller alloy.js ännu inte har implementerats på webbplatsen visas ett meddelande i VEC om att du har installerat tillägget.
* Om du försöker använda det nya tillägget och sedan går tillbaka till det [gamla tillägget](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) och [!DNL Target] inte kan läsa in din webbplats, rensar du alla webbläsardata och inaktiverar det nya tillägget.

## Vanliga frågor

### Gör tillägget, när det är aktivt, något när det används utanför [!DNL Adobe Target] eller [!UICONTROL Adobe Journey Optimizer] (AJO)?

Tillägget aktiveras bara när webbplatsen iFrame läses in i [!DNL Adobe] produkter ([!DNL Target], [!DNL AJO]). Utanför det här flödet försöker tillägget inte lägga till, ta bort eller ändra några rubriker och tillägget försöker inte att mata in någon kod inuti webbplatsen.

### Vad gör tillägget när det är aktivt i VEC:n [!DNL Adobe Target]?

När en webbplats läses in inuti en iFrame i [!DNL Adobe]-produkter ([!DNL Target], [!DNL AJO]) infogar tillägget kod (som medföljer tillägget) på webbplatsen och hämtar hjälpfiler från [!DNL Adobe] CDN för att aktivera visuell redigering.
