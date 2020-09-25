---
keywords: adobe.target.applyOffers;applyOffers;applyoffers;apply offers;at.js;functions;function
description: Information om funktionen adobe.target.applyOffers(options) för JavaScript-biblioteket i Adobe Target at.js.
title: adobe.target.applyOffers(options) - at.js 2.x
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 8789d750e9e0245d88d54a8d3fe342e5b2e616fc
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---


# adobe.target.applyOffers(options) - at.js 2.x

Med den här funktionen kan du tillämpa mer än ett erbjudande som har hämtats av `adobe.target.getOffers()`.

>[!NOTE]
>
>Den här funktionen introducerades med at.js 2.x. Den här funktionen är inte tillgänglig för at.js version 1.*x*.

| Nyckel | Typ | Obligatoriskt? | Beskrivning |
| --- | --- | --- | --- |
| väljare | Sträng | Nej | HTML-element eller CSS-väljare som används för att identifiera HTML-elementet där erbjudandeinnehållet [!DNL Target] ska placeras. Om ingen väljare anges förutsätter [!DNL Target] att HTML-elementet som ska användas är HTML HEAD. |
| Svar | Objekt | Ja | Svarsobjekt från `getOffers()`.<br>Se tabellen över förfrågningar nedan. |

## Svar

>[!NOTE]
>
>Läs dokumentationen [för](http://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) leverans-API om du vill ha information om vilka typer som kan användas för alla fält som listas nedan.

| Fältnamn | Beskrivning |
| --- | --- |
| svar > förhämtning > vyer > alternativ > innehåll | Observera att innehållet i alternativet inte är väldefinierat och är direkt beroende av alternativtypen/mallstrukturen. |
| svar > förhämtning > vyer > alternativ > text | Alternativtyp. Återspeglar typ av&quot;innehåll&quot;-fält. Den typ som stöds är åtgärder. |
| svar > förhämtning > vyer > läge | En token för ogenomskinligt visningsläge som ska vidarebefordras med visningsmeddelande för vyn |
| response > prefetch > views > options > responseTokens | Innehåller kartan över `responseTokens` som samlats in när det aktuella alternativet bearbetades. |
| response > prefetch > views > analytics > payload | Analysens nyttolast för integrering på klientsidan som ska skickas till Analytics när vyn har tillämpats. |
| response > prefetch > views > trace | Det objekt som innehåller alla spårningsdata för förhämtningsanropet per vy.<br>Spårningsobjektet kommer även att innehålla en version för spårningen.<br>Spårningsobjektet innehåller även information om den aktuella vyn. |
| response > prefetch > views > options > eventToken | Händelseloggning görs per alternativ. För varje tillämpat alternativ ska respektive händelsetoken läggas till i listan över meddelandetokens. Observera att en vy består av flera alternativ. Om alla alternativ har tillämpats och identifierats `eventTokens` måste alla inkluderas i meddelandet. |
| svar > förhämtning > vyer > namn | Vynamnet som kan läsas av människor. |
| response > prefetch > views > metrics | Rapporteringsmått som ska övervakas och sedan meddelas [!DNL Target] om. För närvarande stöds bara klickmått. Om ett klick på elementet inträffar, `eventTokens` bör lämplig information samlas in och ett meddelande skickas. |
| response > prefetch > views > key | Nyckeln eller fingeravtrycket som identifierar vyn. |
| svar > förhämtning > vyer > id | ID för vyn. |
| svar > meddelanden > id | Meddelande-ID. |
| svar > meddelanden > händelser > typ | Typ av meddelande, klicka eller visa. |
| svar > meddelanden > händelser > trace | Spårningen för meddelandehändelsen. |
| svar > meddelanden > händelser > token | Den token som skickades med meddelandehändelsen. |
| svar > meddelanden > händelser > tidsstämpel | Tidsstämpeln som skickades med meddelandehändelsen. |
| response > notifications > events > errorCode | Om meddelandet misslyckas anger koden orsaken till felet. |
| svar > meddelanden > händelser | De händelser som loggades eller inte kunde loggas för det aktuella meddelandet. |
| svar > meddelanden | Anger loggade eller misslyckade meddelanden. |
| response > execute > mboxes > mbox > trace | Objektet som innehåller alla spårningsdata för den enskilda mbox-begäran. |
| response > execute > mboxes > mbox > responseTokens | Innehåller karta över `responseTokens` för specifik körning av mbox-begäran. |
| response > execute > mboxes > mbox > option > content | Observera att innehållet i alternativet inte är väldefinierat och är direkt beroende av alternativtypen/mallstrukturen. |
| response > execute > mboxes > mbox > option > type | Alternativtyp. Återspeglar typ av&quot;innehåll&quot;-fält. Typer som stöds är: html, redirect, JSON och dynamic. |
| response > execute > mboxes > mbox > options | Svarsalternativ. |
| response > execute > mboxes > mbox > metrics > eventToken | Token för klickningshändelse. |
| response > execute > mboxes > mbox > metrics > type | &quot;click&quot; |
| response > execute > mboxes > mbox > metrics | Innehåller en lista med `clickThrough` mätvärden. |
| response > execute > mboxes > mbox > mbox | Namnet på mbox. |
| response > execute > mboxes > mbox >index | Anger att svaret är för mbox med detta index från begäran. |
| response > execute > mboxes > mbox > analytics > payload | Analysens nyttolast för integrering på klientsidan som ska skickas till Analytics när mbox har tillämpats. (Se avsnittet A4T-aktiverade kampanjer.) |
| response > execute > mbox | Lista över körda rutor. |
| response > execute > pageLoad > options > content | Observera att innehållet i alternativet inte är väldefinierat och är direkt beroende av alternativtypen/mallstrukturen. |
| response > execute > pageLoad > options > type | Alternativtyp. Återspeglar typ av&quot;innehåll&quot;-fält. Typer som stöds är: html, redirect, JSON, dynamic och actions. |
| response > execute > pageLoad > options | Alternativ som inte grupperas efter vyer (target-global-mbox + alternativ från aktiviteter där vyer inte grupperats efter vyer). |
| response > execute > pageLoad > metrics | Klicka på mätvärden som inte ställts in för att tillhöra en viss vy. |
| response > execute > pageLoad > trace | Objektet som innehåller alla spårningsdata för pageLoad-begäran. |
| response > execute > pageLoad > analytics > payload | Analysens nyttolast för integrering på klientsidan som ska skickas till Analytics efter att sidans inläsningsinnehåll har tillämpats. (Se avsnittet A4T-aktiverade kampanjer.) |

## Exempel på applyOffers()-anrop

```
adobe.target.applyOffers({response:{
  "execute": {
    "pageLoad": {
      "options": [{
        "type": "html",
        "content": "page-load"
      },
      {
        "type": "actions",
        "content": [{
          "type": "setHtml",
          "content": "<h1>Container 1</h1>",
          "selector": "#container1",
          "cssSelector": "#container1"
        },
        {
          "type": "setHtml",
          "content": "<h3>Container 3</h3>",
          "selector": "#container3",
          "cssSelector": "#container3"
        }]
      }],
 
 
      "metrics": [{
        "type": "click",
        "selector": "#container1",
        "eventToken": "page-load-click-metric" 
      }]
    }
  }
}});
```

## Exempel på anrop till Promise-kedja med `getOffers()` och `applyOffers()`, eftersom dessa funktioner är Promise-baserade

```
adobe.target.getOffers({...})
.then(response => adobe.target.applyOffers({ response: response }))
.then(() => console.log("Success"))
.catch(error => console.log("Error", error));
```
