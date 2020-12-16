---
keywords: adobe.target.triggerView;triggerView;triggerview;trigger view;at.js;functions;function;viewName;viewname;view name
description: Information om funktionen adobe.target.triggerView (viewName, options) för JavaScript-biblioteket i Adobe Target at.js.
title: adobe.target.triggerView (viewName, options) - at.js 2.x
feature: client-side
translation-type: tm+mt
source-git-commit: a841c492e5d9e4bfedb20133ba32e37daf738c57
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---


# adobe.target.triggerView (viewName, options) - at.js 2.x

Den här funktionen kan anropas när en ny sida läses in eller när en komponent på en sida återges på nytt. `adobe.target.triggerView()` ska implementeras för applikationer för en sida (SPA) för att kunna använda Visual Experience Composer (VEC) för att skapa A/B-tester och XT-aktiviteter (Experience Targeting). Om `adobe.target.triggerView()` inte implementeras på platsen kan VEC inte användas för SPA. Mer information finns i [Implementering av Single Page-program](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

>[!NOTE]
>
>Den här funktionen introducerades med at.js 2.x. Den här funktionen är inte tillgänglig för at.js version 1.*x*.

| Parameter | Typ | Obligatoriskt? | Beskrivning |
| --- | --- | --- | --- |
| viewName | Sträng | Ja | Ange valfritt namn som en strängtyp som du vill representera vyn. Vynamnet visas på panelen [!UICONTROL Modifications] i VEC så att marknadsförare kan skapa åtgärder och köra A/B- och XT-aktiviteter för dem. |
| alternativ | Objekt | Nej |  |
| alternativ > sida | Boolean | Nej | **TRUE:** Standardvärdet för sidan är true. När page=true skickas meddelanden till [!DNL Target]-backend-objektet för att öka antalet intryckningar.<br>Ett meddelande skickas alltid som standard när en  `triggerView` anropas, utom när alternativen > sida är inställda på false.<br>**FALSE:** När page=false skickas inga meddelanden för ökat antal visningar. Detta bör användas när du endast vill återge en komponent på en sida med ett erbjudande. |

## Exempel: True

`triggerView()` anropa för att skicka ett meddelande till Target-backend för att öka aktivitetsinavbildningar och andra mätvärden.

```javascript
adobe.target.triggerView("homeView")
```

## Exempel: Falskt

`triggerView()` anrop om att inte få meddelanden skickade till Target-backend för att göra en inläsning.

```javascript
adobe.target.triggerView("homeView", {page: false})
```
