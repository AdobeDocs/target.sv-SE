---
keywords: adobe.target.applyOffer;applyOffer;applyoffer;apply offer;at.js;functions;function
description: Information om funktionen adobe.target.applyOffer(options) för JavaScript-biblioteket för Adobe Target at.js.
title: Information om funktionen adobe.target.applyOffer() för JavaScript-biblioteket för Adobe Target at.js.
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# adobe.target.applyOffer(options) {#reference_BBE83F513B5B4E03BBC3F50D90864245}

Den här funktionen används för att tillämpa svarsinnehållet.

>[!NOTE]
>
>`applyOffer` kräver `mbox` parametern. Om inget mbox-namn anges inträffar ett fel.

Alternativparametern är obligatorisk och har följande struktur:

| Nyckel | Typ | Obligatoriskt | Beskrivning |
|--- |--- |--- |--- |
| mbox | Sträng | Ja | Mbox<br>nameWith at.js 1.3.0 (och senare) Target använder mbox-nyckeln. Den här nyckeln har krävts tidigare, men Target använder den nu för att säkerställa att Target har korrekt validering och att kunderna använder funktionen korrekt. |
| väljare | Sträng- eller DOM-element | Nej | HTML-element eller CSS-väljare som används för att identifiera det HTML-element där Target ska placera erbjudandeinnehållet. Om ingen väljare anges antar Target att det HTML-element som ska användas är HTML HEAD. |
| erbjudande | Array | Ja | En array-åtgärd som ska tillämpas på elementet. |

## Exempel {#section_D8D6A17B73DE4542937CDB687193A5CC}

I följande exempel visas hur du använder `getOffer` och `applyOffer` tillsammans:

```
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
