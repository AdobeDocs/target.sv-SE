---
keywords: implementera;implementera;konfigurera;dataleverantörer
description: Hämta data till Target med hjälp av dataleverantörer.
title: Hur får jag in data i Target med Data Providers?
feature: Implementering
role: Developer
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# Dataleverantörer

Dataleverantörer är en funktion som gör att du enkelt kan skicka data från tredje part till [!DNL Adobe Target].

Obs! Dataleverantörer kräver at.js 1.3 eller senare.

## Format

Inställningen `window.targetGlobalSettings.dataProviders` är en matris med dataleverantörer.

Mer information om strukturen för varje dataleverantör finns i [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

## Exempel på användningsområden

Samla in data från tredje part, t.ex. en vädertjänst, en datahanteringsplattform eller till och med din egen webbtjänst. Sedan kan ni använda dessa data för att skapa målgrupper, målinnehåll och berika besökarprofilen.

## Fördelar med metoden

Med den här inställningen kan kunder samla in data från tredjepartsleverantörer av data, som Demandbase, BlueKai och anpassade tjänster, och skicka data till Target som mbox-parametrar i den globala mbox-begäran.

Det stöder insamling av data från flera leverantörer via asynkrona och synkroniserade begäranden.

Med den här metoden blir det enkelt att hantera flimmer av standardsidinnehåll, samtidigt som oberoende tidsgränser för varje leverantör tas med för att begränsa effekten på sidans prestanda

## Caveats

Om dataleverantörerna som läggs till i `window.targetGlobalSettings.dataProviders` är asynkrona körs de parallellt. Visitor-API-begäran körs parallellt med funktioner som lagts till i `window.targetGlobalSettings.dataProviders` för att ge en minimal väntetid.

at.js försöker inte cachelagra data. Om dataleverantören bara hämtar data en gång, bör dataleverantören se till att data cachelagras och, när providerfunktionen anropas, hantera cachedata för det andra anropet.

## Exempel på koder

Flera exempel finns i [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

## Länkar till relevant information

Dokumentation: [Dataleverantörer](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

## Utbildningsvideor:

* [Använda Data Providers i Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Implementera Data Providers i Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html)