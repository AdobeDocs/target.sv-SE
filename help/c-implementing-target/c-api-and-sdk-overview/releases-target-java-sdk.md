---
keywords: at.js;sdk;release;updates;sdks;server side;serverside;server-side;java;java sdk
description: Versionsinformation om Adobe Target Java SDK.
title: Versionsinformation om Adobe Target Java SDK.
topic: Standard
translation-type: tm+mt
source-git-commit: 6b49e4fb6c92da023678c1f27823458229d21711

---


# Versionsinformation - Mål-Java SDK

Versionsinformation om [Java SDK](https://github.com/adobe/target-java-sdk)för mål.

Med [!DNL Target] Java SDK kan du distribuera [!DNL Target] på serversidan. Denna Java SDK hjälper dig att enkelt integrera [!DNL Target] med andra [!DNL Adobe Experience Cloud] lösningar som [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]och [!DNL Adobe Audience Manager].

Java SDK introducerar bästa praxis och eliminerar komplexitet när det integreras med [!DNL Target] via vårt API så att era tekniker kan fokusera på affärslogik.

Läs mer om Target Java SDK i Adobe Tech Blog - Optimering på [serversidan med nya Target Java SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2).

## Version 1.1.0 (16 december 2019)

Följande avsnitt innehåller mer information om version 1.1.0 av Java SDK för mål:

### Tillagd

* Stöd för proxykonfiguration har lagts till på grund av ett öppen källkodsbidrag från @hisham-hassan.

## Version 1.0.1 (11 november 2019)

Följande avsnitt innehåller mer information om version 1.0.1 av Java SDK för mål:

### Fast

* Skicka ytterligare data-ID i en Target-begäran även när det inte finns någon Visitor API-cookie.

## Version 1.0.0 (31 oktober 2019)

I följande avsnitt finns mer information om version 1.0.0 av Java SDK för mål:

### Tillagd

* [Stöd för Target View Delivery v1 API](https://developers.adobetarget.com/api/delivery-api/) , inklusive Page Load och View prefetch.
   * Fullt stöd för alla typer av erbjudanden som skapats i Visual Experience Composer (VEC).
* Stöd för förhämtning och meddelanden som möjliggör prestandaoptimering genom cachelagring av förhämtat innehåll.
* Stöd för optimering av prestanda i hybrida [!DNL Target] integreringar `serverState`när [!DNL Target] driftsätts både på serversidan och på klientsidan.
   * Vi introducerar en inställning som kallas `serverState` som innehåller upplevelser som hämtats via servern, så att at.js v2.2+ inte gör ytterligare ett serveranrop för att hämta upplevelserna. Med den här metoden optimeras sidans laddningsprestanda.
* Öppna från GitHub som Java SDK för [mål](https://github.com/adobe/target-java-sdk).
* Validering av SDK API-metodargument.
* Lagt till README, exempel och enhetstester.
* Lagt till mallar för medarbetare, riktlinjer för bidrag, PR och utgivning.

