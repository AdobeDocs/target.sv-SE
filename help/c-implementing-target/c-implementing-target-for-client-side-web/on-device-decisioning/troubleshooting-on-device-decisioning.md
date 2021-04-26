---
keywords: implementering;javascript-bibliotek;js;atjs;on device decisioning;on device decisioning;at.js;on device;troubleshooting;trouble fotograing
description: Lär dig hur du felsöker enhetsbeslut med biblioteket at.js.
title: Hur felsöker jag Enhetsbeslut med JavaScript-biblioteket at.js?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: a73525a7c2096235d583f54865fcdcbc4b36e7c0
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Felsökning av On-device-beslut för at.js

Följ de här stegen för att felsöka enhetsbeslut i Adobe Target med JavaScript-biblioteket at.js:

1. Aktivera konsolloggen för at.js
1. Verifiera regelartefaktnedladdningen på fliken Nätverk i webbläsaren
1. Verifiera regelartefaktnedladdningen med anpassade at.js-händelser

I följande avsnitt beskrivs varje steg mer ingående:

## Steg 1: Aktivera konsolloggen för at.js

Genom att lägga till URL-parametern `mboxDebug=1` kan at.js skriva ut meddelanden i webbläsarens konsol.

Alla meddelanden innehåller prefixet&quot;AT:&quot; för praktisk översikt. För att säkerställa att en artefakt har lästs in bör konsolloggen innehålla meddelanden som liknar följande:

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

Följande bild visar dessa meddelanden i konsolloggen:

![Konsollogg med artefaktmeddelanden](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

## Steg 2: Verifiera regelartefaktnedladdningen på fliken Nätverk i webbläsaren

Öppna fliken Nätverk i webbläsaren.

Så här öppnar du till exempel DevTools i Google Chrome:

1. Tryck på Ctrl+Skift+J (Windows) eller Kommando+Alt+J (Mac).
1. Gå till fliken Nätverk.
1. Filtrera dina anrop med nyckelordet &quot;rules.json&quot; för att säkerställa att endast artefaktregelfilen visas.

   Dessutom kan du filtrera efter &quot;/delivery|rules.json/&quot; för att visa alla [!DNL Target] anrop och artefaktregler.json.

   ![Fliken Nätverk i Google Chrome](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

## Steg 3: Verifiera regelartefaktnedladdningen med anpassade at.js-händelser

At.js-biblioteket skickar två nya anpassade händelser som stöd för enhetsbeslut.

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

Du kan prenumerera för att lyssna på dessa anpassade händelser i ditt program för att agera när artefaktreglerna har hämtats eller inte.

I följande exempel visas ett exempel på kod som avlyssnar lyckade artefaktnedladdningar och felhändelser:

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
