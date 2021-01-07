---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: Information om CSP-direktiv (Content Security Policy) som du bör lägga till när du använder Adobe Target at.js 2.1 eller senare.
title: CSP (Content Security Policies)
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 0%

---


# CSP-direktiv (Content Security Policy)

Om du använder [Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) för din [!DNL Adobe Target]-implementering bör du lägga till följande CSP-direktiv när du använder [at.js 2.1 eller senare](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` med  `*.tt.omtrdc.net` tillåtslista. Nödvändigt för att tillåta nätverksbegäran till kanten [!DNL Target].
* `style-src unsafe-inline`. Krävs för att dölja och flimra kontrollen.
* `script-src unsafe-inline`.  Krävs för att tillåta JavaScript-körning som kan vara en del av ett HTML-erbjudande.
