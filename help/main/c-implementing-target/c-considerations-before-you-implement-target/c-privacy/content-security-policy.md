---
keywords: skyddsprofil för innehåll;csp;at.js;whitelist;tillåtelselista;flimmer;pre-hide;prehide
description: Läs mer om de CSP-direktiv (Content Security Policy) som du bör lägga till när du använder Adobe Target.
title: Hur [!DNL Target] Vill du hantera CSP (Content Security Policies)?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# CSP-direktiv (Content Security Policy)

Om du använder [Skyddsprofil för innehåll](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) för [!DNL Adobe Target] implementering bör du lägga till följande CSP-direktiv när du använder [at.js 2.1 eller senare](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}:

* `connect-src` med `*.tt.omtrdc.net` tillåtslista. Nödvändigt för att tillåta nätverksbegäran till [!DNL Target] kant.
* `style-src unsafe-inline`. Krävs för att dölja och flimra kontrollen.
* `script-src unsafe-inline`.  Krävs för att tillåta JavaScript-körning som kan vara en del av ett HTML-erbjudande.

## Vanliga frågor och svar

Läs följande frågor och svar om säkerhetsprofiler:

### Finns det säkerhetsproblem i korsdomänsprinciper som korsdomänsdelning (CORS) och Flash?

Det rekommenderade sättet att implementera CORS-policyn är att tillåta åtkomst till endast betrodda ursprung som kräver det via en tillåtelselista med betrodda domäner. Samma sak kan sägas om Flash Cross Domain Policy. Några [!DNL Adobe Target] kunderna är oroade över användningen av jokertecken för domäner i [!DNL Target]. Problemet är att om en användare är inloggad på ett program och besöker en domän som tillåts enligt principen, kan allt skadligt innehåll som körs på den domänen potentiellt hämta känsligt innehåll från programmet och utföra åtgärder i säkerhetskontexten för den inloggade användaren. Detta kallas ofta CSRF (Cross-Site Request Forgery).

I en [!DNL Adobe Target] implementeringen bör dock inte utgöra ett säkerhetsproblem.

&quot;adobe.tt.omtrdc.net&quot; är en domän som ägs av Adobe. [!DNL Adobe Target] är ett verktyg för testning och personalisering och man förväntar sig att [!DNL Target] kan ta emot och behandla förfrågningar var som helst utan att någon autentisering krävs. Dessa begäranden innehåller nyckel/värde-par som används för A/B-testning, rekommendationer eller innehållspersonalisering.

[!DNL Adobe] inte lagrar personligt identifierbar information (PII) eller annan känslig information om [!DNL Adobe Target] edge-servrar som&quot;adobe.tt.omtrdc.net&quot; pekar på.

Det förväntas att [!DNL Target] kan nås från alla domäner via JavaScript-anrop. Det enda sättet att ge åtkomst är att använda&quot;Access-Control-Allow-Origin&quot; med jokertecken.
