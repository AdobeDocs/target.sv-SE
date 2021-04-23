---
keywords: adobe.target.applyOffer;applyOffer;apply offer;apply offer;at.js;functions;function
description: Använd funktionen adobe.target.applyOffer() för JavaScript-biblioteket Adobe [!DNL Target] at.js om du vill använda svarsinnehållet.
title: Hur använder jag funktionen adobe.target.applyOffer()?
feature: at.js
role: Developer
exl-id: d230d48f-0d6c-4f55-96a0-681dd31e8d16
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# adobe.target.applyOffer(options)

Den här funktionen används för att tillämpa svarsinnehållet med [!DNL Adobe Target].

>[!NOTE]
>
>`applyOffer` kräver  `mbox` parametern. Om inget mbox-namn anges inträffar ett fel.

Alternativparametern är obligatorisk och har följande struktur:

| Nyckel | Typ | Obligatoriskt | Beskrivning |
|--- |--- |--- |--- |
| mbox | Sträng | Ja | Mbox name<br>Med at.js 1.3.0 (och senare) Target tvingas mbox-nyckeln att användas. Den här nyckeln har krävts tidigare, men Target använder den nu för att säkerställa att Target har korrekt validering och att kunderna använder funktionen korrekt. |
| väljare | Sträng- eller DOM-element | Nej | HTML-element eller CSS-väljare som används för att identifiera det HTML-element där Target ska placera erbjudandeinnehållet. Om ingen väljare anges förutsätter Target att HTML-elementet ska använda HTML HEAD. |
| Erbjudande | Array | Ja | En array-åtgärd som ska tillämpas på elementet. |

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
