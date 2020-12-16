---
keywords: variables;profiles;parameters;built in profiles;methods;url variables;geo profiles;third party profiles;mbox variables;campaign variables;customer attributes
description: På den här sidan visas profiler, variabler och parametrar som är användbara i profilskript.
title: Profil och variabel ordlista
feature: visitor profiles
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 0%

---


# Profil och variabel ordlista{#profile-and-variable-glossary}

På den här sidan visas profiler, variabler och parametrar som är användbara i profilskript.

## Inbyggda profiler {#section_2B694370003C4F8E8E29E0B2F6E52045}

| Profil | Anteckningar |
|--- |--- |
| user.activeActivities<br>user.activeCampaigns | Returnera kampanj-ID:t för alla kampanjer/aktiviteter som användaren befinner sig i, även om han/hon inte har interagerat med kampanjen/aktiviteten i den aktuella sessionen. |
| user.pcId |  |
| user.sessionId |  |
| user.categoryAffinity |  |
| user.categoryAffinities | Returnera en array med tillhörigheter som en besökare har fyllt i |
| user.isFirstSession |  |
| user.isNewSession |  |
| user.daysSinceLastVisit |  |
| user.browser | Användaragenten |
| user.header | Alla `user.header`-profiler är inbyggda från rubrikdata för Mbox-begäran |
| user.header(&#39;x-forward-for&#39;) | Den offentliga IP-adressen för den nätverksanslutning som besökaren är ansluten till.<br>Du kan få detta på flera sätt, till exempel  [whatismyip.com](https://www.whatismyip.com/). IP-adressen är inte NAT-adressen (intern adress), med början 10.192.168 eller 172.<br>Obs! user.header(&#39;x-Cluster-client-ip&#39;) har tagits bort. |
| user.header(&#39;host&#39;) | Värdnamn för webbplats |
| user.header(&#39;cookie&#39;) | Data för besöks-cookie |
| user.header(&#39;user-agent&#39;) | Användaragent för besökare |
| user.header(&#39;accept-language&#39;) | Besökarspråk |
| user.header(&#39;accept-encoding&#39;) | Teckenkodning för besökare |
| user.header(&#39;accept&#39;) | Besökarspråk och teckenkodning |
| user.header(&#39;connection&#39;) | Serveranslutning. Till exempel:  keep-live |
| user.header(&#39;referrer&#39;) | Webbplats-URL för besökarens aktuella sida. Fungerar inte för Internet Explorer. |
| user.getLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.setLocal(&#39;param_name&#39;,&#39;value&#39;); |  |
| user.get(&#39;param_name&#39;) |  |
| user.parameter | Beständiga profilattribut som har skapats från profilskript. Refererar också till&quot;systemprofiler&quot; som geopositionering, besöksantal osv. |
| profile.get(&#39;param_name&#39;) | Det rätta sättet att få en profilparameter att använda i ett profilskript är metoden profile.get(&#39;param_name&#39;). |
| profile.param(&#39;param_name&#39;); |  |
| profile.parameter(&#39;parameter_name&#39;); | Mbox-parametrar som görs beständiga på grund av deras profil.  prefix. |
| profile.browserTime | Besökarens lokala webbläsartid. Skapa ett nytt datumobjekt i profilskriptet för systemtid |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount |  |
| parameter= | Allmän term för ytterligare värden som skickas med en mbox, vanligtvis som namn/värde-par. Inte beständig om den inte har gjorts med `profile.parameter` eller `user.parameter`. |

## URL-variabler {#section_8F25958273164EBAA6DC659302993FD3}

| `landing` | `referrer` | `page` |
|---|---|---|
| `landing.url` | `referrer.url` | `page.url` |
| `landing.domain` | `referrer.domain` | `page.domain` |
| `landing.protocol` | `referrer.protocol` | `page.protocol` |
| `landing.param` | `referrer.param` | `page.param` |
| `landing.query` | `referrer.query` | `page.query` |

## Geo- och mobiltransportprofiler {#section_08441DA42E7346918FBB345818854997}

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`
* `profile.geolocation.latitude`
* `profile.geolocation.longitude`

## Mbox-variabler {#section_C42F0D33BD8044BE812FA0B7905CC0ED}

| Variabel | Anteckningar |
|--- |--- |
| `mbox.name` |  |
| mbox.param(&#39;param_name&#39;) |  |
| Parametrar skickas automatiskt med varje begäran:<ul><li>mbox.param(&#39;browserHeight&#39;)</li><li>mbox.param(&#39;browserTimeOffset&#39;)</li><li>mbox.param(&#39;browserWidth&#39;)</li><li>mbox.param(&#39;colorDepth&#39;)</li><li>mbox.param(&#39;mboxXDomain&#39;)</li><li>mbox.param(&#39;mboxTime&#39;)</li><li>mbox.param(&#39;screenHeight&#39;)</li><li>mbox.param(&#39;screenWidth&#39;)</li></ul> |
| Parametrar skickade med orderrutor:<ul><li>mbox.param(&#39;orderId&#39;)</li><li>mbox.param(&#39;orderTotal&#39;)</li><li>mbox.param(&#39;productPurchasedId&#39;)</li></ul> |
| mbox3rdPartyId | En mbox-parameter för att synkronisera ett kund-ID till Target mboxPCID. Ett kund-ID är ett ID som ditt företag använder för att spåra besökare, till exempel ett CRM-ID, ett medlems-ID eller något liknande. Detta ID kan sedan användas för att lägga till information via profil-API:erna och [kundattribut](/help/c-target/c-visitor-profile/working-with-customer-attributes.md). |
| mboxPageValue | I varje mbox-anrop tilldelas sidan ett värde. |
| mboxDebug | Används endast för felsökningsinformation. Tillagd på sid-URL:en där mbox.js letar efter den. |
| mboxOverride.browserIp | Ställer in en annan region än den faktiska platsen så att du kan testa hur någonting skulle se ut på en annan plats.<br>**Obs!** Använda mboxOverride-parametrar bör bara användas när aktiviteten testas och inte i produktion. Om du använder någon av parametrarna mboxOverride kan det orsaka rapporteringsavvikelser när du använder [Analytics för Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Du bör använda [Aktivitets-QA-läge](/help/c-activities/c-activity-qa/activity-qa.md) under testningen för att kontrollera att din aktivitet fungerar som förväntat innan du flyttar aktiviteten till din livemiljö. |

## Kundattribut {#section_62B4821EB6564FF4A14159A837AD4EDB}

Kundattribut kan refereras i profilskript, formaterade som `crs.get('<Datasource Name>.<Attribute name>')`.

Dessa attribut är också tillgängliga som token i profilskript och direkt i erbjudanden utan att först behöva ett profilskript. Token ska ha följande format: `${crs.datasourceName.attributeName}`. Observera att blanksteg i `datasourceName` bör tas bort från alla API-anrop.
