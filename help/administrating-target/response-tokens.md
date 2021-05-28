---
keywords: svarstoken;tokens;plugins;plugin-program;at.js;response
description: Lär dig hur du använder svarstoken i Adobe [!DNL Target] utdataspecifik information för felsökning och integrering med tredjepartssystem (som Clicktale).
title: Vad är svarstoken och hur använder jag dem?
feature: Administration och konfiguration
role: Administrator
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: fe63e3922ec0e4457c72d041cabb8e863f99cbd8
workflow-type: tm+mt
source-wordcount: '1605'
ht-degree: 0%

---

# Svarstoken

Med svarstoken kan du automatiskt få ut information som är specifik för [!DNL Adobe Target] till ditt varumärkes webbsida. Den här informationen kan innehålla information om aktivitet, erbjudande, upplevelse, användarprofil, geo-information med mera. De här detaljerna innehåller extra svarsdata som kan delas med interna eller externa verktyg eller som kan användas för felsökning.

Med svarstoken kan du välja vilka variabler (i nyckelvärdepar) som ska användas och sedan aktivera att de skickas som en del av ett [!DNL Target]-svar. Du aktiverar en variabel med växeln och variabeln skickas med [!DNL Target] svar, som kan valideras i nätverksanrop. Svarstoken fungerar även i [!UICONTROL Preview]-läge.

En viktig skillnad mellan plugin-program och svarstoken är att plugin-program levererar JavaScript till sidan som körs vid leverans. Svarstoken levererar emellertid ett objekt som sedan kan läsas och hanteras med händelseavlyssnare. Svarstoken är säkrare och gör det enklare att utveckla och underhålla tredjepartsintegreringar.

>[!NOTE]
>
>Svarstoken är tillgängliga med [!DNL Adobe Experience Platform Web SDK] version 2.5.0 eller senare (version schemalagd till 1 juni 2021) och med at.js version 1.1 eller senare.

| Mål-SDK | Föreslagna åtgärder |
|--- |--- |
| [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) | Kontrollera att du använder Platform Web SDK version 2.5.0 eller senare. Information om hur du hämtar den senaste versionen av Platform Web SDK finns i [Installera SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) i *översikten för Platform Web SDK*-guiden. Information om de nya funktionerna i respektive version av Platform Web SDK finns i [Versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html) i *översikten för Platform Web SDK*-handboken. |
| [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) | Kontrollera att du använder at.js version 1.1 eller senare. Information om hur du hämtar den senaste versionen av at.js finns i [Hämta på.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md). Information om de nya funktionerna i varje version av at.js finns i [at.js Versionsinformation](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).<br>Kunder som använder at.js uppmuntras att använda svarstoken och gå bort från plugin-program. Vissa plugin-program som är beroende av interna metoder som finns i mbox.js, men inte i at.js, levereras men misslyckas. Mer information finns i [at.js-begränsningar](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md). |

## Använda svarstoken {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. Kontrollera att du använder Platform Web SDK version 2.5.0 (eller senare) eller at.js version 1.1 (eller senare).

   Mer information:

   * **SDK** för plattformswebben: Se  [Installera ](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) SDK i översiktsguiden för  *Platform Web SDK* .
   * **at.js**: Se  [Hämta på.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_1E1F958F9CCC4E35AD97581EFAF659E2).

1. I [!DNL Target] klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Response Tokens]**.

   ![](assets/response_tokens-new.png)

1. Aktivera önskade svarstoken, t.ex. `activity.id` och `option.id`.

   Följande parametrar är tillgängliga som standard:

   | Typ | Parameter | Anteckningar |
   |--- |--- |--- |
   | Inbyggda profiler | `profile.activeActivities` | Returnerar en array med `activityIds` som besökaren är kvalificerad för. Det ökar efterhand som användarna kvalificerar sig. På en sida med två [!DNL Target]-begäranden som levererar två olika aktiviteter, innehåller den andra begäran till exempel båda aktiviteterna. |
   |  | `profile.isFirstSession` | Returnerar &quot;true&quot; eller &quot;false&quot;. |
   |  | `profile.isNewSession` | Returnerar &quot;true&quot; eller &quot;false&quot;. |
   |  | `profile.daysSinceLastVisit` | Returnerar antalet dagar sedan besökarens senaste besök. |
   |  | `profile.tntId` | Returnerar besökarens tntID |
   |  | `profile.marketingCloudVisitorId` | Returnerar besökarens Experience Cloud Visitor-ID. |
   |  | `profile.thirdPartyId` | Returnerar besökarens tredjeparts-ID. |
   |  | `profile.categoryAffinity` | Returnerar besökarens favoritkategori. |
   |  | `profile.categoryAffinities` | Returnerar en array med besökarens fem populäraste kategorier som strängar. |
   | Aktivitet | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`option.name`<br>`option.id` | Information om den aktuella aktiviteten. Observera att&quot;option&quot; är lika med&quot;offer&quot;. |
   | Geo | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | Mer information om hur du använder geomål i aktiviteter finns i [Geo](/help/c-target/c-audiences/c-target-rules/geo.md). |
   | Trafikallokeringsmetod<br>(Gäller endast för aktiviteter av typen [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization].) | `experience.trafficAllocationId` | Returnerar 0 om en besökare har fått en upplevelse av att vara i&quot;kontrolltrafik&quot; och 1 om en besökare har fått en upplevelse av den&quot;riktade&quot; trafikfördelningen. |
   |  | `experience.trafficAllocationType` | Returnera&quot;control&quot; eller&quot;target&quot;. |

   Attribut för användarprofiler och kundattribut visas också i listan.

   >[!NOTE]
   >
   >Parametrar med specialtecken visas inte i listan. Endast alfanumeriska tecken och understreck stöds.

1. (Villkorligt) Om du vill använda en profilparameter som en svarstoken, men parametern inte har skickats via en [!DNL Target]-begäran och därför inte har lästs in i användargränssnittet för [!DNL Target], kan du använda knappen [!UICONTROL Add Response Token] för att lägga till profilen i användargränssnittet.

   Klicka på **[!UICONTROL Add Response Token]**, ange tokennamnet och klicka sedan på **[!UICONTROL Activate]**.

   ![](assets/response_token_create.png)

1. Skapa en aktivitet.

## Lyssna efter svar och läs svarstoken

Den process som du använder för att avlyssna [!DNL Target]-svar och läsa svarstoken skiljer sig åt beroende på om du har en [!DNL Platform Web SDK]- eller at.js-implementering.

### ![Adobe Experience Platform Web SDK ](/help/assets/platform.png) [!DNL Platform Web SDK] badgemed objektklassen Handle

Använd objektklassen Handle, som har ett metadata-objekt och ett dataobjekt som ska avlyssna [!DNL Target]-svar och läsa svarstoken.

I följande svarsexempel läggs en anpassad [!DNL Platform Web SDK]-händelsehanterare till direkt på HTML-sidan (tabellen förklarar vilka objekt som används i koden):

| Objekt | Information |
| --- | --- |
| Typ - Personalization.Decision | Anger om beslutet fattades av [!DNL Target]- eller Offer decisioning-providern. |
| DecisionProvider - TGT | TGT-[!DNL Target]. [!DNL Target] innehåller metadata och värden för svarstoken för sidan. |
| Meta | Metadata som skickas till sidan. |
| Data | Värden för de metadata som skickas till sidan. |

```html
<html>

<head>
 ...
 <script src="alloy.js"></script>
 <script>
  {
   "requestId": "4d0a7cfd-952c-408c-b3b8-438edc38250a",
   "handle": [{
    "type": "personalization:decisions",
    "payload": [{
     "id": "....",
     "scope": "__view__",
     "scopeDetails": {
      "decisionProvider": "TGT",
      "activity": {
       "id": "..."
      },
      "experience": {
       "id": "...."
      }
     },
     "items": [{
      "id": "123",
      "schema": "https://ns.adobe.com/personalization/dom-action",
      "meta": {
       "activity.id": "...",
       "activity.name": "...",
       "profile.foo": "...",
       "profile.bar": "..."
      },
      "data": {
       "id": "123",
       "type": "setHtml",
       "selector": "#foo",
       "prehidingSelector": "#foo",
       "content": "<div>Hello world</div>"
      }
     }]
    }]
   }]
  }
  });
 </script>
</head>

<body>
 ...
</body>

</html>
```

### ![at.js ](/help/assets/atjs.png) badgeat.js med anpassade händelser

Använd [at.js anpassade händelser](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) för att lyssna efter [!DNL Target]-svaret och läsa svarstoken.

Följande kodexempel lägger till en [!DNL at.js] anpassad händelsehanterare direkt på HTML-sidan:

```html
<html> 
  <head> 
    .... 
    <script src="at.js"></script> 
    <script> 
      document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
        console.log("Request succeeded", e.detail); 
      }); 
    </script> 
  <head> 
  <body> 
  ... 
  </body> 
</html>
```

## Vanliga frågor om svarstoken {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**Vilken roll krävs för att aktivera eller inaktivera svarstoken?**

Svarstoken kan bara aktiveras eller inaktiveras av användare med rollen [!DNL Target] [!UICONTROL Administrator].

**Vad händer om jag kör [!DNL Platform Web SDK] 2.5.0 (eller tidigare)?

Du har inte åtkomst till svarstoken.

**Vad händer om jag kör på .js 1.0 (eller tidigare)?**

Svarstoken visas, men at.js kan inte använda dem.

**Kan jag ha både  [!DNL Target Classic] plugin-program och svarstoken aktiva samtidigt?**

Plugins och svarstoken finns tillgängliga parallellt. plugin-program kommer dock att bli inaktuella i framtiden.

**Levereras svarstoken via alla  [!DNL Target] svar eller endast via  [!DNL Target] svar som levererar en aktivitet?**

Svarstoken levereras endast via [!DNL Target]-svar som levererar en aktivitet.

**Mitt  [!DNL Target Classic] plugin-program innehöll JavaScript. Hur replikerar jag funktionaliteten med hjälp av svarstoken?**

När du migrerar till svarstoken måste den här typen av JavaScript finnas i kodbas- eller tagghanteringslösningen. Du kan utlösa den här koden med anpassade [!DNL Platform Web SDK]- eller [!DNL at.js]-händelser och skicka svarstokenvärden till dina JavaScript-funktioner.

**Varför visas inte min profil-/kundattributparameter i svarstokenlistan?**

[!DNL Target] uppdaterar normalt parametrar var 15:e minut. Den här uppdateringen är beroende av användaråtgärder och data uppdateras bara när du visar svarstokensidan. Om parametrarna inte visas i svarstokenlistan har [!DNL Target] inte uppdaterat data än.

Om parametern innehåller något annat än icke-alfanumeriska tecken eller någon annan symbol än understreck, visas inte parametern i listan. För närvarande stöds endast alfanumeriska tecken och understreck.

**Levererar svarstoken fortfarande innehåll om den använder ett borttaget profilskript eller en profilparameter?**

Svarstoken extraherar information från användarprofiler och skickar sedan informationen. Om du tar bort ett profilskript eller en parameter innebär det inte att informationen har tagits bort från användarprofilerna. Användarprofilerna har fortfarande data som motsvarar profilskriptet. Svarstoken fortsätter leverera innehållet. För användare som inte har den informationen sparad i sina profiler, eller för nya besökare, levereras inte denna token eftersom informationen inte finns i deras profiler.

[!DNL Target] tar inte bort token automatiskt. Om du tar bort ett profilskript och inte längre vill att variabeln ska levereras, måste du inaktivera variabeln själv.

**Jag har bytt namn på mitt profilskript, men varför är den token som använder skriptet fortfarande aktiv med det gamla namnet?**

Som nämnts ovan fungerar svarstoken på den profilinformation som har sparats för användare. Även om du har bytt namn på ditt profilskript kommer användare som har besökt din webbplats att spara det gamla profilskriptvärdet i sina profiler. Token fortsätter att hämta det gamla värdet som redan har sparats i användarprofilerna. Om du nu vill leverera innehåll med det nya namnet måste du inaktivera den tidigare variabeln och aktivera den nya variabeln.

**Om mina attribut har ändrats, när tas de bort från listan?**

[!DNL Target] uppdaterar attribut med regelbundna intervall. Alla attribut som inte är aktiverade tas bort under nästa uppdatering. Om du har ett attribut som har aktiverats och tagits bort tas det skriptet inte bort från attributlistan förrän du har inaktiverat det. Du tog till exempel bort ett profilskript som användes som token. [!DNL Target] tar endast bort de inaktiverade attributen från listan när de tas bort eller byter namn.

## Skicka data till Google Analytics

I följande avsnitt beskrivs hur du skickar [!DNL Target]-data till Google Analytics. Data som skickas av svarstoken kan också skickas till andra tredjepartsintegreringar.

### ![AEP ](/help/assets/platform.png) badgeSkicka data till Google Analytics via Platform Web SDK

Google Analytics kan skicka data via Platform Web SDK version 2.5.0 (eller senare) genom att lägga till följande kod på HTML-sidan:

(Kod kommer)

### ![at.js ](/help/assets/atjs.png) badgeSkicka data till Google Analytics via at.js {#section_04AA830826D94D4EBEC741B7C4F86156}

Google Analytics kan skicka data via at.js genom att lägga till följande kod på HTML-sidan:

```javascript
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
<script type="text/javascript"> 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
    var tokens = e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
 
    var activityNames = []; 
    var experienceNames = []; 
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      activityNames.push(token["activity.name"]); 
      experienceNames.push(token["experience.name"]); 
    }); 
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
    }); 
  }); 
 
  function isEmpty(val) { 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## Felsökning

I följande avsnitt finns information om felsökning av svarstoken:

### ![at.js ](/help/assets/atjs.png) badgeGoogle Analytics och debugging

Med följande kod kan du felsöka med Google Analytics:

```javascript
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
<script type="text/javascript"> 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
    var tokens = e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
 
    var activityNames = []; 
    var experienceNames = []; 
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      activityNames.push(token["activity.name"]); 
      experienceNames.push(token["experience.name"]); 
    }); 
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
    }); 
  }); 
 
  function isEmpty(val) { 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
```

### Felsöka med motsvarigheten till plug-inen ttMeta

Motsvarigheten till ttMeta-plugin-programmet för felsökning kan skapas genom att lägga till följande kod på HTML-sidan:

```javascript
<script type="text/javascript" > 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function (e) { 
    window.ttMETA= typeof(window.ttMETA)!="undefined" ? window.ttMETA : []; 
 
    var tokens=e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
     
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      window.ttMETA.push({ 
        'CampaignName': token["activity.name"], 
        'CampaignId' : token["activity.id"], 
        'RecipeName': token["experience.name"], 
        'RecipeId': token["experience.id"], 
        'OfferId': token["option.id"], 
        'OfferName': token["option.name"], 
        'MboxName': e.detail.mbox}); 
      console.log(ttMETA); 
    }); 
  }); 
 
  function isEmpty(val){ 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## ![at.](/help/assets/atjs.png) jsTraining Video: Svarstoken och anpassade at.js-händelser {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

I följande video förklaras hur du använder svarstoken och anpassade at.js-händelser för att dela profilinformation från [!DNL Target] till tredjepartssystem.

>[!NOTE]
>
>Menygränssnittet [!DNL Target] [!UICONTROL Administration] (tidigare [!UICONTROL Setup]) har omarbetats för att ge bättre prestanda, minska den underhållstid som krävs när nya funktioner släpps och för att förbättra användarupplevelsen i hela produkten. Informationen i följande video är korrekt: Men alternativen finns på något olika platser.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
