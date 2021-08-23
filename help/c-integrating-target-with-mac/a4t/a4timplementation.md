---
keywords: A4T;Adobe Analytics;Analytics-baserad aktivitet;Analytics report suite;report suite;Analytics Target integration;configure report suite;at.js;atjs;adobe experience platform web sdk;aep web sdk;platform web sdk
description: Följ stegen som krävs för att implementera lösningar med Analytics för [!DNL Target] (A4T) in your Adobe [!DNL Target] och Adobe Analytics.
title: Hur implementerar jag analyser för [!DNL Target] (A4T)?
feature: Analyser för mål (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: f509fca07305d72cfc3ffd99d0e9a21b19dc6521
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 0%

---

# Analyser för [!DNL Target]-implementering

Flera steg krävs när du implementerar [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T). Processen varierar beroende på om du implementerar A4T med [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) eller med at.js.

## ![Adobe Experience Platform Web SDK ](/help/assets/platform.png) badgeImplementeringssteg för en Adobe Experience Platform Web SDK-implementering {#platform}

I följande avsnitt beskrivs de steg som krävs för att distribuera integreringen till din webbplats om du tänker använda Platform Web SDK:

### Steg 1: Begär etablering för [!DNL Analytics] och [!DNL Target]

Innan du implementerar A4T måste du ha etablerats för [!DNL Analytics] och [!DNL Target]. [Använd det här formuläret om du vill begära att få etableras](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES).

### Steg 2: Konfigurera användarbehörigheter

Kraven för användarkontot måste uppfyllas innan du kan skapa en aktivitet som baseras på [!DNL Analytics] i [!DNL Target]. Se [Krav för användarbehörighet](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

### Steg 3: Skapa en Edge-konfiguration

Skapa en Edge-konfiguration med [!DNL Adobe Experience Platform Launch] och edge-konfigurationsverktyget. Konfigurera [[!DNL Analytics] and [!DNL Target] edge-konfigurationsinställningarna](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html).

### Steg 4: Installera och konfigurera Platform Web SDK

[Installera](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) och [konfigurera](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) Platform Web SDK på webbplatssidorna om du vill börja leverera [!DNL Target]-upplevelser och använda [!DNL Analytics] för spårnings- och analysändamål.

### Steg 5: Aktivera alternativen för A4T

I gränssnittet för [!DNL Target] klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** och väljer sedan antingen **[!UICONTROL Select per activity]** eller **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL Select per activity]** gör att du kan välja mellan  [!DNL Target] och  [!DNL Analytics] när du skapar varje aktivitet.
* **[!UICONTROL Adobe Analytics]** anger  [!DNL Analytics] som rapportkälla för alla aktiviteter som du skapar.

## ![at.js ](/help/assets/atjs.png) badgeImplementeringssteg för en at.js-implementering{#section_73961BAD5BB4430A95E073DE5C026277}

I följande avsnitt beskrivs de steg som krävs för att distribuera den här integreringen till din webbplats om du tänker använda at.js:

### Steg 1: Begär etablering för Analytics och Target

När du har implementerat [!DNL Analytics] som rapporteringskälla för [!DNL Target] måste du etableras för [!DNL Analytics] och [!DNL Target]. [Använd det här formuläret om du vill begära att få etableras](https://www.adobe.com/go/audiences).

### Steg 2: Konfigurera användarbehörigheter

Kraven för användarkontot måste uppfyllas innan du kan skapa en [!DNL Analytics]-baserad aktivitet i [!DNL Target]. Se [Krav för användarbehörighet](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

### Steg 3: Implementera tjänsten Experience Cloud Visitor ID

Med besökar-ID-tjänsten kan du identifiera användare i [!DNL Adobe Experience Cloud]-lösningar. Implementera eller migrera till den version av Experience Cloud Visitor-ID som krävs. Mer information finns i Implementeringskrav i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Se [Implementera Experience Cloud ID-tjänsten för mål](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) i *Experience Cloud Visitor ID-tjänsten*-dokumentationen.

### Steg 4: Uppdatera AppMeasurement för JavaScript eller s_code

Implementera eller migrera till den version av appMeasurement.js som krävs. Mer information finns i Implementeringskrav i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Information om nya implementeringar finns i [Översikt över JavaScript-implementering](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) i *implementeringshandboken för analyser*.

Om du vill ha en migrering läser du i [Migrera till AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) i *implementeringshandboken för analyser*.

### Steg 5: Ladda ned och uppdatera på js

Implementera eller migrera till den version av at.js som krävs med ditt produktionskonto. Koden behöver inte ändras.

Mer information finns i Implementeringskrav i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

### Steg 6: Host at.js

Om du tidigare distribuerade at at.js kan du ersätta den befintliga filen med den uppdaterade versionen. Mer information finns i Implementeringskrav i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Annars kan den här filen lagras tillsammans med Visitor ID-tjänsten och AppMeasurement för JavaScript-filer. Dessa filer måste finnas på en webbserver som är tillgänglig för alla sidor på platsen. Du behöver sökvägen till de här filerna i nästa steg.

### Steg 7: Referens vid .js på alla webbplatssidor {#step7}

Inkludera at.js under VisitorAPI.js genom att lägga till följande kodrad i taggen på varje sida:

For at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js måste läsas in före at.js. Om du uppdaterar en befintlig at.js-fil måste du kontrollera inläsningsordningen.

Standardinställningen för [!DNL Target]- och [!DNL Analytics]-integrering, från ett implementeringsperspektiv, är att använda SDID som skickas från sidan för att sammanfoga [!DNL Target]- och [!DNL Analytics]-begäran automatiskt.

Du kan styra hur och när analysdata som är relaterade till [!DNL Target] ska skickas till [!DNL Analytics] för rapportering. Om du inte vill använda standardinställningarna för att låta [!DNL Target] och [!DNL Analytics] sammanfoga analysdata automatiskt via SDID, anger du **analyticsLogging = client_side** via **window.targetGlobalSettings**. Obs! versioner under 2.1 stöder inte detta tillvägagångssätt.

Exempel:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Den här konfigurationen har en global effekt, vilket innebär att alla anrop från at.js har **analyticsLogging: &quot;client_side&quot;** skickas inom [!DNL Target]-begäranden och en analysnyttolast returneras för varje begäran. När det här alternativet är konfigurerat ser nyttolastens format ut så här:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

Nyttolasten kan sedan vidarebefordras till Analytics via [API:t för datainfogning](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Om du vill använda Automatisk allokering och Automatiskt mål-aktiviteter måste du även vidarebefordra sessions-ID. Mer information finns i [Analytics for Target-rapportering (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) i *Adobe Target SDKs*-guiden.

Om en global inställning inte är önskad och en mer on demand-metod är att föredra, använder du funktionen at.js [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) genom att ange **analyticsLogging: &quot;client_side&quot;**. Analysens nyttolast returneras endast för det här anropet och [!DNL Target]-serverdelen vidarebefordrar inte nyttolasten till [!DNL Analytics]. Genom att följa den här metoden returnerar varje at.js [!DNL Target]-begäran nyttolasten som standard, men i stället bara när det önskas och anges.

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

### Steg 8: Validera implementeringen {#step8}

Läs in sidorna när du har uppdaterat JavaScript-biblioteken för att bekräfta att parametervärdena `mboxMCSDID` i [!DNL Target]-anropen matchar parametervärdet `sdid` i sidvisningsanropet för [!DNL Analytics].

Det är särskilt viktigt att du bekräftar att dessa värden matchar i Single Page-program (SPA), där det inte alltid går att förutse hur anropet kommer att ordnas.

>[!NOTE]
>
>Matchningen av dessa värden krävs för att A4T ska fungera korrekt.

### Steg 9: (Valfritt) Ta bort föregående integreringskod

Adobe rekommenderar att du tar bort den tidigare integreringen för att förenkla implementeringen och eliminerar behovet av att korrigera skillnader mellan systemen. Du kan ta bort kod som du har distribuerat för en tidigare SC till T&amp;T-integrering, inklusive `mboxLoadSCPlugin`.

### Steg 10: Aktivera alternativen för att använda Analytics som rapportkälla för Target

I [!DNL Target] klickar du på **[!UICONTROL Administration > Visual Experience Composer]** och väljer antingen **[!UICONTROL Select per activity]** eller **[!UICONTROL Adobe Analytics]** för att aktivera alternativen.

* **[!UICONTROL Select per activity]** gör att du kan välja mellan  [!DNL Target] och  [!DNL Analytics] när du skapar varje aktivitet.
* **[!UICONTROL Adobe Analytics]** anger  [!DNL Analytics] som rapportkälla för alla aktiviteter som du skapar.


