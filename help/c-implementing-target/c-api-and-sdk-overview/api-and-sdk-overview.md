---
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
description: Information om Adobe Target server-side delivery API:er, Node.js SDK och Target Recommendations API:er.
title: Information om Adobe Target server-side delivery API:er, Node.js SDK och Target Recommendations API:er.
feature: server-side
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 08ad3291a1f981fbc3963ce403bf19849c358b97
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 0%

---


# Serversida: implementera mål{#server-side-implement-target}

Information om [!DNL Adobe Target] leverans-API:er på serversidan, Node.js SDK och API: [!DNL Target Recommendations] er.

Följande process utförs i en implementering på serversidan av [!DNL Target]:

1. En klientenhet begär en upplevelse via servern.
1. Servern skickar begäran till [!DNL Target].
1. [!DNL Target] skickar tillbaka svaret till servern.
1. Servern bestämmer vilken upplevelse som ska levereras till klientenheten för att den ska kunna återges.

Upplevelsen behöver inte visas i en webbläsare. Upplevelsen kan visas i ett e-postmeddelande eller i en kioskdator, via en röstassistent eller via någon annan icke-visuell upplevelse eller icke-webbläsarbaserad enhet. Eftersom servern sitter mellan klienten och [!DNL Target]är den här typen av implementering också idealisk om du behöver större kontroll och säkerhet eller har komplexa serverprocesser som du vill köra på servern.

I följande avsnitt finns mer information om de olika API:erna och NodeJS SDK:

## API:er för leverans på serversidan

Länk: [API:er för leverans på serversidan](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Med [!DNL Target] Delivery API kan du:

* Leverera upplevelser på webben, inklusive SPA, och mobila kanaler liksom icke-webbläsarbaserade IoT-enheter, som anslutna tv-apparater, kioskdatorer eller digitala butiksskärmar.
* Leverera upplevelser från alla plattformar eller applikationer på serversidan som kan ringa HTTP/s-samtal.
* Leverera enhetliga och personaliserade upplevelser till en besökare oavsett vilken kanal eller vilka enheter besökaren använde för att interagera med ert företag.
* Cachelagra upplevelser för en besökare i en session på servern så att flera API-anrop kan undvikas, vilket ger bättre prestanda.
* Integrera smidigt med [!DNL Adobe Experience Cloud] produkter som [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) och [!DNL Experience Cloud ID Service] från serversidan.

## Node.js SDK

Länk: [Node.js SDK](https://github.com/adobe/target-nodejs-sdk)

Node.js SDK är ett avancerat programutvecklingspaket som eliminerar svårigheterna med att hantera cookies, sessioner och integrering med [!DNL Experience Cloud] produkter som [!DNL Analytics], [!DNL Experience Cloud Visitor ID Service]och [!DNL Audience Manager]. Bakom scenerna använder Node.js SDK `/rest/v1/delivery` -gränssnittet. Här är några bra funktioner som stöds i Node.js SDK:

* **Stöd för förhämtning och meddelanden som gör att du kan optimera prestanda via cachning:** Du kan använda Node.js SDK för att hämta upplevelser och cachelagra dem lokalt på din Node.js-server i syfte att minimera serveranrop till [!DNL Target] och optimera programprestanda.
* **Möjlighet att hämta VEC-skapade aktiviteter:** Hämta VEC-skapade aktiviteter på serversidan. Svaret som innehåller VEC-skapade aktiviteter har väljare som kan användas för att i förväg dölja endast delar av sidan som behöver vara personaliserade. Detta bidrar till att optimera sidans [första innehållsangivelse](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html), som är en viktig nyckeltal för att ditt företag ska få en hög poäng i [Google PageRank](https://en.wikipedia.org/wiki/PageRank) -systemet.

## Mål-Java SDK

Länk: [Mål-Java SDK](https://github.com/adobe/target-java-sdk)

Java SDK är ett avancerat programutvecklingspaket som eliminerar svårigheterna med att hantera cookies, sessioner och integrering med [!DNL Adobe Experience Cloud] lösningar som [!DNL Adobe Analytics], [!DNL Experience Cloud Visitor ID Service]och [!DNL Adobe Audience Manager]. Bakom scenerna använder Java SDK `/rest/v1/delivery` -API:t. Här är några bra funktioner som stöds i Java SDK:

* **Stöd för förhämtning och meddelanden som gör att du kan optimera prestanda via cachning**: Du kan använda JavaSDK för att hämta upplevelser och cacha dem lokalt på Java-servern i syfte att minimera serveranrop till [!DNL Target] och optimera programprestanda.
* **Möjlighet att hämta VEC-skapade aktiviteter**: Hämta VEC-skapade aktiviteter på serversidan. Svaret som innehåller VEC-skapade aktiviteter har väljare som kan användas för att i förväg dölja endast delar av sidan som behöver vara personaliserade. Detta bidrar till att optimera sidans [första innehållsangivelse](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html) , som är en viktig nyckeltal för att ditt företag ska få en hög poäng i [Google PageRank](https://en.wikipedia.org/wiki/PageRank) -systemet.

## Adobe Target-utvecklare

Länk: [Adobe Target-utvecklare](http://developers.adobetarget.com/)

På webbplatsen för Adobe Target-utvecklare kan du implementera [!DNL Target] program på klientsidan, program på serversidan, mobilappar, IoT och mycket mer. Du kan också exportera dina [!DNL Target] data till tredjepartslösningar.

## Ange Recommendations API:er

Länk: [Ange Recommendations API](https://developers.adobetarget.com/api/recommendations) och [Adobe Recommendations API - översikt](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html).

Med Recommendations API:er kan du programmässigt interagera med [!DNL Target] rekommendationsservrar. Dessa API:er kan integreras med en rad programstackar för att utföra funktioner som du vanligtvis gör via [!DNL Target] användargränssnittet.
