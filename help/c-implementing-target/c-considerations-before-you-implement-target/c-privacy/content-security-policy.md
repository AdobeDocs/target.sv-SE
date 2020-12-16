---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: Information om CSP-direktiv (Content Security Policy) som du bör lägga till när du använder Adobe Target at.js 2.1 eller senare.
title: CSP (Content Security Policies)
feature: privacy and security
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---


# CSP-direktiv (Content Security Policy)

Om du använder [Säkerhetsprincip för innehåll](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) för målimplementeringen bör du lägga till följande CSP-direktiv när du använder [at.js 2.1 eller senare](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` med  `*.tt.omtrdc.net` tillåtslista. Nödvändigt för att tillåta nätverksbegäran till kanten [!DNL Target].
* `style-src unsafe-inline`. Krävs för att dölja och flimra kontrollen.
* `script-src unsafe-inline`.  Krävs för att tillåta JavaScript-körning som kan vara en del av ett HTML-erbjudande.
