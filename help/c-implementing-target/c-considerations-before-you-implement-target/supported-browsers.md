---
keywords: Browsers;Prerequisites;Requirements;internet explorer;chrome;firefox;safari;android;surface
description: Adobe Target program- och innehållsleverans har testats i en rad olika webbläsare och enheter.
title: Webbläsare som stöds
feature: reference general
subtopic: Getting Started
topic: Standard
uuid: 614088da-412c-45e3-9f2d-6985391973be
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---


# Webbläsare som stöds{#supported-browsers}

Programmet och [!DNL Adobe Target] innehållet har testats i en rad olika webbläsare och enheter.

Mer information om TLS finns i Krypteringsändringar för [TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

## [!DNL Target] Standard-/Premium-gränssnitt {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

Gränssnittet har stöd [!DNL Target] för följande webbläsare och enheter:

| Enhetstyp | Webbläsarversion |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome (senaste, senaste minus 1)</li><li>Mozilla Firefox (senaste, senaste minus 1)</li></ul> |
| Mac | <ul><li>Firefox (senaste, senaste minus 1)</li><li>Krom (senaste, senaste minus 1)</li></ul> |

## Innehållsleverans {#section_1045A946056441268D40025529918D3D}

Materialet har testats i följande webbläsare och enheter:

| Enhetstyp | Webbläsarversion |
|--- |--- |
| Windows | <ul><li>Internet Explorer 9 och 10. Testad i emuleringsläge.<br>**Obs**: at.js 1.3.0 (och senare) stöder inte längre innehållsleverans i Microsoft Internet Explorer 9.</li><li>Internet Explorer 11</li><li>Microsoft Edge</li><li>Krom (senaste, senaste minus 1)</li><li>Firefox (senaste, senaste minus 1)</li></ul> |
| Mac | <ul><li>Apple Safari (Latest)<br>**Note**: Mer information om hur Safari hanterar cookies från första och tredje part finns i [Målcookies](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md).</li><li>Firefox (senaste, senaste minus 1)</li><li>Krom (senaste, senaste minus 1)</li></ul> |
| Mobil/surfplatta | <ul><li>Apple iOS (senaste)</li><li>Android-enheter och -surfplattor (Android 4 och senare)</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

Observera följande:

* För [!DNL at.js] implementeringar [!DNL Target] visas standardinnehåll i tidigare versioner av Internet Explorer och eventuellt i tidigare versioner av webbläsarna ovan. För [!DNL mbox.js] implementeringar [!DNL Target] försöker återge innehåll, men det kanske inte lyckas.
* I Internet Explorer behandlas alla okända element (t.ex. anpassade element) som samma elementtyp. Leveransen fungerar därför inte med anpassade element.
* [!DNL Target] visar standardinnehåll i webbläsare som inte listas ovan och i webbläsare som använder [läget](https://en.wikipedia.org/wiki/Quirks_mode)quirks. at.js kräver en doctype som återges i standardläge, till exempel: `<!DOCTYPE html>` .
* Adobe Delivery Infrastructure skyddas för att INTE stödja TLS 1.0-enheter och -webbläsare efter den 12 september 2018. Se Krypteringsändringar [för](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) TLS (Transport Layer Security) för att förstå den övergripande effekten av den här ändringen.
