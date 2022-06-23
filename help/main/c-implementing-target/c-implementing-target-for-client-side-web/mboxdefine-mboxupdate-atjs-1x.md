---
keywords: mboxDefine;mbox define;mbox define;mboxUpdate;mbox update;mbox update;at.js;functions;function
description: Använd funktionerna mboxDefine() och mboxUpdate() för Adobe [!DNL Target] at.js JavaScript-bibliotek för att definiera eller uppdatera en mbox. (at.js 1.x)
title: Hur använder jag funktionerna mboxDefine() och mboxUpdate()?
feature: at.js
role: Developer
exl-id: 48261be0-c4d0-4961-9712-ef7e0d2cb1c0
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# mboxDefine() och mboxUpdate() - at.js 1.x

Definiera och uppdatera en mbox i Adobe Target.

>[!NOTE]
>
>Dessa funktioner är tillgängliga för version 1 av at.js.*x* endast. De här funktionerna har tagits bort i och med versionen av at.js 2.x. Dessa funktioner returnerar standardinnehåll om de används med at.js 2.x.

`mboxDefine()` och `mboxCreate()` är knutna till HTML DIV-element där erbjudandet ska visas. Dessa HTML DIV-element bör ha `mboxDefault` klassen. Om den här klassen inte är kopplad till elementen i HTML kan du se en viss märkbar flimmer.

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

Skapar en intern mappning mellan ett nodeId och ett mbox-namn, men kör inte begäran. Används tillsammans med `mboxUpdate()`. Inbyggt i [!DNL at.js] mest för att underlätta övergången från [!DNL mbox.js] (nu borttagen) till [!DNL at.js].

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

Kör begäran och tillämpar erbjudandet på det element som identifieras av `nodeId` i `mboxDefine()`. Kan även användas för att uppdatera en mbox som initierats av `mboxCreate`. Inbyggt i [!DNL at.js] mest för att underlätta övergången från [!DNL mbox.js] (nu borttagen) till [!DNL at.js]. `mboxDefine()`/ `mboxUpdate()` kan ersättas med [adobe.target.getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/) och [adobe.target.applyOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffer/) med alternativet väljare.

## Exempel {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```javascript
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
