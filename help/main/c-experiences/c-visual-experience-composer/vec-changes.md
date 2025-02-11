---
keywords: Visual experience disposition;vec;wysiwyg
description: Förstå ändringarna i Visual Experience Composer (VEC) i Adobe Target 25.2.1-utgåvan (11 februari 2025).
title: Vilka ändringar införs i den nya Visual Experience Composer (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: 3d6597c869d5959e34c6108d6c8b9bfa750ab6c6
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer] ändringar

Version [!DNL Adobe Target Standard/Premium] 25.2.1 (11 februari 2015) innehåller en uppdaterad version av [!UICONTROL Visual Experience Composer] (VEC). I den här artikeln förklaras skillnaderna mellan tidigare och uppdaterade versioner av VEC.

>[!IMPORTANT]
>
>Det uppdaterade [!UICONTROL Visual Editing Composer] kräver [!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper]-tillägget ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) som är tillgängligt på Chrome Web Store.

VEC visas när du skapar eller redigerar en befintlig aktivitet.

![Visual Experience Composer (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/new-vec.png)

## Viktiga förändringar i VEC

I följande avsnitt förklaras de största förändringarna i den uppdaterade VEC jämfört med den tidigare versionen.

### Panelen [!UICONTROL Experiences]

Precis som i den tidigare versionen finns panelen [!UICONTROL Experiences] kvar på VEC:s vänstra sida. Det går inte att komprimera panelen [!UICONTROL Experiences].

![Panelen Erfarenheter](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Du kan skapa, byta namn på eller ta bort upplevelser med panelen [!UICONTROL Experiences]. Klicka på ikonen **[!UICONTROL Add]** ( ![Lägg till ](/help/main/assets/icons/Add.svg) ) för att lägga till en ny upplevelse. Klicka på ikonen [!UICONTROL More Actions] ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmall.svg) ) om du vill duplicera, ta bort eller omdirigera en upplevelse.

### [!UICONTROL Components] panel (ny)

Du kan lägga till ett antal komponenter på webbsidan och redigera dem med den nya [!UICONTROL Components]-panelen.

![Panelen Komponenter](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

Om du vill lägga till en ny komponent drar du komponenten som du vill infoga över ett befintligt sidelement på arbetsytan för redigering. Välj sedan att infoga komponenten före eller efter det markerade elementet.

Jämfört med den tidigare VEC-versionen kan du inte ersätta ett markerat element med en komponent.

### Panelen [!UICONTROL Modifications]

Om du vill öppna panelen [!UICONTROL Modifications] klickar du på ikonen [!UICONTROL Show Modifications] ( ![Visa ändringspanelen](/help/main/assets/icons/History.svg) ) på panelen [!UICONTROL Components] . Panelen [!UICONTROL Modifications] ändrade position från höger sida till vänster på arbetsytan för redigering.

![Panelen Ändringar](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

Panelen [!UICONTROL Modifications] visar alla ändringar som har gjorts på sidan i [!UICONTROL Visual Experience Composer] (VEC) och gör att du kan göra ytterligare ändringar (till exempel CSS-väljare, Mbox och anpassad kod).

Klicka på ikonen [!UICONTROL More Options] ( ![ ikonen Fler åtgärder ](/help/main/assets/icons/MoreSmall.svg) ) om du vill lägga till en ändring, ta bort alla ändringar eller ta bort alla ogiltiga ändringar. Klicka på [!UICONTROL Select] om du vill utföra gruppåtgärder: [!UICONTROL Apply to All Pages] eller [!UICONTROL Delete].

### [!UICONTROL Properties] panel (ny)

Med den nya panelen [!UICONTROL Properties] kan du ändra egenskaper för markerade element på sidan, oavsett om dessa element är HTML-element eller objekt som är specifika för [!DNL Target], till exempel rekommendationer eller erbjudanden.

![Egenskapspanelen](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Klicka på ikonerna överst på panelen för att redigera HTML-kod eller ta bort, duplicera eller dölja element. Ändringarna visas på panelen [!UICONTROL Modifications].

Panelen [!UICONTROL Properties] kan komprimeras i den högra listen. Klicka på ikonen [!UICONTROL Show/Hide Properties] ( ![ egenskapsikonen ](/help/main/assets/icons/Propertie.svg) ) till höger om panelen för att komprimera eller visa panelen [!UICONTROL Properties].

### Aktivitetsinställningar/konfiguration

Klicka på ikonen [!UICONTROL Configure] ( ![ ikonen Konfigurera ](/help/main/assets/icons/Setting.svg) ) som visas högst upp på arbetsytan för design för att visa aktivitetsegenskapsmenyn.

![Alternativ för aktivitetskonfigurationer](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

Med de olika alternativen kan du aktivera eller inaktivera flersidiga eller flera målgruppsaktiviteter, tilldela egenskaper ([[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)-funktion) eller redigera regler för sidleverans.

Positionen och funktionaliteten liknar det tidigare VEC-gränssnittet.

### [!UICONTROL Design]/[!UICONTROL Browse] lägen

Använd de [!UICONTROL Design]/[!UICONTROL Browse]-reglage som visas ovanpå arbetsytan för att växla mellan design- och bläddringsläge.

![Designa och bläddra bland växlar](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Använd läget [!UICONTROL Browse] för att navigera på webbplatsen och för att välja den vy eller sida som du vill uppdatera. Växla tillbaka till läget [!UICONTROL Design] om du vill lägga till eller redigera dina ändringar.

### [!UICONTROL Undo]/[!UICONTROL Redo]

Du kan ångra ändringar som gjorts genom att klicka på ikonen [!UICONTROL Undo] ( ![Ångra-ikonen ](/help/main/assets/icons/Undo.svg) ).

![Ångra-ikonen i VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Om du vill göra om en åtgärd expanderar du knappgruppen Ångra/[!UICONTROL Redo] och väljer [!UICONTROL Redo].

### [!UICONTROL Design] arbetsyta

På arbetsytan i [!UICONTROL Design] kan du välja visningsrutor, inklusive anpassa till skärmen, [!UICONTROL Desktop], [!UICONTROL Tablet], [!UICONTROL Mobile Landscape] och [!UICONTROL Mobile Portrait]. Som standard passar arbetsytan sidan på skärmen tillsammans med de visningsrutor som definieras i avsnittet [Administration](/help/main/administrating-target/visual-experience-composer-set-up.md) .

![Alternativ för visningsruta](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

Med den uppdaterade VEC-funktionen kan du även zooma in eller ut genom att klicka på lämplig ikon ( ![ikonen Zooma in](/help/main/assets/icons/ZoomIn.svg) eller ![ikonen Zooma ut](/help/main/assets/icons/ZoomOut.svg) ).

## Visuell illustration med gränssnittsändringar

Följande bild visar de ändringar på hög nivå av användargränssnitt som gjorts i den uppdaterade VEC:n. I bildens överkant visas det uppdaterade VEC-gränssnittet och i nederkanten visas det tidigare gränssnittet. Pilar visar var olika element har flyttats.

(Klicka på bilden för att expandera den till webbläsarens hela bredd.)

![VEC-jämförelse - nytt till föregående användargränssnitt](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}