---
keywords: targetPageParamsAll;targetpageparamsall;PageParamsAll;pageparamsall;page params;page parameters;at.js;functions;function
description: Information om funktionen targetPageParamsAll() för JavaScript-biblioteket för Adobe Target at.js.
title: Information om funktionen targetPageParamsAll() för JavaScript-biblioteket för Adobe Target at.js.
feature: null
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# targetPageParamsAll()

Med den här metoden kan du bifoga parametrar till alla rutor utanför begärandekoden.

Detta är mycket användbart om du vill inkludera samma uppsättning parametrar för flera mbox-anrop. Funktionen måste definieras av kunden. Den ska returnera en array med parametrar som skickas till alla mbox-begäranden på sidan. Den här funktionen kan definieras innan at.js har lästs in eller i **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

Du kan skicka in parametrar till target-global-mbox med funktionen targetPageParamsAll() på något av följande sätt:

* En avgränsad lista
* En array
* Ett JSON-objekt

## Exempel

Et-avgränsad lista (värdena måste vara URL-kodade):

```
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Array (värdena behöver inte vara URL-kodade):

```
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (värdena behöver inte vara URL-kodade):

```
targetPageParamsAll = function() { 
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
