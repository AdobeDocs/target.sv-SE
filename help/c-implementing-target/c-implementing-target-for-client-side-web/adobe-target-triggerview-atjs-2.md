---
keywords: adobe.target.triggerView;triggerView;triggerview;trigger view;at.js;functions;function;viewName;viewname;view name
description: Information om funktionen adobe.target.triggerView (viewName, options) för Adobe Target at.js JavaScript-biblioteket.
title: Information om funktionen adobe.target.triggerView (viewName, options) för Adobe Target at.js JavaScript-biblioteket.
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# adobe.target.triggerView (viewName, options) - at.js 2.x

Den här funktionen kan anropas när en ny sida läses in eller när en komponent på en sida återges på nytt. `adobe.target.triggerView()` ska implementeras för applikationer för en enda sida (SPA) för att använda Visual Experience Composer (VEC) för att skapa A/B-tester och XT-aktiviteter (Experience Targeting). Om `adobe.target.triggerView()` inte implementeras på platsen kan VEC inte användas för SPA. Mer information finns i Implementering [av](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)Single Page-program.

>[!NOTE]
>
>Den här funktionen introducerades med at.js 2.x. Den här funktionen är inte tillgänglig för at.js version 1.*x*.

| Parameter | Typ | Obligatoriskt? | Beskrivning |
| --- | --- | --- | --- |
| viewName | Sträng | Ja | Ange valfritt namn som en strängtyp som du vill representera vyn. Vynamnet visas på VEC-panelen [!UICONTROL Modifications] där marknadsförare kan skapa åtgärder och köra A/B- och XT-aktiviteter. |
| alternativ | Objekt | Nej |  |
| alternativ > sida | Boolean | Nej | **TRUE:** Standardvärdet för sidan är true. När page=true skickas meddelanden till [!DNL Target] backend-objektet för att öka antalet intryckningar.<br>Om ingen aktivitetsupplevelse eller aktivitetsmått är associerad med vyn skickas inget meddelande.<br>**FALSE:**När page=false skickas inga meddelanden för ökat antal visningar. Detta bör användas när du endast vill återge en komponent på en sida med ett erbjudande. |

## Exempel: True

`triggerView()` anropa för att skicka ett meddelande till Target-backend för att öka aktivitetsinavbildningar och andra mätvärden.

```
adobe.target.triggerView("homeView")
```

## Exempel: Falskt

`triggerView()` anrop om att inte få meddelanden skickade till Target-backend för att göra en inläsning.

```
adobe.target.triggerView("homeView", {page: false})
```
