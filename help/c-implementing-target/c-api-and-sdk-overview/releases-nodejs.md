---
keywords: at.js;sdk;node.js;release;updates;sdks;server side;serverside;server-side;nodejs
description: Versionsinformation om Adobe Target serversides-API:er.
title: Versionsinformation om Adobe Target Node.js SDK.
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 0%

---


# Versionsinformation - Target Node.js SDK

Versionsinformation om [Adobe Target Node.js SDK](https://github.com/adobe/target-nodejs-sdk).

Med Target Node.js SDK kan du distribuera [!DNL Target] på serversidan.

Denna Node.js SDK hjälper dig att enkelt integrera [!DNL Target] med andra [!DNL Adobe Experience Cloud] lösningar, som [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]och [!DNL Adobe Audience Manager].

Node.js SDK introducerar bästa praxis och eliminerar komplexitet när de integreras med [!DNL Target] via vårt API, så att era tekniker kan fokusera på affärslogik.

Läs mer om Target Node.js SDK i Adobe Tech Blog - [Öppna Sourcing the New Adobe Target Node.js SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc).

## Version 1.0.0 (9 oktober 2019)

I följande avsnitt finns mer information om version 1.0.0 av Target Node.js SDK:

### Tillagd

* Stöd för Target View Delivery v1 API, inklusive Page Load och View prefetch.
* Fullt stöd för alla typer av erbjudanden som skapats i Visual Experience Composer (VEC).
* Stöd för förhämtning och meddelanden om prestandaoptimering genom cachelagring av förhämtat innehåll.
* Stöd för optimering av prestanda i hybrida [!DNL Target] integreringar via `serverState` när [!DNL Target] driftsätts både på serversidan och på klientsidan.

   Vi introducerar en inställning som kallas `serverState` som innehåller upplevelser som hämtats via servern, så att at.js v2.2+ inte gör ytterligare ett serveranrop för att hämta upplevelserna. Med den här metoden optimeras sidans laddningsprestanda.

* Open sourced on GitHub as [Target Node.js SDK](https://github.com/adobe/target-nodejs-sdk).
* Ny [sendNotifications()-API-metod](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) för att skicka visade/klickade meddelanden till [!DNL Target] för innehåll som är förhämtat via [getOffers()](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers).
* Förenklad vy för att skapa API-förfrågningar, med automatisk ifyllning av interna fält med standardvärden (t.ex. `request.id``request.context`).
* Validering av SDK API-metodargument.
* Uppdaterade README-, samplings- och enhetstester.
* Nytt CI-flöde har konfigurerats med GitHub-åtgärder.
* Lagt till mallar för medarbetare, riktlinjer för bidrag, PR och utgivning

### Ändrad

* Projektet har bytt namn till `target-nodejs-sdk`.
* Större omfaktorisering, som ersätter Target BatchMbox v2 API med Target View Delivery v1 API.
* [create() API-metodargument](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) har ändrats, vilket tar bort redundant kapsling (se gammal metoddeklaration [här](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate)).
* [API-metodargumenten](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) getOffers() har ändrats (se gammal metoddeklaration [här](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers)).
* API- `getTargetCookieName()` metoden har ersatts med en `TargetCookieName` åtkomstmetod. Se [Hjälpmedel](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)för TargetClient-verktyget.
* API- `getTargetLocationHintCookieName()` metoden har ersatts med en `TargetLocationHintCookieName` åtkomstmetod.  Se [Hjälpmedel](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors)för TargetClient-verktyget.

### Borttagen

* Stöd för Target BatchMbox v2 API.
* API-metoden [](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) getOffer() har tagits bort. Använd i stället API-metoden [](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) getOffers().

