---
keywords: adobe.target.applyOffer;applyOffer;applyoffer;apply offer;at.js;functions;function
description: Information om funktionen adobe.target.applyOffer(options) för JavaScript-biblioteket i Adobe Target at.js.
title: adobe.target.applyOffer(options)
feature: client-side
translation-type: tm+mt
source-git-commit: a841c492e5d9e4bfedb20133ba32e37daf738c57
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---


# adobe.target.applyOffer(options)

Den här funktionen används för att tillämpa svarsinnehållet.

>[!NOTE]
>
>`applyOffer` kräver  `mbox` parametern. Om inget mbox-namn anges inträffar ett fel.

Alternativparametern är obligatorisk och har följande struktur:

| Nyckel | Typ | Obligatoriskt | Beskrivning |
|--- |--- |--- |--- |
| mbox | Sträng | Ja | Mbox name<br>Med at.js 1.3.0 (och senare) Target tvingas mbox-nyckeln att användas. Den här nyckeln har krävts tidigare, men Target använder den nu för att säkerställa att Target har korrekt validering och att kunderna använder funktionen korrekt. |
| väljare | Sträng- eller DOM-element | Nej | HTML-element eller CSS-väljare som används för att identifiera det HTML-element där Target ska placera erbjudandeinnehållet. Om ingen väljare anges antar Target att det HTML-element som ska användas är HTML HEAD. |
| erbjudande | Array | Ja | En array-åtgärd som ska tillämpas på elementet. |

## Exempel {#section_D8D6A17B73DE4542937CDB687193A5CC}

I följande exempel visas hur du använder `getOffer` och `applyOffer` tillsammans:

```javascript
adobe.target.getOffer({   
  "mbox": "mbox",   
  "success": function(offers) {           
        adobe.target.applyOffer( {  
           "mbox": "mbox", 
           "offer": offers  
        } ); 
  },   
  "error": function(status, error) {           
      if (console && console.log) { 
        console.log(status); 
        console.log(error); 
      } 
  }, 
 "timeout": 5000 
}); 
```
