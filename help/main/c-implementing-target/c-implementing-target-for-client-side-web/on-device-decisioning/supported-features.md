---
keywords: implementering;javascript-bibliotek;js;atjs;on device decisioning;on device decisioning;supported features
description: Lär dig vilka funktioner som stöds för enhetsbeslut.
title: Vilka funktioner som stöds i Enhetsbeslut
feature: at.js
role: Developer
exl-id: 3531ff55-c3db-44c1-8d0a-d7ec2ccb6505
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Funktioner som stöds för beslut på enheten

The [!DNL Adobe Target] JS SDK ger kunderna flexibilitet att välja mellan prestanda och aktualitet för data för beslut. Med andra ord, om det viktigaste är att leverera det mest relevanta och engagerande personaliserade innehållet via maskininlärning, bör du ringa ett live-serversamtal. Men när prestanda är viktigare bör man fatta beslut på enheten och i minnet. Information om hur du bestämmer dig för att arbeta på en enhet finns i följande avsnitt som visar vilka funktioner som stöds.

## Aktivitetstyper som stöds

I följande tabell visas vilka [aktivitetstyper](/help/main/c-activities/target-activities-guide.md) skapad av [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) eller [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) stöds eller stöds inte för enhetsbeslut.

| Typ av aktivitet | Stöds? |
| --- | --- |
| [A/B-test](/help/main/c-activities/t-test-ab/test-ab.md) | Ja |
| [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Nej |
| [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ![Premium](/help/main/assets/premium.png) | Nej |
| [Multivariata tester](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Nej |
| [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md) (XT) | Ja |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) ![Premium](/help/main/assets/premium.png) | Nej |
| [Recommendations](/help/main/c-recommendations/recommendations.md) ![Premium](/help/main/assets/premium.png) | Nej |
| [Aktiviteter som använder analys för Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Ja |

## Målgruppsanpassning

Tabellen nedan visar vilka målgruppsregler som stöds eller inte stöds för enhetsbeslut.

| Målgruppsregel | Stöds? |
| --- | --- |
| [Geo](/help/main/c-target/c-audiences/c-target-rules/geo.md) | Ja |
| [Nätverk](/help/main/c-target/c-audiences/c-target-rules/network.md) | Nej |
| [Mobil](/help/main/c-target/c-audiences/c-target-rules/mobile.md) | Nej |
| [Egna parametrar](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md) | Ja |
| [Operativsystem](/help/main/c-target/c-audiences/c-target-rules/operating-system.md) | Ja |
| [Webbplatssidor](/help/main/c-target/c-audiences/c-target-rules/site-pages.md) | Ja |
| [Webbläsare](/help/main/c-target/c-audiences/c-target-rules/browser.md) | Ja |
| [Besökarprofil](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) | Nej |
| [Trafikkällor](/help/main/c-target/c-audiences/c-target-rules/traffic-sources.md) | Nej |
| [Tidsram](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | Ja |
| Adobe Experience Cloud-målgrupper<br>(Målgrupper från [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]och [!DNL Adobe Experience Manager] | Nej |

### Målinriktning för geolokalisering för beslut på enheter

Adobe rekommenderar att du anger geovärdena själv i anropet till [getOffers](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/). Ange Geo-objektet i sammanhanget för begäran. Det innebär att webbläsaren ska avgöra var besökarna befinner sig. Du kan till exempel utföra en IP-till-Geo-sökning med en tjänst som du konfigurerar. Vissa värdtjänstleverantörer, som Google Cloud, tillhandahåller den här funktionen via anpassade rubriker i varje `HttpServletRequest`.

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				city: "SAN FRANCISCO", 
				countryCode: "US", 
				stateCode: "CA", 
				latitude: 37.75, 
				longitude: -122.4 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

Om du inte kan utföra IP-till-Geo-sökningar på servern, men ändå vill utföra enhetsbeslut för [getOffers](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/) -förfrågningar som innehåller geobaserade målgrupper stöds också. Nackdelen med detta är att det använder en IP-till-Geo-sökning på fjärrbasis, vilket ger fördröjning för varje `getOffers` ring. Denna fördröjning bör vara lägre än en `getOffers` anropa med serversidesbeslut eftersom det träffar ett CDN som ligger nära servern. Ange endast fältet&quot;ipAddress&quot; i Geo-objektet i kontexten för din begäran om att SDK ska hämta geoplatsen för din besökares IP-adress. Om något annat fält förutom&quot;ipAddress&quot; anges, visas [!DNL Target] SDK hämtar inte metadata för geopositionering för upplösning.

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				ipAddress: "127.0.0.1" 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

### Allokeringsmetod

Följande tabell visar vilka allokeringsmetoder som stöds eller inte stöds för enhetsbeslut.

| Allokeringsmetod | Stöds? |
| --- | --- |
| Manuell | Ja |
| [Autoallokera till bästa upplevelse](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Nej |
| [Automatisk målgruppsanpassning för personaliserade upplevelser](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Nej |
