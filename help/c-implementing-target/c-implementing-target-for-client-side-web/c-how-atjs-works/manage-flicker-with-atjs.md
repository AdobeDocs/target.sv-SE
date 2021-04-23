---
keywords: flimmer;at.js;implementation;asynkront;asynkront;synkront;synkront
description: Lär dig hur at.js och Adobe [!DNL Target] förhindrar flimmer (standardinnehåll visas snabbt innan det ersätts av aktivitetsinnehåll) under sidinläsning eller appinläsning.
title: Hur hanterar At.js Flicker?
feature: at.js
role: Developer
exl-id: f6c26973-e046-42ed-91db-95c8a4210a9d
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 0%

---

# Hur at.js hanterar flimmer

Information om hur JavaScript-biblioteket Target at.js förhindrar flimmer vid inläsning av sidor eller appar.

Flimmer inträffar när standardinnehåll visas för besökare innan det ersätts av aktivitetsinnehållet. Flimmer är inte önskvärt eftersom det kan vara förvirrande för besökare.

## Använda en automatiskt skapad global mbox {#section_C502170D551C4F52AAFD8E82C41BB63A}

Om du aktiverar inställningen [Auto Create Global Mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/understanding-global-mbox.md#concept_76AC0EC995A048238F3220F53773DB13) när du konfigurerar at.js hanterar at.js flimmer genom att ändra opacitetsinställningen när sidan läses in. När at.js läses in ändras opacitetsinställningen för `<body>`-elementet till &quot;0&quot;, vilket gör sidan till att börja med osynlig för besökarna. När ett svar från Target har tagits emot, eller om ett fel med Target-begäran upptäcks, återställer at opacitet till&quot;1&quot;. Detta garanterar att besökaren bara ser sidan när innehållet i dina aktiviteter har tillämpats.

Om du aktiverar inställningen när du konfigurerar at.js kommer at.js att ange HTML BODY-formatopaciteten till 0. När ett svar från Target har tagits emot återställer at.js opaciteten för HTML BODY till 1.

Med Opacitet 0 döljs sidinnehållet för att förhindra flimmer, men webbläsaren återger sidan och läser in alla nödvändiga resurser som CSS, bilder osv.

Om opacitet 0 inte fungerar i implementeringen kan du även hantera flimmer genom att anpassa `bodyHiddenStyle` och ställa in den på `body {visibility:hidden !important}`. Du kan använda antingen värdetexten `{opacity:0 !important}` eller `body {visibility:hidden !important}`, beroende på vilket som fungerar bäst för den aktuella situationen.

Följande bild visar anropet Dölj brödtext och Visa brödtext i båda at.js 1.** xand at.js 2.x.

**at.js 2.x**

![Målflöde: at.js page load request](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-flow-page-load-request.png)

**at.js 1.*x***

![](assets/target-flow2.png)

Mer information om åsidosättningen av `bodyHiddenStyle` finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Hantera flimmer vid inläsning av at.js asynkront

Att läsa in at.js asynkront är ett bra sätt att undvika att blockera webbläsaren från återgivning. Den här tekniken kan dock leda till att webbsidan flimrar.

Du kan undvika flimmer genom att använda ett fragment som är synligt i förväg när de relevanta HTML-elementen har anpassats av [!DNL Target].

at.js kan läsas in asynkront, antingen direkt inbäddat på sidan eller via en tagghanterare (Adobe Launch, Dynamic Tag Manager (DTM) osv.).

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

Som standard döljs hela HTML-BODY av fragmentet. I vissa fall kanske du bara vill dölja vissa HTML-element i förväg och inte hela sidan. Du kan uppnå det genom att anpassa style-parametern. Den kan ersättas med något som bara döljer vissa delar av sidan.

Du har till exempel två områden som identifieras av ID:n container-1 och container-2, och sedan kan formatet ersättas med följande:

```
#container-1, #container-2 {opacity: 0 !important}
```

I stället för standardinställningen:

```
body {opacity: 0 !important}
```

## Hantera flimmer i at.js 2.x för triggerView()

När du använder `triggerView()` för att visa riktat innehåll i SPA, tillhandahålls flimmerhantering direkt. Det innebär att fördold logik inte behöver läggas till manuellt. I stället döljer at.js 2.x platsen där din vy måste visas innan målinnehållet används.

## Hantera flimmer med getOffer() och applyOffer()

Eftersom både `getOffer()` och `applyOffer()` är API:er på låg nivå finns det ingen inbyggd flimmerkontroll. Du kan skicka en väljare eller ett HTML-element som ett alternativ till `applyOffer()`. I det här fallet lägger `applyOffer()` till aktivitetsinnehållet i det här specifika elementet. Du måste dock se till att elementet är korrekt fördolt innan du anropar `getOffer()` och `applyOffer()`.

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
