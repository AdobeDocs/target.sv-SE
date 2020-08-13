---
keywords: mboxCreate;mboxcreate;mbox create;at.js;functions;function
description: Information om funktionen mboxCreate(mbox,params) för JavaScript-biblioteket för Adobe Target at.js.
title: Information om funktionen mboxCreate(mbox,params) för JavaScript-biblioteket för Adobe Target at.js.
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 0%

---


# mboxCreate(mbox,params) - at.js 1.x {#reference_E68805FE86C64792B2066DB17B253D74}

Kör en begäran och tillämpar erbjudandet på närmaste DIV med mboxDefault-klassnamn.

>[!NOTE]
>
>Den här funktionen är tillgänglig för version 1 av at.js.*Endast x* . Den här funktionen har ersatts med versionen av at.js 2.x. Den här funktionen returnerar standardinnehåll om den används med at.js 2.x.

Den här funktionen är i [!DNL at.js] huvudsak inbyggd för att underlätta övergången från [!DNL mbox.js] till [!DNL at.js]. Ett nyare alternativ till `mboxCreate()` är `adobe.target.getOffer()`/ `adobe.target.applyOffer()` eller vinkeldirektivet.

## Exempel

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## Anteckningar

`mboxCreate()` använder nu slutpunkten &quot;json&quot; i stället för standardslutpunkten och aktiveras asynkront. På grund av detta:

* [Felsökning](../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) är lite annorlunda.
* Undvik erbjudandekod som kräver synkrona, blockerande anrop.

   I erbjudanden anges till exempel JavaScript-variabler som används av platskod eller andra rutor som kommer senare på sidan.

* Se till att du har en `<div class="mboxDefault"></div>`innan du anropar `mboxCreate()`eftersom ingen [!DNL at.js] läggs till åt dig.

* Tomma funktioner på översta sidan `mboxCreate()` rekommenderas inte som en global mbox.

   Den automatiskt skapade globala mbox i [!DNL at.js] är ett bättre alternativ eftersom den aktiveras från `<head>` och kan returnera innehåll tidigare.