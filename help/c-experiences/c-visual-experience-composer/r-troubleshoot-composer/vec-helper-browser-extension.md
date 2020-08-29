---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Information om hur du använder webbläsartillägget Adobe Target Visual Experience Composer (VEC) för att läsa in webbplatser tillförlitligt i VEC för att snabbt skapa och skapa QA-upplevelser.
title: Hjälptillägg för Adobe Target Visual Experience Composer (VEC)
feature: vec
topic: Standard
translation-type: tm+mt
source-git-commit: c77561696c35a5890c10591fc1014d812485f0f8
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 0%

---


# Hjälptillägg för Visual Experience Composer

Med webbläsartillägget VEC ( [!DNL Adobe Target] Visual Experience Composer) Helper för Google Chrome kan du läsa in webbplatser tillförlitligt i VEC för att snabbt skapa och skapa QA-webbupplevelser.

Orsaker till att vissa webbplatser kanske inte öppnas som de ska i VEC:

* Webbplatsen har strikta säkerhetsprinciper.
* Webbplatsen ligger i en iframe.
* at.js-biblioteket är ännu inte implementerat på webbplatsen.
* Kundens QA- och/eller scensajt är inte tillgänglig för omvärlden (webbplatsen är intern).
* Du använder Google Chrome 80+ med förbättrade efterlevnadsprinciper för cookie-appar för samma webbplats. Mer information finns i [Hur påverkar den nyligen lanserade policyn för Google Chrome SameSite-cookie reglerna VEC och EEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

VEC Helper-webbläsartillägget för Chrome löser problem med webbplatsinläsning som kunderna nu förlitar sig på [!DNL Target] [!UICONTROL Enhanced Experience Composer] eller tillägg från tredje part, som TrueSant.

Fördelar med att använda VEC Helper-tillägget:

* Alla iframe-rubriker, som X-Frame-Options och Content-Security-Policy, tas implicit bort från webbplatsen. Du behöver inte längre skapa komplicerade regler för att göra detta.
* Om en webbsida ännu inte innehåller JavaScript-biblioteket [!DNL Target] at.js kan du använda tillägget för att mata in biblioteket så att du kan skapa upplevelser för webbplatsen. Du kan sedan skapa aktiviteter och köra frågor och svar med hjälp av förhandsgranskningslänkar.
* Mobila visningsrutor stöds även utan [!UICONTROL Enhanced Experience Composer] (EEC).
* Kunder som inte är tidigare [!DNL Target] kan använda tillägget för att experimentera med [!DNL Target] , även om deras IT-utvecklare ännu inte har implementerat [!DNL Target] på sina webbplatser.
* Partners som betjänar flera kunders webbplatser och [!DNL Target] konton har nu en enkel mekanism som stöder VEC-inläsning, i stället för att hantera flera regler i tredjepartsverktyg.

## Hämta och installera VEC Helper-webbläsartillägget

1. Navigera till webbläsartillägget [Adobe Target VEC Helper i Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Klicka på [!UICONTROL Add to Chrome > Add Extension].
1. Om du vill använda tillägget klickar du på ikonen för VEC Helper-webbläsartillägget ( ![VEC Helper-ikonen](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ) i webbläsarens verktygsfält när du är i VEC- eller [QA-läge](/help/c-activities/c-activity-qa/activity-qa.md).

I följande bild visas VEC Helper med [!UICONTROL Inject Target Libraries] inställningen aktiverad:

![VEC-hjälp 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

Följande bild visar VEC Helper där du tillfrågas om du vill att den ska injicera [!DNL Target] bibliotek på sidan för att möjliggöra redigering:

![VEC-hjälp 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

## Anteckningar

* Implementeringen måste använda biblioteket [!DNL Target] at.js. Du kan inte använda en mbox.js-implementering med tillägget.
* Flaggan [!UICONTROL Inject Target libraries] i tillägget är som standard AV. Du kan aktivera den här flaggan om du vill använda VEC på en webbplats som ännu inte har implementerats för [!DNL Target].

   Tänk på att den här flaggan är en global inställning. Flaggan är aktiverad eller inaktiverad för alla webbplatser som öppnas i VEC. Om du t.ex. anger den här flaggan som ON och öppnar en webbplats som redan har implementerats med at.js får du ett meddelande om att at.js redan har lästs in. Vi räknar med att de flesta kunder redan har at.js implementerat på sina sidor och att de kommer att använda standardinställningen OFF.

* Tillägget läser in den senaste versionen av at.js som är tillgänglig från [!DNL Target UI] i [!UICONTROL Administration > Implementation].
* När du använder tillägget för att injicera at.js i [QA-läge](/help/c-activities/c-activity-qa/activity-qa.md)måste du ha en annan flik i Chrome öppen. Denna Chrome-flik måste autentiseras i samma [!DNL Adobe Experience Cloud] organisation som du skapade aktiviteten i.
* Följande meddelanden hjälper dig att hålla dig informerad:

   * Om du försöker läsa in en webbplats med VEC som inte kan läsas in visas ett meddelande om att du har installerat webbläsartillägget VEC Helper.
   * Om at.js ännu inte har implementerats på webbplatsen visas ett meddelande i VEC om att du har installerat tillägget.
   * Om tillägget är aktiverat och aktiverar inläsningen visas meddelanden när tillägget injicerar at.js-biblioteket (om det behövs) eller hjälper till att öppna webbplatsen på ett tillförlitligt sätt i VEC.