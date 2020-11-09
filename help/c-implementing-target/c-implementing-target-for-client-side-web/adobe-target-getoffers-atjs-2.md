---
keywords: adobe.target.getOffers;getOffers;getoffers;get offers;at.js;functions;function
description: Information om funktionen adobe.target.getOffers(options) för JavaScript-biblioteket i Adobe Target at.js.
title: adobe.target.getOffers(options) - at.js 2.x
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1215'
ht-degree: 0%

---


# adobe.target.getOffers(options) - at.js 2.x

Med den här funktionen kan du hämta flera erbjudanden genom att skicka in flera rutor. Dessutom kan flera erbjudanden hämtas för alla vyer i aktiva aktiviteter.

>[!NOTE]
>
>Den här funktionen introducerades med at.js 2.x. Den här funktionen är inte tillgänglig för at.js version 1.*x*.

| Nyckel | Typ | Obligatoriskt? | Beskrivning |
| --- | --- | --- | --- |
| ConsumerId | Sträng | Nej | Standardvärdet är klientens globala mbox om den inte anges. Den här nyckeln används för att generera det kompletterande data-ID som används för A4T-integrering. Nyckeln är en unik sträng per besökare. |
| förfrågan | Objekt | Ja | Se tabellen över förfrågningar nedan. |
| timeout | Nummer | Nej | timeout för begäran. Om inget anges används standardtimeout för at.js. |

## Begäran

>[!NOTE]
>
>Läs dokumentationen [för](http://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) leverans-API om du vill ha information om vilka typer som kan användas för alla fält som listas nedan.

| Fältnamn | Obligatoriskt? | Begränsningar | Beskrivning |
| --- | --- | --- | --- |
| request > id | Nej |  | Ett av `tntId`, `thirdPartyId`eller `marketingCloudVisitorId` krävs. |
| Begäran > id > thirdPartyId | Nej | Maximal storlek = 128 |  |  |
| Request > experienceCloud | Nej |  |  |
| Request > experienceCloud > analytics | Nej |  | Integrering med Adobe Analytics |
| Request > experienceCloud > analytics > log | Nej | Följande måste implementeras på sidan:<ul><li>Tjänst för besökar-ID</li><li>Appmeasurement.js</li></ul> | Följande värden stöds:<br>**client_side**: När det anges returneras en analyslast till anroparen som ska användas för att skicka till Adobe Analytics via API:t för datainmatning.<br>**server_side**: Det här är standardvärdet där Target- och Analytics-serverdelen använder SDID för att sammanfoga anropen i rapporteringssyfte. |
| Begäran > förhämtning | Nej |  |  |
| Request > prefetch > views | Nej | Maximalt antal 50<br>Namnet får inte<br>vara tomtNamn längd `<=` 128<br>Värdets längd `<=` 5000<br>Namnet får inte börja med &quot;profile&quot;<br>Otillåtna namn: &quot;orderId&quot;, &quot;orderTotal&quot;, &quot;productPurchasedId&quot; | Ange parametrar som ska användas för att hämta relevanta vyer i aktiva aktiviteter. |
| Request > prefetch > views > profileParameters | Nej | Maximalt antal 50<br>Namnet får inte<br>vara tomtNamn längd `<=` 128<br>Värdets längd `<=` 5000<br>Namnet får inte börja med &quot;profile&quot; | Ange profilparametrar som ska användas för att hämta relevanta vyer i aktiva aktiviteter. |
| Request > prefetch > views > product | Nej |  |  |
| Request > prefetch > views > product -> id | Nej | Inte<br>full maxstorlek = 128 | Ange produkt-ID:n som ska användas för att hämta relevanta vyer i aktiva aktiviteter. |
| Request > prefetch > views > product > categoryId | Nej | Inte<br>full maxstorlek = 128 | Ange produktkategori-ID:n som ska användas för att hämta relevanta vyer i aktiviteter. |
| Request > prefetch > views > order | Nej |  |  |
| Begäran > förhämtning > vyer > ordning > id | Nej | Maximal längd = 250 | Ange beställnings-ID:n som ska användas för att hämta relevanta vyer i aktiva aktiviteter. |
| Request > prefetch > views > order > total | Nej | Totalt `>=` 0 | Ange ordersummor som ska användas för att hämta relevanta vyer i aktiva aktiviteter. |
| Request > prefetch > views > order > purchaseProductIds | Nej | Inga tomma<br>värdenVarje värdes maximala längd är 50<br>Sammanfogad och separerad med<br>kommaProduct ID:n, total längd `<=` 250 | Skicka in köpta produkt-ID:n som ska användas för att hämta relevanta vyer i aktiva aktiviteter. |
| Begäran > Kör | Nej |  |  |
| Request > execute > pageLoad | Nej |  |  |
| Request > execute > pageLoad > parameters | Nej | Maximalt antal 50<br>Namnet får inte vara<br>blankName-längd `<=` 128<br>Värdets längd `<=` 5000<br>Namn får inte börja med &quot;profile&quot;.<br>Otillåtna namn: &quot;orderId&quot;, &quot;orderTotal&quot;, &quot;productPurchasedId&quot; | Hämta erbjudanden med angivna parametrar när sidan läses in. |
| Request > execute > pageLoad > profileParameters | Nej | Maximalt antal 50<br>Namnet får inte vara<br>blankName-längd `<=` 128<br>Värdets längd `<=`256<br>Namnet får inte börja med &quot;profile&quot;. | Hämta erbjudanden med angivna profilparametrar när sidan läses in. |
| Request > execute > pageLoad > product | Nej |  |  |
| Request > execute > pageLoad > product -> id | Nej | Inte<br>blankMaximum-storlek = 128 | Hämta erbjudanden med angivna produkt-ID:n när sidan läses in. |
| Request > execute > pageLoad > product > categoryId | Nej | Inte<br>blankMaximum-storlek = 128 | Hämta erbjudanden med angivna produktkategori-ID:n när sidan läses in. |
| Request > execute > pageLoad > order | Nej |  |  |
| Request > execute > pageLoad > order > id | Nej | Maximal längd = 250 | Hämta erbjudanden med angivna order-ID:n när sidan läses in. |
| Request > execute > pageLoad > order > total | Nej | `>=` 0 | Hämta erbjudanden med angivna ordersummor när sidan läses in. |
| Request > execute > pageLoad > order > purchaseProductIds | Nej | Inga tomma<br>värdenVarje värdes maximala längd är 50<br>Sammanfogad och separerad med<br>kommaProduct ID:n, total längd `<=` 250 | Hämta erbjudanden med angivna produkt-ID:n när sidan läses in. |
| Request > execute > mboxes | Nej | Maximal storlek = 50<br>Inga null-element |  |
| Request > execute > mboxes>mbox | Ja | Not<br>blankNo &#39;-clicked&#39;<br>suffixMaximum size = 250<br>Tillåtna tecken: `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | Namn på mbox. |
| Begäran > Kör > mbox>mbox>index | Ja | Inte<br>nullUnique<br>`>=` 0 | Observera att indexet inte representerar den ordning i vilken rutorna bearbetas. På samma sätt som på en webbsida med flera regionala kryssrutor kan ordningen som de ska bearbetas i inte anges. |
| Request > execute > mboxes > mbox > parameters | Nej | Maximalt antal = 50<br>Namnet får inte vara<br>blankName-längd `<=` 128<br>Värdets längd `<=` 5000<br>Namn får inte börja med &quot;profile&quot;.<br>Otillåtna namn: &quot;orderId&quot;, &quot;orderTotal&quot;, &quot;productPurchasedId&quot; | Hämta erbjudanden för en given mbox med de angivna parametrarna. |
| Request > execute > mboxes>mbox>profileParameters | Nej | Maximalt antal = 50<br>Namnet får inte vara<br>blankName-längd `<=` 128<br>Värdets längd `<=`256<br>Namnet får inte börja med &quot;profile&quot;. | Hämta erbjudanden för en given mbox med de angivna profilparametrarna. |
| Request > execute > mboxes>mbox > product | Nej |  |  |
| Request > execute > mboxes > mbox > product > id | Nej | Inte<br>blankMaximum-storlek = 128 | Hämta erbjudanden för en angiven mbox med angivet produkt-ID. |
| Request > execute > mboxes > mbox > product > categoryId | Nej | Inte<br>blankMaximum-storlek = 128 | Hämta erbjudanden för en angiven mbox med angivna produktkategori-ID:n. |
| Request > execute > mboxes > mbox > order | Nej |  |  |
| Request > execute > mbox>mbox > order > id | Nej | Maximal längd = 250 | Hämta erbjudanden för en angiven mbox med de angivna order-ID:n. |
| Request > execute > mboxes > mbox > order > total | Nej | `>=` 0 | Hämta erbjudanden för en angiven mbox med de angivna ordersummorna. |
| Request > execute > mboxes > mbox > order > purchaseProductIds | Nej | Inga tomma<br>värdenVarje värdes maximala längd = 50<br>Sammanfogad och separerad med<br>kommaProduct ID:s totala längd `<=` 250 | Hämta erbjudanden för en angiven mbox med angivet produkt-ID för beställning. |

## Ring `getOffers()` för alla vyer

```
adobe.target.getOffers({
    request: {
      prefetch: {
        views: [{}]
    }
  }
});
```

## Anropa `getOffers()` för att hämta de senaste vyerna med skickade parametrar och profilparametrar

```
adobe.target.getOffers({
  request: {
    "prefetch": {
      "views": [
        {
          "parameters": {
            "ad": "1"
          },
          "profileParameters": {
            "age": 23
          }
        }
      ]
    }
  }
});
```

## Anrop `getOffers()` till hämtning av mbox med parametrar och profilparametrar skickade.

```
adobe.target.getOffers({
  request: {
    execute: {
      mboxes: [
        {
          index: 0,
          name: "first-mbox"
        },
        {
          index: 1,
          name: "second-mbox",
          parameters: {
            a: 1
          },
          profileParameters: {
            b: 2
          }
        }
      ]
    }
  }
});
```

## Anropa getOffers() för att hämta analysnyttolasten från klientsidan

```
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

**Svar**:

```
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

Nyttolasten kan sedan vidarebefordras till Adobe Analytics via API:t för [datainmatning](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Hämta och återge data från flera rutor via getOffers() och applyOffers() {#multiple}

Med at.js 2.x kan du hämta flera mbox via `getOffers()` API. Du kan också hämta data för flera rutor och sedan använda för `applyOffers()` att återge data på olika platser som identifieras av en CSS-väljare.

I följande exempel visas en enkel HTML-sida med at.js 2.x implementerad:

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>at.js 2.x, multiple selectors and multiple mboxes</title>
  <script src="at.js"></script>
</head>
<body>
  <div id="container1">Default content 1</div>
  
  <div id="container2">Default content 2</div>

  <div id="container3">Default content 3</div>
</body>
</html>
```

Anta att du har tre behållare som du vill ändra via innehåll som tagits emot från [!DNL Target]. Du kan skapa en enda begäran för tre mrutor där varje mbox har visst innehåll som ska återges i respektive behållare.

Koden för begäran och återgivning kan se ut som i följande exempel:

```
adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "mbox1"
        },
        {
          index: 1,
          name: "mbox2"
        },
        {
          index: 2,
          name: "mbox3"
        }
      ]
    }
  }
})
.then(response => {
  // get all mboxes from response
  const mboxes = response.prefetch.mboxes;
  let count = 1;

  mboxes.forEach(el => {
    adobe.target.applyOffers({
      selector: "#container" + count,
      response: {
        prefetch: {
          mboxes: [el]
        }
      }
    });

    count += 1;
  });
});
```

I `request > prefetch > mboxes` avsnittet finns det tre olika rutor. Om begäran har slutförts får du svaret för varje ruta från `response > prefetch > mboxes`. När du har fått svar och de platser du vill använda för återgivning kan du anropa `applyOffers()` för att återge det innehåll som hämtats från [!DNL Target]. I det här exemplet har vi följande mappning:

* mbox1 > CSS-väljare #container1
* mbox2 > CSS-väljare #container2
* mbox3 > CSS-väljare #container3

I det här exemplet används variabeln count för att skapa CSS-väljarna. I ett verkligt scenario kan du använda en annan mappning mellan CSS-väljaren och mbox.

Observera att det här exemplet använder `prefetch > mboxes`men du kan också använda `execute > mboxes`. Om du använder prefetch i `getOffers()`måste du också använda prefetch i `applyOffers()` anropet.

## Anrop `getOffers()` att utföra en pageLoad

I följande exempel visas hur du utför en pageLoad med getOffers() med at.js 2.*x*

```
adobe.target.getOffers({
    request: {
        execute: {
            pageLoad: {
                parameters: {}
            }
        }
    }
});
```
