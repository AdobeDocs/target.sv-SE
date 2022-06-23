---
keywords: serversida;serversida;api;sdk;node.js;nodats;node js;recommendations api;api:apis
description: Läs om Adobe [!DNL Target] API:er, SDK:er och [!DNL Target] Recommendations API:er.
title: Var kan jag läsa mer om [!DNL Target] Leverans-API:er och SDK:er på serversidan?
feature: Implement Server-side
role: Developer
exl-id: cdee007f-f54d-4cf3-9575-6319da3434a5
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 0%

---

# Serversida: implementera mål

Information om [!DNL Adobe Target] API:er, SDK:er och [!DNL Target Recommendations] API:er.

Följande process utförs i en implementering på serversidan av [!DNL Target]:

1. En klientenhet begär en upplevelse via servern.
1. Servern skickar begäran till [!DNL Target].
1. [!DNL Target] skickar tillbaka svaret till servern.
1. Servern bestämmer vilken upplevelse som ska levereras till klientenheten för att den ska kunna återges.

Upplevelsen behöver inte visas i en webbläsare. Upplevelsen kan visas i ett e-postmeddelande eller i en kioskdator, via en röstassistent eller via någon annan icke-visuell upplevelse eller icke-webbläsarbaserad enhet. Eftersom servern är placerad mellan klienten och [!DNL Target]är den här typen av implementering också idealisk om du behöver större kontroll och säkerhet eller har komplexa serverprocesser som du vill köra på servern.

>[!NOTE]
>
>En förstagångsbesökare kan bara initieras på klientsidan. En förstagångsbesökare *inte* initieras på serversidan.

I följande avsnitt finns mer information om de olika API:erna och NodeJS SDK:

## API:er för leverans på serversidan

Länk: [API:er för leverans på serversidan](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Använda [!DNL Target] Delivery API, du kan:

* Leverera upplevelser via webben, inklusive SPA, mobilkanaler och icke-webbläsarbaserade IoT-enheter, som anslutna tv-apparater, kioskdatorer eller digitala butiksskärmar.
* Leverera upplevelser från alla plattformar eller applikationer på serversidan som kan ringa HTTP/s-samtal.
* Leverera enhetliga och personaliserade upplevelser till en besökare oavsett vilken kanal eller vilka enheter besökaren använde för att interagera med ert företag.
* Cachelagra upplevelser för en besökare i en session på servern så att flera API-anrop kan undvikas, vilket ger bättre prestanda.
* Smidig integrering med [!DNL Adobe Experience Cloud] produkter, som [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) och [!DNL Experience Cloud ID Service] från serversidan.

## SDK:er på serversidan

Länk: [Adobe Target SDKs](https://developer.adobe.com/target/)

The [!DNL Adobe Target] via dokumentationsportalen för SDK på serversidan kan du implementera [!DNL Target] på valfritt språk.

## Ange Recommendations API:er

Länk: [Ange Recommendations API:er](https://developer.adobe.com/target/).

Med Recommendations API:er kan du programmässigt interagera med [!DNL Target] rekommendationsservrar. Dessa API:er kan integreras med en rad programstackar för att utföra funktioner som du vanligtvis gör via [!DNL Target] användargränssnitt.
