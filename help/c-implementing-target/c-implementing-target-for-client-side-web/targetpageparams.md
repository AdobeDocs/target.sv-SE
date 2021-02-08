---
keywords: targetPageParams;målpageparams;pageParams;pageparams;page params;page parameters;at.js;functions;function
description: Använd funktionen targetPageParams() för JavaScript-biblioteket för Adobe Target at.js om du vill koppla parametrar till den globala mbox utanför begärandekoden.
title: Hur använder jag funktionen targetPageParams()?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# targetPageParams() {#reference_B235C9F6DA79449ABE3E23F914FEABAE}

Med den här metoden kan du bifoga parametrar till den globala mbox utanför begärandekoden.

Den här funktionen är mycket användbar om du vill ta med samma uppsättning parametrar för flera mbox-anrop. Funktionen måste definieras av kunden. Den ska returnera en array med parametrar som bara skickas till den globala mbox-begäran. Den här funktionen kan definieras innan at.js har lästs in eller i **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit]** > **[!UICONTROL Library Header]**.

Du kan skicka in parametrar till target-global-mbox med funktionen `targetPageParams()` på något av följande sätt:

* En avgränsad lista
* En array
* Ett JSON-objekt

## Exempel

Et-avgränsad lista (värdena måste vara URL-kodade):

```javascript
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Array (värdena behöver inte vara URL-kodade):

```javascript
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (värdena behöver inte vara URL-kodade):

```javascript
targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
        "age": 26, 
        "country": { 
          "city": "San Francisco" 
        } 
      } 
  }; 
};
```
