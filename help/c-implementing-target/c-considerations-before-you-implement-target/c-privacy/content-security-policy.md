---
keywords: content security policy;csp;at.js;whitelist;flicker;pre-hide;pre-hiding;prehiding
description: Information om CSP-direktiv (Content Security Policy) som du bör lägga till när du använder Adobe Target på.js 2.1 eller senare.
title: CSP (Content Security Policies)
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# CSP-direktiv (Content Security Policy)

Om du använder [CSP (Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) ) för målitimplementeringen bör du lägga till följande CSP-direktiv när du använder [at.js 2.1 eller senare](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` med `*.tt.omtrdc.net` vitlistad. Nödvändigt för att tillåta nätverksbegäran till [!DNL Target] gränsen.
* `style-src unsafe-inline`. Krävs för att dölja och flimra kontrollen.
* `script-src unsafe-inline`.  Krävs för att tillåta JavaScript-körning som kan vara en del av ett HTML-erbjudande.
