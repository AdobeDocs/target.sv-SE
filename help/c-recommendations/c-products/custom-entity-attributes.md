---
keywords: multi-value entity attributes;custom entity attributes;valid JSON;entity attribute value;JSON array;multi-valued;multivalued
description: Använd anpassade entitetsattribut med ett eller flera värden för att definiera ytterligare information om objekt i din katalog.
title: Anpassade entitetsattribut
feature: Recommendations
mini-toc-levels: 3
translation-type: tm+mt
source-git-commit: 4fb3603946850092ff2db47e2ad319ab84ff9261
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMCustom entitetsattribut{#custom-entity-attributes}

Använd anpassade entitetsattribut med ett eller flera värden i [!DNL Adobe Target Recommendations] för att definiera ytterligare information om objekt i din katalog.

## Gränser {#limits}

Du kan inkludera upp till 100 anpassade entitetsattribut för att definiera ytterligare information om objekt i katalogen. Du kan till exempel skapa ett anpassat attribut med namnet `entity.genre` för att definiera en bok eller film. Eller så kan en biljettförsäljare skapa attribut för en eventplats som inkluderar en sekundär utförare, till exempel ett besöksteam i ett idrottsevenemang eller en öppningsakt på en konsert.

Den maximala längden för anpassade attribut för en entitet med ett värde är 15 000 tecken (för UTF-8-kodade språk med en eller två byte, som engelska och andra latinska skriftspråk) eller 10 000 tecken (för UTF-8-kodade språk med tre byte som kinesiska, japanska och koreanska).

Anpassade attribut för entiteter med flera värden får inte innehålla fler än 500 värden. Varje enskilt värde är begränsat till 100 tecken. Det totala antalet tecken i alla värden måste uppfylla begränsningarna för den maximala längden för anpassade entitetsattribut med ett värde (se ovan).

## Anpassade värden för entitetsattribut {#section_313331A9F8194A89B5EDD89363018651}

Anpassade entitetsattribut kan innehålla ett eller flera värden. Entitetsattributvärden visas i produktvyn.

![](assets/multi-value_product.png)

Ett anpassat entitetsattribut med ett enda värde formateras på samma sätt som ett fördefinierat entitetsattribut med ett enda värde:

`entity.genre=genre1`

Ett anpassat entitetsattribut med flera värden måste skickas som en giltig JSON-matris:

`entity.genre=[“genre1”, “genre2”]`

Exempel på giltiga JSON-matriser som stöds av [!DNL Recommendations]:

* `["AB","BC"]` alla värden är strängar
* `[1,2]` alla värden är numeriska

>[!NOTE]
>
>[!DNL Recommendations] stöder inte blandade värdetyper i entitetsattribut med flera värden. `["AB",1,true, [1,2,3]]` är till exempel en giltig JSON-array, men den stöds inte i [!DNL Recommendations] eftersom den innehåller blandade värdetyper (sträng, numeriskt, booleskt, objekt).

När ett anpassat attribut har skickats som en giltig JSON-array behandlas attributet som ett flervärdesattribut för alla produkter i katalogen.

>[!NOTE]
>
>Om du vill ändra ett attribut från flera värden till ett enda värde måste du ta bort katalogen och överföra korrigerade produktdata. När du tar bort katalogen tas inte de historiska data som är kopplade till dina produkt-ID:n bort. Mer information finns i [Ta bort alla objekt från systemet](/help/assets/adobe-recommendations-classic.pdf) i *dokumentationen för Adobe Recommendations Classic*.

**Begränsningar**:

* Du kan inte använda fördefinierade entitetsattributnamn för anpassade entitetsattribut. (Se [Entitetsattribut](/help/c-recommendations/c-products/entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F).)
* Attributet `entity.environment` är reserverat av systemet och kan inte användas för anpassade entitetsattribut. Försök att skicka `entity.environment` med `targetPageParams`, feeds eller API:er ignoreras.
* Matriser måste innehålla en värdetyp. Matriser med blandade värden ( `["AB",1,true]`) stöds inte.
* Ett flervärdesattribut som innehåller en kapslad JSON-array ( `[10,12,[1,2,3]]`) behandlas som ett enkelvärdesattribut.

## Implementera attribut med flera värden {#section_80FEFE49E8AF415D99B739AA3CBA2A14}

Anpassade entitetsattribut för flera värden stöds när feeds (CSV), `targetPageParams`, Delivery API och Save entities API används för att överföra produkter. Nya värden ersätter aktuella värden; de är inte tillagda. Tomma arrayer ( []) behandlas som om de inte har några värden.

Dubbla citattecken måste undantas. `"[""test"", ""value""]"` är till exempel en giltig JSON-array som kan användas i CSV.

Du kan ta med upp till 500 värden i ett flervärdesattribut.

### Använda targetPageParams

I följande exempel visas hur du använder `targetPageParams`

```javascript
function targetPageParams() { 
  return { 
    'entity.id':                   '123', 
    'entity.categoryId':            '["A", "A:B", "A:B:C", "A:B:C:D"]',        
    'entity.MultiValueAttribute':   '["X", "Y", "Z"]', 
    'entity.event.detailsOnly':     'true', 
    'excludedIds":                  '[123, 3232, 2323, 4344]', 
    'orderId":                      '123456', 
    'orderTotal":                   '195.32', 
    'productPurchaseId":            '[001,002,003]' 
  }; 
}
```

### Använda CSV

Du kan hantera dina CSV-filer i Raw-format med en textredigerare eller använda kalkylbladsprogram.

CSV-filen med Raw-format ser ut så här:

![](assets/multi-value_example_raw.png)

Samma katalog kommer att se ut så här i ett kalkylblad:

![](assets/multi-value_example_excel.png)

När du konverterar till CSV-format lägger kalkylbladsprogrammet till citattecken runt cellinnehållet för att förhindra att kommatecken i cellen fungerar som kolumnavgränsare. Det lägger också till citattecken runt JSON-strängvärden som du inkluderar i anpassade attribut med flera värden. Det kan göra det okomplicerat att arbeta direkt med råfilen. Exempel:

* Kalkylblad: `["1","2","3"]`
* Råformat: `"[""1"",""2"",""3""]"`

Var försiktig när du redigerar en CSV-fil med Raw-katalog direkt.

### Använda API:er

Du kan skicka flervärdesattribut med leverans-API:t i en mbox-parameter som ett strängvärde som innehåller en escape-matris.

```javascript
"execute": {
    "mboxes": [
      {
        "index": 0,
        "name": "first-mbox",
        "parameters": {
          "entity.id": "32323",
          "entity.categoryId": "My Category",
          "entity.MultiValueAttribute": "[\"X\", \"Y\", \"Z\"]"
        }
      }
    ]
  }
```

Mer information om hur du använder enhets-API:erna Delivery och Save finns i [Adobe Recommendations API-dokumentationen](http://developers.adobetarget.com/api/recommendations).

## Använda operatorer med attribut för flera värden {#section_83C2288A805242D9A02EBC4F07DEE945}

När du använder operatorer för anpassade attribut med flera värden i inkluderingsregler för algoritmer, katalogregler och exkluderingsregler blir resultatet *true* om minst ett värde i listan klarar åtgärden (booleskt *eller*).

I följande exempel är regeln `message contains abc`.

* Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde innehåller `abc`.
* Fall 2: `entity.genre = ["abcde","de","ef"]`. Resultatet är sant eftersom ett värde innehåller `abc`.

För negativa operatorer måste alla attributvärden skickas (booleskt *och*). Om operatorn till exempel är `notEquals` blir resultatet *false* om något värde matchar.

I följande avsnitt finns information om operatorbeteende i algoritminkluderingsregler, katalogregler och exkluderingsregler.

### Lika med

Om något attributvärde är lika med indatavärdet, blir resultatet true.

Exempel: `genre equals abc`

* Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde är lika med `abc`.
* Fall 2: `entity.genre = ["abc", "de", "ef"]`. Resultatet är sant eftersom ett värde är lika med `abc`.
* Fall 3: `entity.genre = ["abcde", "de", "ef"]`. Resultatet är false eftersom `abc` inte är lika med något element i listan.

### Är inte lika med

Om inget attributvärde är lika med indatavärdet blir resultatet true.

Exempel: `genre not equals abc`

* Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är sant eftersom inget värde är lika med `abc`.
* Fall 2: `entity.genre = ["abc", "de", "ef"]`. Resultatet är false eftersom ett värde är lika med `abc`.
* Fall 3: `entity.genre = ["abcde", "de", "ef"]`. Resultatet är sant eftersom `abc`inte är lika med något element i listan.

### Innehåller

Om något värde för attributet innehåller indatavärdet, blir resultatet true.

Exempel: `genre contains abc`

* Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde innehåller `abc`.
* Fall 2: `entity.genre = ["abcde", "de", "ef"]`. Resultatet är sant eftersom ett värde innehåller `abc`.

### Innehåller inte

Om inget värde för attributet innehåller indatavärdet blir true.

Exempel: `genre does not contain abc`

* Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är sant eftersom inget värde innehåller `abc`.
* Fall 2: `entity.genre = ["abcde", "de", "ef"]`. Regeln resulterar i false eftersom ett värde innehåller`abc`.

### Börjar med

Om ett värde för ett attribut börjar med indatavärdet blir true.

Exempel: `genre starts with abc`

* Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde börjar med `abc`.
* Fall 2: `entity.genre = ["abcde", "de", "ef"]`. Resultatet är sant eftersom ett värde börjar med `abc`.
* Fall 3: `entity.genre = ["ab", "de", "abc"]`. Resultatet är sant eftersom ett värde börjar med `abc` (inte nödvändigtvis det första elementet i listan).

### Slutar med

Om ett värde för ett attribut slutar med indatavärdet blir true.

Exempel: `genre ends with abc`

* Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde slutar med `abc`.
* Fall 2: `entity.genre = ["deabc", "de", "ef"]`. Resultatet är sant eftersom ett värde slutar med `abc`.

### Större än eller lika med (endast numeriska värden)

Attributvärdet konverteras till det dubbla. Attribut som inte kan konverteras hoppas över när regeln körs.

Efter bearbetning blir alla attributvärden som är större än eller lika med indatavärdet true.

Exempel: `price greater than or equal to 100`

* Fall 1: `entity.price = ["10", "20", "45"]`. Resultatet är false eftersom inget värde är större än eller lika med 100. Värdet `de` hoppas över eftersom det inte kan konverteras till dubbel.
* Fall 2: `entity.price = ["100", "101", "90", "80"]`. Resultatet är sant eftersom två värden är större än eller lika med 100.

### Mindre än eller lika med (endast numeriska värden)

Attributvärdet konverteras till det dubbla. Attribut som inte kan konverteras hoppas över när regeln körs.

Efter bearbetning blir alla attributvärden som är mindre än eller lika med indatavärdet true.

Exempel: `price less than or equal to 100`

* Fall 1: `entity.price = ["101", "200", "141"]`. Resultatet är false eftersom inget värde är mindre än eller lika med 100. Värdet `de` hoppas över eftersom det inte kan konverteras till dubbel.
* Fall 2: `entity.price = ["100", "101", "90", "80"]`. Resultatet är sant eftersom två värden är mindre än eller lika med 100.

### Matchar dynamiskt (endast tillgängligt i objektbaserade algoritmer)

Om något attributvärde matchar indatavärdet blir true.

Exempel: `genre matches abc`

* Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde matchar `abc`.
* Fall 2: `entity.genre = ["abc", "de", "ef"]`. Resultatet är sant eftersom ett värde matchar `abc`.

### Matchar inte dynamiskt (endast tillgängligt i objektbaserade algoritmer)

Om något attributvärde matchar indatavärdet blir resultatet false.

Exempel: `genre does not match abc`

* Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är sant eftersom inget värde matchar `abc`.
* Fall 2: `entity.genre = ["abc", "de", "ef"]`. Regeln resulterar i false eftersom ett värde matchar `abc`.

### Dynamiskt omfång (endast tillgängligt i objektbaserade algoritmer, endast numeriska värden)

Om ett numeriskt attributvärde ligger inom det angivna intervallet blir resultatet sant.

Exempel: `price dynamically ranges in 80% to 120% of 100`

* Fall 1: `entity.price = ["101", "200", "125"]`. Resultatet är sant eftersom `101` är mellan 80 % och 120 % av 100. Värdet `de` hoppas över eftersom det inte kan konverteras till dubbel.
* Fall 2: `entity.price = ["130", "191", "60", "75"]`. Resultatet är false eftersom inget värde ligger i intervallet 80 % till 120 % av 100.

>[!NOTE]
>
>*Doubleis* är en Java-datatyp. Om du konverterar till dubbel för operatorer som kräver numeriska värden tas icke-numeriska värden bort från resultatet.

## Flervärdesattribut i design {#section_F672E4F6E1D44B3196B7ADE89334ED4A}

Flervärdesattribut visas som kommaavgränsade listor när de refereras i en design.

Exempel:

När `entity.genre=["genre1","genre2"]` i en design refereras till som `$entity<N>.genre` är resultatet `genre1, genre2`.

## Relaterade ämnen:

* [Entitetsattribut](/help/c-recommendations/c-products/entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F)
