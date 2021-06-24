---
keywords: implementering;mbox.js;domarhanteringsbibliotek;target.js;visual experience comser;iframe;angular sites;single page applications;single page app;SPA
description: Läs om den gamla implementeringen av mbox.js i Adobe Target. Migrera till Adobe Experience Platform Web SDK (AEP Web SDK) eller till den senaste versionen av at.js.
title: Vad gör biblioteket [!DNL Target] mbox.js?
feature: at.js
role: Developer
exl-id: 62f0cbd2-17f0-43f4-98d3-ea39f314525e
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# Vad mbox.js gör

Information som hjälper din tekniska personal att förstå mbox.js-implementeringen och hur den kan påverka din webbplats.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## DOM-manipulering {#section_169F8D4C077948DCB4F891ABBB03FF63}

[!DNL Target.js] styr DOM-manipuleringsbiblioteket som används av Standard. Om du vill visa innehållet på en webbplats refererar [!DNL target.js] till [!DNL sizzle.js] (version1.10.8-pre). [!DNL Sizzle.js] aktiverar HTML-elementväljarna. Förutom [!DNL sizzle.js] används endast systemspecifikt JavaScript. Ingen jquery krävs.

Dessutom används följande utdrag för att avfråga DOM:
`https://github.com/dperini/ContentLoaded`

## Target.js och Visual Experience Composer {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

När du använder [!UICONTROL Visual Experience Composer] för att ställa in en upplevelse för en aktivitet öppnas webbsidan i en iFrame. När iFrame har lästs in skickar Standard ett HTML5 `postMessage` API-anrop. [!DNL Target.js] identifierar eventuella  `postMessage` anrop och inkluderar följande JavaScript-bibliotek på webbplatsen:

* För generering av miniatyrbilder: [!DNL https://html2canvas.hertzen.com/]
* För korsdomänfråga: [!DNL Admin.js], [!DNL CDQ.base.js], [!DNL CDQ.host.js], [!DNL admin.css] som används för att skicka meddelanden i iFrames. Dessa skript gör att Adobe kan skicka data mellan sidorna.

## Att tänka på vid Angular Sites och Single-page Applications {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

Om du implementerar Target på en Angular-plats eller i ett ensidigt program (SPA) bör du använda biblioteket at.js i stället för mbox.js.
