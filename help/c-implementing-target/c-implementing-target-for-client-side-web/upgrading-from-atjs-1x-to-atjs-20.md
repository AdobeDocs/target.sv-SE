---
keywords: at.js releases;at.js versions;single page app;spa;cross domain;cross-domain
description: Information om hur du uppgraderar från Adobe Target på .js 1.*x* till at.js version 2.0.0
title: Uppgradera från Adobe Target at.js version 1.*x* till at.js version 2.*x*
feature: null
subtopic: Getting Started
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '2733'
ht-degree: 0%

---


# Uppgraderar från at.js 1.*x* to at.js 2.*x* {#upgrading-from-atjs-1x-to-atjs-200}

Den senaste versionen av at.js i [!DNL Adobe Target] innehåller funktionsrika uppsättningar som gör det möjligt för ditt företag att utföra personalisering på nästa generations klientteknologier. Den nya versionen fokuserar på att uppgradera at.js för att få harmonisk interaktion med Single page applications (SPA).

Här är några fördelar med att använda at.js 2.*x* som inte finns i tidigare versioner:

* Möjligheten att cachelagra alla erbjudanden vid sidinläsning för att minska antalet serveranrop till ett enda serveranrop.
* Förbättra slutanvändarnas upplevelser enormt på er webbplats, eftersom erbjudandena visas direkt via cachen utan den fördröjning som traditionella serversamtal ger.
* Enkel kodrad och engångskonfiguration för utvecklare som gör det möjligt för era marknadsförare att skapa och köra A/B- och XT-aktiviteter via VEC på era SPA.

## at.js 2.*x* -systemdiagram

Följande diagram hjälper dig att förstå arbetsflödet i at.js 2.*x* with Views och hur detta förbättrar SPA-integreringen. För att få en bättre introduktion till de koncept som används i at.js 2.*x*, se Implementering [av](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)Single Page-program.

![Målflöde med at.js 2.*x *](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| Utlysning | Detaljer |
| --- | --- |
| 1 | Samtalet returnerar [!DNL Experience Cloud ID] om användaren är autentiserad. ett annat samtal synkroniserar kund-ID:t. |
| 2 | At.js-biblioteket läses in synkront och döljer dokumentets brödtext.<br>at.js kan också läsas in asynkront med ett alternativ som gör att fragment för att dölja kan implementeras på sidan. |
| 3 | En sidinläsningsbegäran görs med alla konfigurerade parametrar (MCID, SDID och kund-ID). |
| 4 | Profilskript körs och matas sedan in i profilarkivet. Store begär kvalificerade målgrupper från Audience Library (till exempel målgrupper som delas från Adobe Analytics, Audience Management, osv.).<br>Kundattribut skickas till profilarkivet i en gruppbearbetning. |
| 5 | Baserat på parametrar för URL-begäran och profildata bestämmer du vilka aktiviteter och upplevelser som ska returneras till besökaren för den aktuella sidan och framtida vyer. [!DNL Target] |
| 6 | Målinriktat innehåll skickas tillbaka till sidan, eventuellt med profilvärden för ytterligare personalisering.<br>Målinriktat innehåll på den aktuella sidan visas så snabbt som möjligt utan att du behöver flimra standardinnehållet.<br>Målanpassat innehåll för vyer som visas som ett resultat av användaråtgärder i en SPA som cachas i webbläsaren så att det kan tillämpas direkt utan ett extra serveranrop när vyerna aktiveras via `triggerView()`. |
| 7 | Analysdata skickas till datainsamlingsservrar. |
| 8 | Målinriktade data matchas mot analysdata via SDID och bearbetas till lagringsplatsen för analysrapporter.<br>Analysdata kan sedan visas i både Analytics- och Target-rapporter via Analytics for Target-rapporter (A4T). |

Nu hämtas vyer och åtgärder från cachen och visas för användaren utan ett serveranrop, oavsett var i SPA-filen `triggerView()` implementeras. `triggerView()` skickar också en meddelandebegäran till [!DNL Target] backend-objektet för att öka antalet och registrera antalet visningar.

![Målflöde vid .js 2.*x* triggerView](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| Utlysning | Detaljer |
| --- | --- |
| 1 | `triggerView()` anropas i SPA för att återge vyn och tillämpa åtgärder för att ändra visuella element. |
| 2 | Målinnehåll för vyn läses från cachen. |
| 3 | Målinriktat innehåll visas så snabbt som möjligt utan att man behöver flimra standardinnehållet. |
| 4 | En meddelandebegäran skickas till [!DNL Target] Profile Store för att räkna besökaren i aktiviteten och ökningsvärdena. |
| 5 | Analysdata skickas till datainsamlingsservrar. |
| 6 | Måldata matchas mot Analytics-data via SDID och bearbetas till lagringsplatsen för analysrapporter. Analysdata kan sedan visas både i Analytics och Target via A4T-rapporter. |

## Driftsätt på js 2.*x* {#deploy-atjs-200}

1. Driftsätt på js 2.*x* via tillägget [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) .

   >[!NOTE]
   >
   > Att distribuera at.js med Adobe Launch är den bästa metoden.

   eller

   Ladda ned på.js 2 manuellt.*x* med Target-användargränssnittet och distribuera det med den [metod du väljer](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md).

## Borttagna at.js-funktioner

Det finns flera funktioner som har tagits bort i at.js 2.*x*.

>[!IMPORTANT]
>
>Om dessa inaktuella funktioner fortfarande används på din webbplats i .js 2.*När x* distribueras visas konsolvarningar. Det rekommenderade tillvägagångssättet vid uppgradering är att testa distributionen av at.js 2.*x* i en staging-miljö och se till att du går igenom alla varningar som har loggats i konsolen och översätter de borttagna funktionerna till nya funktioner som introducerades i at.js 2.*x*.

Du hittar de borttagna funktionerna och deras motsvarighet nedan. En fullständig lista över funktioner finns i [funktionerna](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)at.js.

>[!NOTE]
>at.js 2.*x* döljer inte längre automatiskt `mboxDefault` markerade element. Kunderna måste därför anpassa sig till fördöljningslogiken manuellt på webbplatsen eller via en tagghanterare.

### mboxCreate(mbox,params)

**Beskrivning**:

Kör en begäran och tillämpar erbjudandet på närmaste DIV med `mboxDefault` klassnamnet.

**Exempel**:

```
<div class="mboxDefault">
  default content to replace by offer
</div>
<script>
  mboxCreate('mboxName','param1=value1','param2=value2');
</script>
```

**at.js 2.*x*-motsvarighet**

Ett alternativ till `mboxCreate(mbox, params)` är `getOffer()` och `applyOffer()`.

**Exempel**:

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  var el = document.currentScript.previousElementSibling;
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2"
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: el,
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      el.style.visibility = "visible";
    }
  });
</script> 
```

### mboxDefine() och mboxUpdate()

**Beskrivning**:

Skapar en intern mappning mellan ett element och ett mbox-namn, men kör inte begäran. Används tillsammans med `mboxUpdate()`, som kör begäran och tillämpar erbjudandet på elementet som identifieras av nodeId i `mboxDefine()`. Kan även användas för att uppdatera en mbox som initierats av `mboxCreate`.

**Exempel**:

```
<div id="someId" class="mboxDefault"></div>
<script>
 mboxDefine('someId','mboxName','param1=value1','param2=value2');
 mboxUpdate('mboxName','param3=value3','param4=value4');
</script>
```

**at.js 2.*x*-motsvarighet**:

Ett alternativ till `mboxDefine()` och `mboxUpdate` är `getOffer()` och `applyOffer()`, med alternativet väljare i `applyOffer()`. På så sätt kan du mappa erbjudandet till ett element med hjälp av en CSS-väljare, inte bara en med ett ID.

**Exempel**:

```
<div id="someId" class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2",
      param3: "value3",
      param4: "value4" 
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: "#someId",
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      var el = document.getElementById("someId");
      el.style.visibility = "visible";
    }
  });
</script>
```

### adobe.target.registerExtension()

**Beskrivning**:

Tillhandahåller ett standardsätt att registrera ett specifikt tillägg.

Detta stöds inte längre och bör inte användas.

## Sammanfattning av borttagna, nya och stöds i 2. js-funktioner.*x*

| Metod | Stöds? | Nytt? | Föråldrad?<br>(Standardinnehåll visas) |
| --- | --- | --- | --- |
| `getOffer()` | Ja |  |  |
| `getOffers()` |  | Ja |  |
| `applyOffer()` | Ja |  |  |
| `applyOffers()` |  | Ja |  |
| `triggerView()` |  | Ja |  |
| `trackEvent()` | Ja |  |  |
| `mboxCreate()` |  |  | Ja |
| `mboxDefine()`<br>`mboxUpdate()` |  |  | Ja |
| `targetGlobalSettings()` | Ja |  |  |
| `Data Providers` | Ja |  |  |
| `targetPageParams()` | Ja |  |  |
| `targetPageParamsAll()` | Ja |  |  |
| `registerExtension()` |  |  | Ja |
| `At.js Custom Events` | Ja |  |  |

## Begränsningar och bildtexter

Tänk på följande begränsningar och hänvisningar:

### Konverteringsspårning

Kunder som använder `mboxCreate()` för konverteringsspårning måste använda `trackEvent()` eller `getOffer()`.

### Erbjudandeleverans

Kunder som inte ersätter `mboxCreate()` med `getOffer()` eller `applyOffer()` riskerar att inte få erbjudanden levererade.

### Can at.js 2.*x* kan användas på vissa sidor medan at.js 1.*x* eller mbox.js finns på andra sidor?

Ja, besökarprofilen bevaras på olika sidor med olika versioner och bibliotek. Cookie-formatet är detsamma.

### Ny API-användning i at.js 2.*x*

at.js 2.*x* använder ett nytt API, som vi kallar leverans-API. Om du vill felsöka om at.js anropar [!DNL Target] edge-servern korrekt kan du filtrera fliken Nätverk i webbläsarens utvecklingsverktyg till &quot;delivery&quot;, &quot;`tt.omtrdc.net`&quot; eller din klientkod. Du kommer också att märka att [!DNL Target] en JSON-nyttolast skickas i stället för nyckelvärdepar.

### Global målruta används inte längre

I at.js 2.*x* visas inte längre&quot;`target-global-mbox`&quot; synligt i nätverksanropen. I stället har vi ersatt syntaxen&quot;`target-global-mbox`&quot; med&quot;`execute > pageLoad`&quot; i JSON-nyttolasten som skickas till [!DNL Target] servrarna, vilket visas nedan:

```
{
  "id": {
    // ...
  },
  "context": {
    "channel": "web",
    // ...
  },
  "execute": {
    "pageLoad": {}
  }
}
```

Det globala mbox-konceptet introducerades för att ge [!DNL Target] information om huruvida erbjudanden och innehåll ska hämtas vid sidinläsning. Därför har vi gjort detta tydligare i vår senaste version.

### Spelar det globala mbox-namnet i at.js längre någon roll?

Kunderna kan ange ett globalt mbox-namn via [!UICONTROL Target > Administration > Implementation > Edit at.js Settings]. Den här inställningen används av [!DNL Target] edge-servrarna för att översätta execute > pageLoad till det globala mbox-namnet som visas i [!DNL Target] gränssnittet. Detta gör att kunderna kan fortsätta att använda serversidans API:er, den formulärbaserade dispositionen, profilskript och skapa målgrupper med hjälp av den globala mbox-namnet. Vi rekommenderar att du även ser till att samma globala mbox-namn är konfigurerat på [!UICONTROL Administration > Visual Experience Composer] sidan om du fortfarande har sidor som använder at.js 1.*x* eller mbox.js, som på följande bilder.

![Dialogrutan Ändra at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

och

![Anpassad global mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

### Måste inställningen för att automatiskt skapa en global mbox aktiveras för at.js 2.*x*?

I de flesta fall, ja. Den här inställningen anger at.js 2.*x* för att skicka en begäran till [!DNL Target] edge-servrarna vid sidinläsning. Eftersom global mbox översätts till execute > pageLoad, och om du vill utlösa en begäran vid sidinläsning, bör den här inställningen vara aktiverad.

### Kommer befintliga VEC-aktiviteter att fortsätta fungera, även om målets globala mbox-namn inte anges från at.js 2.*x*?

Ja, eftersom execute > pageLoad behandlas som på [!DNL Target] backend-objektet `target-global-mbox`.

### Om mina formulärbaserade aktiviteter är inriktade på `target-global-mbox`, kommer dessa aktiviteter att fortsätta att fungera?

Ja, eftersom execute > pageLoad behandlas på [!DNL Target] edge-servrar som `target-global-mbox`.

### Stöds och stöds inte i .js 2.*x* -inställningar

| Inställning | Stöds? |
| --- | --- |
| X-domän | Nej |
| Skapa global Mbox automatiskt | Ja |
| Namn på global mbox | Ja |

### Stöd för spårning mellan domäner i at.js 2.x {#cross-domain}

Spårning mellan domäner gör det möjligt att sammanfoga besökare i olika domäner. Eftersom en ny cookie måste skapas för varje domän är det svårt att spåra besökare när de navigerar från en domän till en domän. För att uppnå domänövergripande spårning använder [!DNL Target] en cookie från tredje part för att spåra besökare över domäner. På så sätt kan du skapa en Target-aktivitet som sträcker sig över flera domäner `siteA.com` och `siteB.com` besökarna behåller samma upplevelse när de navigerar mellan olika domäner. Den här funktionen är kopplad till Target cookie-beteende från tredje part och från första part.

>[!NOTE]
>
>Spårning mellan domäner stöds inte i paketet at.js 2.*x*. Spårning mellan domäner stöds i at.js 2.*x* via Experience Cloud ID-biblioteket (ECID) v4.3.0+.

I Target lagras tredjeparts-cookie i `<CLIENTCODE>.tt.omtrdc.net`. Den första partens cookie lagras i `clientdomain.com`. Den första begäran returnerar HTTP-svarshuvuden som försöker ange cookies från tredje part som heter `mboxSession` och `mboxPC`som, medan en omdirigeringsbegäran skickas tillbaka med en extra parameter (`mboxXDomainCheck=true`). Om webbläsaren accepterar cookies från tredje part inkluderar omdirigeringsbegäran dessa cookies och upplevelsen returneras. Det här arbetsflödet är möjligt eftersom vi använder metoden HTTP GET.

I at.js 2.*x* används inte längre HTTP-GET, utan HTTP-POST. HTTP-POST används nu via at.js 2.*x* för att skicka JSON-nyttolaster till edge-servrar. Detta innebär att omdirigeringsbegäran för att kontrollera om en webbläsare stöder cookies från tredje part nu avbryts. Detta beror på att HTTP GET-begäranden är viktiga transaktioner, medan HTTP-POST är icke-idempotent och inte får upprepas godtyckligt. Därför kan du spåra korsdomäner i at.js 2.*x* stöds inte längre. Endast i js 1.*x* har färdiga funktioner för domänövergripande spårning.

Om du vill använda domänövergripande spårning måste du installera [ECID-biblioteket v4.3.0+](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) i kombination med at.js 2.*x*. ECID-biblioteket finns för att hantera beständiga ID:n som används för att identifiera en besökare även mellan domäner.

>[!NOTE]
>
>Efter installation av ECID-biblioteket v4.3.0+ och at.js 2.*x* kan du skapa aktiviteter som spänner över unika domäner samt spåra användare. Det är viktigt att komma ihåg att den här funktionen fungerar först när sessionen har upphört.

### Automatisk generering av global Mbox stöds

Den här inställningen anger at.js 2.*x* för att skicka en begäran till [!DNL Target] edge-servrarna vid sidinläsning. Eftersom den globala mbox översätts till execute > pageLoad, och detta tolkas av [!DNL Target] edge-servrarna, bör kunderna aktivera detta om de vill starta en begäran vid sidinläsning.

### Namn på global Mbox stöds

Kunderna kan ange ett globalt mbox-namn via [!UICONTROL Target > Administration > Implementation > Edit]. Den här inställningen används av [!DNL Target] edge-servrarna för att översätta execute > pageLoad till det inmatade globala mbox-namnet. Detta gör att kunderna kan fortsätta att använda serversidans API:er, den formulärbaserade dispositionen, profilskript och skapa målgrupper som har den globala mbox som mål.

### Gäller de anpassade händelserna at.js nedan för `triggerView()` eller gäller de bara `applyOffer()` eller `applyOffers()`?

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

Ja, de anpassade händelserna at.js gäller `triggerView()` också.

### Det står att när jag ringer `triggerView()` med `{“page” : “true”}`kommer det att skicka ett meddelande till [!DNL Target] backend-objektet och öka intrycket. Gör det även att profilskripten körs?

När ett förhämtningsanrop görs till [!DNL Target] serverdelen körs profilskripten. Därefter krypteras profildata som påverkas och skickas tillbaka till klientsidan. När `triggerView()` det `{"page": "true"}` anropas skickas ett meddelande tillsammans med de krypterade profildata. Detta är när [!DNL Target] backend-objektet dekrypterar profildata och lagrar dem i databaserna.

### Behöver vi lägga till kod som döljs i förväg innan vi anropar `triggerView()` för att hantera flimmer?

Nej, du behöver inte lägga till kod som döljs innan du anropar `triggerView()`. at.js 2.*x* hanterar logiken för att dölja och flimra innan vyn visas och används.

### Som i .js 1.*x* -parametrar för att skapa målgrupper stöds inte i at.js 2.*x*? {#audience-parameters}

Följande at.js 1.x-parametrar stöds för närvarande *INTE* för målgruppsgenerering när at.js 2 används.*x*:

* browserHeight
* browserWidth
* browserTimeOffset
* screenHeight
* screenWidth
* screenOrientation
* colorDepth
* devicePixelRatio

## kompatibilitet med at.js

I följande tabeller beskrivs at.js. 2.*x* -kompatibilitet med olika aktivitetstyper, integreringar, funktioner och at.js-funktioner.

### Typ av aktivitet {#types}

| Typ | Stöds? |
| --- | --- |
| A/B-test | Ja |
| Automatisk allokering | Ja |
| Automatiskt mål | Ja |
| Experience Targeting | Ja |
| Multivariata tester | Ja |
| Automated Personalization | Ja |
| Recommendations | Ja |

>[!NOTE]
>
>Automatiskt mål-aktiviteter stöds i at.js 2.*x* och VEC när alla ändringar tillämpas på `Page Load Event`. När ändringar läggs till i vissa vyer stöds endast aktiviteterna A/B Test, Auto-Allocate och Experience Targeting (XT).

### Integreringar {#integrations}

| Typ | Stöds? |
| --- | --- |
| Analyser för mål (A4T) | Ja |
| Målgrupper | Ja |
| Kundattribut | Ja |
| AEM Experience Fragments | Ja |
| Adobe Launch-tillägg | [Ja](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) |
| Felsökning | Ja |
| Revisor | Regler har ännu inte uppdaterats för kl. 2.js.*x* |
| Dynamic Tag Manager (DTM) | Ja |
| Anmäl dig | Nej. Stöd för deltagande i [GDPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) stöds i [at.js version 2.1.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
| AEM Förbättrad personalisering med Adobe Target | Nej |

### Funktioner

| Funktion | Stöds? |
| --- | --- |
| X-domän | Nej |
| Egenskaper/arbetsytor | Ja |
| QA-länkar | Ja |
| Formulärbaserad Experience Composer | Ja |
| Visual Experience Composer (VEC) | Ja |
| Egen kod | Ja |
| Svarstoken | [Ja](#response-tokens) |
| Klickspårning | Ja |
| Fleraktivitetsleverans | Ja |
| targetGlobalSettings | Ja (men inte x-domain) |
| at.js-metoder | Allt stöds förutom<br>`mboxCreate()`<br>`mboxUpdate()`<br>`mboxDefine()`<br>för vilket standardinnehåll visas. |

### Frågesträngsparametrar

| Parameter | Stöds? |
| --- | --- |
| `?mboxDisable` | Ja |
| `?mboxDisable` | Ja |
| `?mboxTrace` | Ja |
| `?mboxSession` | Nej |
| `?mboxOverride.browserIp` | Nej |

## Svarstoken {#response-tokens}

at.js 2.*x*, precis som at.js 1.*x* använder den anpassade händelsen `at-request-succeeded` för att visa svarstoken. Exempel på kod som använder den `at-request-succeeded` anpassade händelsen finns i [Svarstoken](/help/administrating-target/response-tokens.md).

## at.js 1.*x* -parametrar till at.js 2.*x* -nyttolastmappning {#payload-mapping}

I det här avsnittet beskrivs mappningarna mellan at.js 1.*x* och at.js 2.*x*.

Innan parametermappningen tas bort har slutpunkterna som används i dessa biblioteksversioner ändrats:

* at.js 1.*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at.js 2.*x* - `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

En annan viktig skillnad är att

* at.js 1.*x* - Klientkoden är en del av sökvägen
* at.js 2.*x* - Klientkoden skickas som en frågesträngsparameter, till exempel:
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

I följande avsnitt listas var och en at.js 1.*x* -parametern, dess beskrivning och motsvarande 2.*x* JSON-nyttolast (om tillämpligt):

### at_property

(at.js 1.*x* -parameter)

Används för [Enterprise-användarbehörigheter](/help/administrating-target/c-user-management/property-channel/property-channel.md).

```
{
  ....
  "property": {
    "token": "1213213123122313121"
  }
  ....
}
```

### mboxHost

(at.js 1.*x* -parameter)

Domänen för sidan där målbiblioteket körs.

at.js 2.*x* JSON-nyttolast:

```
{
  "context": {
    "browser": {
       "host": "test.com"
    }
  }
}
```

### webGLRenderer

(at.js 1.*x* -parameter)

Webbläsarens WEB GL-återgivningsfunktioner. Detta används av vår mekanism för enhetsidentifiering för att avgöra om besökarens enhet är en stationär dator, iPhone, Android-enhet osv.

at.js 2.*x* JSON-nyttolast:

```
{
  "context": {
    "browser": {
       "webGLRenderer": "AMD Radeon Pro 560X OpenGL Engine"
    }
  }
}
```

### mboxURL

(at.js 1.*x* -parameter)

Sidans URL.

at.js 2.*x* JSON-nyttolast:

```
{
  "context": {
    "address": {
       "url": "http://test.com"
    }
  }
}
```

### mboxReferer

(at.js 1.*x* -parameter)

Sidreferenten.

at.js 2.*x* JSON-nyttolast:

```
{
  "context": {
    "address": {
       "referringUrl": "http://google.com"
    }
  }
}
```

### mbox (namnet) är lika med global mbox

(at.js 1.*x* -parameter)

Leverans-API har inte längre något globalt mbox-koncept. I JSON-nyttolasten måste du använda `execute > pageLoad`.

at.js 2.*x* JSON-nyttolast:

```
{
  "execute": {
    "pageLoad": {
       "parameters": ....
       "profileParameters": ...
       .....
    }
  }
}
```

### mbox (namnet) är *inte* lika med global mbox

(at.js 1.*x* -parameter)

Om du vill använda ett mbox-namn skickar du det till `execute > mboxes`. En mbox kräver ett index och namn.

at.js 2.*x* JSON-nyttolast:

```
{
  "execute": {
    "mboxes": [{
       "index": 0,
       "name": "some-mbox",
       "parameters": ....
       "profileParameters": ...
       .....
    }]
  }
}
```

### mboxId

(at.js 1.*x* -parameter)

Används inte längre.

### mboxCount

(at.js 1.*x* -parameter)

Används inte längre.

### mboxRid

(at.js 1.*x* -parameter)

Begär-ID som används av system längre fram i kedjan för att underlätta felsökningen.

at.js 2.*x* JSON-nyttolast:

```
{
  "requestId": "2412234442342"
  ....
}
```

### mboxTime

(at.js 1.*x* -parameter)

Används inte längre.

### mboxSession

(at.js 1.*x* -parameter)

Sessions-ID skickas som en frågesträngsparameter (`sessionId`) till slutpunkten för leverans-API.

### mboxPC

(at.js 1.*x* -parameter)

TNT-ID:t skickas till `id > tntId`.

at.js 2.*x* JSON-nyttolast:

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

(at.js 1.*x* -parameter)

Marketing Cloud Visitor-ID skickas till `id > marketingCloudVisitorId`.

at.js 2.*x* JSON-nyttolast:

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### `vst.aaaa.id` och `vst.aaaa.authState`

(at.js 1.*x* -parametrar)

Kund-ID:n ska skickas till `id > customerIds`.

at.js 2.*x* JSON-nyttolast:

```
{
  "id": {
    "customerIds": [{
       "id": "1232131",
       "integrationCode": "aaaa",
       "authenticatedState": "....."
     }]
  }
  ....
}
```

### mbox3rdPartyId

(at.js 1.*x* -parameter)

Kundens tredje parts-ID som används för att länka olika mål-ID:n.

at.js 2.*x* JSON-nyttolast:

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### mboxMCSDID

(at.js 1.*x* -parameter)

SDID, även kallat kompletterande data-ID. Ska passera in i `experienceCloud > analytics > supplementalDataId`.

at.js 2.*x* JSON-nyttolast:

```
{
  "experienceCloud": {
    "analytics": {
      "supplementalDataId": "1212321132123131"
    }
  }
  ....
}
```

### vst.trk

(at.js 1.*x* -parameter)

Analysspårningsserver. Ska passera in i `experienceCloud > analytics > trackingServer`.

at.js 2.*x* JSON-nyttolast:

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServer": "analytics.test.com"
    }
  }
  ....
}
```

### vst.trks

(at.js 1.*x* -parameter)

Analysspårningsservern är säker. Ska passera in i `experienceCloud > analytics > trackingServerSecure`.

at.js 2.*x* JSON-nyttolast:

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServerSecure": "secure-analytics.test.com"
    }
  }
  ....
}
```

### mboxMCGLH

(at.js 1.*x* -parameter)

Platstips för Audience Manager. Ska passera in i `experienceCloud > audienceManager > locationHint`.

at.js 2.*x* JSON-nyttolast:

```
{
  "experienceCloud": {
    "audienceManager": {
      "locationHint": 9
    }
  }
  ....
}
```

### mboxAAMB

(at.js 1.*x* -parameter)

Audience Manager blob. Ska passera in i `experienceCloud > audienceManager > blob`.

at.js 2.*x* JSON-nyttolast:

```
{
  "experienceCloud": {
    "audienceManager": {
      "blob": "2142342343242342"
    }
  }
  ....
}
```

### mboxVersion

(at.js 1.*x* -parameter)

Version skickas som en frågesträngsparameter via versionsparametern.

## Utbildningsvideo: at.js 2.*brickan* Översikt över x ![-arkitekturdiagram](/help/assets/overview.png)

at.js 2.*x* förbättrar Adobe Target stöd för SPA och kan integreras med andra Experience Cloud-lösningar. Den här videon förklarar hur allt hänger ihop.

>[!VIDEO](https://video.tv.adobe.com/v/26250)

Se [Så här fungerar at.js 2.*x* fungerar](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) för mer information.