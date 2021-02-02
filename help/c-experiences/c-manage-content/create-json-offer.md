---
keywords: fjärrerbjudande;skapa fjärrerbjudande
description: Hur skapar jag JSON-erbjudanden?
title: Skapa JSON-erbjudanden
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---


# Skapa JSON-erbjudanden{#create-json-offers}

Skapa JSON-erbjudanden i [!UICONTROL Offer Library] i [!DNL Adobe Target] för användning i [!UICONTROL Form-Based Experience Composer].

JSON-erbjudanden kan användas i formulärbaserade aktiviteter där aktivering av användningsfall där [!DNL Target] måste skicka ett erbjudande i JSON-format för användning i SPA ramverk eller serverintegreringar.

## JSON-överväganden

Tänk på följande när du arbetar med JSON:

* JSON-erbjudanden är för närvarande bara tillgängliga för [!UICONTROL A/B Test]- och [!UICONTROL Experience Targeting]-aktiviteter (XT).
* JSON-erbjudanden kan endast användas i [formulärbaserade aktiviteter](/help/c-experiences/form-experience-composer.md).
* JSON-erbjudandet kan hämtas direkt när du använder API:t för serversidan, Mobile SDK eller NodeJS SDK.
* I webbläsaren kan JSON-erbjudanden ENDAST hämtas via at.js 1.2.3 (eller senare) och med [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) genom att filtrera åtgärder med åtgärden `setJson`.
* JSON-erbjudanden levereras som systemspecifika JSON-objekt i stället för som strängar. Konsumenter av dessa objekt behöver inte längre hantera objekt som strängar och konvertera dem till JSON-objekt.
* JSON-erbjudanden tillämpas inte automatiskt i motsats till andra erbjudanden (som HTML-erbjudanden) eftersom JSON-erbjudanden är icke-visuella erbjudanden. Utvecklare måste skriva kod för att uttryckligen få erbjudandet med [getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md).
* JSON-erbjudanden stöds inte om du använder mbox.js.

## Skapa ett JSON-erbjudande {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. Klicka på **[!UICONTROL Offers]** > **[!UICONTROL Code Offers]**.

   ![Erbjudanden > fliken Koderbjudanden](/help/c-experiences/c-manage-content/assets/code-offers-tab.png)

1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL JSON Offer]**.

   ![](assets/offer-json.png)

1. Skriv ett erbjudandenamn.
1. Skriv eller klistra in JSON-koden i rutan **[!UICONTROL Code]**.
1. Klicka på **[!UICONTROL Save]**.

## JSON-exempel {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

JSON-erbjudanden stöds endast i aktiviteter som skapats med [formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md). För närvarande är det enda sättet att kunna använda JSON-erbjudanden via direkta API-anrop.

Här är ett exempel:

```json
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

```json
{ 
  "demo": {"a": 1, "b": 2} 
}
```

Åtgärdsarrayen har följande struktur:

```json
[ 
 { 
   action: "setJson", 
   content: [{ 
     "demo": {"a": 1, "b": 2} 
   }] 
 }  
]
```

För att extrahera JSON-erbjudandet itererar du genom åtgärder och söker efter åtgärden med åtgärden `setJson` och itererar sedan genom innehållsarrayen.

## Använd skiftläge {#section_85B07907B51A43239C8E3498EF58B1E5}

Låt oss säga att följande JSON-erbjudande levereras till din webbsida:

```json
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

```json
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

## JSON-erbjudandetypen {#section_52533555BCE6420C8A95EB4EB8907BDE} filtrerar erbjudanden

Du kan filtrera biblioteket [!UICONTROL Offers] genom att klicka på listrutan **[!UICONTROL Type]** och sedan markera kryssrutan **[!UICONTROL JSON]**.

![](assets/offer-json-filter.png)

