---
keywords: mboxCreate;mbox create;mbox create;at.js;functions;function
description: Använd funktionen mboxCreate() för JavaScript-biblioteket Adobe [!DNL Target] at.js om du vill tillämpa erbjudanden på närmaste DIV med mboxDefault-klassnamnet. (at.js 1.x)
title: Hur använder jag funktionen mboxCreate()?
feature: at.js
role: Developer
exl-id: 821ad97a-345a-4e56-9be6-ab1c7d3a651d
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# mboxCreate(mbox,params) - at.js 1.x

Kör en begäran och tillämpar erbjudandet på närmaste DIV med mboxDefault-klassnamn.

>[!NOTE]
>
>Den här funktionen är tillgänglig för version 1 av at.js.*Endast* . Den här funktionen har ersatts med versionen av at.js 2.x. Den här funktionen returnerar standardinnehåll om den används med at.js 2.x.

Den här funktionen är inbyggd i [!DNL at.js] för att underlätta övergången från [!DNL mbox.js] till [!DNL at.js]. Ett nyare alternativ till `mboxCreate()` är `adobe.target.getOffer()`/ `adobe.target.applyOffer()` eller Angular-direktivet.

## Exempel

```javascript
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## Anteckningar

`mboxCreate()` använder nu slutpunkten &quot;json&quot; i stället för standardslutpunkten och aktiveras asynkront. På grund av detta:

* [Felsökning ](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) är lite annorlunda.
* Undvik erbjudandekod som kräver synkrona, blockerande anrop.

   I erbjudanden anges till exempel JavaScript-variabler som används av platskod eller andra rutor som kommer senare på sidan.

* Se till att du har en `<div class="mboxDefault"></div>`innan du anropar `mboxCreate()` eftersom [!DNL at.js] inte lägger till en åt dig.

* Tomma `mboxCreate()`-funktioner på översta sidan rekommenderas inte som en global mbox.

   Den automatiskt skapade globala mbox i [!DNL at.js] är ett bättre alternativ eftersom den aktiveras från `<head>` och kan returnera innehåll tidigare.
