---
keywords: Browsers;Prerequisites;Requirements;internet explorer;chrome;firefox;safari;android;surface
description: Adobe Target program- och innehållsleverans har testats i en rad olika webbläsare och enheter.
title: Webbläsare som stöds
feature: Implementation
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---


# Webbläsare som stöds

[!DNL Adobe Target]-programmet och innehållsleveransen har testats i en rad olika webbläsare och enheter.

Mer information om TLS finns i [TLS (Transport Layer Security) Krypteringsändringar](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

## [!DNL Target] Standard-/Premium-gränssnitt  {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

Gränssnittet [!DNL Target] har stöd för följande webbläsare och enheter:

| Enhetstyp | Webbläsarversion |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome (senaste, senaste minus 1)</li><li>Mozilla Firefox (senaste, senaste minus 1)</li></ul> |
| Mac | <ul><li>Firefox (senaste, senaste minus 1)</li><li>Krom (senaste, senaste minus 1)</li></ul> |

## Innehållsleverans {#section_1045A946056441268D40025529918D3D}

Materialet har testats i följande webbläsare och enheter:

| Enhetstyp | Webbläsarversion |
|--- |--- |
| Windows | <ul><li>Internet Explorer 9 och 10. Testad i emuleringsläge.<br>**Obs**: at.js 1.3.0 (och senare) stöder inte längre innehållsleverans i Microsoft Internet Explorer 9.</li><li>Internet Explorer 11</li><li>Microsoft Edge</li><li>Krom (senaste, senaste minus 1)</li><li>Firefox (senaste, senaste minus 1)</li></ul> |
| Mac | <ul><li>Apple Safari (senaste)<br>**Anm**: Mer information om hur Safari hanterar cookies från första och tredje part finns i [Målcookie](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md).</li><li>Firefox (senaste, senaste minus 1)</li><li>Krom (senaste, senaste minus 1)</li></ul> |
| Mobil/surfplatta | <ul><li>Apple iOS (senaste)</li><li>Android-enheter och -surfplattor (Android 4 och senare)</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

Observera följande:

* För [!DNL at.js]-implementeringar visar [!DNL Target] standardinnehåll i tidigare versioner av Internet Explorer och eventuellt i tidigare versioner av webbläsarna ovan. För [!DNL mbox.js]-implementeringar försöker [!DNL Target] återge innehåll, men det kanske inte lyckas.
* I Internet Explorer behandlas alla okända element (t.ex. anpassade element) som samma elementtyp. Leveransen fungerar därför inte med anpassade element.
* [!DNL Target] visar standardinnehåll i webbläsare som inte listas ovan och i webbläsare som använder  [läget](https://en.wikipedia.org/wiki/Quirks_mode) quirks. at.js kräver en doctype som återges i standardläge, till exempel: `<!DOCTYPE html>` .
* Adobe Delivery Infrastructure skyddas för att INTE stödja TLS 1.0-enheter och -webbläsare efter den 12 september 2018. Se [TLS (Transport Layer Security) Krypteringsändringar](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) för att förstå den övergripande effekten av den här ändringen.
