---
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
description: Information om Adobe Target server-side delivery API:er, SDK:er och Target Recommendations API:er.
title: Information om Adobe Target server-side delivery API:er, Node.js SDK och Target Recommendations API:er.
feature: server-side
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 0%

---


# Serversida: implementera mål{#server-side-implement-target}

Information om [!DNL Adobe Target] server-side delivery API:er, SDK:er och API: [!DNL Target Recommendations] er.

Följande process utförs i en implementering på serversidan av [!DNL Target]:

1. En klientenhet begär en upplevelse via servern.
1. Servern skickar begäran till [!DNL Target].
1. [!DNL Target] skickar tillbaka svaret till servern.
1. Servern bestämmer vilken upplevelse som ska levereras till klientenheten för att den ska kunna återges.

Upplevelsen behöver inte visas i en webbläsare. Upplevelsen kan visas i ett e-postmeddelande eller i en kioskdator, via en röstassistent eller via någon annan icke-visuell upplevelse eller icke-webbläsarbaserad enhet. Eftersom servern sitter mellan klienten och [!DNL Target]är den här typen av implementering också idealisk om du behöver större kontroll och säkerhet eller har komplexa serverprocesser som du vill köra på servern.

>[!NOTE]
>
>En förstagångsbesökare kan bara initieras på klientsidan. En förstagångsbesökare *kan inte* initieras på serversidan.

I följande avsnitt finns mer information om de olika API:erna och NodeJS SDK:

## API:er för leverans på serversidan

Länk: [API:er för leverans på serversidan](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Med [!DNL Target] Delivery API kan du:

* Leverera upplevelser via webben, inklusive SPA, mobilkanaler och icke-webbläsarbaserade IoT-enheter, som anslutna tv-apparater, kioskdatorer eller digitala butiksskärmar.
* Leverera upplevelser från alla plattformar eller applikationer på serversidan som kan ringa HTTP/s-samtal.
* Leverera enhetliga och personaliserade upplevelser till en besökare oavsett vilken kanal eller vilka enheter besökaren använde för att interagera med ert företag.
* Cachelagra upplevelser för en besökare i en session på servern så att flera API-anrop kan undvikas, vilket ger bättre prestanda.
* Integrera smidigt med [!DNL Adobe Experience Cloud] produkter som [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) och [!DNL Experience Cloud ID Service] från serversidan.

## SDK:er på serversidan

Länk: [Adobe Target SDKs](https://adobetarget-sdks.gitbook.io/docs/)

Med dokumentationsportalen för SDK på [!DNL Adobe Target] serversidan kan du implementera [!DNL Target] på dina servrar på det språk du föredrar.

## Ange Recommendations API:er

Länk: [Ange Recommendations API](https://developers.adobetarget.com/api/recommendations) och [Adobe Recommendations API - översikt](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html).

Med Recommendations API:er kan du programmässigt interagera med [!DNL Target] rekommendationsservrar. Dessa API:er kan integreras med en rad programstackar för att utföra funktioner som du vanligtvis gör via [!DNL Target] användargränssnittet.
