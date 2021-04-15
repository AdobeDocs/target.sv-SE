---
keywords: implementering;javascript-bibliotek;js;atjs;on device decisioning;on device decisioning;supported features
description: Lär dig vilka funktioner som stöds för enhetsbeslut.
title: Vilka funktioner som stöds i Enhetsbeslut
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: 5fcc5776e69222e0a232bd92ddfd10cee748e577
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Funktioner som stöds för beslut på enheten

JS SDK:n [!DNL Adobe Target] ger kunderna flexibilitet att välja mellan prestanda och aktualitet för data för beslut. Med andra ord, om det viktigaste är att leverera det mest relevanta och engagerande personaliserade innehållet via maskininlärning, bör du ringa ett live-serversamtal. Men när prestanda är viktigare bör man fatta beslut på enheten och i minnet. Information om hur du bestämmer dig för att arbeta på en enhet finns i följande avsnitt som visar vilka funktioner som stöds.

## Aktivitetstyper som stöds

Följande tabell visar vilka [aktivitetstyper](/help/c-activities/target-activities-guide.md) som skapats av [formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md) eller [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) som stöds eller inte för enhetsbeslut.

| Typ av aktivitet | Stöds? |
| --- | --- |
| [A/B-test](/help/c-activities/t-test-ab/test-ab.md) | Ja |
| [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Nej |
| [Auto-](/help/c-activities/auto-target/auto-target-to-optimize.md) ![TargetPremium](/help/assets/premium.png) | Nej |
| [Multivariata tester](/help/c-activities/c-multivariate-testing/multivariate-testing.md)  (MVT) | Nej |
| [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) (XT) | Ja |
| [Automatiserad ](/help/c-activities/t-automated-personalization/automated-personalization.md) ![personaliseringPremium](/help/assets/premium.png) | Nej |
| [](/help/c-recommendations/recommendations.md) ![RecommendationsPremium](/help/assets/premium.png) | Nej |
| [Aktiviteter som använder analys för Target](/help/c-integrating-target-with-mac/a4t/a4t.md)  (A4T) | Ja |

## Målgruppsanpassning

Tabellen nedan visar vilka målgruppsregler som stöds eller inte stöds för enhetsbeslut.

| Målgruppsregel | Stöds? |
| --- | --- |
| [Geo](/help/c-target/c-audiences/c-target-rules/geo.md) | Ja |
| [Nätverk](/help/c-target/c-audiences/c-target-rules/network.md) | Nej |
| [Mobil](/help/c-target/c-audiences/c-target-rules/mobile.md) | Nej |
| [Egna parametrar](/help/c-target/c-audiences/c-target-rules/custom-parameters.md) | Ja |
| [Operativsystem](/help/c-target/c-audiences/c-target-rules/operating-system.md) | Ja |
| [Webbplatssidor](/help/c-target/c-audiences/c-target-rules/site-pages.md) | Ja |
| [Webbläsare](/help/c-target/c-audiences/c-target-rules/browser.md) | Ja |
| [Besökarprofil](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) | Nej |
| [Trafikkällor](/help/c-target/c-audiences/c-target-rules/traffic-sources.md) | Nej |
| [Tidsram](/help/c-target/c-audiences/c-target-rules/time-frame.md) | Ja |
| Adobe Experience Cloud-målgrupper<br>(målgrupper från [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] och [!DNL Adobe Experience Manager] | Nej |

### Målinriktning för geolokalisering för beslut på enheter

Adobe rekommenderar att du anger geovärdena själv i anropet till [getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) för att behålla minimal fördröjning för enhetsspecifika beslutsaktiviteter med geobaserade målgrupper. Ange Geo-objektet i sammanhanget för begäran. Det innebär att webbläsaren ska avgöra var besökarna befinner sig. Du kan till exempel utföra en IP-till-Geo-sökning med en tjänst som du konfigurerar. Vissa värdtjänstleverantörer, som Google Cloud, tillhandahåller den här funktionen via anpassade rubriker i varje `HttpServletRequest`.

(Kod kommer)

Om du inte kan utföra IP-till-Geo-sökningar på servern, men ändå vill utföra enhetsbeslut för [getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)-begäranden som innehåller geobaserade målgrupper, stöds detta också. Nackdelen med det här tillvägagångssättet är att det använder en fjärr-IP-till-Geo-sökning, som lägger till fördröjning för varje `getOffers`-anrop. Denna fördröjning bör vara lägre än ett `getOffers`-anrop med beslut på serversidan, eftersom det träffar ett CDN som ligger nära servern. Ange endast fältet&quot;ipAddress&quot; i Geo-objektet i kontexten för din begäran om att SDK ska hämta geoplatsen för din besökares IP-adress. Om något annat fält förutom&quot;ipAddress&quot; anges kommer SDK:n för [!DNL Target] inte att hämta metadata för geopositionering för upplösning.

(Kod kommer)

### Allokeringsmetod

Följande tabell visar vilka allokeringsmetoder som stöds eller inte stöds för enhetsbeslut.

| Allokeringsmetod | Stöds? |
| --- | --- |
| Manuell | Ja |
| [Autoallokera till bästa upplevelse](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Nej |
| [Automatisk målgruppsanpassning för personaliserade upplevelser](/help/c-activities/auto-target/auto-target-to-optimize.md) | Nej |
