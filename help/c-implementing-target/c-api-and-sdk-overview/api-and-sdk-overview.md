---
keywords: serversida;serversida;api;sdk;node.js;nodats;node js;recommendations api;api:apis
description: Läs mer om Adobe Target server-side delivery API:er, SDK:er och Target Recommendations API:er.
title: Var kan jag lära mig mer om API:er för leverans på serversidan och SDK:er?
feature: Implement Server-side
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Serversida: implementera mål

Information om [!DNL Adobe Target] API:er för leverans på serversidan, SDK:er och [!DNL Target Recommendations] API:er.

Följande process utförs i en implementering på serversidan av [!DNL Target]:

1. En klientenhet begär en upplevelse via servern.
1. Servern skickar begäran till [!DNL Target].
1. [!DNL Target] skickar tillbaka svaret till servern.
1. Servern bestämmer vilken upplevelse som ska levereras till klientenheten för att den ska kunna återges.

Upplevelsen behöver inte visas i en webbläsare. Upplevelsen kan visas i ett e-postmeddelande eller i en kioskdator, via en röstassistent eller via någon annan icke-visuell upplevelse eller icke-webbläsarbaserad enhet. Eftersom servern finns mellan klienten och [!DNL Target] är den här typen av implementering också idealisk om du behöver större kontroll och säkerhet eller har komplexa serverprocesser som du vill köra på servern.

>[!NOTE]
>
>En förstagångsbesökare kan bara initieras på klientsidan. En förstagångsbesökare *kan inte* initieras på serversidan.

I följande avsnitt finns mer information om de olika API:erna och NodeJS SDK:

## API:er för leverans på serversidan

Länk: [API:er för leverans på serversidan](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Med leverans-API:t [!DNL Target] kan du:

* Leverera upplevelser via webben, inklusive SPA, mobilkanaler och icke-webbläsarbaserade IoT-enheter, som anslutna tv-apparater, kioskdatorer eller digitala butiksskärmar.
* Leverera upplevelser från alla plattformar eller applikationer på serversidan som kan ringa HTTP/s-samtal.
* Leverera enhetliga och personaliserade upplevelser till en besökare oavsett vilken kanal eller vilka enheter besökaren använde för att interagera med ert företag.
* Cachelagra upplevelser för en besökare i en session på servern så att flera API-anrop kan undvikas, vilket ger bättre prestanda.
* Integrera smidigt med [!DNL Adobe Experience Cloud]-produkter som [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) och [!DNL Experience Cloud ID Service] från serversidan.

## SDK:er på serversidan

Länk: [Adobe Target SDK](https://adobetarget-sdks.gitbook.io/docs/)

Med hjälp av [!DNL Adobe Target]-dokumentationsportalen för SDK på serversidan kan du implementera [!DNL Target] på dina servrar på det språk du föredrar.

## Ange Recommendations API:er

Länk: [Recommendations API:er](https://developers.adobetarget.com/api/recommendations) och [Adobe Recommendations API - översikt](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html).

Med Recommendations API:er kan du programmässigt interagera med [!DNL Target] rekommendationsservrar. Dessa API:er kan integreras med en rad programstackar för att utföra funktioner som du vanligtvis gör via användargränssnittet för [!DNL Target].
