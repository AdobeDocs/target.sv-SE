---
keywords: A4T;Adobe Analytics;Analytics-baserad aktivitet;Analytics report suite;report suite;Analytics Target integration;configure report suite;at.js;atjs;adobe experience platform web sdk;aep web sdk;platform web sdk
description: Följ stegen som krävs för att implementera Analytics för [!DNL Target] (A4T) på Adobe [!DNL Target] och Adobe Analytics lösningar.
title: Hur implementerar jag analyser för [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 0%

---

# Analyser för [!DNL Target] implementering

Flera steg krävs vid implementering [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T). Processen varierar beroende på om du implementerar A4T med [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) eller med at.js.

## ![Adobe Experience Platform Web SDK badge](/help/main/assets/platform.png) Implementeringssteg för en Adobe Experience Platform Web SDK-implementering {#platform}

I följande avsnitt beskrivs de steg som krävs för att distribuera integreringen till din webbplats om du tänker använda Platform Web SDK:

### Steg 1: Begär etablering för [!DNL Analytics] och [!DNL Target]

Innan du implementerar A4T måste du ha etablerat dig för [!DNL Analytics] och [!DNL Target]. [Använd det här formuläret för att begära etablering](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES).

### Steg 2: Konfigurera användarbehörigheter

Kraven för användarkontot måste uppfyllas innan du kan skapa en aktivitet baserat på [!DNL Analytics] in [!DNL Target]. Se [Krav på användarbehörighet](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Steg 3: Skapa en Edge-konfiguration

Skapa en Edge-konfiguration med [!DNL Adobe Experience Platform] med verktyget för kantkonfiguration. Konfigurera [[!DNL Analytics] and [!DNL Target] inställningar för kantkonfiguration](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html).

### Steg 4: Installera och konfigurera Platform Web SDK

Att börja leverera [!DNL Target] upplevelser och använda [!DNL Analytics] för spårnings- och analysändamål, [Installera](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) och [konfigurera](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) Platform Web SDK på era webbplatssidor.

### Steg 5: Aktivera alternativen för A4T

I [!DNL Target] Gränssnitt, klicka **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** väljer du antingen **[!UICONTROL Select per activity]** eller **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL Select per activity]** låter dig välja mellan [!DNL Target] och [!DNL Analytics] när du skapar varje aktivitet.
* **[!UICONTROL Adobe Analytics]** uppsättningar [!DNL Analytics] som rapportkälla för alla aktiviteter som du skapar.

## ![at.js badge](/help/main/assets/atjs.png) Implementeringssteg för en at.js-implementering{#section_73961BAD5BB4430A95E073DE5C026277}

I följande avsnitt beskrivs de steg som krävs för att distribuera den här integreringen till din webbplats om du tänker använda at.js:

### Steg 1: Begär etablering för Analytics och Target

Efter implementeringen [!DNL Analytics] som rapportkälla för [!DNL Target]måste du vara etablerad för [!DNL Analytics] och [!DNL Target]. [Använd det här formuläret för att begära etablering](https://www.adobe.com/go/audiences).

### Steg 2: Konfigurera användarbehörigheter

Kraven för användarkontot måste uppfyllas innan du kan skapa en [!DNL Analytics]-baserad aktivitet i [!DNL Target]. Se [Krav på användarbehörighet](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Steg 3: Implementera tjänsten Experience Cloud Visitor ID

Med besökar-ID-tjänsten kan du identifiera användare i [!DNL Adobe Experience Cloud] lösningar. Implementera eller migrera till den version av Experience Cloud Visitor-ID som krävs. Mer information finns i&quot;Implementeringskrav&quot; i [Innan du implementerar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Se [Implementera Experience Cloud ID-tjänsten för Target](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) i *Experience Cloud Visitor ID-tjänst* dokumentation.

### Steg 4: Uppdatera AppMeasurement för JavaScript eller s_code

Implementera eller migrera till den version av appMeasurement.js som krävs. Mer information finns i&quot;Implementeringskrav&quot; i [Innan du implementerar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Information om nya implementeringar finns i [Översikt över JavaScript-implementering](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) i *Implementeringshandbok för analyser*.

Information om migrering finns på [Migrera till AppMeasurement för JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) i *Implementeringshandbok för analyser*.

### Steg 5: Ladda ned och uppdatera på js

Implementera eller migrera till den version av at.js som krävs med ditt produktionskonto. Koden behöver inte ändras.

Mer information finns i&quot;Implementeringskrav&quot; i [Innan du implementerar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

### Steg 6: Host at.js

Om du tidigare distribuerade at at.js kan du ersätta den befintliga filen med den uppdaterade versionen. Mer information finns i&quot;Implementeringskrav&quot; i [Innan du implementerar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Annars kan den här filen lagras tillsammans med Visitor ID-tjänsten och AppMeasurement för JavaScript-filer. Dessa filer måste finnas på en webbserver som är tillgänglig för alla sidor på platsen. Du behöver sökvägen till de här filerna i nästa steg.

### Steg 7: Referens vid .js på alla webbplatssidor {#step7}

Inkludera at.js under VisitorAPI.js genom att lägga till följande kodrad i taggen på varje sida:

For at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.js måste läsas in före at.js. Om du uppdaterar en befintlig at.js-fil måste du kontrollera inläsningsordningen.

Standardinställningen för [!DNL Target] och [!DNL Analytics] från ett implementeringsperspektiv är att använda SDID som skickas från sidan för att sätta ihop [!DNL Target] och [!DNL Analytics] begär automatiskt tillsammans på baksidan.

Du kan styra hur och när analysdata som rör [!DNL Target] till [!DNL Analytics] för rapportering. Om du inte vill använda standardinställningarna för att [!DNL Target] och [!DNL Analytics] sammanfogar automatiskt analysdata via SDID, set **analyticsLogging = client_side** via **window.targetGlobalSettings**. Obs! versioner under 2.1 stöder inte detta tillvägagångssätt.

Exempel:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Den här konfigurationen har en global effekt, vilket innebär att alla anrop från at.js har **analyticsLogging: &quot;client_side&quot;** skickas inom [!DNL Target] förfrågningar och en analysnyttolast returneras för varje begäran. När det här alternativet är konfigurerat ser nyttolastens format ut så här:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

Nyttolasten kan sedan vidarebefordras till Analytics via [API för datainfogning](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Om du vill använda Automatisk allokering och Automatiskt mål-aktiviteter måste du även vidarebefordra sessions-ID. Mer information finns i [Analyser för målrapportering (A4T)](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} i *Adobe Target SDKs* guide.

Om en global inställning inte är önskad och en mer on-demand-metod är att föredra använder du funktionen at.js [getOffers()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/){target=_blank} genom att skicka in **analyticsLogging: &quot;client_side&quot;**. Analysens nyttolast returneras endast för det här anropet och [!DNL Target] backend vidarebefordrar inte nyttolasten till [!DNL Analytics]. Genom att följa detta tillvägagångssätt [!DNL Target] begäran returnerar nyttolasten som standard, men i stället bara när det önskas och anges.

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

Nyttolasten kan sedan vidarebefordras till [!DNL Analytics] via [API för datainfogning](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### Steg 8: Validera implementeringen {#step8}

Läs in sidorna när du har uppdaterat JavaScript-biblioteken för att bekräfta att `mboxMCSDID` parametervärden i [!DNL Target] anropen matchar `sdid` parametervärde i [!DNL Analytics] sidvisningssamtal.

Det är särskilt viktigt att du bekräftar att dessa värden matchar i Single Page-program (SPA), där det inte alltid går att förutse hur anropet kommer att ordnas.

>[!NOTE]
>
>Matchningen av dessa värden krävs för att A4T ska fungera korrekt.

### Steg 9: (Valfritt) Ta bort föregående integreringskod

Adobe rekommenderar att du tar bort den tidigare integreringen för att förenkla implementeringen och eliminerar behovet av att korrigera skillnader mellan systemen. Du kan ta bort kod som du har distribuerat för en tidigare SC till T&amp;T-integrering, inklusive `mboxLoadSCPlugin`.

### Steg 10: Aktivera alternativen för att använda Analytics som rapportkälla för Target

I [!DNL Target], klicka **[!UICONTROL Administration > Visual Experience Composer]** och välj antingen **[!UICONTROL Select per activity]** eller **[!UICONTROL Adobe Analytics]** för att aktivera alternativen.

* **[!UICONTROL Select per activity]** låter dig välja mellan [!DNL Target] och [!DNL Analytics] när du skapar varje aktivitet.
* **[!UICONTROL Adobe Analytics]** uppsättningar [!DNL Analytics] som rapportkälla för alla aktiviteter som du skapar.


