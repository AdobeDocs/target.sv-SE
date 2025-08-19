---
keywords: entitet;entitetsattribut;skicka information till rekommendationer;beteendedata;dataräknare;definiera relativ URL;visa lagernivå;definiera pris;definiera vinstmarginal;anpassade attribut
description: Lär dig hur du använder entitetsattribut för att skicka produkt- eller innehållsinformation till  [!DNL Target] rekommendationer.
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
title: Hur använder jag entitetsattribut?
feature: Recommendations
exl-id: 4ed5fad3-b8b6-4675-a741-9f85cf73fcf1
source-git-commit: b6697eee5925cb8fa3b2fa2e107af0c617d30f94
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 0%

---

# Entitetsattribut

Använd entitetsattribut för att skicka produkt- eller innehållsinformation till [!DNL Adobe Target Recommendations].

Enheter refererar till de objekt som du vill rekommendera. Exempel på organisationer är produkter, innehåll (artiklar, bildspel, bilder, filmer och TV-program), jobblistor, restauranger och så vidare.

[!DNL Recommendations] skickar `productId` eller `productPurchasedId` (kallas `entity.id` i koden) som används i algoritmerna.

Tänk på följande:

* `entity.id` måste matcha det `productPurchasedId` som skickas till orderbekräftelsesidan och det `productId` som används i [!DNL Adobe Analytics] produktrapporter.
* Entitetsattributvärden som du skickar till [!DNL Recommendations] upphör att gälla efter 61 dagar. Adobe rekommenderar att du skickar det senaste värdet för varje entitetsattribut till [!DNL Recommendations] minst en gång i månaden för varje objekt i katalogen.

De flesta fördefinierade parametrar accepterar endast ett värde, med nya värden som skriver över gamla värden. Parametern `categoryId` kan acceptera en kommaavgränsad lista med värden för varje kategori som innehåller den produkten. Nya `categoryId`-värden skriver inte över befintliga värden, utan läggs till under entitetsuppdateringen (högst 250 tecken).

I allmänhet ser visningsinformationsrutan ut som i följande exempel om du använder at.js 1.*x* med `mboxCreate`. Alla entitetsparameterattribut är skiftlägeskänsliga.

>[!NOTE]
>
>Om du använder at.js 2.*x*, `mboxCreate` (som i följande exempel) stöds inte längre. Om du vill skicka produkt- eller innehållsinformation till [!DNL Recommendations] med at.js 2.*x*, använd [targetPageParams](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparams.html?lang=sv-SE){target=_blank}. Se till exempel [Planera och implementera rekommendationer](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=sv-SE){target=_blank}.

```javascript
<div class="mboxDefault"></div><script language="JavaScript1.2"> 
 
mboxCreate('productPage', 
 
'entity.id=67833', 
 
'entity.name=GIANTS VS ROCKIES 5/12', 
 
'entity.categoryId=BASEBALL, GIANTS, SF BAY AREA', 
 
'entity.pageUrl=/help/baseball/giants-tix/giantsvrockies5.12.2000-67833', 
 
'entity.venue=AT&T PARK', 
 
'entity.secondary=ROCKIES', 
 
'entity.thumbnailUrl=/help/baseball/giants-tix/giants-136px.gif', 
 
'entity.message=FAMILY SPECIAL', 
 
'entity.value=15.99', 
 
'entity.inventory=1' 
 
); 
 
</script>
```

>[!NOTE]
>
>Relativa URL:er rekommenderas för `pageUrl` och `thumbnailUrl` i stället för absoluta URL:er eftersom rekommendationer tar emot data från alla miljöer på webbplatsen. Genom att använda relativa URL-adresser undviker du hårdkodade länkar till en mellanlagrings- eller utvecklingsserver.

Om mbox finns på en produktsida kan du inkludera både produkt-ID och kategori-ID. Den valda algoritmen avgör vilka som visas. Produkt-ID används för tillhörighetsalgoritmer och kategori-ID används för kategorialgoritmer.

## Tillgängliga variabler

I följande lista beskrivs de tillgängliga variablerna.

### entity.id

Endast ett värde.

Den här obligatoriska parametern identifierar produkten. Detta alfanumeriska ID måste vara samma för alla [!DNL Adobe Experience Cloud]-produkter som används, inklusive [!DNL Analytics], för att de olika produkterna ska kunna identifiera objektet och dela data om det.

`entity.id`-värdena får *inte* innehålla mellanslag, snedstreck, et-tecken, frågetecken, procentsymboler, kommatecken eller andra skiljetecken som kräver URL-kodning när de skickas i ett REST API-anrop. Bindestreck och understreck tillåts. Om ogiltig interpunktion ingår i ett `entity.id`-värde misslyckas vissa [!DNL Recommendations]-funktioner.

Exempel: `'entity.id=67833'`

### entity.name

Endast ett värde.

Det produktnamn som visas på webbplatsen när produkten rekommenderas.

Exempel: `'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

Stöder flera värden (kommaavgränsad lista).

Den aktuella sidans kategori. Entity.categoryID kan innehålla flera kategorier, t.ex. underavsnittet cardigans (t.ex. `womens`, `womens:sweaters`, `womens:sweaters:cardigans`). Flera kategorier måste avgränsas med kommatecken.

Värdet `categoryId` får innehålla högst 250 tecken.

>[!NOTE]
>
>Om du vill visa en rekommendation baserad på en kategori på en [!UICONTROL Category]-sida kan bara en `categoryId` skickas till mbox som används för att visa den aktuella rekommendationen. Värdet för `categoryId` måste matcha exakt värdet för `entity.categoryId` som skickats på sidan [!UICONTROL Product Detail].

Exempel:

* Exempel på produktinformationssida: `womens`, `womens:sweaters`, `womens:sweaters:cardigans`
* Exempel på kategorisidomatare: `womens:sweaters`
* Exempel på sidnumrering för kategori: `womens:sweaters:cardigans`

För kategoribaserade rekommendationer avgränsar ett kommatecken kategorivärdet. Alla värden som avgränsas med kommatecken blir kategorier. Du kan också definiera underkategorier genom att använda en annan avgränsare, t.ex. ett kolon (:), för att skilja underkategorier inom kategorivärdet.

I följande kod delas kategorin Kvinnor in i flera underkategorier:

```javascript
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban', 'entity.thumbnailUrl=...', 'entity.message=...', );
```

För leverans av mbox används det längsta attributnamnet för nyckeln. Om det finns en slips används det sista attributet. I exemplet ovan är kategorinyckeln `Womens:Outerwear:Jackets:Caban`.

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

Ett meddelande om produkten som visas i rekommendationen, t.ex.&quot;vid försäljning&quot; eller&quot;godkännande&quot;. Meddelandet är vanligtvis mer detaljerat än produktnamnet. Använd entity.message för att definiera ytterligare information som ska visas med produkten i mallen.

Exempel: `'entity.message=Family&nbsp;special'`

### entity.inventory

Endast ett värde. Kräver ett heltal eller ett långt värde.

Visar artikelns lagernivå.

Exempel: `'entity.inventory=1'`

**Tom attributhantering för lager:** Om du har en inkluderingsregel, samlingsregel eller kriterieinställning med `entity.inventory` > 0 eller `entity.inventory` = 0 och produkten inte har angett något lager utvärderar [!DNL Target] det här värdet till TRUE och inkluderar produkter där lagret inte har angetts. Detta resulterar i att produkter med lager som inte är inställda visas i rekommendationsresultat.

Om du har en global exkluderingsregel med `entity.inventory` = 0 och `entity.inventory` inte har angetts utvärderar [!DNL Target] den här regeln till TRUE och utesluter produkten.

**Känt fel:** Produktsökning är inkonsekvent med leverans för lagervärdesattribut som inte har angetts. För en regel med `entity.inventory` = 0 visar produktsökningen inte produkter där lagervärdet inte har angetts.

### entity.value

Endast ett värde.

Definierar pris eller värde för artikeln.

Exempel: `'entity.value=15.99'`

entity.value stöder endast decimalformat (till exempel 15.99). Kommaformatet (15,99) stöds inte.

### entity.margin

Endast ett värde.

Vinstmarginalen eller annat värde för artikeln.

Exempel: `'entity.margin=1.00'`

### enhet.*anpassad*

Stöder flervärdesmatris (JSON-matris).

Definiera upp till 100 anpassade variabler som innehåller ytterligare information om objektet. Du kan ange vilket attributnamn som inte används för varje anpassat attribut. Du kan till exempel skapa ett anpassat attribut med namnet `entity.genre` för att definiera en bok eller film. En biljettleverantör kan skapa attribut för en evenemangsplats för en sekundär utförare, till exempel ett besöksteam i ett idrottsevenemang eller en öppningsakt på en konsert.

Begränsningar:

* Du kan inte använda fördefinierade entitetsattributnamn för anpassade entitetsattribut.
* Attributet entity.environment är reserverat för systemet och kan inte användas för anpassade entitetsattribut. Försök att skicka entity.environment med targetPageParams, feed eller API ignoreras.

Exempel:

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

Anpassade entitetsattribut har stöd för flera värden. Se [Anpassade entitetsattribut](/help/main/c-recommendations/c-products/custom-entity-attributes.md#limits) för tecken- och värdegränser.

Exempel: `'entity.secondary=["band1",&nbsp;"band2"]'`

Anpassade entitetsattribut med flera värden kräver giltiga JSON-matriser. Korrekt syntaxinformation finns i [Anpassade entitetsattribut](/help/main/c-recommendations/c-products/custom-entity-attributes.md).

### entity.event.detailsOnly

Endast ett värde.

Används för att förhindra att ett mbox-anrop ökar beteendedataräknare för en algoritm.

Exempel: `'entity.event.detailsOnly=true'`

I exemplen nedan uppdaterar det första mbox-anropet katalogen och beteendedata. Det andra mbox-anropet uppdaterar bara katalogen.

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

>[!MORELIKETHIS]
>
>* [Anpassade entitetsattribut](/help/main/c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)
