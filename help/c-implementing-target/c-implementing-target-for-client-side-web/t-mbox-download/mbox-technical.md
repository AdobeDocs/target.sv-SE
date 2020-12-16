---
keywords: implementation;mbox.js;dom manipulation library;target.js;visual experience composer;iframe;angular sites;single page applications;single page app;SPA
description: Information som hjälper din tekniska personal att förstå mbox.js-implementeringen och hur den kan påverka din webbplats.
title: Vad mbox.js gör
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---


# Vad mbox.js gör{#what-mbox-js-does}

Information som hjälper din tekniska personal att förstå mbox.js-implementeringen och hur den kan påverka din webbplats.

Målstandard kräver [!DNL mbox.js] version 58 eller senare. Instruktioner om hur du hämtar och uppdaterar [!DNL mbox.js] finns i [Mbox Implementation](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).

För Target Standard anropar [!DNL mbox.js] en annan JavaScript-fil, [!DNL target.js]. [!DNL Target.js] ligger hos Adobe och uppdateras automatiskt av Adobe. Du behöver inte uppdatera [!DNL target.js] och det finns inga klientspecifika anpassningar.

[!DNL Target.js] skapar en mbox som anropas  `target-global-mbox` i  `<head>` sidans avsnitt.

[!DNL Target.js] anropas från  [!DNL mbox.js] en rad med JavaScript-kod som läggs till i  [!UICONTROL Extra JavaScript] fältet i  [!DNL mbox.js]. Det enda sättet att inaktivera [!DNL target.js] är att inte ta med den här kodraden, vilket innebär att även [!DNL Target] inaktiveras.

[!DNL Target.js] har två funktioner i  [!DNL Target]:

* DOM-manipulering
* Aktiverar visuella element för [!UICONTROL Visual Experience Composer]

## DOM-manipulering {#section_169F8D4C077948DCB4F891ABBB03FF63}

[!DNL Target.js] styr DOM-manipuleringsbiblioteket som används av Standard. Om du vill visa innehållet på en webbplats refererar [!DNL target.js] till [!DNL sizzle.js] (version1.10.8-pre). [!DNL Sizzle.js] aktiverar HTML-elementväljarna. Förutom [!DNL sizzle.js] används endast systemspecifikt JavaScript. Ingen jquery krävs.

Dessutom används följande utdrag för att avfråga DOM:
`https://github.com/dperini/ContentLoaded`

## Target.js och Visual Experience Composer {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

När du använder [!UICONTROL Visual Experience Composer] för att ställa in en upplevelse för en aktivitet öppnas webbsidan i en iFrame. När iFrame har lästs in skickar Standard ett HTML5 `postMessage` API-anrop. [!DNL Target.js] identifierar eventuella  `postMessage` anrop och inkluderar följande JavaScript-bibliotek på webbplatsen:

* För generering av miniatyrbilder: [!DNL https://html2canvas.hertzen.com/]
* För korsdomänfråga: [!DNL Admin.js], [!DNL CDQ.base.js], [!DNL CDQ.host.js], [!DNL admin.css] som används för att skicka meddelanden i iFrames. Dessa skript gör att Adobe kan skicka data mellan sidorna.

## Överväganden för vinkelwebbplatser och enkelsidiga program {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

Om du implementerar Target på en Angular-webbplats eller i ett Single-Page Application (SPA) bör du använda biblioteket at.js i stället för mbox.js.

Mer information finns i [at.js-implementering](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17).
