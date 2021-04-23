---
keywords: skyddsprofil för innehåll;csp;at.js;whitelist;tillåtelselista;flimmer;pre-hide;prehide
description: Läs mer om de CSP-direktiv (Content Security Policy) som du bör lägga till när du använder Adobe Target.
title: Hur hanterar  [!DNL Target] CSP (Content Security Policies)?
feature: Integritet och säkerhet
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# CSP-direktiv (Content Security Policy)

Om du använder [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) för din [!DNL Adobe Target]-implementering bör du lägga till följande CSP-direktiv när du använder [at.js 2.1 eller senare](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` med  `*.tt.omtrdc.net` tillåtslista. Nödvändigt för att tillåta nätverksbegäran till kanten [!DNL Target].
* `style-src unsafe-inline`. Krävs för att dölja och flimra kontrollen.
* `script-src unsafe-inline`.  Krävs för att tillåta JavaScript-körning som kan vara en del av ett HTML-erbjudande.
