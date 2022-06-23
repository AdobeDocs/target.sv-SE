---
keywords: targetPageParamsAll;targetPageparamsall;PageParamsAll;pageparamsall;page params;page parameters;at.js;functions;function
description: Använd funktionen targetPageParamsAll() för Adobe [!DNL Target] at.js JavaScript-bibliotek för att bifoga parametrar till alla mbox-filer utanför begärandekoden.
title: Hur använder jag funktionen targetPageParamsAll()?
feature: at.js
role: Developer
exl-id: 58fbb62e-30da-486f-b771-6452ad5e27e6
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# targetPageParamsAll()

Med den här metoden kan du bifoga parametrar till alla rutor utanför begärandekoden.

Detta är mycket användbart om du vill inkludera samma uppsättning parametrar för flera mbox-anrop. Funktionen måste definieras av kunden. Den ska returnera en array med parametrar som skickas till alla mbox-begäranden på sidan. Funktionen kan definieras innan at.js läses in eller **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

Du kan skicka in parametrar till target-global-mbox med funktionen targetPageParamsAll() på något av följande sätt:

* En avgränsad lista
* En array
* Ett JSON-objekt

## Exempel

Et-avgränsad lista (värdena måste vara URL-kodade):

```javascript
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Array (värdena behöver inte vara URL-kodade):

```javascript
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (värdena behöver inte vara URL-kodade):

```javascript
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
