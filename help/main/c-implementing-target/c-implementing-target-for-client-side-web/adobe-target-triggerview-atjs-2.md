---
keywords: adobe.target.triggerView;triggerView;trigger view;trigger view;at.js;functions;function;viewName;view name;view name
description: Använd funktionen adobe.target.triggerView() för Adobe [!DNL Target] at.js JavaScript-bibliotek för användning i Single Page Applications (SPA). (at.js 2.x)
title: Hur använder jag funktionen adobe.target.triggerView()?
feature: at.js
role: Developer
exl-id: 619d5166-d1d9-49a6-9807-338544782e66
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---

# adobe.target.triggerView (viewName, options) - at.js 2.x

Den här funktionen kan anropas när en ny sida läses in eller när en komponent på en sida återges på nytt. `adobe.target.triggerView()` ska implementeras för applikationer för en sida (SPA) för att kunna använda Visual Experience Composer (VEC) för att skapa A/B-tester och XT-aktiviteter (Experience Targeting). If `adobe.target.triggerView()` har inte implementerats på platsen, VEC kan inte användas för SPA. Mer information finns i [Implementering av Single Page-program](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

>[!NOTE]
>
>Den här funktionen introducerades med at.js 2.x. Den här funktionen är inte tillgänglig för at.js version 1.*x*.

| Parameter | Typ | Obligatoriskt? | Beskrivning |
| --- | --- | --- | --- |
| viewName | Sträng | Ja | Ange valfritt namn som en strängtyp som du vill representera vyn. Vynamnet visas i [!UICONTROL Modifications] -panelen i VEC där marknadsförare kan skapa åtgärder och köra A/B- och XT-aktiviteter. |
| alternativ | Objekt | Nej |  |
| alternativ > sida | Boolean | Nej | **TRUE:** Standardvärdet för sidan är true. När page=true skickas meddelanden till [!DNL Target] för att öka antalet intryckta.<br>Ett meddelande skickas alltid som standard när en `triggerView` anropas utom när alternativ > sida är inställd på false.<br>**FALSE:** När page=false skickas inga meddelanden för ökat antal visningar. Detta bör användas när du endast vill återge en komponent på en sida med ett erbjudande. |

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
