---
keywords: entity;entity attributes;pass information to Recommendations;behavioral data;data counter;define relative URL;display inventory level;define price;define profit margin;custom attributes
description: Använd entitetsattribut för att skicka produkt- eller innehållsinformation till Adobe Target Recommendations.
title: Entitetsattribut
feature: entities
uuid: 27672881-a79c-4271-9a61-defddb9a5249
translation-type: tm+mt
source-git-commit: 37f2faf8f82286d909f813fd7cc349c3e769bb4d
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) -enhetsattribut{#entity-attributes}

Använd entitetsattribut för att skicka produkt- eller innehållsinformation till [!DNL Adobe Target Recommendations].

[!DNL Recommendations] skickar `productId` eller `productPurchasedId` (kallas `entity.id` i koden) som används i algoritmerna.

>[!NOTE]
>
>* `entity.id` måste matcha den `productPurchasedId` som skickas till orderbekräftelsesidan och den som `productId` används i Adobe Analytics produktrapporter.
   >
   >
* Angivna värden för entitetsattribut upphör att gälla efter 61 dagar. Det innebär att du bör se till att det senaste värdet för varje entitetsattribut skickas till Target Recommendations minst en gång i månaden för varje objekt i din katalog.


De flesta fördefinierade parametrar accepterar bara ett enda värde, med nya värden som skriver över gamla värden. Parametern `categoryId` kan acceptera en kommaavgränsad lista med värden för varje kategori som innehåller den produkten. Nya `categoryId` värden skriver inte över befintliga värden, utan läggs till under entitetsuppdateringen (högst 250 tecken).

I allmänhet kan visningsinformationsrutan se ut som i följande exempel om du använder at.js 1.*x* with `mboxCreate`.

>[!NOTE]
>
>* Om du använder at.js 2.*x*, `mboxCreate` (som i följande exempel) stöds inte längre. Skicka produkt- eller innehållsinformation till Recommendations med at.js 2.*x*, använd [targetPageParams](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md). Ett exempel finns i [Planera och implementera Recommendations](/help/c-recommendations/plan-implement.md).

>



Alla entitetsparameterattribut är skiftlägeskänsliga.

```
<div class="mboxDefault"></div><script language="JavaScript1.2"> 
 
mboxCreate('productPage', 
 
'entity.id=67833', 
 
'entity.name=GIANTS VS ROCKIES 5/12', 
 
'entity.categoryId=BASEBALL, GIANTS, SF BAY AREA', 
 
'entity.pageUrl=../baseball/giants-tix/giantsvrockies5.12.2000-67833', 
 
'entity.venue=AT&T PARK', 
 
'entity.secondary=ROCKIES', 
 
'entity.thumbnailUrl=../baseball/giants-tix/giants-136px.gif', 
 
'entity.message=FAMILY SPECIAL', 
 
'entity.value=15.99', 
 
'entity.inventory=1' 
 
); 
 
</script>
```

>[!NOTE]
>
>Relativa URL:er rekommenderas för `pageUrl` och `thumbnailUrl` inte för absoluta URL:er eftersom rekommendationer tar emot data från alla miljöer på webbplatsen. Genom att använda relativa URL-adresser undviker du hårdkodade länkar till en mellanlagrings- eller utvecklingsserver.

Om mbox finns på en produktsida kan du inkludera både produkt-ID och kategori-ID. Den valda algoritmen avgör vilka som visas. Produkt-ID används för tillhörighetsalgoritmer och kategori-ID används för kategorialgoritmer.

## Tillgängliga variabler

I följande lista beskrivs de tillgängliga variablerna.

### entity.id

Endast ett värde.

Den här obligatoriska parametern identifierar produkten. Detta alfanumeriska ID måste vara samma för alla [!DNL Adobe Experience Cloud] produkter som används, inklusive [!DNL Analytics]för de olika produkterna, för att artikeln ska kunna identifieras och för att dela data om den.

`entity.id` värden får inte innehålla snedstreck, et-tecken, frågetecken, procentsymboler, kommatecken eller andra skiljetecken som kräver URL-kodning när de skickas i ett REST API-anrop. Bindestreck och understreck är tillåtna. Om du tar med ogiltig interpunktion i ett `entity.id` värde misslyckas vissa [!DNL Recommendations] funktioner.

Exempel: `'entity.id=67833'`

### entity.name

Endast ett värde.

Det produktnamn som visas på webbplatsen när produkten rekommenderas.

Exempel: `'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

Stöder flera värden (kommaavgränsad lista).

Den aktuella sidans kategori. Detta kan omfatta flera kategorier, t. ex. en underavdelning till mordianer (t. ex. kvinnor, kvinnor: svettare, kvinnor: vårdare: vårdare). Flera kategorier ska avgränsas med kommatecken.

`categoryId` får innehålla högst 250 tecken.

>[!NOTE]
>
>Om du vill visa en rekommendation baserat på en kategori på en [!UICONTROL Category] `categoryId` sida, kan bara en av dem skickas till rutan som används för att visa den aktuella rekommendationen. Värdet för `categoryId` måste matcha exakt värdet för den `entity.categoryId` som skickas på [!UICONTROL Product Detail] sidan.

Exempel:

* Exempel på produktinformationssida: kvinnor, kvinnor:trötthet, kvinnor:trötthet:vårdnadshavare
* Exempel: Kategorisidomatare: kvinnor:trötthet
* Exempel: Kategorisidnumrering: kvinnor:tröja:morfar

För kategoribaserade rekommendationer används ett kommatecken för att skilja kategorivärden åt. Alla värden som avgränsas med kommatecken blir kategorier. Du kan också definiera underkategorier genom att använda en annan avgränsare, t.ex. ett kolon (:), för att skilja underkategorier inom kategorivärdet.

I följande kod är till exempel kategorin Vinnare indelad i flera underkategorier:

```
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban’, 'entity.thumbnailUrl=...', 'entity.message=...', );
```

För leverans av mbox används det längsta attributnamnet för nyckeln. Om det finns en slips används det sista attributet. I exemplet ovan är kategorinyckeln Womens:Outerwear:Jackets:Caban .

### entity.brand

Endast ett värde.

Visar ett objekts varumärke.

Exempel: `'entity.brand=brandxyz'`

### entity.pageUrl

Endast ett värde.

Definierar den relativa URL-adressen till sidan där objektet kan köpas.

Exempel: `'entity.pageUrl=baseball/giants-tix/giantsvrockies5.12.2000-67833'`

### entity.thumbnailUrl

Endast ett värde.

Definierar den relativa URL-adressen till miniatyrbilden som visas med objektet.

Exempel: `'entity.thumbnailUrl=baseball/giants-tix/giants-136px.gif'`

### entity.message

Endast ett värde.

Ett meddelande om produkten som visas i rekommendationen, t.ex.&quot;vid försäljning&quot; eller&quot;godkännande&quot;. Meddelandet är vanligtvis mer detaljerat än produktnamnet. Använd för att definiera ytterligare information som ska visas med produkten i mallen.

Exempel: `'entity.message=Family&nbsp;special'`

### entity.inventory

Endast ett värde. Kräver ett heltal eller ett långt värde.

Visar artikelns lagernivå.

Exempel: `'entity.inventory=1'`

**Tom attributhantering för lager:** Om du för leverans har en inkluderingsregel, samlingsregel eller kriterieinställning med `entity.inventory` > 0 eller `entity.inventory` = 0 och produkten inte har angett något lager, [!DNL Target] utvärderar detta till TRUE och inkluderar produkter där lagret inte har angetts. Detta gjordes som standard så att produkter med lager som inte är inställda visas i rekommendationsresultat.

Om du har en global exkluderingsregel med `entity.inventory` = 0 och `entity.inventory` inte har angetts, [!DNL Target] utvärderas den här regeln som TRUE och produkten exkluderas.

**Känt fel:** Produktsökningen är inkonsekvent med leveransen för lagervärdesattribut som inte har angetts. För en regel med `entity.inventory` = 0 visas inte produkter där lagervärdet inte har angetts.

### entity.value

Endast ett värde.

Definierar pris eller värde för artikeln.

Exempel: `'entity.value=15.99'`

### entity.margin

Endast ett värde.

Vinstmarginalen eller annat värde för artikeln.

Exempel: `'entity.margin=1.00'`

### enhet.*anpassad*

Stöder flervärdesmatris (JSON-matris).

Definiera upp till 100 anpassade variabler som innehåller ytterligare information om objektet. Du kan ange vilket attributnamn som inte används för varje anpassat attribut. Du kan till exempel skapa ett anpassat attribut som kallas `entity.genre` för att definiera en bok eller film. Eller så kan en biljettförsäljare skapa attribut för en eventplats för en sekundär utförare, till exempel ett besöksteam i ett idrottsevenemang eller en öppningsakt i en konsert.

Begränsningar:

* Du kan inte använda fördefinierade entitetsattributnamn för anpassade entitetsattribut.
* Attributet entity.environment är reserverat för systemet och kan inte användas för anpassade entitetsattribut. Försök att skicka entity.environment med targetPageParams, feed eller API ignoreras.

Exempel:

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

Anpassade entitetsattribut har stöd för flera värden. Se [Anpassade entitetsattribut](/help/c-recommendations/c-products/custom-entity-attributes.md#limits) för tecken- och värdegränser.

Exempel: `'entity.secondary=["band1",&nbsp;"band2"]'`

>[!NOTE]
>
>Anpassade entitetsattribut med flera värden kräver giltiga JSON-matriser. Korrekt syntaxinformation finns i Anpassade entitetsattribut.

### entity.event.detailsOnly

Endast ett värde.

Används för att förhindra att ett mbox-anrop ökar beteendedataräknare för en algoritm.

Exempel: `'entity.event.detailsOnly=true'`

I exemplen nedan uppdaterar det första mbox-anropet katalogen och beteendedata. Det andra mbox-anropet uppdaterar bara katalogen.

```
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

## Relaterade ämnen:

* [Anpassade entitetsattribut](../../c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)
