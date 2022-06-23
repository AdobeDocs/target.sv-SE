---
keywords: serverstate;targetGlobalSettings;targetSettings;globalSettings;globalSettings;global settings;at.js;functions;function;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVieinställningar sibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders;Hybrid Personalization;deviceIdLifetime
description: Använd funktionen targetGlobalSettings() för Adobe [!DNL Target] at.js JavaScript-bibliotek som åsidosätter inställningar i stället för att använda [!DNL Target] API:er för användargränssnitt eller REST.
title: Hur använder jag funktionen targetGlobalSettings()?
feature: at.js
role: Developer
exl-id: 14080cf6-6a15-4829-b95d-62c068898564
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '2371'
ht-degree: 0%

---

# targetGlobalSettings()

Du kan åsidosätta inställningarna i at.js-biblioteket med `targetGlobalSettings()`i stället för att konfigurera inställningarna i [!DNL Target] Standard-/Premium-gränssnitt eller med REST API:er.

## Inställningar {#section_42C759AE9B524A43B8659018677224B8}

Du kan åsidosätta följande inställningar:

### bodyHiddenStyle

* **Typ**: Sträng
* **Standardvärde**: body { opacity: 0 }
* **Beskrivning**: Används endast när `globalMboxAutocreate === true` för att minimera risken för flimmer.

   Mer information finns i [How at.js Manages Flicker](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/manage-flicker-with-atjs/).

### bodyHidingEnabled

* **Typ**: Boolean
* **Standardvärde**: true
* **Beskrivning**: Används för att kontrollera flimmer när `target-global-mbox` används för att leverera erbjudanden som skapats i Visual Experience Composer, även kallade visuella erbjudanden.

### clientCode

* **Typ**: Sträng
* **Standardvärde**: Värdet anges via användargränssnittet.
* **Beskrivning**: Representerar klientkoden.

### cookieDomain

* **Typ**: Sträng
* **Standardvärde**: Ange om möjligt domänens högsta nivå.
* **Beskrivning**: Representerar domänen som används när cookies sparas.

### crossDomain

* **Typ**: Sträng
* **Standardvärde**: Värdet anges via användargränssnittet.
* **Beskrivning**: Anger om spårning mellan domäner är aktiverat eller inte. Tillåtna värden är: inaktiverat, aktiverat eller endast x.

### cspScriptNonce

* **Typ**: Se [Skyddsprofil för innehåll](#content-security) nedan.
* **Standardvärde**: Se [Skyddsprofil för innehåll](#content-security) nedan.
* **Beskrivning**: Se [Skyddsprofil för innehåll](#content-security) nedan.

### cspStyleNonce

* **Typ**: Se [Skyddsprofil för innehåll](#content-security) nedan.
* **Standardvärde**: Se [Skyddsprofil för innehåll](#content-security) nedan.
* **Beskrivning**: Se [Skyddsprofil för innehåll](#content-security) nedan.

### dataProviders

* **Typ**: Se [Dataleverantörer](#data-providers) nedan.
* **Standardvärde**: Se [Dataleverantörer](#data-providers) nedan.
* **Beskrivning**: Se [Dataleverantörer](#data-providers) nedan.

### decisioningMethod {#on-device-decisioning}

* **Typ**: Sträng
* **Standardvärde**: serversida
* **Andra värden**: på enheten, hybrid
* **Beskrivning**: Se Beslutsmetoder nedan.

   **Beslutsmetoder**

   Med enhetsbeslut introducerar Target en ny inställning med namnet [!UICONTROL Decisioning Method] som styr hur at.js levererar era upplevelser. The `decisioningMethod` har tre värden: endast på serversidan, endast på enheten och hybrid. När `decisioningMethod` anges i `targetGlobalSettings()`fungerar det som standardmetod för beslut för alla [!DNL Target] beslut.

   **[!UICONTROL Server-side only]**:

   [!UICONTROL Server-side only] är standardmetoden för beslut som anges i rutan när at.js 2.5+ implementeras och distribueras på dina webbegenskaper.

   Använda [!UICONTROL server-side only] som standardkonfiguration innebär att alla beslut fattas på [!DNL Target] edge-nätverk, vilket innebär ett blockerande serveranrop. Den här metoden kan innebära inkrementell fördröjning, men ger även avsevärda fördelar, som att du kan använda Target maskininlärningsfunktioner som inkluderar [Recommendations](/help/main/c-recommendations/recommendations.md), [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP), och [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) verksamhet.

   Dessutom kan ni förbättra era personaliserade upplevelser genom att använda Target-användarprofilen, som bevaras i olika sessioner och kanaler, och få ett kraftfullt resultat för ert företag.

   Till sist [!UICONTROL server-side only] Med kan ni använda Adobe Experience Cloud och finjustera målgrupper som kan riktas mot genom Audience Manager och Adobe Analytics.

   **[!UICONTROL On-device only]**:

   [!UICONTROL On-Device only] är den beslutsmetod som måste anges i at.js 2.5+ när enhetsbeslut endast ska användas på alla dina webbsidor.

   Enhetsbeslut kan leverera upplevelser och personaliseringsaktiviteter blixtsnabbt eftersom besluten fattas utifrån en cache-lagrad regelartefakt som innehåller alla aktiviteter som är kvalificerade för enhetsbeslut.

   Mer information om vilka aktiviteter som är kvalificerade för enhetsbeslut finns i avsnittet med funktioner som stöds.

   Den här beslutsmetoden bör endast användas om prestanda är mycket kritiskt för alla sidor som kräver beslut från [!DNL Target]. Tänk dessutom på att när du väljer den här beslutsmetoden ska du [!DNL Target] aktiviteter som inte är kvalificerade för enhetsbeslut kommer inte att levereras eller utföras. At.js-biblioteket 2.5+ är konfigurerat att endast söka efter den cachelagrade regelartefakten för att fatta beslut.

   **Hybrid**:

   [!UICONTROL Hybrid] är den beslutsmetod som måste anges i at.js 2.5+ när både enhetsbeslut och aktiviteter som kräver ett nätverksanrop till Adobe Target Edge-nätverket måste köras.

   När du hanterar både enhetsspecifika och serverbaserade beslutsaktiviteter kan det vara lite komplicerat och omständligt att fundera på hur ni ska driftsätta och tillhandahålla [!DNL Target] på era sidor. Med hybridmetoden som beslutsmetod [!DNL Target] känner till när det måste ringa ett serveranrop till Adobe Target Edge-nätverket för aktiviteter som kräver körning på serversidan, och även när endast enhetsbeslut ska verkställas.

   JSON-regelartefakten innehåller metadata som informerar at.js om en mbox har en aktivitet på serversidan som körs eller en beslutsaktivitet på enheten. Denna beslutsmetod säkerställer att aktiviteter som du avser att leverera snabbt genomförs via enhetsspecifika beslut och för aktiviteter som kräver mer kraftfull ML-driven personalisering utförs dessa aktiviteter via Adobe Target Edge-nätverket.

### defaultContentHiddenStyle

* **Typ**: Sträng
* **Standardvärde**: synlighet: dold
* **Beskrivning**: Används endast för omslutningsrutor som använder DIV med klassnamnet &quot;mboxDefault&quot; och som körs via `mboxCreate()`, `mboxUpdate()`, eller `mboxDefine()` om du vill dölja standardinnehåll.

### defaultContentVisibleStyle

* **Typ**: Sträng
* **Standardvärde**: synlighet: visible
* **Beskrivning**: Används endast för omslutningsrutor som använder DIV med klassnamnet &quot;mboxDefault&quot; och som körs via `mboxCreate()`, `mboxUpdate()`, eller `mboxDefine()` för att visa det tillämpade erbjudandet om något eller standardinnehåll.

### deviceIdLifetime

* **Typ**: Nummer
* **Standardvärde**: 63244800000 ms = 2 år
* **Beskrivning**: Tidsmängd `deviceId` lagras i cookies.

>[!NOTE]
>
>Inställningen deviceIdLifetime kan åsidosättas i version 2.3.1 eller senare av at.js.

### aktiverad

* **Typ**: Boolean
* **Standardvärde**: true
* **Beskrivning**: När det här alternativet är aktiverat [!DNL Target] begära att få upplevelser och DOM-manipulering för att återge upplevelserna utförs automatiskt. Dessutom [!DNL Target] anrop kan utföras manuellt via `getOffer(s)` / `applyOffer(s)`.

   När det är inaktiverat [!DNL Target] begäranden utförs inte automatiskt eller manuellt.

### globalMboxAutoCreate

* **Typ**: Nummer
* **Standardvärde**: Värdet anges via användargränssnittet.
* **Beskrivning**: Anger om den globala mbox-begäran ska utlösas eller inte.

### imsOrgId

* **Typ**: Sting
* **Standardvärde**: true
* **Beskrivning**: Representerar IMS ORG ID.

### optinEnabled

* **Typ**: Boolean
* **Standardvärde**: false
* **Beskrivning**: [!DNL Target] ger stöd för tillvalsfunktioner via [!DNL Adobe Experience Platform] för att stödja er strategi för samtyckeshantering. Tack vare avanmälningsfunktionen kan kunderna styra hur och när [!DNL Target] -taggen utlöses. Det finns också ett alternativ via [!DNL Adobe Experience Platform] för att förgodkänna [!DNL Target] -tagg. Så här aktiverar du möjligheten att använda Opt-In i [!DNL Target] at.js-biblioteket, lägg till `optinEnabled=true` inställning. I [!DNL Adobe Experience Platform] du måste välja&quot;enable&quot; på [!UICONTROL GDPR Opt-In] nedrullningsbar lista i installationsvyn för tillägget. Se [Adobe Experience Platform-dokumentation](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/) för mer information. Mer information om den här inställningen när det gäller sekretess- och dataskyddsbestämmelser, inklusive EU:s allmänna dataskyddsförordning (GDPR) och Kaliforniens konsumentsekretesslag (CCPA), finns på [Sekretess- och dataskyddsbestämmelser](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/).

### optoutEnabled

* **Typ**: Boolean
* **Standardvärde**: false
* **Beskrivning**: Anger om Target ska anropa besökar-API:t `isOptedOut()` funktion. Detta är en del av aktiveringen av Device Graph.

### overrideMboxEdgeServer

* **Typ**: Boolean
* **Standardvärde**: true (true med början från at.js version 1.6.2)
* **Beskrivning**: Anger om vi ska använda `<clientCode>.tt.omtrdc.net` domän eller `mboxedge<clusterNumber>.tt.omtrdc.net` domän.

   Om värdet är true, `mboxedge<clusterNumber>.tt.omtrdc.net` domänen sparas i en cookie. Arbetar för närvarande inte med [CNAME](https://developer.adobe.com/target/before-implement/implement-cname-support-in-target/) när du använder at.js-versioner före at.js 1.8.2 och at.js 2.3.1. Om detta är ett problem för dig bör du överväga [uppdatera at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/) till en nyare version som stöds.

### overrideMboxEdgeServerTimeout

* **Typ**: Nummer
* **Standardvärde**: 1860000 => 31 minuter
* **Beskrivning**: Anger den cookie-livstid som innehåller `mboxedge<clusterNumber>.tt.omtrdc.net` värde.

### pageLoadEnabled

* **Typ**: Boolean
* **Standardvärde**: true
* **Beskrivning**: När det här alternativet är aktiverat hämtar du automatiskt upplevelser som måste returneras vid sidinläsning.

### secureOnly

* **Typ**: Boolean
* **Standardvärde**: false
* **Beskrivning**: Anger om at.js endast ska använda HTTPS eller tillåtas växla mellan HTTP och HTTPS baserat på sidprotokollet. När värdet är true anger secureOnly även attributen Secure och SameSite till mbox-cookien.

### selectorsPollingTimeout

* **Typ**: Nummer
* **Standardvärde**: 5000 ms = 5 s
* **Beskrivning**: in at.js 0.9.6, [!DNL Target] introducerade den här nya inställningen som kan åsidosättas via `targetGlobalSettings`.

   The `selectorsPollingTimeout` anger hur länge klienten är beredd att vänta på att alla element som identifieras av väljarna ska visas på sidan.

   Aktiviteter som skapas via Visual Experience Composer (VEC) har erbjudanden som innehåller väljare.

### serverDomain

* **Typ**: Sträng
* **Standardvärde**: Värdet anges via användargränssnittet.
* **Beskrivning**: Representerar målkantsservern.

### serverState

* **Typ**: Se [Hybrid-personalisering](#server-state) nedan.
* **Standardvärde**: Se [Hybrid-personalisering](#server-state) nedan.
* **Beskrivning**: Se [Hybrid-personalisering](#server-state) nedan.

### telemetryEnabled {#telemetry}

* **Typ**: Boolean
* **Standardvärde**: true
* **Beskrivning**: När det är aktiverat [!DNL Adobe] samlar in SDK-funktionens användnings- och prestandatelemetridata. Personuppgifter samlas inte in.

### timeout

* **Typ**: Nummer
* **Standardvärde**: Värdet anges via användargränssnittet.
* **Beskrivning**: Representerar [!DNL Target] timeout för edge-begäran.

### viewsEnabled

* **Typ**: Boolean
* **Standardvärde**: true
* **Beskrivning**: När det här alternativet är aktiverat hämtas vyer automatiskt som måste returneras vid sidinläsning. Vyer stöds i at.js 2.*x* endast.

### visitorApiTimeout

* **Typ**: Nummer
* **Standardvärde**: 2000 ms = 2 s
* **Beskrivning**: Representerar [!UICONTROL Visitor API] timeout för begäran.

## Användning {#section_9AD6FA3690364F7480C872CB55567FB0}

Funktionen kan definieras innan at.js läses in eller **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

I fältet Bibliotekshuvud kan du ange JavaScript utan formulär. Anpassningskoden ska se ut ungefär som i följande exempel:

```javascript
window.targetGlobalSettings = {  
   timeout: 200, // using custom timeout  
   visitorApiTimeout: 500, // using custom API timeout  
   enabled: document.location.href.indexOf('https://www.adobe.com') >= 0 // enabled ONLY on adobe.com  
};
```

## Dataleverantörer {#data-providers}

Med den här inställningen kan kunder samla in data från tredjepartsleverantörer av data, som Demandbase, BlueKai och anpassade tjänster, och skicka data till Target som mbox-parametrar i den globala mbox-begäran. Det stöder insamling av data från flera leverantörer via asynkrona och synkroniserade begäranden. Med den här metoden blir det enkelt att hantera flimmer av standardsidinnehåll, samtidigt som oberoende tidsgränser för varje leverantör tas med för att begränsa effekten på sidans prestanda

>[!NOTE]
>
>Dataleverantörer kräver [!DNL at.js] 1.3 eller senare.

Följande videofilmer innehåller mer information:

| Video | Beskrivning |
|--- |--- |
| [Använda Data Providers i Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html) | Data Providers är en funktion som gör att du enkelt kan skicka data från tredje part till Target. En tredje part kan vara en vädertjänst, en datahanteringsplattform eller till och med en egen webbtjänst. Sedan kan ni använda dessa data för att skapa målgrupper, målinnehåll och berika besökarprofilen. |
| [Implementera Data Providers i Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html) | Implementeringsinformation och exempel på hur du använder funktionen Adobe Target dataProviders för att hämta data från tredjepartsleverantörer och skicka dem i Target-begäran. |

The `window.targetGlobalSettings.dataProviders` -inställningen är en matris med dataleverantörer.

Varje dataleverantör har följande struktur:

| Nyckel | Typ | Beskrivning |
|--- |--- |--- |
| name | Sträng | Leverantörens namn. |
| version | Sträng | Providerversion. Den här nyckeln kommer att användas för leverantörens utveckling. |
| timeout | Nummer | Representerar providerns timeout om det här är en nätverksbegäran.  Den här nyckeln är valfri. |
| provider |  -funktion | Funktionen som innehåller logiken för hämtning av providerdata.<br>Funktionen har en enda obligatorisk parameter: `callback`. Callback-parametern är en funktion som bara ska anropas när data har hämtats eller när ett fel uppstår.<br>Återanropet förväntar sig två parametrar:<ul><li>fel: Anger om ett fel uppstod. Om allt är OK ska den här parametern anges till null.</li><li>parametrar: Ett JSON-objekt som representerar de parametrar som ska skickas i en Target-begäran.</li></ul> |

I följande exempel visas var dataleverantören använder synkroniseringskörning:

```javascript
var syncDataProvider = { 
  name: "simpleDataProvider", 
  version: "1.0.0", 
  provider: function(callback) { 
    callback(null, {t1: 1}); 
  } 
}; 
  
window.targetGlobalSettings = { 
  dataProviders: [ 
    syncDataProvider 
  ] 
};
```

After at.js-processer `window.targetGlobalSettings.dataProviders`innehåller Target-begäran en ny parameter: `t1=1`.

Följande är ett exempel om parametrarna som du vill lägga till i Target-begäran hämtas från en tredjepartstjänst, till exempel Bluekai, Demandbase o.s.v.:

```javascript
var blueKaiDataProvider = { 
   name: "blueKai", 
   version: "1.0.0", 
   provider: function(callback) { 
      // simulating network request 
     setTimeout(function() { 
       callback(null, {t1: 1, t2: 2, t3: 3}); 
     }, 1000); 
   } 
} 
  
window.targetGlobalSettings = { 
   dataProviders: [ 
      blueKaiDataProvider 
   ] 
};
```

After at.js-processer `window.targetGlobalSettings.dataProviders`kommer Target-begäran att innehålla ytterligare parametrar: `t1=1`, `t2=2` och `t3=3`.

I följande exempel används dataleverantörer för att samla in väder-API-data och skicka dem som parametrar i en Target-begäran. Målbegäran kommer att ha ytterligare parametrar, som `country` och `weatherCondition`.

```javascript
var weatherProvider = { 
      name: "weather-api", 
      version: "1.0.0", 
      timeout: 2000, 
      provider: function(callback) { 
        var API_KEY = "caa84fc6f5dc77b6372d2570458b8699"; 
        var lat = 44.426767399999996; 
        var lon = 26.1025384; 
        var url = "//api.openweathermap.org/data/2.5/weather?lang=en"; 
        var data = { 
          lat: lat, 
          lon: lon, 
          appId: API_KEY 
        } 
 
        $.ajax({ 
          type: "GET", 
                url: url, 
          dataType: "json", 
          data: data, 
          success: function(data) { 
            console.log("Weather data", data); 
            callback(null, { 
              country: data.sys.country, 
              weatherCondition: data.weather[0].main 
            }); 
          }, 
          error: function(err) { 
            console.log("Error", err); 
            callback(err); 
          } 
        });         
      } 
    }; 
 
    window.targetGlobalSettings = { 
      dataProviders: [weatherProvider] 
    };
```

Tänk på följande när du arbetar med `dataProviders` inställning:

* Om dataleverantörerna har lagts till i `window.targetGlobalSettings.dataProviders` är asynkrona kommer de att köras parallellt. Besökar-API-begäran körs parallellt med funktioner som lagts till i `window.targetGlobalSettings.dataProviders` för att tillåta en minimal väntetid.
* at.js försöker inte cachelagra data. Om dataleverantören bara hämtar data en gång, bör dataleverantören se till att data cachelagras och, när providerfunktionen anropas, hantera cachedata för det andra anropet.

## Skyddsprofil för innehåll {#content-security}

at.js 2.3.0+ stöder inställning av Content Security Policy-noces för SCRIPT- och STYLE-taggar som läggs till på sidan DOM när levererade Target-erbjudanden används.

Strängarna SCRIPT och STYLE ska anges i `targetGlobalSettings.cspScriptNonce` och `targetGlobalSettings.cspStyleNonce` före inläsning av .js 2.3.0+. Se ett exempel nedan:

```javascript
...
<head>
 <script nonce="<script_nonce_value>">
window.targetGlobalSettings = {
  cspScriptNonce: "<csp_script_nonce_value>",
  cspStyleNonce: "<csp_style_nonce_value>"
};
 </script>
 <script nonce="<script_nonce_value>" src="at.js"></script>
...
</head>
...
```

Efter `cspScriptNonce` och `cspStyleNonce` -inställningarna anges, anger at.js 2.3.0+ dessa som nonce-attribut för alla SCRIPT- och STYLE-taggar som läggs till i DOM när Target-erbjudanden används.

## Hybrid-personalisering {#server-state}

`serverState` är en inställning som är tillgänglig i at.js v2.2+ som kan användas för att optimera sidprestanda när en hybridintegrering av Target implementeras. Hybrid-integrering innebär att du använder både at.js v2.2+ på klientsidan och leverans-API:t eller en Target SDK på serversidan för att leverera upplevelser. `serverState` ger at.js v2.2+ möjlighet att tillämpa upplevelser direkt från innehåll som hämtas på serversidan och returneras till klienten som en del av den sida som skickas.

### Krav

Du måste ha en hybridintegrering av [!DNL Target].

* **Serversidan**: Du måste använda den nya [leverans-API](https://developers.adobetarget.com/api/delivery-api/) eller [Mål-SDK](https://developers.adobetarget.com/api/delivery-api/#section/SDKs).
* **Klientsidan**: Du måste använda [at.js version 2.2 eller senare](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/).

### Kodexempel

Mer information om hur detta fungerar finns i kodexemplen nedan som du skulle ha på servern. Koden förutsätter att du använder [Target Node.js SDK](https://github.com/adobe/target-nodejs-sdk).

```javascript
// First, we fetch the offers via Target Node.js SDK API, as usual
const targetResponse = await targetClient.getOffers(options);
// A successfull response will contain Target Delivery API request and response objects, which we need to set as serverState
const serverState = {
  request: targetResponse.request,
  response: targetResponse.response
};
// Finally, we should set window.targetGlobalSettings.serverState in the returned page, by replacing it in a page template, for example
const PAGE_TEMPLATE = `
<!doctype html>
<html>
<head>
  ...
  <script>
    window.targetGlobalSettings = {
      overrideMboxEdgeServer: true,
      serverState: ${JSON.stringify(serverState, null, " ")}
    };
  </script>
  <script src="at.js"></script>
</head>
...
</html>
`;
// Return PAGE_TEMPLATE to the client ...
```

Ett exempel `serverState` objekt-JSON för vyförhämtning ser ut så här:

```
{
 "request": {
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "context": {
   "channel": "web",
   "timeOffsetInMinutes": 0
  },
  "experienceCloud": {
   "analytics": {
    "logging": "server_side",
    "supplementalDataId": "7D3AA246CC99FD7F-1B3DD2E75595498E"
   }
  },
  "prefetch": {
   "views": [
    {
     "address": {
      "url": "my.testsite.com/"
     }
    }
   ]
  }
 },
 "response": {
  "status": 200,
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "client": "testclient",
  "edgeHost": "mboxedge21.tt.omtrdc.net",
  "prefetch": {
   "views": [
    {
     "name": "home",
     "key": "home",
     "options": [
      {
       "type": "actions",
       "content": [
        {
         "type": "setHtml",
         "selector": "#app > DIV.app-container:eq(0) > DIV.page-container:eq(0) > DIV:nth-of-type(2) > SECTION.section:eq(0) > DIV.container:eq(1) > DIV.heading:eq(0) > H1.title:eq(0)",
         "cssSelector": "#app > DIV:nth-of-type(1) > DIV:nth-of-type(1) > DIV:nth-of-type(2) > SECTION:nth-of-type(1) > DIV:nth-of-type(2) > DIV:nth-of-type(1) > H1:nth-of-type(1)",
         "content": "<span style=\"color:#FF0000;\">Latest</span> Products for 2020"
        }
       ],
       "eventToken": "t0FRvoWosOqHmYL5G18QCZNWHtnQtQrJfmRrQugEa2qCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
       "responseTokens": {
        "profile.memberlevel": "0",
        "geo.city": "dublin",
        "activity.id": "302740",
        "experience.name": "Experience B",
        "geo.country": "ireland"
       }
      }
     ],
     "state": "J+W1Fq18hxliDDJonTPfV0S+mzxapAO3d14M43EsM9f12A6QaqL+E3XKkRFlmq9U"
    }
   ]
  }
 }
}
```

När sidan har lästs in i webbläsaren använder at.js alla [!DNL Target] erbjudanden från `serverState` direkt, utan att utlösa några nätverksanrop mot [!DNL Target] kant. At.js döljer dessutom bara de DOM-element för vilka [!DNL Target] Erbjudandena finns i det innehåll som hämtas på servern, vilket positivt påverkar sidladdningsprestanda och slutanvändarupplevelsen.

### Viktiga anteckningar

Tänk på följande när du använder `serverState`:

* För närvarande stöder at.js v2.2 endast leverans av upplevelser via serverState för:

   * VEC-skapade aktiviteter som körs vid sidinläsning.
   * Förhämtade vyer.

      Om SPA använder [!DNL Target] Vyer och `triggerView()` i API:t at.js, cache-lagrar at.js v2.2 innehållet för alla vyer som har förhämtats på serversidan och tillämpar dessa så snart varje vy aktiveras via `triggerView()`, utan att anropa Target för att hämta ytterligare innehåll.

   * **Anteckning**: För närvarande stöds inte lådor som hämtats på serversidan i `serverState`.

* Vid användning `serverState `erbjudanden, at.js, tar hänsyn till `pageLoadEnabled` och `viewsEnabled` inställningar, t.ex. sidladdningserbjudanden kommer inte att tillämpas om `pageLoadEnabled` inställningen är false.

   Aktivera det här alternativet om du vill aktivera de här inställningarna **[!UICONTROL Administration]> [!UICONTROL Implementation] > [!UICONTROL Edit] >[!UICONTROL Page Load Enabled]**.

   ![Inställningar för sidinläsning aktiverat](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* Om du använder `serverState` och använda `<script>` -taggar i det returnerade innehållet, se till att ditt HTML-innehåll använder `<\/script>` i stället för `</script>`. Om du använder `</script>`, tolkar webbläsaren `</script>` som slutet på ett textbundet SCRIPT och kan komma att bryta HTML-sidan.

### Ytterligare resurser

Läs mer om hur `serverState` fungerar, se följande resurser:

* [Exempelkod](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [Exempelapp för SPA med enkelsidigt program `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo).
