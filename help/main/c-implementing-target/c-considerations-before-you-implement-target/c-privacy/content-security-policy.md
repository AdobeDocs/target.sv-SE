---
keywords: skyddsprofil för innehåll;csp;at.js;whitelist;tillåtelselista;flimmer;pre-hide;prehide
description: Läs mer om de CSP-direktiv (Content Security Policy) som du bör lägga till när du använder Adobe Target.
title: Hur [!DNL Target] Vill du hantera CSP (Content Security Policies)?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 0%

---

# CSP-direktiv (Content Security Policy)

Om du använder [Skyddsprofil för innehåll](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) för [!DNL Adobe Target] implementering bör du lägga till följande CSP-direktiv när du använder [at.js 2.1 eller senare](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` med `*.tt.omtrdc.net` tillåtslista. Nödvändigt för att tillåta nätverksbegäran till [!DNL Target] kant.
* `style-src unsafe-inline`. Krävs för att dölja och flimra kontrollen.
* `script-src unsafe-inline`.  Krävs för att tillåta JavaScript-körning som kan vara en del av ett HTML-erbjudande.
