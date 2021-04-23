---
keywords: mboxDefine;mbox define;mbox define;mboxUpdate;mbox update;mbox update;at.js;functions;function
description: Använd funktionerna mboxDefine() och mboxUpdate() för JavaScript-biblioteket Adobe [!DNL Target] at.js för att definiera eller uppdatera en mbox. (at.js 1.x)
title: Hur använder jag funktionerna mboxDefine() och mboxUpdate()?
feature: at.js
role: Developer
exl-id: 48261be0-c4d0-4961-9712-ef7e0d2cb1c0
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# mboxDefine() och mboxUpdate() - at.js 1.x

Definiera och uppdatera en mbox i Adobe Target.

>[!NOTE]
>
>Dessa funktioner är tillgängliga för version 1 av at.js.*Endast* . De här funktionerna har tagits bort i och med versionen av at.js 2.x. Dessa funktioner returnerar standardinnehåll om de används med at.js 2.x.

`mboxDefine()` och  `mboxCreate()` är kopplade till HTML DIV-element där erbjudandet ska visas. Dessa HTML DIV-element ska ha klassen `mboxDefault`. Om den här klassen inte är kopplad till HTML-elementen kan du se en viss märkbar flimmer.

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

Skapar en intern mappning mellan ett nodeId och ett mbox-namn, men kör inte begäran. Används tillsammans med `mboxUpdate()`. Inbyggd i [!DNL at.js]för att underlätta övergången från [!DNL mbox.js]till [!DNL at.js].

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

Kör begäran och tillämpar erbjudandet på elementet som identifieras av `nodeId` i `mboxDefine()`. Kan även användas för att uppdatera en mbox som initierats av `mboxCreate`. Inbyggd i [!DNL at.js] för att underlätta övergången från [!DNL mbox.js] till [!DNL at.js]. `mboxDefine()`/  `mboxUpdate()` kan ersättas med  [adobe.target.getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) och  [adobe.target.applyOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) med alternativet selector.

## Exempel {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```javascript
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
