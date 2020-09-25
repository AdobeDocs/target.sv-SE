---
keywords: registerExtension;registerextension;register extension;at.js;functions;function;clientCode;serverDomain;globalMboxName;globalMboxAutoCreate;timeout
description: Information om funktionen registerExtension() för Adobe Target JavaScript-biblioteket at.js.
title: registerExtension() - at.js 1.x
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 8789d750e9e0245d88d54a8d3fe342e5b2e616fc
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 1%

---


# registerExtension() - at.js 1.x

Tillhandahåller ett standardsätt att registrera ett specifikt tillägg.

>[!NOTE]
>
>Den här funktionen är tillgänglig för version 1 av at.js.*Endast x* . Den här funktionen har ersatts med versionen av at.js 2.x. Den här funktionen returnerar standardinnehåll om den används med at.js 2.x.

Alternativparametern är obligatorisk och har följande struktur:

| Nyckel | Typ | Obligatoriskt | Beskrivning |
|--- |--- |--- |--- |
| name | Sträng | Ja | Tilläggsnamn. |
| moduler | [ArrayString] | Ja | En array med strängar som representerar begärda modulnamn. |
| register |  -funktion | Ja | En funktion som används för att initiera och skapa tillägget. Den här funktionen tar emot argument baserade på modularrayen. |

Anteckningar:

* Om en av parametrarna inte anges genereras ett undantag.
* Om modularrayen är tom genereras ett undantag.

Mer information och exempel på hur du använder `registerExtension`finns på sidan [Adobe Experience Cloud Target atjs Extensions](https://github.com/Adobe-Marketing-Cloud/target-atjs-extensions) på GitHub.

## Metoder för inställningsmodulen {#section_8501CDD4B0624FA2B10532C98C5F4328}

| Nyckel | Typ | Beskrivning |
|--- |--- |--- |
| clientCode | Sträng | Klientkod |
| serverDomain | Sträng | Edge Server-domän |
| globalMboxName | Sträng | Namn på global mbox |
| globalMboxAutoCreate | Boolean | Anger om autoskapa är aktiverat eller inte |
| timeout | Nummer | Timeout för begäran |

## Metoder för loggningsmodul {#section_10AF62B49AEF48F981E950D26E176138}

| Nyckel | Typ | Beskrivning |
|--- |--- |--- |
| logg |  -funktion | Loggar variabellistan med argument till webbläsarkonsolen, om den finns. Den aktiveras bara när `mboxDebug=true` skickas till URL:en. |
| fel |  -funktion | Loggar variabellistan med argument till webbläsarkonsolen. Den aktiveras bara när det finns allvarliga fel, som nätverkstimeout, HTML-nod som inte hittas osv. |
