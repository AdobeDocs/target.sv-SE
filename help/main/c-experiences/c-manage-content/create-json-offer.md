---
keywords: fjärrerbjudande;skapa fjärrerbjudande
description: Lär dig hur du skapar JSON-erbjudanden i Adobe [!DNL Target] för användning i den formulärbaserade Experience Composer.
title: Hur skapar jag JSON-erbjudanden?
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
source-git-commit: 33d85fcbfc971c188f4154cca5b4d21103b4dbb7
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 0%

---

# Skapa JSON-erbjudanden

Skapa JSON-erbjudanden i [!UICONTROL Offer Library] in [!DNL Adobe Target] för användning i [!UICONTROL Form-Based Experience Composer].

JSON-erbjudanden kan användas i blankettbaserade aktiviteter, där man kan använda [!DNL Target] Du måste fatta beslut för att skicka ett erbjudande i JSON-format för konsumtion i SPA ramverk eller serverintegreringar.

## JSON-överväganden

Tänk på följande när du arbetar med JSON:

* JSON-erbjudanden är för närvarande bara tillgängliga för [!UICONTROL A/B Test], Automated Personalization (AP) och [!UICONTROL Experience Targeting] (XT) aktiviteter.
* JSON-erbjudanden kan användas i [formulärbaserad verksamhet](/help/main/c-experiences/form-experience-composer.md) endast.
* JSON-erbjudandet kan hämtas direkt när du använder [API:er på serversidan och Mobile Node.js, Java, .NET och Python SDK:er](https://developer.adobe.com/target/implement/server-side/){target=_blank}.
* I webbläsaren kan JSON-erbjudanden ENDAST hämtas via at.js 1.2.3 (eller senare) och med [getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/){target=_blank} genom att filtrera åtgärder med `setJson` åtgärd.
* JSON-erbjudanden levereras som systemspecifika JSON-objekt i stället för som strängar. Konsumenter av dessa objekt behöver inte längre hantera objekt som strängar och konvertera dem till JSON-objekt.
* JSON-erbjudanden tillämpas inte automatiskt i motsats till andra erbjudanden (till exempel erbjudanden från HTML) eftersom JSON-erbjudanden är icke-visuella erbjudanden. Utvecklare måste skriva kod för att explicit få erbjudandet med [getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/){target=_blank}.

## Skapa ett JSON-erbjudande {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. Klicka på **[!UICONTROL Offers]** > **[!UICONTROL Code Offers]**.

   ![Erbjudanden > fliken Koderbjudanden](/help/main/c-experiences/c-manage-content/assets/code-offers-tab.png)

1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL JSON Offer]**.

   ![offer-json image](assets/offer-json.png)

1. Skriv ett erbjudandenamn.
1. Skriv eller klistra in JSON-koden i **[!UICONTROL Code]** box.
1. Klicka på **[!UICONTROL Save]**.

## JSON-exempel {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

JSON-erbjudanden stöds endast i aktiviteter som skapats med [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md). För närvarande är det enda sättet att kunna använda JSON-erbjudanden via direkta API-/SDK-anrop.

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

Arrayen actions har följande struktur:

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

Om du vill extrahera JSON-erbjudandet itererar du genom åtgärder och hittar åtgärden med `setJson` och iterera sedan genom content-arrayen.

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

## JSON erbjuder exempel med CDP-profilattribut i realtid

CDP-profilattribut i realtid kan delas med [!DNL Target] för HTML och JSON. (Observera att den här funktionen för närvarande är i betaversionen.)

Exempel: Som onlinemarknadsförare vill Grace att AEP/Unified Profile ska dela attributvärden med [!DNL Target] för att tillhandahålla personalisering i realtid. Med CDP-profilattribut i realtid kan Grace visa AEP-attributets värde i en [!DNL Target] Erbjudande med tokenersättning. Hon kan till exempel anpassa sig efter kundens favoritfärg med `${aep.profile.favoriteColor}`eller deras lojalitetsnivå och förmånspoängvärde med hjälp av tokens `${aep.loyalty.tier}` och `${aep.loyalty.points}`.

![offer-json-aep-shared-attribute image](assets/offer-json-aep-shared-attribute.png)

Observera att det är valfritt att tilldela standardvärden.

## Filtrera erbjudanden efter erbjudandetypen JSON {#section_52533555BCE6420C8A95EB4EB8907BDE}

Du kan filtrera [!UICONTROL Offers] biblioteket efter erbjudandetypen för JSON genom att klicka på **[!UICONTROL Type]** nedrullningsbar lista genom att välja **[!UICONTROL JSON]** kryssrutan.

![offer-json-filter, bild](assets/offer-json-filter.png)
