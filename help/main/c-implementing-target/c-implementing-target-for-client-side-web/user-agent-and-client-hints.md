---
keywords: at.js;webbläsaranvändaragent;användaragent;klienttips;användaragent
description: Lär dig mer [!DNL Adobe Target] använder användaragenten och klienttips för att kvalificera besökare för segmentering och personalisering.
title: Tips för användaragent och klient
feature: at.js
role: Developer
exl-id: 22d29bfe-e022-44b2-913f-c8c32c65bc48
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 0%

---

# Tips för användaragent och klient

[!DNL Adobe Target] använder användaragenten för att kvalificera besökare för segmentering och personalisering.

>[!NOTE]
>
>Informationen i den här artikeln gäller för [at.js version 2.9.0](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) (eller senare).


Varje gång en webbläsare skickar en begäran till en server, som ingår i huvudet i begäran, är information om webbläsaren och miljön där webbläsaren körs. Sedan de första dagarna på Internet har dessa data sammanställts i en enda sträng som kallas user-agent.

Följande text är ett exempel på en användaragent för en Mac OS X-baserad dator som använder en Safari-webbläsare:

```
Mozilla/5.0 (Linux; Android 12; SM-S908E) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.41 Mobile Safari/537.36 
```

Från den här användaragenten kan servern som tar emot begäran identifiera följande information om webbläsaren och operativsystemet:

| Information | Detaljer |
| --- | --- |
| Programvarunamn | Krom |
| Programversion | 101 |
| Fullversion av programmet | 101.0.4951.41 |
| Namn på layoutmotor | AppleWebKit |
| Layoutmotorversion | 537.36 |
| Operativsystem | Android |
| Operativsystemversion | Android 12 (Snökon) |
| Enhet | SM-S908E (Samsung Galaxy S22 Ultra) |

Under årens lopp har mängden webbläsarinformation och enhetsinformation som ingår i användaragentsträngen ökat.

## Användningsexempel för användaragent

Användaragenter har länge använts för att ge marknadsförings- och utvecklarteam viktiga insikter i hur webbläsare och operativsystem fungerar. och enheter visar webbplatsinnehåll samt hur användarna interagerar med webbplatser. Användaragenter används också för att blockera skräppost och filterbottnar som crawlar webbplatser för en mängd andra syften.

Under de senaste åren har dock vissa webbplatsägare och marknadsföringsleverantörer använt användaragenten tillsammans med annan information i begärandehuvuden för att skapa digitala fingeravtryck som kan användas som ett sätt att identifiera användare utan deras vetskap. Trots det viktiga syftet med användaragenten för webbplatsägare har webbläsarutvecklare beslutat att ändra hur användaragenter arbetar för att begränsa eventuella sekretessproblem för webbplatsbesökare.

Klienttips för användaragenten är den lösning som webbläsarutvecklare har utvecklat. Klienttips gör det fortfarande möjligt för webbplatser att samla in nödvändig information om webbläsare, operativsystem och enheter, samtidigt som de får ett bättre skydd mot dolda spårningsmetoder, som fingeravtryck.

## Klienttips

Klienttips för användaragenten ger webbplatsägare möjlighet att komma åt mycket av den information som finns tillgänglig i användaragenten, men på ett mer sekretessbelagt sätt. När moderna webbläsare skickar en användaragent till en webbserver skickas hela användaragenten vid varje begäran, oavsett om det krävs eller inte. Klienttips tvingar å andra sidan en modell där servern måste fråga webbläsaren om ytterligare information om klienten. När webbläsaren tar emot den här begäran kan den tillämpa egna profiler eller användarkonfiguration för att avgöra vilka data som returneras. I stället för att visa hela användaragenten som standard på alla förfrågningar hanteras nu åtkomsten på ett explicit och spårbart sätt.

Klienttips för användaragenten har varit tillgängliga i Chrome sedan version 89. De senaste versionerna av Chromium-baserade webbläsare, som Microsoft Edge, Opera, Brave, Chrome Android, Opera Android och Samsung Internet, har också stöd för Client Hints API.

Klienttips som finns i rubrikerna för den första begäran som webbläsaren gör till en webbserver innehåller webbläsarvarumärket, huvudversionen av webbläsaren och en indikator på om klienten är en mobil enhet. Varje datadel har ett eget rubrikvärde, i stället för att grupperas i en enskild användar-agent-sträng, vilket visas i följande exempel:

```
Sec-CH-UA: "Chromium";v="101", "Google Chrome";v="101", " Not;A Brand";v="99" 
Sec-CH-UA-Mobile: ?0 
Sec-CH-UA-Platform: "macOS"
```

Följande exempel är användaragenten för samma webbläsare:

```
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36 
```

Även om informationen är liknande innehåller den första begäran till servern klienttips som bara innehåller en delmängd av det som är tillgängligt i användar-agent-strängen. Saknas i begäran är operativsystemets arkitektur, operativsystemets fullständiga version, namnet på layoutmotorn, versionen av layoutmotorn och webbläsarversionen. Vid efterföljande begäranden tillåter emellertid API:t för klienttips webbservrar att be om ytterligare, hög entropinformation om enheten. När dessa höga entropisvärden begärs, beroende på webbläsarprincipen eller användarinställningarna, kan webbläsarsvaret inkludera den informationen.

Följande exempel är ett JSON-objekt som returneras av API:t för klienttips när höga entropinavärden begärs:

```
{ 

    "architecture":"x86", 
    "bitness":"64", 
    "brands":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100" 
        } 
    ], 
    "fullVersionList":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99.0.0.0" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100.0.4896.127" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100.0.4896.127" 
        } 
    ], 
    "mobile":false, 
    "model":"", 
    "platformVersion":"12.2.1" 
} 
```

De höga entropisymvärdena innehåller flera ytterligare informationsdelar som inte är tillgängliga i standardinformationen för klienttips. Följande tabell innehåller information om vilka data som är tillgängliga i standardbegäran jämfört med informationen om användaragentklienttips för hög entropi.

| HTTP-huvud | JavaScript | Användaragent | Klienttips | Tips för hög entropi-klient |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | varumärken | Ja | Ja | Nej |
| Sec-CH-UA-Platform | plattform | Ja | Ja | Nej |
| Sec-CH-UA-Mobile | mobil | Ja | Ja | Nej |
| Sec-CH-UA-platform-version | platformVersion | Ja | Nej | Ja |
| Sec-CH-UA-Arch | arkitektur | Ja | Nej | Ja |
| Sec-CH-UA-Model | modell | Ja | Nej | Ja |
| Avsn-CH-UA-bitness | Bitness | Ja | Nej | Ja |
| Sec-CH-UA-full-version-list | fullVersionList | Ja | Nej | Ja |

## Migrering till klienttips

För närvarande fortsätter Chromium-baserade webbläsare att skicka användaragenten tillsammans med klienttips i rubrikerna för begäranden som görs till webbservrar. Från och med april 2022 och fram till februari 2023 kommer mängden data i användaragentsträngen att minskas. Andra webbläsare, som Safari och Firefox, fortsätter att utnyttja användaragentsträngen. Även de kommer dock att minska mängden information i dem.

## [!DNL Target] använder fall som kräver klontips

Följande användningsfall i Target kräver klienttips:

### Målgruppsattribut

Om du använder [!DNL Target] målgrupper och använder något av följande målgruppsattribut, [!DNL Target] Kräver att klienttips utför rätt segmentering:

* Webbläsare
* Operativsystem
* Mobil

### Profilskript

Om du använder profilskript och refererar till `user.browser` attribute (som refererar till user-agent), you may need to update the profile script to also check one or more Client Hints. Du kan komma åt alla klienttips med funktionen `user.clientHint('sec-ch-ua-xxxxx')`. Namnet på klienttipshuvudet måste vara i gemener.

I följande exempel visas hur du korrekt identifierar ett Windows-operativsystem i ett profilskript:

```
"return (((user.browser != null) && (user.browser.indexOf(\"Windows\") > -1)) || " + 
      "((user.clientHint('sec-ch-ua-platform') != null) && 
(user.clientHint('sec-ch-ua-platform') === 'Windows')));" 
```

I följande avsnitt visas användarsemantik för klienttips och deras motsvarande profilskript.

#### Sec-CH-UA

Entropy: Låg dokumentation: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA){target=_blank} Målgruppsattribut: Skriptanvändning för webbläsarprofil: `user.clientHint('sec-ch-ua')`

#### Sec-CH-UA-Arch

Entropy: Hög dokumentation: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch){target=_blank} Målgruppsattribut: Exponerad för användare via profilskript.
Profilskriptanvändning: `user.clientHint('sec-ch-ua-arch')`

#### Avsn-CH-UA-bitness

Entropy: Hög dokumentation: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness){target=_blank} Målgruppsattribut: Exponerad för användare via profilskript.
Profilskriptanvändning: `user.clientHint('sec-ch-ua-bitness')`

#### Sec-CH-UA-full-version-list

Entropy: Hög dokumentation: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List){target=_blank} Målgruppsattribut: Skriptanvändning för webbläsarprofil: `user.clientHint('sec-ch-ua-full-version-list')`

#### Sec-CH-UA-Mobile

Entropy: Låg dokumentation: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile){target=_blank} Målgruppsattribut: Användning av skript för mobilprofiler: `user.clientHint('sec-ch-ua-mobile')`

#### Sec-CH-UA-Model

Entropy: Hög dokumentation: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model){target=_blank} Målgruppsattribut: Användning av skript för mobilprofiler: `user.clientHint('sec-ch-ua-model')`

#### Sec-CH-UA-Platform

Entropy: Låg dokumentation: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform){target=_blank} Målgruppsattribut: Användning av operativsystemets profilskript: `user.clientHint('sec-ch-ua-platform')`

#### Sec-CH-UA-platform-version

Entropy: Hög dokumentation: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version){target=_blank} Målgruppsattribut: Exponerad för användare via profilskript.
Profilskriptanvändning: `user.clientHint('sec-ch-ua-platform-version')`

## Så här skickar du klienttips till [!DNL Adobe Target]

Följande avsnitt innehåller mer information om hur du skickar klienttips, beroende på [!DNL Target] implementering.

### at.js version 2.9.0 (eller senare)

Från och med kl.js 2.9.0 kommer klienttips för användaragenten att samlas in automatiskt från webbläsaren och skickas till [!DNL Target] när `getOffer/getOffers()` anropas. Som standard samlar at.js bara in &quot;Low Entropy&quot;-klienttips. Om du utför målgruppssegmentering eller använder profilskript baserade på data som kategoriserats som&quot;High Entropy&quot; från de föregående avsnitten, måste du konfigurera at.js för att samla in&quot;High Entropy&quot;-klienttips från webbläsaren via `targetGlobalSettings`.

`window.targetGlobalSettings = { allowHighEntropyClientHints: true };`

### SDK:er på serversidan

Mer information om hur du skickar klienttips via SDK:er på serversidan finns i [Klienttips](https://developer.adobe.com/target/implement/server-side/sdk-guides/core-principles/audience-targeting/){target=_blank} under *Målgruppsanpassning* i *Adobe Target SDKs* dokumentation.
