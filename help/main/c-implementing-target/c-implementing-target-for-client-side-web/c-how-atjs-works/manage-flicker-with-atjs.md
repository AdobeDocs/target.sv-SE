---
keywords: flimmer;at.js;implementation;asynkront;asynkront;synkront;synkront
description: Se hur at.js och Adobe [!DNL Target] förhindra flimmer (standardinnehåll visas tillfälligt innan det ersätts av aktivitetsinnehåll) under sidinläsning eller appinläsning.
title: Hur hanterar At.js Flicker?
feature: at.js
role: Developer
exl-id: f6c26973-e046-42ed-91db-95c8a4210a9d
source-git-commit: a62a0a3a4dd08ce93daff68a50613ad58af6de58
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Hur at.js hanterar flimmer

Information om hur JavaScript-biblioteket Target at.js förhindrar flimmer vid inläsning av sidor eller appar.

Flimmer inträffar när standardinnehåll visas för besökare innan det ersätts av aktivitetsinnehållet. Flimmer är inte önskvärt eftersom det kan vara förvirrande för besökare.

## Använda en automatiskt skapad global mbox {#section_C502170D551C4F52AAFD8E82C41BB63A}

Om du aktiverar [Skapa global Mbox automatiskt](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/understanding-global-mbox.md#concept_76AC0EC995A048238F3220F53773DB13) Vid konfigurering av at.js hanterar at.js flimmer genom att ändra opacitetsinställningen när sidan läses in. När at.js läses in ändras opacitetsinställningen för `<body>` -element till&quot;0&quot;, vilket gör sidan osynlig för besökare. När ett svar från Target har tagits emot, eller om ett fel med Target-begäran upptäcks, återställer at opacitet till&quot;1&quot;. Detta garanterar att besökaren bara ser sidan efter att innehållet i dina aktiviteter har tillämpats.

Om du aktiverar inställningen när du konfigurerar at.js anger at.js opaciteten för HTML BODY-formatet till 0. När ett svar från Target har tagits emot, återställer at.js opaciteten för HTML BODY till 1.

Med Opacitet 0 döljs sidinnehållet för att förhindra flimmer, men webbläsaren återger sidan och läser in alla nödvändiga resurser som CSS, bilder osv.

Om opacitet 0 inte fungerar i implementeringen kan du även hantera flimmer genom att anpassa `bodyHiddenStyle` och ange `body {visibility:hidden !important}`. Du kan använda båda typerna av värdebrödtext `{opacity:0 !important}` eller `body {visibility:hidden !important}`, det som fungerar bäst för just din situation.

Följande bild visar anropet Dölj brödtext och Visa brödtext i båda at.js 1.*x* och at.js 2.x.

**at.js 2.x**

![Målflöde: at.js page load request](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-flow-page-load-request.png)

**at.js 1.*x***

![](assets/target-flow2.png)

Mer information om `bodyHiddenStyle` åsidosätta, se [targetGlobalSettings()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Hantera flimmer vid inläsning av at.js asynkront

Att läsa in at.js asynkront är ett bra sätt att undvika att blockera webbläsaren från återgivning. Den här tekniken kan dock leda till att webbsidan flimrar.

Du kan undvika flimmer genom att använda ett fragment som är synligt i förväg när de relevanta HTML-elementen har anpassats av [!DNL Target].

at.js kan läsas in asynkront, antingen direkt inbäddad på sidan eller via en tagghanterare (till exempel [!DNL Adobe Experience Platform Launch]).

Om at.js är inbäddad på sidan måste fragmentet läggas till innan at.js läses in. Om du läser in at.js via en tagghanterare, som också läses in asynkront, måste du lägga till fragmentet innan du läser in tagghanteraren. Om tagghanteraren läses in synkront kan skriptet inkluderas i tagghanteraren före at.js.

Så här döljer du kodfragment:

```
;(function(win, doc, style, timeout) {
  var STYLE_ID = 'at-body-style';

  function getParent() {
    return doc.getElementsByTagName('head')[0];
  }

  function addStyle(parent, id, def) {
    if (!parent) {
      return;
    }

    var style = doc.createElement('style');
    style.id = id;
    style.innerHTML = def;
    parent.appendChild(style);
  }

  function removeStyle(parent, id) {
    if (!parent) {
      return;
    }

    var style = doc.getElementById(id);

    if (!style) {
      return;
    }

    parent.removeChild(style);
  }

  addStyle(getParent(), STYLE_ID, style);
  setTimeout(function() {
    removeStyle(getParent(), STYLE_ID);
  }, timeout);
}(window, document, "body {opacity: 0 !important}", 3000));
```

Som standard döljs hela HTML BODY med fragmentet. I vissa fall kanske du bara vill dölja vissa element i HTML i förväg och inte hela sidan. Du kan uppnå det genom att anpassa style-parametern. Den kan ersättas med något som bara döljer vissa delar av sidan.

Du har till exempel två områden som identifieras av ID:n container-1 och container-2, och sedan kan formatet ersättas med följande:

```
#container-1, #container-2 {opacity: 0 !important}
```

I stället för standardinställningen:

```
body {opacity: 0 !important}
```

## Hantera flimmer i at.js 2.x för triggerView()

När du använder `triggerView()` Om du vill visa riktat innehåll i SPA får du hjälp direkt. Det innebär att fördold logik inte behöver läggas till manuellt. I stället döljer at.js 2.x platsen där din vy måste visas innan målinnehållet används.

## Hantera flimmer med getOffer() och applyOffer()

Eftersom båda `getOffer()` och `applyOffer()` är lågnivå-API:er, det finns ingen inbyggd flimmerkontroll. Du kan skicka en väljare eller ett HTML-element som ett alternativ till `applyOffer()`, i detta fall `applyOffer()` lägger till aktivitetsinnehållet i detta särskilda element, Du måste dock se till att elementet är fördolt innan du anropar det `getOffer()` och `applyOffer()`.

```
document.documentElement.style.opacity = "0";
 
adobe.target.getOffer({
    mbox: 'target-global-mbox',
    success: function(offer) {
        adobe.target.applyOffer({
            mbox: 'target-global-mbox',
            offer: offer
        });
 
        document.documentElement.style.opacity = "1";
    },
    error: function() {
        document.documentElement.style.opacity = "1";        
    }
});
```

## Använda en regional mbox med mboxCreate() i at.js 1.x (stöds inte i at.js 2.x)

Om du använder en regional mbox-implementering kan du använda `mboxCreate()` med din sida etablerad som liknar följande exempelkod:

```
<div class="mboxDefault">
Some default content
</div>
<script>
mboxCreate('some-mbox');
</script>
```

Om sidorna är korrekt konfigurerade hanterar at.js flimmer genom att ändra CSS-egenskapen &quot;visibility&quot; för elementet med klassen mboxDefault.
