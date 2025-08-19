---
keywords: A4T;Adobe Analytics;Analytics-baserad aktivitet;Analytics report suite;report suite;Analytics Target integration;configure report suite;at.js;atjs;adobe experience platform web sdk;aep web sdk;platform web sdk
description: Följ stegen som krävs för att implementera Analytics för  [!DNL Target] (A4T) i dina Adobe [!DNL Target] - och Adobe Analytics-lösningar.
title: Hur implementerar jag analyser för  [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ddfb06a17a24200b2aa4f01d370cc0e92ff5f180
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 0%

---

# Analyser för implementering av [!DNL Target]

Flera steg krävs när [!DNL Adobe Analytics] implementeras som rapportkälla för [!DNL Adobe Target] (A4T). Processen varierar beroende på om du implementerar A4T med [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) eller med at.js.

## ![Adobe Experience Platform Web SDK badge](/help/main/assets/platform.png) Implementeringssteg för en Adobe Experience Platform Web SDK-implementering {#platform}

I följande avsnitt beskrivs de steg som krävs för att distribuera integreringen till din webbplats om du tänker använda Platform Web SDK:

### Steg 1: Begär etablering för [!DNL Analytics] och [!DNL Target]

Innan du implementerar A4T måste du etableras för [!DNL Analytics] och [!DNL Target]. [Använd det här formuläret för att begära att bli etablerad](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y).

### Steg 2: Ange användarbehörigheter

Kraven för användarkontot måste uppfyllas innan du kan skapa en aktivitet baserad på [!DNL Analytics] i [!DNL Target]. Se [Krav för användarbehörighet](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Steg 3: Skapa en Edge-konfiguration

Skapa en Edge-konfiguration med [!DNL Adobe Experience Platform] med hjälp av edge-konfigurationsverktyget. Konfigurera [Skapa och konfigurera datastreams](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

### Steg 4: Installera och konfigurera Platform Web SDK

Om du vill börja leverera [!DNL Target]-upplevelser och använda [!DNL Analytics] i spårnings- och analyssyfte, [installerar](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) och [konfigurerar](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) Platform Web SDK på webbplatsens sidor.

### Steg 5: Aktivera alternativen för A4T

Klicka på [!DNL Target] > **[!UICONTROL Administration]** i användargränssnittet för **[!UICONTROL Visual Experience Composer]** och välj sedan antingen **[!UICONTROL Select per activity]** eller **[!UICONTROL Adobe Analytics]**.

* Med **[!UICONTROL Select per activity]** kan du välja mellan [!DNL Target] och [!DNL Analytics] när du skapar varje aktivitet.
* **[!UICONTROL Adobe Analytics]** anger [!DNL Analytics] som rapportkälla för alla aktiviteter som du skapar.

## ![at.js badge](/help/main/assets/atjs.png) Implementeringssteg för en at.js-implementering{#section_73961BAD5BB4430A95E073DE5C026277}

I följande avsnitt beskrivs de steg som krävs för att distribuera den här integreringen till din webbplats om du tänker använda at.js:

### Steg 1: Begär etablering för analys och mål

När du har implementerat [!DNL Analytics] som rapportkälla för [!DNL Target] måste du etableras för [!DNL Analytics] och [!DNL Target]. [Använd det här formuläret för att begära att bli etablerad](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}.

### Steg 2: Ange användarbehörigheter

Kraven för användarkontot måste uppfyllas innan du kan skapa en [!DNL Analytics]-baserad aktivitet i [!DNL Target]. Se [Krav för användarbehörighet](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Steg 3: Implementera tjänsten Experience Cloud Visitor ID

Med besökar-ID-tjänsten kan du identifiera användare för alla [!DNL Adobe Experience Cloud]-lösningar. Implementera eller migrera till den version av Experience Cloud Visitor-ID som krävs. Mer information finns i Implementeringskrav i [Innan du implementerar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Se [Implementera Experience Cloud ID-tjänsten för mål](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) i dokumentationen för *Experience Cloud Visitor ID-tjänsten*.

### Steg 4: Uppdatera AppMeasurement för JavaScript eller s_code

Implementera eller migrera till den version av appMeasurement.js som krävs. Mer information finns i Implementeringskrav i [Innan du implementerar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Information om nya implementeringar finns i [Översikt över JavaScript-implementering](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) i *Implementeringshandboken för analyser*.

Om du vill ha en migrering läser du [Migrera till AppMeasurement för JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) i *Implementeringshandboken för analyser*.

### Steg 5: Hämta och uppdatera på .js

Implementera eller migrera till den version av at.js som krävs med ditt produktionskonto. Koden behöver inte ändras.

Mer information finns i Implementeringskrav i [Innan du implementerar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

### Steg 6: Värddator på.js

Om du tidigare distribuerade at at.js kan du ersätta den befintliga filen med den uppdaterade versionen. Mer information finns i Implementeringskrav i [Innan du implementerar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

I annat fall kan den här filen lagras tillsammans med Visitor ID-tjänsten och AppMeasurement for JavaScript-filer. Dessa filer måste finnas på en webbserver som är tillgänglig för alla sidor på platsen. Du behöver sökvägen till de här filerna i nästa steg.

### Steg 7: Referera at.js på alla webbplatssidor {#step7}

Inkludera at.js under VisitorAPI.js genom att lägga till följande kodrad i taggen på varje sida:

For at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js måste läsas in före at.js. Om du uppdaterar en befintlig at.js-fil måste du kontrollera inläsningsordningen.

Standardinställningen för [!DNL Target]- och [!DNL Analytics]-integrering, från ett implementeringsperspektiv, är att använda SDID som skickas från sidan för att sammanfoga [!DNL Target] - och [!DNL Analytics] -begäran automatiskt.

Du kan styra hur och när analysdata som är relaterade till [!DNL Target] ska skickas till [!DNL Analytics] för rapportering. Om du inte vill använda standardinställningarna för att låta [!DNL Target] och [!DNL Analytics] sammanfoga analysdata automatiskt via SDID, anger du **analyticsLogging = client_side** via **window.targetGlobalSettings**. Obs! Versioner under 2.1 stöder inte detta tillvägagångssätt.

Exempel:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Den här konfigurationen har en global effekt, vilket innebär att alla anrop från at.js har **analyticsLogging: &quot;client_side&quot;** som skickas i [!DNL Target] -begäranden och en analysvolym returneras för varje begäran. När det här alternativet är konfigurerat ser nyttolastens format ut så här:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

Nyttolasten kan sedan vidarebefordras till Analytics via [API:t för datainfogning](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Om du vill använda Automatisk allokering och Automatiskt mål-aktiviteter måste du även vidarebefordra sessions-ID. Mer information finns i [Analytics for Target-rapportering (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} i guiden *Adobe Target SDK*.

Om en global inställning inte önskas och en mer on demand-metod är att föredra, använder du funktionen at.js [getOffers()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html){target=_blank} genom att skicka **analyticsLogging: &quot;client_side&quot;**. Analysens nyttolast returneras endast för det här anropet och [!DNL Target]-serverdelen vidarebefordrar inte nyttolasten till [!DNL Analytics]. Genom att följa den här metoden returnerar varje at.js [!DNL Target]-begäran nyttolasten som standard, men i stället bara när det önskas och anges.

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

Nyttolasten kan sedan vidarebefordras till [!DNL Analytics] via [API:t för datainfogning](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### Steg 8: Validera implementeringen {#step8}

Läs in sidorna när du har uppdaterat JavaScript-biblioteken för att bekräfta att parametervärdena `mboxMCSDID` i [!DNL Target] -anropen matchar parametervärdet `sdid` i sidvisningsanropet [!DNL Analytics].

Det är särskilt viktigt att du bekräftar att dessa värden matchar i SPA (Single Page Applications) där det inte alltid går att förutse hur anropet är.

>[!NOTE]
>
>Matchningen av dessa värden krävs för att A4T ska fungera korrekt.

### Steg 9: (Valfritt) Ta bort föregående integreringskod

Adobe rekommenderar att du tar bort den tidigare integreringen för att förenkla implementeringen och eliminerar behovet av att korrigera skillnader mellan systemen. Du kan ta bort kod som du har distribuerat för en tidigare SC till T&amp;T-integrering, inklusive `mboxLoadSCPlugin`.

### Steg 10: Aktivera alternativen för att använda Analytics som rapportkälla för Target

I [!DNL Target] klickar du på **[!UICONTROL Administration > Reporting]** och väljer antingen **[!UICONTROL Select per activity]** eller **[!UICONTROL Adobe Analytics]** för att aktivera alternativen.

* Med **[!UICONTROL Select per activity]** kan du välja mellan [!DNL Target] och [!DNL Analytics] när du skapar varje aktivitet.
* **[!UICONTROL Adobe Analytics]** anger [!DNL Analytics] som rapportkälla för alla aktiviteter som du skapar.


