---
keywords: flicker;at.js;implementation;asynchronously;asynchronous;synchronously;synchronous
description: Information om hur JavaScript-biblioteket Adobe Target at.js förhindrar flimmer vid inläsning av sidor eller appar.
title: Hur Adobe Target at.js hanterar flimmer
feature: client-side
topic: Standard
uuid: 65f67c4a-a931-4e0d-80d9-29ab67b62573
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 0%

---


# Hur at.js hanterar flimmer{#how-at-js-manages-flicker}

Information om hur JavaScript-biblioteket Target at.js förhindrar flimmer vid inläsning av sidor eller appar.

Flimmer inträffar när standardinnehåll visas för besökare innan det ersätts av aktivitetsinnehållet. Flimmer är inte önskvärt eftersom det kan vara förvirrande för besökare.

## Använda en automatiskt skapad global mbox {#section_C502170D551C4F52AAFD8E82C41BB63A}

Om du aktiverar inställningen [Skapa global Mbox](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/understanding-global-mbox.md#concept_76AC0EC995A048238F3220F53773DB13) automatiskt när du konfigurerar at.js hanterar at.js flimmer genom att ändra opacitetsinställningen när sidan läses in. När at.js läses in ändras opacitetsinställningen för <body> -element till&quot;0&quot;, vilket gör sidan osynlig för besökare. När ett svar från Target har tagits emot, eller om ett fel med Target-begäran upptäcks, återställer at opacitet till&quot;1&quot;. Detta garanterar att besökaren bara ser sidan efter att innehållet i dina aktiviteter har tillämpats.

Om du aktiverar inställningen när du konfigurerar at.js kommer at.js att ange HTML BODY-formatopaciteten till 0. När ett svar från Target har tagits emot återställer at.js opaciteten för HTML BODY till 1.

Med Opacitet 0 döljs sidinnehållet för att förhindra flimmer, men webbläsaren återger sidan och läser in alla nödvändiga resurser som CSS, bilder osv.

Om opacitet 0 inte fungerar i implementeringen kan du även hantera flimmer genom att anpassa `bodyHiddenStyle` och ställa in den på `body {visibility:hidden !important}`. Du kan använda antingen värdebrödtext `{opacity:0 !important`} eller `body {visibility:hidden !important}`den som passar bäst för dina specifika omständigheter.

Följande bild visar anropet Dölj brödtext och Visa brödtext i båda at.js 1.*x* och at.js 2.x.

**at.js 2.x**

![Målflöde: at.js page load request](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-flow-page-load-request.png)

**at.js 1.*x***

![](assets/target-flow2.png)

Mer information om `bodyHiddenStyle` åsidosättningen finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Hantera flimmer vid inläsning av at.js asynkront

Att läsa in at.js asynkront är ett bra sätt att undvika att blockera webbläsaren från återgivning. Den här tekniken kan dock leda till att webbsidan flimrar.

Du kan undvika flimmer genom att använda ett fragment som är synligt i förväg när de relevanta HTML-elementen har anpassats efter [!DNL Target].

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

När du använder `triggerView()` för att visa riktat innehåll i ditt SPA-program ingår funktionen för hantering av flimmer. Det innebär att fördold logik inte behöver läggas till manuellt. I stället döljer at.js 2.x platsen där din vy måste visas innan målinnehållet används.

## Hantera flimmer med getOffer() och applyOffer()

Eftersom både `getOffer()` och `applyOffer()` lågnivå-API:er är det ingen inbyggd flimmerkontroll. Du kan skicka en väljare eller ett HTML-element som ett alternativ för att `applyOffer()`i det här fallet `applyOffer()` lägga till aktivitetsinnehållet i det här specifika elementet. Du måste dock se till att elementet är rätt fördolt innan du anropar `getOffer()` och `applyOffer()`.

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

Om du använder en regional mbox-implementering kan du använda `mboxCreate()` med din sida som är provisionerad på liknande sätt som följande exempelkod:

```
<div class="mboxDefault">
Some default content
</div>
<script>
mboxCreate('some-mbox');
</script>
```

Om sidorna är korrekt konfigurerade hanterar at.js flimmer genom att ändra CSS-egenskapen &quot;visibility&quot; för elementet med klassen mboxDefault.