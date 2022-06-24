---
keywords: implementera;implementera;konfigurera;dataleverantörer
description: Hämta data till [!DNL Target] med dataleverantörer.
title: Hur får jag in data på [!DNL Target] Använda Data Providers?
feature: Implementation
role: Developer
exl-id: 05fe9190-4d36-43e2-9fc7-c354a6821bfb
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# Dataleverantörer

Dataleverantörer är en funktion som gör att du enkelt kan skicka data från tredje part till [!DNL Adobe Target].

Obs! Dataleverantörer kräver at.js 1.3 eller senare.

## Format

The `window.targetGlobalSettings.dataProviders` -inställningen är en matris med dataleverantörer.

Mer information om strukturen för varje DataProvider finns i [Dataleverantörer](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}.

## Exempel på användningsområden

Samla in data från tredje part, t.ex. en vädertjänst, en datahanteringsplattform eller till och med din egen webbtjänst. Sedan kan ni använda dessa data för att skapa målgrupper, målinnehåll och berika besökarprofilen.

## Fördelar med metoden

Med den här inställningen kan kunder samla in data från tredjepartsleverantörer av data, som Demandbase, BlueKai och anpassade tjänster, och skicka data till Target som mbox-parametrar i den globala mbox-begäran.

Det stöder insamling av data från flera leverantörer via asynkrona och synkroniserade begäranden.

Med den här metoden blir det enkelt att hantera flimmer av standardsidinnehåll, samtidigt som oberoende tidsgränser för varje leverantör tas med för att begränsa effekten på sidans prestanda

## Caveats

Om dataleverantörerna har lagts till i `window.targetGlobalSettings.dataProviders` är asynkrona, utförs de parallellt. Besökar-API-begäran körs parallellt med funktioner som lagts till i `window.targetGlobalSettings.dataProviders` för att tillåta en minimal väntetid.

at.js försöker inte cachelagra data. Om dataleverantören bara hämtar data en gång, bör dataleverantören se till att data cachelagras och, när providerfunktionen anropas, hantera cachedata för det andra anropet.

## Exempel på koder

Flera exempel finns i [Dataleverantörer](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}.

## Länkar till relevant information

Dokumentation: [Dataleverantörer](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/)

## Utbildningsvideor:

* [Använda Data Providers i Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Implementera Data Providers i Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html)
