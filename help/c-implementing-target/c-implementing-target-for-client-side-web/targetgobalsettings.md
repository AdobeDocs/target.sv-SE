---
keywords: serverstate;targetGlobalSettings;targetSettings;globalSettings;globalSettings;global settings;at.js;functions;function;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVieinställningar sibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders;Hybrid Personalization;deviceIdLifetime
description: Information om funktionen targetGlobalSettings() för Adobe Target JavaScript-biblioteket at.js.
title: targetglobalsettings()
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1719'
ht-degree: 0%

---


# targetGlobalSettings()

Du kan åsidosätta inställningarna i at.js-biblioteket med `targetGlobalSettings()`, i stället för att konfigurera inställningarna i gränssnittet för [!DNL Target] Standard/Premium eller genom att använda REST API:er.

Det finns några användningsområden, särskilt när at.js levereras via [!DNL Dynamic Tag Management] (DTM) när du vill åsidosätta vissa inställningar.

## Inställningar {#section_42C759AE9B524A43B8659018677224B8}

Du kan åsidosätta följande inställningar:

### bodyHiddenStyle

* **Typ**: Sträng
* **Standardvärde**: body { opacity: 0 }
* **Beskrivning**: Används endast när du  `globalMboxAutocreate === true` vill minimera risken för flimmer.

   Mer information finns i [How at.js Hantera flimmer](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md).

### bodyHidingEnabled

* **Typ**: Boolean
* **Standardvärde**: true
* **Beskrivning**: Används för att styra flimmer när  `target-global-mbox` används för att leverera erbjudanden som skapats i Visual Experience Composer, även kallat visuella erbjudanden.

### clientCode

* **Typ**: Sträng
* **Standardvärde**: Värdet anges via användargränssnittet.
* **Beskrivning**: Representerar klientkoden.

### cookieDomain

* **Typ**: Sträng
* **Standardvärde**: Ange om möjligt till toppnivådomänen.
* **Beskrivning**: Representerar domänen som används när cookies sparas.

### crossDomain

* **Typ**: Sträng
* **Standardvärde**: Värdet anges via användargränssnittet.
* **Beskrivning**: Anger om spårning mellan domäner är aktiverat eller inte. Tillåtna värden är: inaktiverat, aktiverat eller endast x.

### cspScriptNonce

* **Typ**: Se  [Säkerhetspolicy ](#content-security) för innehåll nedan.
* **Standardvärde**: Se  [Säkerhetspolicy ](#content-security) för innehåll nedan.
* **Beskrivning**: Se  [Säkerhetspolicy ](#content-security) för innehåll nedan.

### cspStyleNonce

* **Typ**: Se  [Säkerhetspolicy ](#content-security) för innehåll nedan.
* **Standardvärde**: Se  [Säkerhetspolicy ](#content-security) för innehåll nedan.
* **Beskrivning**: Se  [Säkerhetspolicy ](#content-security) för innehåll nedan.

### dataProviders

* **Typ**: Se  [Data ](#data-providers) Providers nedan.
* **Standardvärde**: Se  [Data ](#data-providers) Providers nedan.
* **Beskrivning**: Se  [Data ](#data-providers) Providers nedan.

### defaultContentHiddenStyle

* **Typ**: Sträng
* **Standardvärde**: synlighet: dold
* **Beskrivning**: Används endast för omslutningsrutor som använder DIV med klassnamnet &quot;mboxDefault&quot; och körs via  `mboxCreate()`,  `mboxUpdate()`eller  `mboxDefine()` för att dölja standardinnehåll.

### defaultContentVisibleStyle

* **Typ**: Sträng
* **Standardvärde**: synlighet: visible
* **Beskrivning**: Används endast för omslutningsrutor som använder DIV med klassnamnet&quot;mboxDefault&quot; och körs via  `mboxCreate()`,  `mboxUpdate()`eller  `mboxDefine()` för att visa det tillämpade erbjudandet om något eller standardinnehåll.

### deviceIdLifetime

* **Typ**: Nummer
* **Standardvärde**: 63244800000 ms = 2 år
* **Beskrivning**: Hur lång tid  `deviceId` sparas i cookies.

>[!NOTE]
>
>Inställningen deviceIdLifetime kan åsidosättas i version 2.3.1 eller senare av at.js.

### aktiverad

* **Typ**: Boolean
* **Standardvärde**: true
* **Beskrivning**: När det här alternativet är aktiverat utförs en  [!DNL Target] begäran om att hämta upplevelser och DOM-manipulering för att återge upplevelserna automatiskt. Dessutom kan [!DNL Target]-anrop utföras manuellt via `getOffer(s)` / `applyOffer(s)`.

   När [!DNL Target]-begäranden är inaktiverade körs de inte automatiskt eller manuellt.

### globalMboxAutoCreate

* **Typ**: Nummer
* **Standardvärde**: Värdet anges via användargränssnittet.
* **Beskrivning**: Anger om den globala mbox-begäran ska utlösas eller inte.

### imsOrgId

* **Typ**: Sting
* **Standardvärde**: true
* **Beskrivning**: Representerar IMS ORG ID.

### optoutEnabled

* **Typ**: Boolean
* **Standardvärde**: false
* **Beskrivning**: Anger om Target ska anropa  `isOptedOut()` funktionen för Visitor API. Detta är en del av aktiveringen av Device Graph.

### overrideMboxEdgeServer

* **Typ**: Boolean
* **Standardvärde**: true (true med början från at.js version 1.6.2)
* **Beskrivning**: Anger om vi ska använda  `<clientCode>.tt.omtrdc.net` domän eller  `mboxedge<clusterNumber>.tt.omtrdc.net` domän.

   Om det här värdet är true sparas `mboxedge<clusterNumber>.tt.omtrdc.net`-domänen i en cookie. För närvarande fungerar inte med [CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) när du använder at.js-versioner före at.js 1.8.2 och at.js 2.3.1. Om det här är ett problem för dig bör du överväga att [uppdatera at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) till en nyare version som stöds.

### overrideMboxEdgeServerTimeout

* **Typ**: Nummer
* **Standardvärde**: 1860000 => 31 minuter
* **Beskrivning**: Anger den cookie-livstid som innehåller  `mboxedge<clusterNumber>.tt.omtrdc.net` värdet.

### pageLoadEnabled

* **Typ**: Boolean
* **Standardvärde**: true
* **Beskrivning**: När det här alternativet är aktiverat hämtar du automatiskt upplevelser som måste returneras vid sidinläsning.

### secureOnly

* **Typ**: Boolean
* **Standardvärde**: false
* **Beskrivning**: Anger om at.js endast ska använda HTTPS eller tillåtas växla mellan HTTP och HTTPS baserat på sidprotokollet.

### selectorsPollingTimeout

* **Typ**: Nummer
* **Standardvärde**: 5000 ms = 5 s
* **Beskrivning**: I at.js 0.9.6  [!DNL Target] introducerades den här nya inställningen som kan åsidosättas via  `targetGlobalSettings`.

   Inställningen `selectorsPollingTimeout` representerar hur länge klienten är beredd att vänta på att alla element som identifieras av väljarna ska visas på sidan.

   Aktiviteter som skapas via Visual Experience Composer (VEC) har erbjudanden som innehåller väljare.

### serverDomain

* **Typ**: Sträng
* **Standardvärde**: Värdet anges via användargränssnittet.
* **Beskrivning**: Representerar målkantsservern.

### serverState

* **Typ**: Se  [Hybrid-](#server-state) personalisering nedan.
* **Standardvärde**: Se  [Hybrid-](#server-state) personalisering nedan.
* **Beskrivning**: Se  [Hybrid-](#server-state) personalisering nedan.

### timeout

* **Typ**: Nummer
* **Standardvärde**: Värdet anges via användargränssnittet.
* **Beskrivning**: Representerar timeout för  [!DNL Target] edge-begäran.

### viewsEnabled

* **Typ**: Boolean
* **Standardvärde**: true
* **Beskrivning**: När det här alternativet är aktiverat hämtas vyer automatiskt som måste returneras vid sidinläsning. Vyer stöds i at.js 2.*Endast* .

### visitorApiTimeout

* **Typ**: Nummer
* **Standardvärde**: 2000 ms = 2 s
* **Beskrivning**: Representerar tidsgränsen för  [!UICONTROL Visitor API] begäran.

## Användning {#section_9AD6FA3690364F7480C872CB55567FB0}

Den här funktionen kan definieras innan at.js har lästs in eller i **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Edit at.js Settings]** > **[!UICONTROL Code Settings]** > **[!UICONTROL Library Header]**.

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
>Data Providers kräver [!DNL at.js] 1.3 eller senare.

Följande videofilmer innehåller mer information:

| Video | Beskrivning |
|--- |--- |
| [Använda Data Providers i Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html) | Data Providers är en funktion som gör att du enkelt kan skicka data från tredje part till Target. En tredje part kan vara en vädertjänst, en datahanteringsplattform eller till och med en egen webbtjänst. Sedan kan ni använda dessa data för att skapa målgrupper, målinnehåll och berika besökarprofilen. |
| [Implementera Data Providers i Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html) | Implementeringsinformation och exempel på hur du använder funktionen Adobe Target dataProviders för att hämta data från tredjepartsleverantörer och skicka dem i Target-begäran. |

Inställningen `window.targetGlobalSettings.dataProviders` är en matris med dataleverantörer.

Varje dataleverantör har följande struktur:

| Nyckel | Typ | Beskrivning |
|--- |--- |--- |
| name | Sträng | Leverantörens namn. |
| version | Sträng | Providerversion. Den här nyckeln kommer att användas för leverantörens utveckling. |
| timeout | Nummer | Representerar providerns timeout om det här är en nätverksbegäran.  Den här nyckeln är valfri. |
| provider |  -funktion | Funktionen som innehåller logiken för hämtning av providerdata.<br>Funktionen har en enda obligatorisk parameter:  `callback`. Callback-parametern är en funktion som bara ska anropas när data har hämtats eller när ett fel uppstår.<br>Återanropet förväntar sig två parametrar:<ul><li>fel: Anger om ett fel uppstod. Om allt är OK ska den här parametern anges till null.</li><li>parametrar: Ett JSON-objekt som representerar de parametrar som ska skickas i en Target-begäran.</li></ul> |

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

Efter at.js-processerna `window.targetGlobalSettings.dataProviders` innehåller Target-begäran en ny parameter: `t1=1`.

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

Efter at.js-processerna `window.targetGlobalSettings.dataProviders` innehåller Target-begäran ytterligare parametrar: `t1=1`, `t2=2` och `t3=3`.

I följande exempel används dataleverantörer för att samla in väder-API-data och skicka dem som parametrar i en Target-begäran. Målbegäran kommer att ha ytterligare parametrar, till exempel `country` och `weatherCondition`.

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

Tänk på följande när du arbetar med inställningen `dataProviders`:

* Om dataleverantörerna som läggs till i `window.targetGlobalSettings.dataProviders` är asynkrona körs de parallellt. Besökar-API-begäran körs parallellt med funktioner som lagts till i `window.targetGlobalSettings.dataProviders` för att ge en minimal väntetid.
* at.js försöker inte cachelagra data. Om dataleverantören bara hämtar data en gång, bör dataleverantören se till att data cachelagras och, när providerfunktionen anropas, hantera cachedata för det andra anropet.

## Säkerhetsprincip för innehåll {#content-security}

at.js 2.3.0+ stöder inställning av Content Security Policy-noces för SCRIPT- och STYLE-taggar som läggs till på sidan DOM när levererade Target-erbjudanden används.

Strängarna SCRIPT och STYLE ska anges i `targetGlobalSettings.cspScriptNonce` och `targetGlobalSettings.cspStyleNonce` motsvarande, före inläsningen av at.js 2.3.0+. Se ett exempel nedan:

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

När inställningarna för `cspScriptNonce` och `cspStyleNonce` har angetts anger at.js 2.3.0+ dessa som nonce-attribut för alla SCRIPT- och STYLE-taggar som läggs till i DOM när Target-erbjudanden tillämpas.

## Hybrid-personalisering {#server-state}

`serverState` är en inställning som är tillgänglig i at.js v2.2+ som kan användas för att optimera sidprestanda när en hybridintegrering av Target implementeras. Hybrid-integrering innebär att du använder både at.js v2.2+ på klientsidan och leverans-API:t eller en Target SDK på serversidan för att leverera upplevelser. `serverState` ger at.js v2.2+ möjlighet att tillämpa upplevelser direkt från innehåll som hämtas på serversidan och returneras till klienten som en del av den sida som skickas.

### Krav

Du måste ha en hybridintegrering av [!DNL Target].

* **Serversidan**: Du måste använda det nya  [leverans-API:t ](https://developers.adobetarget.com/api/delivery-api/) eller  [mål-SDK](https://developers.adobetarget.com/api/delivery-api/#section/SDKs).
* **Klientsidan**: Du måste använda  [at.js version 2.2 eller senare](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

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

Ett `serverState`-objektets JSON-exempel för vyförhämtning ser ut så här:

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

När sidan har lästs in i webbläsaren tillämpar at.js omedelbart alla [!DNL Target]-erbjudanden från `serverState`, utan att utlösa några nätverksanrop mot kanten [!DNL Target]. Dessutom kan at.js bara dölja DOM-element som [!DNL Target] erbjuder på den hämtade serversidan, vilket positivt påverkar sidinläsningsprestanda och slutanvändarupplevelsen.

### Viktiga anteckningar

Tänk på följande när du använder `serverState`:

* För närvarande stöder at.js v2.2 endast leverans av upplevelser via serverState för:

   * VEC-skapade aktiviteter som körs vid sidinläsning.
   * Förhämtade vyer.

      Om du SPA använda [!DNL Target]-vyer och `triggerView()` i API:t at.js, cachelagrar at.js v2.2 innehållet för alla vyer som är förhämtade på servern och använder dessa så snart varje vy aktiveras via `triggerView()`, återigen utan att anropa Target för ytterligare innehållshämtning.

   * **Obs**: För närvarande stöds inte lådor som har hämtats på serversidan i  `serverState`.

* När du tillämpar `serverState `erbjudanden tar at.js hänsyn till inställningarna `pageLoadEnabled` och `viewsEnabled`, t.ex. kommer sidinläsning inte att användas om inställningen `pageLoadEnabled` är false.

   Aktivera de här inställningarna genom att aktivera växlingen i **[!UICONTROL Administration]> [!UICONTROL Implementation] > [!UICONTROL Edit] >[!UICONTROL Page Load Enabled]**.

   ![Inställningar för sidinläsning aktiverat](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* Om du använder `serverState` och `<script>`-taggar i det returnerade innehållet måste du se till att HTML-innehållet använder `<\/script>` i stället för `</script>`. Om du använder `</script>` tolkar webbläsaren `</script>` som slutet på ett infogat SCRIPT och den kan komma att bryta HTML-sidan.

### Ytterligare resurser

Mer information om hur `serverState` fungerar finns i följande resurser:

* [Exempelkod](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [Exempelprogram för SPA med  `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo).
