---
keywords: json offer;create json offer
description: Lär dig hur du skapar JSON-erbjudanden som kan användas i [!UICONTROL Form-Based Experience Composer].
title: Hur skapar jag JSON-erbjudanden?
feature: Experiences and Offers
hide: true
hidefromtoc: true
exl-id: e022c2d1-3326-405b-aead-5bb4ffa309b3
source-git-commit: 4b57712b838906611702db521b51af84077501e6
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# Create JSON offers

Skapa JSON-erbjudanden i [!UICONTROL Offer Library] i [!DNL Adobe Target] för användning i [!UICONTROL Form-Based Experience Composer].

JSON-erbjudanden kan användas i formulärbaserade aktiviteter för att aktivera användningsfall där [!DNL Target] måste fatta beslut för att skicka ett erbjudande i JSON-format för konsumtion i SPA ramverk eller serverbaserade integreringar.

## JSON-överväganden

Tänk på följande när du arbetar med JSON:

* JSON-erbjudanden är för närvarande bara tillgängliga för [!UICONTROL A/B Test]-, [!UICONTROL Automated Personalization]- (AP) och [!UICONTROL Experience Targeting] (XT)-aktiviteter.
* JSON-erbjudanden kan endast användas i [formulärbaserade aktiviteter](/help/main/c-experiences/form-experience-composer.md).
* JSON-erbjudanden kan hämtas direkt när du använder [API:er på serversidan och Mobile Node.js, Java, .NET och Python SDK:er](https://experienceleague.adobe.com/en/docs/target-dev/developer/server-side/server-side-overview){target=_blank}.
* I webbläsaren kan JSON-erbjudanden bara hämtas via at.js 1.2.3 (eller senare) och med [getOffer()](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer){target=_blank} genom att filtrera åtgärder med åtgärden `setJson`.
* JSON-erbjudanden levereras som systemspecifika JSON-objekt i stället för som strängar. Konsumenter av dessa objekt behöver inte längre hantera objekt som strängar och konvertera dem till JSON-objekt.
* JSON-erbjudanden tillämpas inte automatiskt i motsats till andra erbjudanden (till exempel erbjudanden från HTML) eftersom JSON-erbjudanden är icke-visuella erbjudanden. Utvecklare måste skriva kod för att uttryckligen få erbjudandet med [getOffer()](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer){target=_blank}.

## Skapa ett JSON-erbjudande {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. Klicka på **[!UICONTROL Offers]** > **[!UICONTROL Code Offers]**.
1. Klicka på **[!UICONTROL Create Offer]** > **[!UICONTROL JSON Offer]**.
1. Skriv ett erbjudandenamn.
1. (Villkorligt) Om du har ett [[!DNL Target] Premium-konto](/help/main/c-intro/intro.md#premium) väljer du önskad [arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#workspace).
1. (Villkorligt) Välj önskade profilattribut.
1. Skriv eller klistra in JSON-koden i rutan **[!UICONTROL Code]**.
1. Klicka på **[!UICONTROL Create]**.

## JSON-exempel {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

JSON-erbjudanden stöds endast i aktiviteter som skapats med [formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md). För närvarande är det enda sättet att kunna använda JSON-erbjudanden via direkta API-/SDK-anrop.

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

De åtgärder som skickas till motringningen är en objektmatris. Förutsatt att du har ett enda JSON-erbjudande har det här innehållet:

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

Om du vill extrahera JSON-erbjudandet itererar du genom åtgärder och söker efter åtgärden med åtgärden `setJson`, och itererar sedan genom innehållsarrayen.

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
      "excepteur"
    ], 
    "friends": [ 
      { 
        "id": 0, 
        "name": "Carla Lyons" 
      }, 
      { 
        "id": 1, 
        "name": "Ollie Mooney" 
      } 
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

CDP-profilattribut i realtid kan delas med [!DNL Target] för användning i HTML och JSON.

Mer information finns i [Dela CDP-profilattribut i realtid med  [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes).

## Filtrera erbjudanden efter erbjudandetypen JSON {#section_52533555BCE6420C8A95EB4EB8907BDE}

Du kan filtrera biblioteket [!UICONTROL Offers] med JSON-erbjudandetypen genom att klicka på ikonen **[!UICONTROL Show filters]** ( ![ikonen Visa filter](/help/main/assets/icons/Filter.svg) ) och sedan markera kryssrutan **[!UICONTROL JSON Offers]** .
