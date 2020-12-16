---
keywords: adobe.target.sendNotifications;sendNotifications;sendnotifications;send notifications;notifications;at.js;functions;function
description: Information om funktionen adobe.target.sendNotifications(options) för JavaScript-biblioteket för Adobe Target at.js.
title: adobe.target.sendNotifications(options)
feature: client-side
translation-type: tm+mt
source-git-commit: a841c492e5d9e4bfedb20133ba32e37daf738c57
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---


# adobe.target.sendNotifications(options)

Den här funktionen skickar ett meddelande till Target edge när en upplevelse återges utan att använda `adobe.target.applyOffer()` eller `adobe.target.applyOffers()`.

>[!NOTE]
>
>Den här funktionen har introducerats i at.js 2.1.0 och är tillgänglig för alla versioner över 2.1.0.

| Nyckel | Typ | Obligatoriskt? | Beskrivning |
| --- | --- | --- | --- |
| ConsumerId | Sträng | Nej | Standardvärdet är klientens globala mbox om den inte anges. Den här nyckeln används för att generera det kompletterande data-ID som används för A4T-integrering. |
| Begäran | Objekt | Ja | Se tabellen över förfrågningar nedan. |
| timeout | Nummer | Nej | Timeout för begäran. Om inget anges används standardtimeout för at.js. |

## Begäran

| Fältnamn | Typ | Obligatoriskt? | Begränsning | Beskrivning |
| --- | --- | --- | --- | --- |
| Begär > Meddelanden | Array med objekt | Ja |  | Meddelanden om det visade innehållet, väljare som du klickat på och/eller besökta vyer eller kryssrutor. |
| Begär > Meddelanden > Adress | Objekt | Nej |  |  |
| Begäran > meddelanden > adress > url | Sträng | Nej |  | URL som meddelandet har utlösts från. |
| Begäran > meddelanden > adress > refererande URL | Sträng | Nej |  | Hänvisnings-URL som meddelandet utlöstes från. |
| Begäran > meddelanden > parametrar | Objekt | Nej | Följande namn tillåts inte för parametrar:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Tänk på följande:<ul><li>Max 50 parametrar.</li><li>Parameternamnet får inte vara tomt.</li><li>Parameternamnet får vara högst 128 tecken långt.</li><li>Parameternamnet får inte börja med &quot;profile&quot;.</li><li>Parametervärdets längd är högst 5000.</li></ul> |  |
| Begäran > meddelanden > profileParameters | Objekt | Nej | Följande namn tillåts inte för parametrar:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Tänk på följande:<ul><li>Max 50 parametrar.</li><li>Parameternamnet får inte vara tomt.</li><li>Parameternamnet får vara högst 128 tecken långt.</li><li>Parameternamnet får inte börja med &quot;profile&quot;.</li><li>Parametervärdets längd är högst 5000.</li></ul> |  |
| Begär > Meddelanden > Beställ | Objekt | Nej |  | Objekt som beskriver orderinformationen. |
| Begäran > meddelanden > beställning > id | Sträng | Nej | `<=` 250 tecken. | Beställnings-ID. |
| Request > notifications > order > total | Sträng | Nej | `>=` 0 | Ordersumma. |
| Request > notifications > order > purchaseProductIds | Array med strängen | Nej | <ul><li>Inga tomma värden tillåts.</li><li>Varje produkt-ID får vara högst 50.</li><li>Produkt-ID:n, åtskilda med kommatecken och sammanfogade, får inte vara längre än 250.</li></ul> | Produkt-ID för beställning. |
| Request > notifications > product | Objekt | Nej |  |  |
| Request > notifications > product > id | Sträng | Nej | `<=` 128 tecken; får inte vara tomt. | Produkt-ID. |
| Request > notifications > product > categoryId | Sträng | Nej | `<=` 128 tecken; får inte vara tomt. | Kategori-ID. |
| Begäran > meddelanden > id | Sträng | Ja | `<=` 200 tecken. | Meddelande-ID returneras som svar och anger att meddelandet har bearbetats. |
| Begäran > meddelanden > intryckt-ID | Sträng | Nej | `<= 128` tecken. | Impression-ID används för att sätta ihop (länka) det aktuella meddelandet med ett tidigare meddelande eller en körningsbegäran. Om båda matchar varandra kommer den andra och andra efterföljande förfrågningar inte att generera ett nytt intryck av aktiviteten eller upplevelsen. |
| Request > notifications > type | Sträng | Ja | &quot;click&quot; eller &quot;display&quot; stöds. | Meddelandetyp. |
| Begäran > meddelanden > tidsstämpel | Nummer`<int64>` | Ja |  | Tidsstämpel för meddelandet i millisekunder sedan UNIX-epoken. |
| Begäran > aviseringar > tokens | Array med strängen | Ja |  | En lista med tokens för visat innehåll eller väljare som klickats, baserat på meddelandetypen. |
| Begäran > meddelanden > mbox | Objekt | Nej |  | Meddelanden för mbox. |
| Request > notifications > mbox > name | Sträng | Nej | Inga tomma värden tillåts.<br>Tillåtna tecken: Se anmärkning efter denna tabell. | mbox name. |
| Request > notifications > mbox > state | Sträng | Nej |  | mbox state token. |
| Begär > Meddelanden > Visa | Objekt | Nej |  |  |
| Begäran > meddelanden > visa > id | Heltal `<int64>` | Nej |  | Visa-ID. Det id som tilldelats vyn när vyn skapades via vy-API:t. |
| Begäran > meddelanden > visa > namn | Sträng | Nej | `<= 128` tecken. | Namn på vy. |
| Begäran > meddelanden > visa > nyckel | Sträng | Nej | `<=` 512 tecken. | Visa nyckel. Nyckeln som ställdes in med vyn via API:t. |
| Begäran > meddelanden > visa > läge | Sträng | Nej |  | Visa tillståndstoken. |

**Obs**: Följande tecken är tillåtna för  `Request > notifications > mbox > name`:

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## sendNotifications()-anrop efter återgivning av förhämtade kryssrutor

```javascript
function createTokens(options) {
  return options.map(e => e.eventToken);
}

function createNotification(mbox, type, tokens) {
  const id = 11111; // here we should use a random ID like UUID
  const timestamp = Date.now();
  const { name, state, parameters, profileParameters, order, product } = mbox;
  const result = {
    id,
    type,
    timestamp,
    parameters,
    profileParameters,
    order,
    product
  };

  result.mbox = { name, state };
  result.tokens = tokens;

  return result;
}

adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "a1-serverside-ab"
        }
      ]
    }
  }
})
.then(response => {
  const mboxes = response.prefetch.mboxes;
  const notifications = mboxes.map(mbox => {
    const type = "display";
    const tokens = createTokens(mbox.options);

    return createNotification(mbox, type, tokens);
  });
  
  adobe.target.sendNotifications({
    request: { notifications }
  });
})
```

>[!NOTE]
>
>Om du använder Adobe Analytics, `getOffers()` med endast prefetch och `sendNotifications()`, måste Analytics-begäran skickas när `sendNotifications()` har körts. Syftet med detta är att säkerställa att SDID som genereras av `sendNotifications()` matchar SDID som skickas till Analytics och Target.