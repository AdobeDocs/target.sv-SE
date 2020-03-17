---
keywords: remote offer;create remote offer
description: Skapa JSON-erbjudanden i erbjudandebiblioteket för användning i den formulärbaserade Experience Composer.
title: Skapa JSON-erbjudanden
topic: Standard
uuid: 4ae3ca34-7661-4c1d-a132-fc446e653b90
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Skapa JSON-erbjudanden{#create-json-offers}

Skapa JSON-erbjudanden i erbjudandebiblioteket för användning i den formulärbaserade Experience Composer.

JSON-erbjudanden kan användas i blankettbaserade aktiviteter där man aktiverar användningsfall där Target måste skicka ett erbjudande i JSON-format för användning i SPA-ramverk eller integreringar på serversidan.

Tänk på följande när du arbetar med JSON:

* JSON-erbjudanden är för närvarande bara tillgängliga för AB- och XT-aktiviteter.
* JSON-erbjudanden kan endast användas i formulärbaserade aktiviteter.
* JSON-erbjudandet kan hämtas direkt när du använder API:t för serversidan, Mobile SDK eller NodeJS SDK.
* I webbläsaren kan JSON-erbjudanden ENDAST hämtas via at.js 1.2.3 (eller senare) och med [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) genom att filtrera åtgärder med `setJson` åtgärden.
* JSON-erbjudanden levereras som systemspecifika JSON-objekt i stället för som strängar. Konsumenter av dessa objekt behöver inte längre hantera objekt som strängar och konvertera dem till JSON-objekt.
* JSON-erbjudanden tillämpas inte automatiskt i motsats till andra erbjudanden (som HTML-erbjudanden) eftersom JSON-erbjudanden är icke-visuella erbjudanden. Utvecklare måste skriva kod för att explicit få erbjudandet med [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md).
* JSON-erbjudanden stöds inte om du använder mbox.js.

## Skapa ett JSON-erbjudande {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. Klicka på **[!UICONTROL Offers]** och välj sedan fliken **[!UICONTROL Code Offers]**.
1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL JSON Offer]**.

   ![](assets/offer-json.png)

1. Skriv ett erbjudandenamn.
1. Skriv eller klistra in JSON-koden i **[!UICONTROL Code]** rutan.
1. Klicka på **[!UICONTROL Save]**.

## Exempel {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

JSON-erbjudanden stöds endast i aktiviteter som skapats med den formulärbaserade Experience Composer. För närvarande är det enda sättet att kunna använda JSON-erbjudanden via direkta API-anrop.

Här är ett exempel:

```
adobe.target.getOffer({ 
  mbox: "some-mbox", 
  success: function(actions) { 
    console.log('Success', actions); 
  }, 
  error: function(status, error) { 
    console.log('Error', status, error); 
  } 
});
```

De åtgärder som skickas till motringningen är en objektmatris. Förutsatt att vi har ett enda JSON-erbjudande har det här innehållet:

```
{ 
  "demo": {"a": 1, "b": 2} 
}
```

Åtgärdsarrayen har följande struktur:

```
[ 
 { 
   action: "setJson", 
   content: [{ 
     "demo": {"a": 1, "b": 2} 
   }] 
 }  
]
```

För att extrahera JSON-erbjudandet itererar du genom åtgärder och söker efter åtgärden med `setJson` action och itererar sedan genom innehållsarrayen.

## Användningsfall {#section_85B07907B51A43239C8E3498EF58B1E5}

Låt oss säga att följande JSON-erbjudande levereras till din webbsida:

```
{ 
    "_id": "5a65d24d8fafc966921e9169", 
    "index": 0, 
    "guid": "7c006504-c6f7-468d-a46f-f72531ea454c", 
    "isActive": true, 
    "balance": "$2,075.06", 
    "picture": "https://placehold.it/32x32", 
    "tags": [ 
      "esse", 
      "commodo", 
      "excepteur", 
    ], 
    "friends": [ 
      { 
        "id": 0, 
        "name": "Carla Lyons" 
      }, 
      { 
        "id": 1, 
        "name": "Ollie Mooney" 
      }, 
    ], 
    "greeting": "Hello, Stephenson Fernandez! You have 4 unread messages.", 
    "favoriteFruit": "strawberry" 
} 
  
```

I följande kod visas hur du kommer åt attributet &quot;greeting&quot;:

```
adobe.target.getOffer({   
  "mbox": "name_of_mbox", 
  "params": {}, 
  "success": function(offer) {           
        console.log(offer[0].content[0].greeting); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

## Filtreringserbjudanden efter JSON-erbjudandetyp {#section_52533555BCE6420C8A95EB4EB8907BDE}

Du kan filtrera erbjudandebiblioteket efter erbjudandetypen för JSON genom att klicka på **[!UICONTROL Type]** listrutan och sedan markera **[!UICONTROL JSON]** kryssrutan.

![](assets/offer-json-filter.png)

