---
keywords: custom design;velocity;decimal;comma;customize design
description: Använd designspråket Velocity med öppen källkod för att anpassa rekommendationsdesignen i Adobe Target Recommendations.
title: Anpassa en design med Snabb
feature: designs
uuid: 80701a15-c5eb-4089-a92e-117eda11faa2
translation-type: tm+mt
source-git-commit: afbec50cb0ec4e689bfaa77296ffda91bc6de3a5
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Anpassa en design med Snabb{#customize-a-design-using-velocity}

Använd designspråket Velocity med öppen källkod för att anpassa rekommendationsdesignen i [!DNL Adobe Target Recommendations].

## Översikt över hastighet {#section_C431ACA940BC4210954C7AEFF6D03EA5}

Information om hastighet finns på [https://velocity.apache.org](https://velocity.apache.org).

All snabbhetslogik, syntax och så vidare kan användas för en rekommendationsdesign. Det innebär att du kan skapa *for* -slingor, *if* -programsatser och annan kod med hjälp av Velocity i stället för JavaScript.

Alla variabler som skickas till [!DNL Recommendations] i `productPage` mbox eller CSV-överföringen kan visas i en design. Dessa värden refereras med följande syntax:

```
$entityN.variable
```

Variabelnamn måste följa i förkortningen av Velocity, som består av ett inledande *$* -tecken följt av en VTL-identifierare (Velocity Template Language). VTL-identifieraren måste börja med ett alfabetiskt tecken (a-z eller A-Z).

Variabelnamn för hastighet är begränsade till följande typer av tecken:

* Alfabetisk (a-z, A-Z)
* Numerisk (0-9)
* Bindestreck ( - )
* Understreck ( _ )

Följande variabler är tillgängliga som Velocity-arrayer. Därför kan de itereras över eller refereras via index.

* `entities`
* `entityN.categoriesList`

Exempel:

```
#foreach ($category in $entity1.categoriesList) 
<br/>$category 
#end
```

eller

```
#if ($entities[0].categoriesList.size() >= 3 ) 
$entities[0].categoriesList[2] 
#end
```

Mer information om hastighetsvariabler finns i [https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables).

Om du använder ett profilskript i din design måste $ före skriptnamnet escape-konverteras med ett \. Exempel, `\${user.script_name}`.

>[!NOTE]
>
>Det maximala antalet enheter som kan refereras i en design, antingen hårdkodade eller via slingor, är 99. Mallskriptlängden kan innehålla upp till 65 000 tecken.

Om du till exempel vill ha en design som visar något liknande:

![](assets/velocity_example.png)

du kan använda följande kod:

```
<table style="border:1px solid #CCCCCC;"> 
<tr> 
<td colspan="3" style="font-size: 130%; border-bottom:1px solid  
#CCCCCC;"> You May Also Like... </td> 
</tr> 
<tr> 
<td style="border-right:1px solid #CCCCCC;"> 
<div class="search_content_inner" style="border-bottom:0px;"> 
<div class="search_title"><a href="$entity1.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity1.id</a></div> 
By $entity1.message <a href="?x14=brand;q14=$entity1.message"> 
(More)</a><br/> 
sku: $entity1.prodId<br/> Price: $$entity1.value 
<br/><br/> 
</div> 
</td> 
<td style="border-right:1px solid #CCCCCC; padding-left:10px;"> 
<div class="search_content_inner" style="border-bottom:0px;">  
<div class="search_title"><a href="$entity2.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity2.id</a></div> 
By $entity2.message <a href="?x14=brand;q14=$entity2.message"> 
(More)</a><br/> 
sku: $entity2.prodId<br/> 
Price: $$entity2.value 
<br/><br/> 
</div> 
</td> 
<td style="padding-left:10px;"> 
<div class="search_content_inner" style="border-bottom:0px;"> 
<div class="search_title"><a href="$entity3.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity3.id</a></div> 
By $entity3.message <a href="?x14=brand;q14=$entity3.message"> 
(More)</a><br/> 
sku: $entity3.prodId<br/> Price: $$entity3.value 
<br/><br/> 
</div> 
</td> 
</tr>  
</table>
```

>[!NOTE]
>
>Om du vill lägga till text efter värdet för en variabel före en -tagg som anger att variabelnamnet är slut, kan du göra det med formell notation för att omsluta variabelns namn. Exempel: `${entity1.thumbnailUrl}.gif`.

Du kan också använda `algorithm.name` och `algorithm.dayCount` som variabler i en design, så att en design kan användas för att testa flera villkor, och villkorsnamnet kan visas dynamiskt i designen. Det här visar besökaren att han eller hon tittar på&quot;bästsäljare&quot; eller&quot;personer som såg det här köpte det&quot;. Du kan till och med använda dessa variabler för att visa `dayCount` (antal dagar med data som används i villkoren, som&quot;bästsäljare under de senaste två dagarna&quot; osv.

## Arbeta med siffror i hastighetsmallar

Som standard hanteras alla entitetsattribut som strängvärden i snabbmeddelandemallar. Du kanske vill behandla ett entitetsattribut som ett numeriskt värde för att utföra en matematisk åtgärd eller jämföra det med ett annat numeriskt värde. Så här behandlar du ett entitetsattribut som ett numeriskt värde:

1. Deklarera en dummy-variabel och initiera den till ett godtyckligt heltal eller dubbelvärde.
1. Kontrollera att det entitetsattribut du vill använda inte är tomt (krävs för att Recommendations mallparser för Target ska kunna validera och spara mallen).
1. Skicka entitetsattributet till `parseInt` - eller `parseDouble` -metoden för dummy-variabeln som du skapade i steg 1 för att omvandla strängen till ett heltal eller ett dubbelvärde.
1. Utför matematisk åtgärd eller jämförelse på det nya numeriska värdet.

### Exempel: Beräkna ett rabattpris

Anta att du vill minska det visade priset för en artikel med $0,99 för att tillämpa en rabatt. Du kan använda följande metod för att uppnå detta resultat:

```
#set( $Double = 0.1 )

#if( $entity1.get('priceBeforeDiscount') != '' )
    #set( $discountedPrice = $Double.parseDouble($entity1.get('priceBeforeDiscount')) - 0.99 )
    Item price: $$discountedPrice
#else
    Item price unavailable
#end
```

### Exempel: Välja hur många stjärnor som ska visas baserat på ett objekts klassificering

Anta att du vill visa ett lämpligt antal stjärnor baserat på ett objekts numeriska genomsnittliga kundomdöme. Du kan använda följande metod för att uppnå detta resultat:

```
#set( $Double = 0.1 )

#if( $entity1.get('rating') != '' )
    #set( $rating = $Double.parseDouble($entity1.get('rating')) )
    #if( $rating >= 4.5 )
        <img src="5_stars.jpg">
    #elseif( $rating >= 3.5 )
        <img src="4_stars.jpg">
    #elseif( $rating >= 2.5 )
        <img src="3_stars.jpg">
    #elseif( $rating >= 1.5 )
        <img src="2_stars.jpg">
    #else
        <img src="1_star.jpg">
    #end
#else
    <img src="no_rating_default.jpg">
#end
```

### Exempel: Beräkna tiden i timmar och minuter baserat på en artikels längd i minuter

Anta att du lagrar längden på en film i minuter, men vill visa längden i timmar och minuter. Du kan använda följande metod för att uppnå detta resultat:

```
#if( $entity1.get('length_minutes') )
#set( $Integer = 1 )
#set( $nbr = $Integer.parseInt($entity1.get('length_minutes')) )
#set( $hrs = $nbr / 60)
#set( $mins = $nbr % 60)
#end
```

## Visa ett nyckelobjekt med rekommenderade produkter {#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}

Du kan ändra designen så att nyckelobjektet visas tillsammans med andra rekommenderade produkter. Du kanske vill visa det aktuella objektet som referens bredvid rekommendationerna.

Det gör du genom att skapa en kolumn i designen som använder attributet som du baserar din rekommendation på i stället för `$key` `$entity` attributet. Koden för nyckelkolumnen kan till exempel se ut så här:

```
<div class="at-table-column"> 
   <a href="$key.pageURL"> 
      <img src=$key.thumbnailUrl" class="at-thumbnail"/> 
      <br/><h3>$key.name</h3> 
      <br/><p class="at-light">$key.message</p> 
      <br/><p class="at-light">$key.value</p> 
   </a> 
</div>
```

Resultatet är en design som följande, där nyckelobjektet visas i en kolumn.

![](assets/rec_key.png)

När du skapar din [!DNL Recommendations] aktivitet visas en slumpmässig produkt i [!DNL Target] (VEC) om nyckelobjektet hämtas från besökarens profil, t.ex.&quot;senast köpta artikel&quot; [!UICONTROL Visual Experience Composer] . Detta beror på att en profil inte är tillgänglig när du designar aktiviteten. När besökarna visar sidan visas det förväntade nyckelobjektet.

## Utföra ersättningar i ett strängvärde {#section_01F8C993C79F42978ED00E39956FA8CA}

Du kan ändra designen och ersätta värden i en sträng. Du kan till exempel ersätta decimalpunktsavgränsaren som används i USA med kommaavgränsaren som används i Europa och andra länder.

I följande kod visas en rad i ett exempel på villkorsstyrd försäljningspris:

```
<span class="price">$entity1.value.replace(".", ",") €</span><br>
```

Följande kod är ett fullständigt villkorligt exempel på ett försäljningspris:

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") €</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") €<br> #else 
    <span class="price">$entity1.value.replace(".", ",") €</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
```

## Anpassa mallstorleken och kontrollera om det finns tomma värden {#default}

Med ett Velocity-skript som styr dynamisk storleksanpassning av enhetsvisningen får följande mall ett till många-resultat för att undvika att skapa tomma HTML-element när det inte finns tillräckligt med matchande entiteter som returnerats från [!DNL Recommendations]. Det här skriptet passar bäst för scenarier när det inte går att förvränga rekommendationer för säkerhetskopiering och [!UICONTROL Partial Template Rendering] är aktiverat.

Följande HTML-kodfragment ersätter den befintliga HTML-delen i standarddesignen 4x2 (CSS inkluderas inte här, av tydlighetsskäl):

* Om det finns en femte entitet infogar skriptet en avslutande div och öppnar en ny rad med `<div class="at-table-row">`.
* Med 4x2 blir det maximala resultatet åtta, men det kan anpassas för mindre eller större listor genom att ändra `$count <=8`.
* Observera att logiken inte balanserar enheterna på flera rader. Om det till exempel finns fem eller sex enheter att visa, blir det inte dynamiskt tre överst och två nederst (eller tre överst och tre längst ned). Den översta raden visar fyra objekt innan en andra rad påbörjas.

```
<div class="at-table">
  <div class="at-table-row">
    #set($count=1) 
    #foreach($e in $entities)  
        #if($e.id != "" && $count < $entities.size() && $count <=8) 
            #if($count==5) 
                </div>
                <div class="at-table-row">
            #end
            <div class="at-table-column">
                <a href="$e.pageUrl"><img src="$e.thumbnailUrl" class="at-thumbnail" />
                    <br/>
                    <h3>$e.name</h3>
                    <br/>
                    <p class="at-light">$e.message</p>
                    <br/>
                    <p class="at-light">$$e.value</p>
                </a>
            </div>
            #set($count = $count + 1) 
        #end 
    #end
  </div>
</div>
```
