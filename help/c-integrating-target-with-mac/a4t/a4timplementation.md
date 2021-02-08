---
keywords: A4T;Adobe Analytics;Analysbaserad aktivitet;Analytics report suite;report suite;Analytics Target integration;configure report suite
description: Följ stegen som krävs för att implementera Analytics for Target (A4T) i era Adobe Target- och Adobe Analytics-lösningar.
title: Hur implementerar jag analys för mål (A4T)?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Analyser för målimplementering{#analytics-for-target-implementation}

Flera steg krävs när du implementerar [!DNL Adobe Analytics] som rapportkälla för [!DNL Target] (A4T).

## Implementeringssteg {#section_73961BAD5BB4430A95E073DE5C026277}

I följande avsnitt beskrivs de steg som krävs för att distribuera den här integreringen till din plats.

## Steg 1: Begär etablering för Analytics och Target

När du har implementerat [!DNL Analytics] som rapporteringskälla för [!DNL Target] måste du etableras för [!DNL Analytics] och [!DNL Target]. [Använd det här formuläret om du vill begära att få etableras](http://www.adobe.com/go/audiences).

## Steg 2: Konfigurera användarbehörigheter

Kraven för användarkontot måste uppfyllas innan du kan skapa en [!DNL Analytics]-baserad aktivitet i [!DNL Target]. Se [Krav för användarbehörighet](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## Steg 3: Implementera tjänsten Experience Cloud Visitor ID

Med besökar-ID-tjänsten kan du identifiera användare i [!DNL Adobe Experience Cloud]-lösningar. Du måste implementera eller migrera till den version av Experience Cloud Visitor-ID som krävs. Mer information finns i Implementeringskrav i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Se [Implementera Experience Cloud ID-tjänsten för mål](https://experienceleague.adobe.com/docs/id-service/using/implementation-guides/setup-target.html) i *Experience Cloud Visitor ID-tjänsten*-dokumentationen.

## Steg 4: Uppdatera AppMeasurement för JavaScript eller s_code

Du måste implementera eller migrera till den version av appMeasurement.js som krävs. Mer information finns i Implementeringskrav i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Information om nya implementeringar finns i [Översikt över JavaScript-implementering](https://experienceleague.adobe.com/docs/analytics/implementation/javascript-implementation/javascript-implementation-overview.html) i *implementeringshandboken för analyser*.

Om du vill ha en migrering läser du i [Migrera till AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) i *implementeringshandboken för analyser*.

## Steg 5: Ladda ned och uppdatera på js

Du måste implementera eller migrera till den version av at.js som krävs med ditt produktionskonto. Koden behöver inte ändras.

Mer information finns i Implementeringskrav i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

## Steg 6: Host at.js

Om du tidigare distribuerade at at.js kan du ersätta den befintliga filen med den uppdaterade versionen. Mer information finns i Implementeringskrav i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Annars kan den här filen lagras tillsammans med Visitor ID-tjänsten och AppMeasurement för JavaScript-filer. Dessa filer måste finnas på en webbserver som är tillgänglig för alla sidor på platsen. Du behöver sökvägen till de här filerna i nästa steg.

## Steg 7: Referens at.js på alla webbplatssidor {#step7}

Inkludera at.js under VisitorAPI.js genom att lägga till följande kodrad i taggen på varje sida:

For at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

Det är viktigt att VisitorAPI.js läses in före at.js. Om du uppdaterar en befintlig at.js- eller mbox.js-fil kontrollerar du att inläsningsordningen är korrekt.

Det sätt som inställningarna som är klara att användas för [!DNL Target]- och [!DNL Analytics]-integrering från ett implementeringsperspektiv är att använda det SDID som skickas från sidan för att automatiskt sammanfoga [!DNL Target]- och [!DNL Analytics]-begäran på baksidan.

Om du vill ha större kontroll över hur och när analysdata som är relaterade till [!DNL Target] ska skickas till [!DNL Analytics] för rapportering, och du inte vill använda standardinställningarna att [!DNL Target] och [!DNL Analytics] automatiskt ska sammanfoga analysdata via SDID, kan du ange **analysloggning = client_side** via **window.targetGlobalSettings**. Obs! versioner under 2.1 stöder inte detta tillvägagångssätt.

Exempel:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Den här konfigurationen har en global effekt, vilket innebär att alla anrop från at.js har **analyticsLogging: &quot;client_side&quot;** skickas inom [!DNL Target]-begäranden och en analysnyttolast returneras för varje begäran. När detta är konfigurerat ser nyttolastens format ut så här:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

Nyttolasten kan sedan vidarebefordras till Analytics via [API:t för datainmatning](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Observera att för [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter måste du även vidarebefordra sessions-ID. Mer information finns i [Analytics for Target-rapportering (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) i *Adobe Target SDKs*-guiden.

Om en global inställning inte önskas och en mer on demand-metod är att föredra kan du använda funktionen at.js [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) för att uppnå detta genom att skicka **analyticsLogging: &quot;client_side&quot;**. Analysens nyttolast returneras bara för det här anropet och [!DNL Target]-backend vidarebefordrar inte nyttolasten till [!DNL Analytics]. Om du väljer det här sättet returnerar inte alla at.js [!DNL Target]-begäranden nyttolasten som standard, utan bara när det önskas och anges.

Exempel:

```javascript
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

Det här anropet anropar ett svar från vilket du kan extrahera analysens nyttolast.

Svaret ser ut så här:

```javascript
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

Nyttolasten kan sedan vidarebefordras till [!DNL Analytics] via [API för datainmatning](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Steg 8: Validera implementeringen {#step8}

Läs in sidorna när du har uppdaterat JavaScript-biblioteken för att bekräfta att parametervärdena `mboxMCSDID` i [!DNL Target]-anropen matchar parametervärdet `sdid` i sidvisningsanropet för [!DNL Analytics].

Det är särskilt viktigt att du bekräftar detta i Single Page Applications (SPA), där det inte alltid går att förutse hur samtal ordnas.

**Obs!** Matchningen av dessa värden krävs för att A4T ska fungera korrekt.

## Steg 9: (Valfritt) Ta bort föregående integreringskod

Vi rekommenderar att du tar bort den tidigare integreringen för att förenkla implementeringen och eliminerar behovet av att korrigera skillnader mellan systemen. Du kan ta bort kod som du har distribuerat för en tidigare SC till T&amp;T-integrering, inklusive `mboxLoadSCPlugin`.

## Steg 10: Aktivera alternativen för att använda Analytics som rapportkälla för Target

I [!DNL Target] klickar du på **[!UICONTROL Administation > Visual Experience Composer]** och väljer antingen **[!UICONTROL Select per activity]** eller **[!UICONTROL Adobe Analytics]** för att aktivera alternativen.

* **[!UICONTROL Select per activity]** gör att du kan välja mellan  [!DNL Target] och  [!DNL Analytics] när du skapar varje aktivitet.
* **[!UICONTROL Adobe Analytics]** anger  [!DNL Analytics] som rapportkälla för alla aktiviteter som du skapar.

