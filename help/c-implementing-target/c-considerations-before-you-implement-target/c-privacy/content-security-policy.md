---
keywords: skyddsprofil för innehåll;csp;at.js;whitelist;tillåtelselista;flimmer;pre-hide;prehide
description: Läs mer om de CSP-direktiv (Content Security Policy) som du bör lägga till när du använder Adobe Target.
title: Hur hanterar Target CSP (Content Security Policies)?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---


# CSP-direktiv (Content Security Policy)

Om du använder [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) för din [!DNL Adobe Target]-implementering bör du lägga till följande CSP-direktiv när du använder [at.js 2.1 eller senare](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` med  `*.tt.omtrdc.net` tillåtslista. Nödvändigt för att tillåta nätverksbegäran till kanten [!DNL Target].
* `style-src unsafe-inline`. Krävs för att dölja och flimra kontrollen.
* `script-src unsafe-inline`.  Krävs för att tillåta JavaScript-körning som kan vara en del av ett HTML-erbjudande.
