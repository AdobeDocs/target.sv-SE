---
keywords: Recommendations
description: Scenerna i det här avsnittet visar hur ändringar som gjorts på sidan påverkar Adobe Target förmåga att visa en upplevelse.
title: Scenarier för sidändring
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---


# Scenarier för sidändring

Scenerna i det här avsnittet visar hur ändringar som gjorts på sidan påverkar Adobe Target förmåga att visa en upplevelse.

Målväljaren avgör var en upplevelse ska visas. Om en sida ändras utanför Target kan ändringarna påverka möjligheten att visa upplevelsen i Target.

När du använder väljaren motsvarar den unika klassen inte ID:t. Väljaren fungerar alltid med en unik klass. Om elementet inte har tilldelats någon klass beräknar väljaren antalet tidigare likställda objekt som har samma taggnamn.

>[!NOTE]
>
>Även om dessa scenarier använder listobjekt som exempel, gäller koncepten för alla element.

## Scenario: Infoga ett element med ett annat klassnamn före det markerade elementet {#section_298F661F72384F6AB957D5885A99D822}

I det här exemplet infogas ett nytt element på samma nivå som elementet i målväljaren.

Det är möjligt att den första klassen i elementet kan läggas till av JavaScript. I så fall misslyckas leveransen och åtgärden tillämpas inte.

**Infogat element:**

```html
<li class="kids-section">Kids</li>
```

**Markerat:**

`<li class="women-section">Women</li>`

Väljare: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultat:**

Väljaren fungerar som förväntat eftersom `li.women-section:eq(0)` inte påverkas.

Före:

```html
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul> 
</div>
```

Efter:

```html
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

## Scenario: Infoga ett element med samma klassnamn som det markerade elementet {#section_0969B88C2F154E648D9969C8C85EF55A}

I det här scenariot görs ett försök att infoga en lista när ett objekt i en lista är markerat.

**Infogat element:**

```html
<ul class="nav"> 
   <li class="item"> Sale </li> 
   <li> class="item"> Offers </li> 
</ul>
```

**Markerad**

`<li class="women-section">Women</li>`

Väljare: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultat:**

Väljaren fungerar inte eftersom `ul.nav:eq(0)` innehåller ett dynamiskt tillagt element. Elementet blir inte tillgängligt och åtgärden används inte. När ett liknande listobjekt med samma klass läggs till dynamiskt eller manuellt efter att en aktivitet har skapats, skapas ett nytt element på den första positionen. Detta bryter väljaren.

Före:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

Efter (försök):

```html
<div id="wrap">
     <ul class="nav">
        <li class="item"> Sale</li>
        <li> class="item"> Offers</li>
     </ul>
     <ul class="nav">
       <li class="men-section"> Men</li>
       <li class="women-section">Women</li>
    </ul>
</div>
```

## Scenario: Infoga ett element efter det markerade elementet {#section_15B07B84BEE94ED39D85BBBE0733E170}

I det här scenariot infogas ett listobjekt efter det markerade elementet.

**Infogat element:**

```html
<ul class="nav"> 
   <li class="men-section"> Men Clothes</li> 
   <li class="women-section"> Women Clothes</li> 
</ul>
```

**Markerat:**

`<li class="women-section">Women Shoes</li>`

Väljare: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultat:**

I det här fallet fungerar infogning av en lista efter listslutet med det markerade listobjektet som förväntat. Det nya elementet läggs till på samma plats som det markerade elementet i förhållande till det överordnade elementet.

Före:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>       <li class="women">Women Shoes</li>
    </ul>
</div>
```

Efter:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>
        <li class="women">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## Scenario: Ta bort elementet direkt före ett annat element {#section_F193674F04F84AA593EAA1137C880EBA}

I det här scenariot tas listobjektet före det valda elementet bort.

**Borttaget element:**

```html
<li class="men-section"> Men </li>
```

**Markerat:**

`<li class="women-section">Women</li>`

Väljare: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultat:**

Elementet har tagits bort eftersom det markerade objektets klass inte har ändrats.

Före:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

Efter:

```html
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Scenario: Ta bort elementet omedelbart efter ett annat element {#section_F83B51BE54924FB58679D512DAF1EBB2}

I det här scenariot tas listobjektet efter det valda elementet bort.

**Borttaget element:**

```html
<li class="kids-section">Kids</li>
```

**Markerat:**

`<li class="women-section">Women</li>`

Väljare: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultat:**

Elementet har tagits bort eftersom det markerade objektets klass inte har ändrats. Det borttagna elementet innehåller en unik klass i det överordnade underträdet.

Före:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Women</li>
    </ul>
</div>
```

Efter:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Scenario: Ta bort det markerade elementet {#section_1989CF1E2C344CC5963084ED83C18F9C}

I det här scenariot tas det markerade listobjektet bort.

**Borttaget element:**

```html
<li class="women-shoes">Women</li>
```

**Markerat:**

`<li class="women-shoes">Women</li>`

Väljare: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultat:**

Elementet har tagits bort.

Före:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```

Efter

```html
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## Scenario: Byt namn på klassen för det markerade elementet {#section_79D244C588BA452DB8E433D82B7F63EA}

I det här scenariot ändras klassen för det markerade listobjektet.

**Ändrat element:**

```html
<li class="women-section">Women</li>
```

**Markerat:**

`<li class="women-section">Women</li>`

Väljare: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultat:**

Det går inte att byta namn på elementklassen eftersom det inte gick att hitta `class`.

Före:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

Efter (försök):

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```
