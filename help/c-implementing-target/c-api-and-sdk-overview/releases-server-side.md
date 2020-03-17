---
keywords: at.js;api;release;updates;apis;sdks;server side;serverside;server-side;api;delivery api
description: Versionsinformation om Adobe Target-serversidans API:er.
title: Versionsinformation om Adobe Target-serversidans API:er.
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Versionsinformation - Målserversidans API:er

Versionsinformation om [Adobe Target-API:erna](https://developers.adobetarget.com/api/delivery-api/)på serversidan.

## V1/leverans (9 oktober 2019)

En helt ny leverans-API-slutpunkt har släppts.

* Det finns ny [dokumentation](https://developers.adobetarget.com/api/delivery-api/) .
* En slutpunkt för att hämta upplevelser för en eller flera kryssrutor.
* Hämta VEC-skapade aktiviteter via API:t.

   Svaret som innehåller VEC-skapade aktiviteter har väljare som kan användas för att i förväg dölja endast delar av sidan som behöver vara personaliserade. Detta bidrar till att optimera sidans [första innehållsangivelse](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html), som är en viktig nyckeltal för att ditt företag ska få en hög poäng i [Google PageRank](https://en.wikipedia.org/wiki/PageRank) -systemet.

* Stöd för ett helt nytt objekt, Vyer, som används för [SPA](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md) (Single Page Applications) och [mobilprogram](/help/c-target-mobile-app/target-mobile-app.md).
* Stöd för förhämtning av vyer och rutor för optimering av prestanda via cachning.
* Stöd för att skicka meddelanden för förhämtade vyer och rutor.

>[!IMPORTANT]
>
>Det går fortfarande att komma åt den äldre API-dokumentationen [/v1/mbox och /v2/batchmbox](https://developers.adobetarget.com/api/legacy-api/index.html) . Nya funktioner kommer dock att utvecklas i det nya leverans-API:t och kommer inte att vara bakåtporterade till de äldre API:erna.
