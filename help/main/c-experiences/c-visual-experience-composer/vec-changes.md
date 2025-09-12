---
keywords: Visual experience disposition;vec;wysiwyg
description: Förstå ändringarna i Visual Experience Composer (VEC) i Adobe Target 25.2.1-utgåvan (17 februari 2025).
title: Vilka ändringar införs i den nya Visual Experience Composer (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: 2dabda04aabe720b28e31033052e2076e78d1376
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer] ändringar

Version [!DNL Adobe Target Standard/Premium] 25.2.1 (17 februari 2015) innehåller en uppdaterad version av [!UICONTROL Visual Experience Composer] (VEC). I den här artikeln förklaras skillnaderna mellan tidigare och uppdaterade versioner av VEC.

>[!IMPORTANT]
>
>Den uppdaterade [!UICONTROL Visual Editing Composer] kräver [!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper]-tillägget ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) som finns i [!DNL Chrome Web Store].

VEC visas när du skapar eller redigerar en befintlig aktivitet.

![Visual Experience Composer (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## Viktiga förändringar i VEC

I följande avsnitt förklaras de största förändringarna i den uppdaterade VEC jämfört med den tidigare versionen.

### [!UICONTROL Experiences] spår

Precis som i den tidigare versionen finns den [!UICONTROL Experiences] kvar på VEC:s vänstra sida. Rälen [!UICONTROL Experiences] kan inte komprimeras.

![Upplevelsefältet](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Du kan skapa, byta namn på eller ta bort upplevelser med hjälp av spåret [!UICONTROL Experiences]. Klicka på ikonen **[!UICONTROL Add]** ( ![Lägg till ](/help/main/assets/icons/Add.svg) ) för att lägga till en ny upplevelse. Klicka på ikonen [!UICONTROL More Actions] ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmall.svg) ) om du vill duplicera, ta bort eller omdirigera en upplevelse.

### [!UICONTROL Components] ratt (ny)

Du kan lägga till ett antal komponenter på webbsidan och redigera dem efter behov med den nya [!UICONTROL Components]-listen.

![Komponentspår](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

Om du vill lägga till en ny komponent markerar du den önskade komponenten från [!UICONTROL Components]-listen, håller pekaren över ett befintligt element på sidan och väljer sedan att infoga komponenten före eller efter det markerade elementet.

>[!NOTE]
>
>Om du ser [!UICONTROL Modifications]-rälen i det här området i stället för [!UICONTROL Components]-rälen klickar du på ikonen **[!UICONTROL Show Components]** ( ![Visa komponentikonen ](/help/main/assets/icons/Add.svg) ). Ikonen [!UICONTROL Show Components] ( ![Visa komponentikonen](/help/main/assets/icons/Add.svg) ) och ikonen [!UICONTROL Show Modifications] ( ![Visa ändringslinjen](/help/main/assets/icons/History.svg) ) fungerar som växlar för att visa lämpliga alternativ.
>
>Om du vill komprimera [!UICONTROL Components]-rälen och förstora arbetsytan i [!UICONTROL Design] medan [!UICONTROL Components]-rälen är öppen klickar du på ikonen ( ![Visa komponenter ](/help/main/assets/icons/Add.svg) ).

### [!UICONTROL Modifications] spår

Klicka på ikonen [!UICONTROL Modifications] ( [!UICONTROL Show Modifications]Visa ändringslinjen![ ) i ](/help/main/assets/icons/History.svg)-listen för att öppna [!UICONTROL Components]-listen. Rälen [!UICONTROL Modifications] ändrade position från höger sida till vänster på arbetsytan för redigering.

![Räler för ändringar](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

>[!NOTE]
>
>Ikonen [!UICONTROL Show Components] ( ![Visa komponentikonen](/help/main/assets/icons/Add.svg) ) och ikonen [!UICONTROL Show Modifications] ( ![Visa ändringslinjen](/help/main/assets/icons/History.svg) ) fungerar som växlar för att visa lämpliga alternativ.
>
>Klicka på ikonen [!UICONTROL Modifications] ( [!UICONTROL Design]Visa ändringslinjen [!UICONTROL Modifications] ) om du vill komprimera [!UICONTROL Show Modifications]-rälen och förstora arbetsytan i ![ medan ](/help/main/assets/icons/History.svg)-rälen är öppen.

Rälen [!UICONTROL Modifications] visar alla ändringar som har gjorts på sidan i VEC och gör att du kan göra ytterligare ändringar (till exempel CSS-väljare, Mbox och anpassad kod).

Klicka på ikonen [!UICONTROL More Options] ( ![ ikonen Fler åtgärder ](/help/main/assets/icons/MoreSmall.svg) ) om du vill lägga till en ändring, ta bort alla ändringar eller ta bort alla ogiltiga ändringar. Klicka på [!UICONTROL Select] om du vill utföra gruppåtgärder: [!UICONTROL Apply to All Pages] eller [!UICONTROL Delete].

Om du vill visa [!UICONTROL Modifications]-rälen igen klickar du på ikonen [!UICONTROL Hide Modifications] ( ![Visa ändringslinjen](/help/main/assets/icons/History.svg) ) i [!UICONTROL Modifications]-rälen.

### [!UICONTROL Properties] ratt (ny)

Med [!UICONTROL Properties]-spåret kan du ändra egenskaper för markerade element på sidan, oavsett om dessa element är HTML-element eller objekt som är specifika för [!DNL Target], till exempel rekommendationer eller erbjudanden.

![Egenskapsfältet](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Klicka på ikonerna ovanför listen för att redigera HTML-kod eller ta bort, duplicera eller dölja element. Ändringar visas i [!UICONTROL Modifications]-rälen.

![Egenskapsikoner](/help/main/c-experiences/c-visual-experience-composer/assets/options-icons.png)

Rälen [!UICONTROL Properties] kan döljas i den högra listen. Klicka på ikonen [!UICONTROL Show/Hide Properties] ( ![ egenskapsikonen ](/help/main/assets/icons/Propertie.svg) ) till höger om rälen för att komprimera eller visa [!UICONTROL Properties]-rälen.

### Aktivitetsinställningar/konfiguration

Klicka på ikonen [!UICONTROL Configure] ( ![ ikonen Konfigurera ](/help/main/assets/icons/Setting.svg) ) som visas högst upp på arbetsytan för design för att visa aktivitetsegenskapsmenyn.

![Alternativ för aktivitetskonfigurationer](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

Med de olika alternativen kan du tilldela egenskaper, redigera regler för sidleverans, ange webbplatsinställningar, lägga till ytterligare sidor och aktivera eller inaktivera flersidiga eller flera målgruppsaktiviteter. Tilldela [!UICONTROL Properties] är en [[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)-funktion.

Positionen och funktionaliteten liknar det tidigare VEC-gränssnittet.

### [!UICONTROL Design]/[!UICONTROL Browse] lägen

Använd de [!UICONTROL Design]/[!UICONTROL Browse]-växlar som visas ovanpå [!UICONTROL Properties]-strängen för att växla mellan design- och bläddringsläge.

![Designa och bläddra bland växlar](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Använd läget [!UICONTROL Browse] för att navigera på webbplatsen och för att välja den vy eller sida som du vill uppdatera. Växla tillbaka till läget [!UICONTROL Design] om du vill lägga till eller redigera dina ändringar.

### [!UICONTROL Undo]/[!UICONTROL Redo]

Du kan ångra ändringar som gjorts genom att klicka på ikonen [!UICONTROL Undo] ( ![Ångra-ikonen ](/help/main/assets/icons/Undo.svg) ).

![Ångra-ikonen i VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Om du vill göra om en åtgärd expanderar du knappgruppen Ångra/[!UICONTROL Redo] och väljer [!UICONTROL Redo].

### [!UICONTROL Design] arbetsyta

På arbetsytan i [!UICONTROL Design] kan du välja visningsrutor, inklusive anpassa till skärmen, [!UICONTROL Desktop], [!UICONTROL Tablet], [!UICONTROL Mobile Landscape] och [!UICONTROL Mobile Portrait].

![Alternativ för visningsruta](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

Med den uppdaterade VEC-funktionen kan du även zooma in eller ut genom att klicka på lämplig ikon ( ![ikonen Zooma in](/help/main/assets/icons/ZoomIn.svg) eller ![ikonen Zooma ut](/help/main/assets/icons/ZoomOut.svg) ).

## Visuell illustration med gränssnittsändringar

Följande bild visar de ändringar på hög nivå av användargränssnitt som gjorts i den uppdaterade VEC:n. I bildens överkant visas det uppdaterade VEC-gränssnittet och i nederkanten visas det tidigare gränssnittet. Pilar visar var olika element har flyttats.

(Klicka på bilden för att expandera den till webbläsarens hela bredd.)

![VEC-jämförelse - nytt till föregående användargränssnitt](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}

## Mer information om det uppdaterade användargränssnittet

* Versionsinformation för [[!DNL Target Standard/Premium] 25.2.1 (17 februari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Activities], [!UICONTROL Recommendations] och [!UICONTROL Visual Experience Composer] (VEC).

* Versionsinformation för [[!DNL Target Standard/Premium] 25.1.1 (9 januari 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Innehåller en sammanfattning av viktiga ändringar i användargränssnittet i [!DNL Target] för [!UICONTROL Offers Library].

* [Förstå  [!DNL Target] gränssnittet](/help/main/c-intro/understand-the-target-ui.md): Ger en kort översikt som hjälper dig att bekanta dig med [!DNL Target] och innehåller länkar till mer detaljerad information och stegvisa instruktioner.

* [[!UICONTROL Visual Experience Composer] ändringar ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): [!DNL Adobe Target Standard/Premium] 25.2.1-versionen (17 februari 2025) innehåller en uppdaterad version av [!UICONTROL Visual Experience Composer] (VEC). I den här artikeln förklaras skillnaderna mellan äldre och uppdaterade versioner av VEC.

* [[!UICONTROL Visual Experience Composer] alternativ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): I den här artikeln förklaras det uppdaterade VEC-gränssnittet och dess alternativ.

* [[!DNL Target] Vanliga frågor och svar om gränssnittsuppdatering](/help/main/c-intro/updated-ui-faq.md): Här behandlas vanliga frågor om det nya [!DNL Target] användargränssnittet och [!UICONTROL Visual Experience Composer] (VEC), inklusive navigeringsändringar, funktionsplatser och borttagning av den tillfälliga användargränssnittsversionen. Vare sig du är marknadsförare, utvecklare eller administratör kan du med de här vanliga frågorna få en smidig övergång och få ut det mesta av det uppdaterade användargränssnittet.