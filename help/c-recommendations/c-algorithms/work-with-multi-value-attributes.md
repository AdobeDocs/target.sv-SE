---
keywords: multivalue;attributes;recommendations;multi-value;multivalue;multi-value
description: Information om hur du arbetar med ett flervärdesfält i Adobe Target Recommendations med hjälp av särskilda flervärdesoperatorer.
title: Arbeta med flervärdesattribut i Recommendations Target
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---


# Arbeta med attribut för flera värden

Ibland kanske du vill arbeta med ett fält med flera värden. Titta på följande exempel:

* Du erbjuder filmer till användare. En viss film har flera skådespelare.
* Du säljer biljetter till konserter. En viss användare har flera favoritband.
* Du säljer kläder. En skjorta finns i flera storlekar.

Om du vill hantera rekommendationer i de här scenarierna kan du skicka data med flera värden till [!DNL Target Recommendations] och använda särskilda operatorer med flera värden.

Om du vill att [!DNL Recommendations] ska kunna identifiera data med flera värden, ska det skickas som en JSON-array, som i nedanstående kodexempel.

## Skicka en flervärdesparameter i JavaScript

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

Mer information finns i [Implementera attribut med flera värden](/help/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) i *Anpassade entitetsattribut*.

## Skicka ett entitetsattribut med flera värden i en CSV-fil

```
## RECSRecommendations Upload File,,,,,,,,,,,,,,,,,,,
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines.,,,,,,,,,,,,,,,,,,,
## RECS,,,,,,,,,,,,,,,,,,,
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left.,,,,,,,,,,,,,,,,,,,
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'.,,,,,,,,,,,,,,,,,,,
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations.,,,,,,,,,,,,,,,,,,,
## RECSentity.id ,entity.name,entity. categoryId ,entity. message ,entity.thumbnailUrl ,entity.value ,entity.pageUrl ,entity.inventory ,entity.margin ,entity.custom1 ,entity.custom2 ,entity.custom3 ,entity.custom4,entity.custom5,entity.custom6,entity.custom7,entity.custom8,entity.custom9,entity.custom10,
1,Sample Product 1,category1,Save 10%,http://sample.store/products/images/product1_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=1,1000,48,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
2,Sample Product 2,category1,Save 10%,http://sample.store/products/images/product2_th.jpg,369,http://sample.store/products/product_detail.jsp?productId=2,1000,52,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
3,Sample Product 3,category1,Save 10%,http://sample.store/products/images/product3_th.jpg,479,http://sample.store/products/product_detail.jsp?productId=3,1000,78,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
4,Sample Product 4,category1,Save 10%,http://sample.store/products/images/product4_th.jpg,409,http://sample.store/products/product_detail.jsp?productId=4,1000,66,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
5,Sample Product 5,category1,Save 10%,http://sample.store/products/images/product5_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=5,1000,45,a,"[ ""v1"", ""v2"" ]",,,,,,,,, 
```

När ett entitetsattribut, profilattribut eller mbox-parameter anges som flervärde enligt ovanstående format, innebär [!DNL Recommendations] automatiskt att fältet är flervärde.

Följande operatorer är tillgängliga för användning med entitets-, profil- och mbox-attribut med flera värden:

* [!UICONTROL is contained in list]
* [!UICONTROL is not contained in list]

## Arbeta med attribut med flera värden i inkluderingsregler

>[!NOTE]
>
>Stöd för dynamisk matchning av attribut med flera värden är för närvarande bara tillgängligt i villkor när en matchningsregel för profilattribut eller parameterattribut (mbox) används vid jämförelse av ett enskilt värde från vänster sida till en höger sida med flera värden. Flervärdesattribut stöds för närvarande inte i kampanjer, entitetsattributmatchning eller för listor till vänster om inkluderingsregler.

### Exempel: Uteslut nyligen bevakade objekt

Anta att du vill förhindra att filmer som finns i användarens senaste tio bevakade filmer rekommenderas. Först skriver du ett profilskript med namnet `user.lastWatchedMovies` för att spåra de tio senast visade filmerna som en JSON-array. Sedan kan du exkludera objekten med följande inkluderingsregel:

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
```

JSON API-representation av inkluderingsregeln:

```
{
    "attribute": "id",
    "operation": "isNotContainedInList",
    "source": {
        "name": "user.lastWatchedMovies",
        "type": "PROFILE"
    }
} 
```

### Exempel: Rekommendera objekt från användarens favoriter

Anta att du bara vill rekommendera biljetter till konserter om bandet som spelas är ett av användarens favoritband. Kontrollera först att du har en profilvariabel med namnet `profile.favoriteBands` som innehåller användarens favoritband. Kontrollera sedan att katalogen innehåller attributet `entity.artistPerforming` som innehåller artisten som utför konserten. Sedan kan du använda följande inkluderingsregel:

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
```

JSON API-representation av inkluderingsregeln:

```
{
    "attribute": "artistPerforming",
    "operation": "isContainedInList",
    "source": {
        "name": "profile.favoriteBands",
        "type": "PROFILE"
    }
}
```

### Exempel: API-generering av villkor som rekommenderar objekt från en användares favoriter

Kriterier med flervärdesfiltreringsregler, precis som alla villkor, kan skapas via Adobe I/O API:er. Ett exempel-API-anrop för att skapa ett villkor där entitetsattributet `id` finns i mbox-parameterlistan `favorites` finns här:

```
curl -X POST \
  https://<serverhost>/api/recs/<client>/criteria/item \
  -H 'Accept: application/vnd.adobe.target.v1+json' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: <from API client>' \
  -H 'X-Target-user-email: <email address>' \
  -H 'cache-control: no-cache' \
  -d '{
    "name": "viewed criteria",
    "criteriaTitle": "test title",
    "type": "VIEWED_CF",
    "key": "CURRENT",
    "daysCount": "TWO_WEEKS",
    "aggregation": "NONE",
    "backupDisabled": false,
    "partialDesignAllowed": true,
    "configuration": {
        "inclusionRules": [
            {
                "attribute": "id",
                "operation": "isContainedInList",
                "source": {
                    "name": "mbox.favorites",
                    "type": "MBOX"
                }
            }
        ]
    }
}'
```

Den här kombineras med JavaScript på sidan för att skicka favoritinnehållet:

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
