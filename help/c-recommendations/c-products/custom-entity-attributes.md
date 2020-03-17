---
keywords: multi-value entity attributes;custom entity attributes;valid JSON;entity attribute value;JSON array;multi-valued;multivalued
description: Använd anpassade entitetsattribut med ett eller flera värden för att definiera ytterligare information om objekt i din katalog.
title: Anpassade entitetsattribut
uuid: ccebcd16-7d8f-468f-8474-c89b0f029bdb
translation-type: tm+mt
source-git-commit: a686c6964bba360f013d6fb7effcfc7ae5f1eaf5

---


# ![PREMIUM](/help/assets/premium.png) -attribut för anpassad entitet{#custom-entity-attributes}

Använd anpassade entitetsattribut med ett eller flera värden för att definiera ytterligare information om objekt i din katalog.

## Gränser {#limits}

Du kan inkludera upp till 100 anpassade entitetsattribut för att definiera ytterligare information om objekt i katalogen. Du kan till exempel skapa ett anpassat attribut som kallas `entity.genre` för att definiera en bok eller film. Eller så kan en biljettförsäljare skapa attribut för en eventplats som inkluderar en sekundär utförare, till exempel ett besöksteam i ett idrottsevenemang eller en öppningsakt på en konsert.

Den maximala längden för anpassade attribut för en entitet med ett värde är 15 000 tecken (för UTF-8-kodade språk med en eller två byte, som engelska och andra latinska skriftspråk) eller 10 000 tecken (för UTF-8-kodade språk med tre byte som kinesiska, japanska och koreanska).

Anpassade attribut för entiteter med flera värden får inte innehålla fler än 500 värden. Varje enskilt värde är begränsat till 100 tecken. Det totala antalet tecken i alla värden måste uppfylla begränsningarna för den maximala längden för anpassade entitetsattribut med ett värde (se ovan).

## Anpassade värden för entitetsattribut {#section_313331A9F8194A89B5EDD89363018651}

Anpassade entitetsattribut kan innehålla ett eller flera värden. Entitetsattributvärden visas i produktvyn.

![](assets/multi-value_product.png)

Ett anpassat entitetsattribut med ett enda värde formateras på samma sätt som ett fördefinierat entitetsattribut med ett enda värde:

```
entity.genre=genre1
```

Ett anpassat entitetsattribut med flera värden måste skickas som en giltig JSON-matris:

```
entity.genre=[“genre1”, “genre2”]
```

Exempel på giltiga JSON-arrayer som stöds av [!DNL Recommendations]:

* `["AB","BC"]` alla värden är strängar
* `[1,2]` alla värden är numeriska

>[!NOTE]
>
>[!DNL Recommendations] stöder inte blandade värdetyper i entitetsattribut med flera värden. Till exempel `["AB",1,true, [1,2,3]]` är en giltig JSON-array, men den stöds inte i [!DNL Recommendations] eftersom den innehåller blandade värdetyper (sträng, numeriskt, booleskt, objekt).

När ett anpassat attribut har skickats som en giltig JSON-array behandlas attributet som ett flervärdesattribut för alla produkter i katalogen.

>[!NOTE]
>
>Om du vill ändra ett attribut från flera värden till ett enda värde måste du ta bort katalogen och överföra korrigerade produktdata. När du tar bort katalogen tas inte de historiska data som är kopplade till dina produkt-ID:n bort. Mer information finns i [Ta bort alla objekt från systemet](../../assets/adobe-recommendations-classic.pdf) i dokumentationen till *Adobe Recommendations Classic* .

**Begränsningar**:

* Du kan inte använda fördefinierade entitetsattributnamn för anpassade entitetsattribut. (Se [Entitetsattribut](../../c-recommendations/c-products/entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F).)
* Attributet `entity.environment` är reserverat av systemet och kan inte användas för anpassade entitetsattribut. Försök att skicka `entity.environment` med `targetPageParams`, feeds eller API:er kommer att ignoreras.
* Matriser måste innehålla en värdetyp. Matriser med blandade värden ( `["AB",1,true]`) stöds inte.
* Ett attribut med flera värden som innehåller en kapslad JSON-array ( `[10,12,[1,2,3]]`) behandlas som ett attribut med ett enda värde.

## Implementera attribut med flera värden {#section_80FEFE49E8AF415D99B739AA3CBA2A14}

Anpassade entitetsattribut för flera värden stöds när du använder feeds (CSV), Delivery API `targetPageParams`och Save entities API för att överföra produkter. Nya värden ersätter aktuella värden; de är inte tillagda. Tomma arrayer ( [] ) behandlas som om de saknar värden.

Dubbla citattecken måste undantas. Det `"[""test"", ""value""]"` är till exempel en giltig JSON-array som kan användas i CSV.

Du kan ta med upp till 500 värden i ett flervärdesattribut.

**Använda targetPageParams**

I följande exempel visas hur du använder `targetPageParams`

```
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

**Använda CSV**

Du kan hantera dina CSV-filer i Raw-format med en textredigerare eller använda kalkylbladsprogram.

CSV-filen med Raw-format ser ut så här:

![](assets/multi-value_example_raw.png)

Samma katalog kommer att se ut så här i ett kalkylblad:

![](assets/multi-value_example_excel.png)

När du konverterar till [!DNL .csv] format lägger kalkylbladsprogrammet till dubbla citattecken runt cellinnehållet för att förhindra att kommatecken i cellen fungerar som kolumnavgränsare. Det lägger också till citattecken runt JSON-strängvärden som du inkluderar i anpassade attribut med flera värden. Det kan göra det okomplicerat att arbeta direkt med råfilen. Exempel:

* Kalkylblad: `["1","2","3"]`
* Råformat: `"[""1"",""2"",""3""]"`

Var försiktig när du redigerar en CSV-fil med Raw-katalog direkt.

**Använda API:er**

Du kan skicka flervärdesattribut med leverans-API:t i en mbox-parameter som ett strängvärde som innehåller en escape-matris.

```
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

Se dokumentationen [för](http://developers.adobetarget.com/api/recommendations) Adobe Recommendations API för information om hur du använder enhets-API:erna Delivery och Save.

## Använda operatorer med attribut för flera värden {#section_83C2288A805242D9A02EBC4F07DEE945}

När du använder operatorer för anpassade attribut med flera värden i inkluderingsregler för algoritmer, katalogregler och exkluderingsregler, blir resultatet *true* om minst ett värde i listan klarar åtgärden (booleskt *eller*).

I följande exempel är regeln `message contains abc`.

Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde innehåller `abc`.

Fall 2: `entity.genre = ["abcde","de","ef"]`. Resultatet är sant eftersom ett värde innehåller `abc`.

För negativa operatorer måste alla attributvärden skickas (booleskt *och*). Om operatorn till exempel är `notEquals`, blir resultatet *false* om något värde matchar.

I tabellen nedan finns information om operatorbeteende i inkluderingsregler för algoritmer, katalogregler och exkluderingsregler.

| Operator | Beteende | Exempel |
|--- |--- |--- |
| Lika med | Om något attributvärde är lika med indatavärdet, blir resultatet true. | `genre equals abc`<br>Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde är lika med `abc`.<br>Fall 2: `entity.genre = ["abc", "de", "ef"]`. Resultatet är sant eftersom ett värde är lika med `abc`.<br>Fall 3: `entity.genre = ["abcde", "de", "ef"]`. Resultatet är false eftersom `abc` det inte är lika med något element i listan. |
| Är inte lika med | Om inget attributvärde är lika med indatavärdet blir resultatet true. | `genre not equals abc`<br>Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är sant eftersom inget värde är lika med `abc`.<br>Fall 2: `entity.genre = ["abc", "de", "ef"]`. Resultatet är false eftersom ett värde är lika med `abc`.<br>Fall 3: `entity.genre = ["abcde", "de", "ef"]`. Resultatet är sant eftersom det inte `abc`är lika med något element i listan. |
| Innehåller | Om något värde för attributet innehåller indatavärdet, blir resultatet true. | `genre contains abc`<br>Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde innehåller `abc`.<br>Fall 2: `entity.genre = ["abcde", "de", "ef"]`. Resultatet är sant eftersom ett värde innehåller `abc`. |
| Innehåller inte | Om inget värde för attributet innehåller indatavärdet blir true. | `genre does not contain abc`<br>Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är sant eftersom inget värde innehåller `abc`.<br>Fall 2: `entity.genre = ["abcde", "de", "ef"]`. Regeln resulterar i false eftersom ett värde innehåller`abc`. |
| Börjar med | Om ett värde för ett attribut börjar med indatavärdet blir true. | `genre starts with abc`<br>Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde börjar med `abc`.<br>Fall 2: `entity.genre = ["abcde", "de", "ef"]`. Resultatet är sant eftersom ett värde börjar med `abc`.<br>Fall 3: `entity.genre = ["ab", "de", "abc"]`. Resultatet är sant eftersom ett värde börjar med `abc` (inte nödvändigtvis det första elementet i listan). |
| Slutar med | Om ett värde för ett attribut slutar med indatavärdet blir true. | `genre ends with abc`<br>Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde slutar med `abc`.<br>Fall 2: `entity.genre = ["deabc", "de", "ef"]`. Resultatet är sant eftersom ett värde slutar med `abc`. |
| Större än eller lika med (endast numeriska värden) | Attributvärdet konverteras till det dubbla. Attribut som inte kan konverteras hoppas över när regeln körs.<br>Efter bearbetning blir alla attributvärden som är större än eller lika med indatavärdet true. | `price greater than or equal to 100`<br>Fall 1: `entity.price = ["10", "20", "45"]`. Resultatet är false eftersom inget värde är större än eller lika med 100. Värdet `de` hoppas över eftersom det inte kan konverteras till dubbel.<br>Fall 2: `entity.price = ["100", "101", "90", "80"]`. Resultatet är sant eftersom två värden är större än eller lika med 100. |
| Mindre än eller lika med (endast numeriska värden) | Attributvärdet konverteras till det dubbla. Attribut som inte kan konverteras hoppas över när regeln körs.<br>Efter bearbetning blir alla attributvärden som är mindre än eller lika med indatavärdet true. | `price less than or equal to 100`<br>Fall 1: `entity.price = ["101", "200", "141"]`. Resultatet är false eftersom inget värde är mindre än eller lika med 100. Värdet `de` hoppas över eftersom det inte kan konverteras till dubbel.<br>Fall 2: `entity.price = ["100", "101", "90", "80"]`. Resultatet är sant eftersom två värden är mindre än eller lika med 100. |
| Matchar dynamiskt (endast tillgängligt i objektbaserade algoritmer) | Om något attributvärde matchar indatavärdet blir true. | `genre matches abc`<br> Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är false eftersom inget värde matchar `abc`.<br>Fall 2: `entity.genre = ["abc", "de", "ef"]`. Resultatet är sant eftersom ett värde matchar `abc`. |
| Matchar inte dynamiskt (endast tillgängligt i objektbaserade algoritmer) | Om något attributvärde matchar indatavärdet blir resultatet false. | `genre does not match abc`<br>Fall 1: `entity.genre = ["ab", "bc", "de"]`. Resultatet är sant eftersom inget värde matchar `abc`.<br>Fall 2: `entity.genre = ["abc", "de", "ef"]`. Regeln resulterar i false eftersom ett värde matchar `abc`. |
| Dynamiskt omfång (endast tillgängligt i objektbaserade algoritmer, endast numeriska värden) | Om ett numeriskt attributvärde ligger inom det angivna intervallet blir värdet true. | `price dynamically ranges in 80% to 120% of 100`<br>Fall 1: `entity.price = ["101", "200", "125"]`. Resultatet är sant eftersom `101` det ligger mellan 80 % och 120 % av 100. Värdet `de` hoppas över eftersom det inte kan konverteras till dubbel.<br>Fall 2: `entity.price = ["130", "191", "60", "75"]`. Resultatet är false eftersom inget värde ligger i intervallet 80 % till 120 % av 100. |

>[!NOTE]
>
>*Double* är en Java-datatyp. Om du konverterar till dubbel för operatorer som kräver numeriska värden tas icke-numeriska värden bort från resultatet.

## Attribut med flera värden i design {#section_F672E4F6E1D44B3196B7ADE89334ED4A}

Flervärdesattribut visas som kommaavgränsade listor när de refereras i en design.

Exempel:

När `entity.genre=["genre1","genre2"]` refereras i en design som `$entity<N>.genre`blir resultatet `genre1, genre2`.

>[!MORELIKETHIS]
>
>* [Entitetsattribut](../../c-recommendations/c-products/entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F)

