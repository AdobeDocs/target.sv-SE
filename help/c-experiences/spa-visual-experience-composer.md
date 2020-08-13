---
keywords: spa vec;react;angular;react.js;spa visual experience composer;spa experience composer options;single page apps;single-page-app;spa;mobile experience options;target view
description: Med Visual Experience Composer (VEC) för Single Page Apps (SPA) i Adobe Target kan marknadsförare skapa tester och personalisera innehåll i SPA på ett sätt som gör det möjligt för dig utan kontinuerliga utvecklingsberoenden. VEC kan användas för att skapa aktiviteter på de vanligaste ramverken, som React och Angular.
title: Visual Experience Composer för Single Page App (SPA)
feature: spa vec
topic: Standard
uuid: 4dcd6d9c-b2e3-4759-a2e0-3696c572faba
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '3648'
ht-degree: 0%

---


# Visual Experience Composer för Single Page App (SPA) {#single-page-app-spa-visual-experience-composer}

Dessutom [!DNL Adobe Target]ger [!UICONTROL Visual Experience Composer] (VEC) marknadsförarna möjlighet att skapa aktiviteter och personalisera upplevelser som kan levereras dynamiskt på traditionella flersidiga program via Adobe Target globala mbox. Detta är dock beroende av att du hämtar erbjudanden vid sidinläsning eller efterföljande serveranrop, vilket introducerar fördröjning, vilket visas i diagrammet nedan. Detta arbetssätt fungerar inte så bra med SPA (Single Page Applications) eftersom det försämrar användarupplevelsen och programmets prestanda.

![Traditionell livscykel jämfört med SPA-livscykel](/help/c-experiences/assets/trad-vs-spa.png)

I den senaste versionen presenterar vi nu VEC för SPA. Med VEC for SPA kan marknadsförarna skapa tester och personalisera innehåll på SPA på ett sätt som gör det själv utan kontinuerliga utvecklingsberoenden. VEC kan användas för att skapa [A/B Test](/help/c-activities/t-test-ab/test-ab.md) and [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) (XT)-aktiviteter på populära ramverk som React och Angular.

## Adobe Target Views and Single Page Applications

Adobe Target VEC for SPAs utnyttjar det nya konceptet Views: en logisk grupp visuella element som tillsammans utgör en SPA-upplevelse. En SPA kan därför betraktas som en övergång genom vyer i stället för URL-adresser, baserat på användarinteraktioner. En vy kan vanligtvis representera en hel plats eller grupperade visuella element inom en plats.

Om du vill förklara vad Vyer är kan du navigera på den hypotetiska e-handelsplatsen som implementeras i React och utforska några exempel på Vyer. Klicka på länkarna nedan för att öppna den här webbplatsen på en ny webbläsarflik.

**Länk:[Hemwebbplats](https://target.enablementadobe.com/react/demo/#/)**

![hemsida](/help/c-experiences/assets/home.png)

När vi navigerar till hemsidan ser vi omedelbart en hjältebild som främjar en påskförsäljning samt de senaste produkterna som säljer på webbplatsen. I det här fallet kan en vy definieras som hela hemsidan. Detta är praktiskt att notera eftersom vi kommer att gå vidare med detta i avsnittet Implementera Adobe Target-vyer nedan.

**Länk:[Produktwebbplats](https://target.enablementadobe.com/react/demo/#/products)**

![produktwebbplats](/help/c-experiences/assets/product-site.png)

När vi blir mer intresserade av produkterna väljer vi att klicka på länken Produkter. På samma sätt som hemsidan kan hela produktwebbplatsen definieras som en vy. Vi kan ge den här vyn namnet&quot;products&quot; precis som sökvägsnamnet i `https://target.enablementadobe.com/react/demo/#/products`.

![produktwebbplats 2](/help/c-experiences/assets/product-site-2.png)

I början av det här avsnittet definierade vi Vyer som hela webbplatsen eller till och med en grupp visuella element på webbplatsen. Som framgår ovan kan de fyra produkter som visas på webbplatsen också grupperas och betraktas som en vy. Om vi vill kalla den här vyn kan vi kalla den för&quot;produkter&quot;.

![produktwebbplats 3](/help/c-experiences/assets/product-site-3.png)

Vi väljer att klicka på knappen Läs in mer för att utforska fler produkter på webbplatsen. Webbplatsens URL ändras inte i det här fallet. Men en vy här kan bara representera den andra produktraden som visas ovan. Vynamnet kan heta &quot;PRODUCTS-PAGE-2&quot;.

**Länk:[Utcheckning](https://target.enablementadobe.com/react/demo/#/checkout)**

![utcheckningssida](/help/c-experiences/assets/checkout.png)

Eftersom vi tyckte om vissa produkter som visas på webbplatsen bestämde vi oss för att köpa ett par. På utcheckningssajten har vi fått möjlighet att välja normal leverans eller expressleverans. Eftersom en vy kan vara vilken grupp som helst av visuella element på en webbplats kan vi kalla den här&quot;Visa leveransinställningar&quot;.

Dessutom kan vykonceptet utökas betydligt mer än så. Om marknadsförarna vill anpassa innehållet på webbplatsen beroende på vilken leveransinställning som har valts, kan en vy skapas för varje leveransinställning. När vi väljer Normal leverans får du i så fall namnet&quot;Normal leverans&quot;. Om du väljer Express Delivery får du namnet &quot;Express Delivery&quot;.

Nu kanske marknadsförarna vill köra ett A/B-test för att se om en ändring av färgen från blå till röd när expressleverans är valt kan öka konverteringsgraden i stället för att behålla knappfärgen blå för båda leveransalternativen.

## Implementera Adobe Target-vyer

Nu när vi har täckt vad Adobe Target Views är kan vi utnyttja detta koncept i Target för att göra det möjligt för marknadsförare att köra A/B- och XT-tester på SPA-program via VEC. Detta kräver en engångsinstallation av utvecklare. Låt oss gå igenom stegen för att konfigurera detta.

1. Installera på .js 2.x.

   Först måste vi installera på .js 2.x. Den här versionen av at.js utvecklades med SPA i åtanke. Tidigare versioner av at.js och mbox.js har inte stöd för Adobe Target Views och VEC for SPA.

   ![Dialogrutan Implementeringsinformation](/help/c-experiences/assets/imp-200.png)

   Hämta filen at.js 2.x via Adobe Target-gränssnittet i [!UICONTROL Administration > Implementation]. at.js 2.x kan också distribueras via [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). Adobe Target-tilläggen är dock för närvarande inte aktuella och stöds inte.

1. Implementera funktionen at.js 2.x: [triggerView()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) på dina platser.

   När du har definierat vyerna för SPA där du vill köra ett A/B- eller XT-test implementerar du funktionen at.js 2.x med vyerna som skickas som en parameter. `triggerView()` Detta gör att marknadsförarna kan använda VEC för att utforma och köra A/B- och XT-tester för de vyer som definierats. Om `triggerView()` funktionen inte är definierad för dessa vyer kommer VEC inte att identifiera vyerna och marknadsförarna kan därför inte använda VEC för att utforma och köra A/B- och XT-tester.

   **`adobe.target.triggerView(viewName, options)`**

   | Parameter | Typ | Obligatoriskt? | Validering | Beskrivning |
   | --- | --- | --- | --- | --- |
   | viewName | Sträng | Ja | 1. Inga efterföljande blanksteg.<br>2. Kan inte vara tom.<br>3. Visningsnamnet måste vara unikt för alla sidor.<br>4. **Varning**: Vynamnet får inte börja eller sluta med &#39;`/`&#39;. Detta beror på att kunden vanligtvis extraherar visningsnamnet från URL-sökvägen. För oss är&quot;home&quot; och&quot;`/home`&quot; annorlunda.<br>5. **Varning**: Samma vy bör inte aktiveras flera gånger i följd med `{page: true}` alternativet. | Ange valfritt namn som en strängtyp som du vill representera din vy. Det här visningsnamnet visas på VEC-panelen [!UICONTROL Modifications] så att marknadsförare kan skapa åtgärder och köra A/B- och XT-aktiviteter. |
   | alternativ | Objekt | Nej |  |  |
   | alternativ > sida | Boolean | Nej |  | **TRUE**: Standardvärdet för sidan är true. När `page=true`det är klart skickas meddelanden till edge-servrarna för att öka antalet intryckta.<br>**FALSE**: När `page=false`visas inga meddelanden för ökat antal inläsningar. Detta bör användas när du endast vill återge en komponent på en sida med ett erbjudande. |

   Nu ska vi gå igenom några exempel på hur funktionen i React för vår hypotetiska SPA för e-handel kan anropas: `triggerView()`

   **Länk:[Hemwebbplats](https://target.enablementadobe.com/react/demo/#/)**

   ![hemreaktion-1](/help/c-experiences/assets/react1.png)

   Om vi som marknadsförare vill köra A/B-tester på hela hemsidan kanske vi vill kalla vyn&quot;home&quot; som kan extraheras från webbadressen:

   ```
   function targetView() {
     var viewName = window.location.hash; // or use window.location.pathName if router works on path and not hash
   
     viewName = viewName || 'home'; // view name cannot be empty
   
     // Sanitize viewName to get rid of any trailing symbols derived from URL
     if (viewName.startsWith('#') || viewName.startsWith('/')) {
       viewName = viewName.substr(1);
     }
   
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   // react router v4
   const history = syncHistoryWithStore(createBrowserHistory(), store);
   history.listen(targetView);
   
   // react router v3
   <Router history={hashHistory} onUpdate={targetView} >
   ```

   **Länk:[Produktwebbplats](https://target.enablementadobe.com/react/demo/#/products)**

   Nu ska vi titta på ett exempel som är lite mer komplicerat. Som marknadsförare vill vi personalisera produktraden genom att ändra prisetikettens färg till röd efter att en användare klickat på knappen Läs in mer.

   ![reaktionsprodukter](/help/c-experiences/assets/react4.png)

   ```
   function targetView(viewName) {
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   class Products extends Component {
     render() {
       return (
         <button type="button" onClick={this.handleLoadMoreClicked}>Load more</button>
       );
     }
   
     handleLoadMoreClicked() {
       var page = this.state.page + 1; // assuming page number is derived from component’s state
       this.setState({page: page});
       targetView('PRODUCTS-PAGE-' + page);
     }
   }
   ```

   **Länk:[Utcheckning](https://target.enablementadobe.com/react/demo/#/checkout)**

   ![reagera utcheckning](/help/c-experiences/assets/react6.png)

   Om marknadsförarna vill anpassa innehållet på webbplatsen beroende på vilken leveransinställning som har valts, kan en vy skapas för varje leveransinställning. När vi väljer Normal leverans får du i så fall namnet&quot;Normal leverans&quot;. Om du väljer Express Delivery får du namnet &quot;Express Delivery&quot;.

   Nu kanske marknadsförarna vill göra ett A/B-test för att se om en ändring av färgen från blå till röd när expressleverans är valt kan öka konverteringen i stället för att behålla knappfärgen blå för båda leveransalternativen.

   ```
   function targetView(viewName) {
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   class Checkout extends Component {
     render() {
       return (
         <div onChange={this.onDeliveryPreferenceChanged}>
           <label>
             <input type="radio" id="normal" name="deliveryPreference" value={"Normal Delivery"} defaultChecked={true}/>
             <span> Normal Delivery (7-10 business days)</span>
           </label>
   
           <label>
             <input type="radio" id="express" name="deliveryPreference" value={"Express Delivery"}/>
             <span> Express Delivery* (2-3 business days)</span>
           </label>
         </div>
       );
     }
     onDeliveryPreferenceChanged(evt) {
       var selectedPreferenceValue = evt.target.value;
       targetView(selectedPreferenceValue);
     }
   }
   ```

1. Starta A/B- eller XT-aktiviteter via VEC.

   När `adobe.target.triggerView()` implementeras på din SPA med vynamn skickade som parametrar, kan VEC identifiera dessa vyer och låta användare skapa åtgärder och ändringar för sina A/B- eller XT-aktiviteter.

   >[!NOTE]
   >
   >VEC för SPA är i själva verket samma VEC som du använder på vanliga webbsidor, men det finns vissa ytterligare funktioner när du öppnar en app för en enstaka sida med `triggerView()` implementering.

Det finns två stora förbättringar av [ändringspanelen](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) och åtgärder för VEC som gör att VEC kan fungera bra med SPA.

**Panelen Ändringar**

På [!UICONTROL Modifications] panelen, som visas nedan, hämtas de åtgärder som har skapats för en viss vy. Observera att alla åtgärder för en vy grupperas under den vyn.

**Åtgärder**

Om du klickar på en åtgärd markeras elementet på platsen där den här åtgärden ska tillämpas. Varje VEC-åtgärd som skapas under en vy har följande ikoner: Information, Redigera, Klona, Flytta och Ta bort.

![Ändringar](/help/c-experiences/assets/modifications.png)

I följande tabell beskrivs de olika åtgärderna:

| Sida | Beskrivning |
| --- | --- |
| Information | Visar information om åtgärden. |
| Redigera | Gör att du kan redigera åtgärdens egenskaper direkt. |
| Klona | Klona åtgärden till en eller flera vyer som finns på [!UICONTROL Modifications] panelen eller till en eller flera vyer som du har bläddrat till och navigerat till i VEC. Åtgärden behöver inte nödvändigtvis finnas på [!UICONTROL Modifications] panelen.<br>**Obs**: När en klonåtgärd har utförts måste du navigera till VEC via för [!UICONTROL Browse] att se om den klonade åtgärden var en giltig åtgärd. Om åtgärden inte kan tillämpas på vyn visas ett fel. |
| Flytta | Flyttar åtgärden till en sidinläsningshändelse eller någon annan vy som redan finns på panelen Ändringar.<br>[!UICONTROL Page Load Event] - alla åtgärder som motsvarar sidans load-händelse tillämpas på den första sidinläsningen i webbprogrammet.<br>**Obs** ! När flyttningen är klar måste du navigera till vyn i VEC via Browse för att se om flyttningen var en giltig åtgärd. Om åtgärden inte kan användas i vyn visas ett fel |
| Ta bort | Tar bort åtgärden. |

>[!NOTE]
>
>Du kan utföra många åtgärder innan sidan läses in i VEC, eller även om sidan inte läses in helt. Åtgärder som inte kan redigeras innan webbplatsen läses in inaktiveras i användargränssnittet.

**Exempel 1**

Vi hänvisar till exemplet ovan där vi skapade en hemvy. Vårt mål är tvåfaldigt för den här vyn:

1. Ändra knappen Lägg till i kundvagnen och knappen Gilla till en ljusare blå färg. Detta bör vara i en sidinläsning eftersom vi ändrar komponenterna i sidhuvudet.
1. Ändra etiketten&quot;Senaste produkter för 2019&quot; till&quot;Värdprodukter för 2019&quot; med textfärgen ändrad till lila.

Om du vill utföra de här målen i VEC klickar du på [!UICONTROL Compose] och tillämpar ändringarna i hemvyn.

![Exempel 1](/help/c-experiences/assets/example1.png)

**Exempel 2**

Vi hänvisar till exemplet ovan där vi skapade en PRODUCTS-PAGE-2-vy. Vårt mål är att ändra prisetiketten till&quot;Försäljningspris&quot; med etikettfärgen röd.

1. Klicka [!UICONTROL Browse]och sedan på [!UICONTROL Products] länken i sidhuvudet.
1. Klicka [!UICONTROL Load More] en gång för att gå till den andra produktraden.
1. Klicka på [!UICONTROL Compose].
1. Använd åtgärder för att ändra textetiketten till&quot;Försäljningspris&quot; och färgen till röd.

![Exempel 2](/help/c-experiences/assets/example2.png)

**Exempel 3**

Slutligen kan vyer definieras på detaljnivå, som tidigare nämnts. Vyer kan vara ett läge eller till och med ett alternativ från en alternativknapp. Tidigare har vi skapat Vyer som CHECKOUT-EXPRESS och CHECKOUT-NORMAL. Vårt mål är att ändra knappfärgen till röd för CHECKOUT-EXPRESS-vyn.

1. Klicka på [!UICONTROL Browse].
1. Lägg några produkter i vagnen.
1. Klicka på kundvagnsikonen i det övre högra hörnet.
1. Klicka på Checka ut din beställning.
1. Klicka på alternativknappen Express Delivery.
1. Klicka på [!UICONTROL Compose].
1. Ändra&quot;Betala&quot;-knappen till&quot;Slutför beställningen&quot; och ändra färgen till röd.

![Exempel 3](/help/c-experiences/assets/example3.png)

>[!NOTE]
>
>Vyn CHECKOUT-EXPRESS visas inte på ändringspanelen förrän du klickar på alternativknappen Express Delivery. Detta beror på att `triggerView()` funktionen aktiveras när alternativknappen Express Delivery är markerad och det här är bara när VEC vet att det finns en vy att visa på ändringspanelen.

## Djupdyka in i at.js och SPA

**Hur kan jag hämta vyer för de senaste målgruppsdata som har hydrerats av åtgärder efter att den första sidan har lästs in på min SPA?**

Det typiska arbetsflödet för at.js 2.x är när webbplatsen läses in, alla vyer och åtgärder cachelagras så att efterföljande användaråtgärder på webbplatsen inte utlöser några serveranrop för att hämta erbjudanden. Om du vill hämta vyer beroende på de senaste profildata som kan ha uppdaterats beroende på efterföljande användaråtgärder, kan du ringa `getOffers()` och `applyOffers()` få information om den senaste målgruppsanvändaren eller de profiler som skickas.

Anta till exempel att du är ett telekomföretag och har ett SPA som använder at.js 2.x. Som företag vill du uppnå följande mål:

* För en utloggad eller anonym användare kan du visa den senaste företagskampanjen, till exempel visa hjälteerbjudandet&quot;Första månaden gratis&quot; `http://www.telecom.com/home`.
* För en inloggad användare, visa ett uppgraderingserbjudande för användare vars kontrakt närmar sig, t.ex.&quot;Du är berättigad till en kostnadsfri telefon!&quot; den `http://www.telecom.com/loggedIn/home`.

Nu kan utvecklarna namnvisa och ringa `triggerView()` på följande sätt:

* Vynamnet `http://www.telecom.com/home` är&quot;Utloggad hem&quot;
   * `triggerView(“Logged Out Home”)` anropas.
* Vynamnet `http://www.telecom.com/loggedIn/home` är&quot;Inloggad hemma&quot;
   * `triggerView(“Logged In Home”)` anropas vid flödesändring.

Dina marknadsförare kör sedan följande A/B-aktiviteter via VEC:

* A/B-aktivitet med erbjudandet&quot;Gratis första månaden&quot; för målgrupper med parametern&quot;`loggedIn= false`&quot; som ska visas i `http://www.telecom.com/home`, där visningsnamnet är Utloggad Hem.
* A/B-aktivitet med&quot;Du är berättigad till en kostnadsfri telefon!&quot; erbjudanden för målgrupper med parametern&quot;`loggedIn=true`&quot; som ska visas i `http://www.telecom.com/loggedIn/home`, där visningsnamnet är Loggad in Hero Offer.

Låt oss nu tänka på det här användarflödet:

1. En anonym utloggad användare hamnar på din sida.
1. Eftersom du använder at.js 2.x skickar du parametern&quot;`loggedIn = false`&quot; vid sidinläsning för att hämta alla vyer som finns i aktiva aktiviteter som är kvalificerade för när målgruppen har parametern&quot;`loggedIn = false`&quot;.
1. at.js 2.x hämtar sedan vyn Utloggad hemsida och åtgärden som visar erbjudandet&quot;Fri första månaden&quot; och lagrar det i cache-minnet.
1. När `triggerView(“Logged Out Home”)` det anropas hämtas erbjudandet&quot;Första månaden ledigt&quot; från cache och erbjudandet visas utan ett serversamtal.
1. Användaren klickar nu på Logga in och anger sina uppgifter.
1. Eftersom din webbplats är en SPA-fil utför du inte en hel sidladdning utan dirigerar användaren till `http://www.telecom.com/loggedIn/home`.

Här är problemet. Användaren loggar in och vi stöter på `triggerView(“Logged In Home”)` eftersom den här koden har placerats på en vägändring. Detta anger att at.js 2.x ska hämta vyn och åtgärderna från cachen, men den enda vy som finns i cachen är Utloggad Hem.

Så hur kan vi sedan hämta vår inloggade vy och visa&quot;Du är berättigad till en kostnadsfri telefon!&quot; erbjudandet? Och eftersom alla efterföljande åtgärder på din webbplats kommer från ett inloggat användarperspektiv, hur kan du se till att alla efterföljande åtgärder resulterar i personaliserade erbjudanden för inloggade användare?

Du kan använda de nya funktionerna `getOffers()` och `applyOffers()` funktionerna som stöds i at.js 2.x:

```
adobe.target.getOffers({
  request: {
  prefetch: {
    "views": [
      {
        "parameters": {
          "loggedIn": true
        },
      }
    ]
  },
});
```

Skicka svaret från `getOffers()` till `applyOffers()` och nu kommer alla vyer och åtgärder som är kopplade till &quot;loggedIn = true&quot; att uppdatera cachen at.js.

Med andra ord har at.js 2.x stöd för ett sätt att hämta vyer, åtgärder och erbjudanden med de senaste målgruppsdata på begäran.

**Har .js 2.x stöd för A4T för Single Page-program?**

Ja, at.js 2.x stöder A4T för SPA via `triggerView()` funktionen eftersom du har implementerat Adobe Analytics och Experience Cloud Visitor ID Service. Se diagrammet nedan med stegvisa beskrivningar.

![Målflöde](/help/c-experiences/assets/atjs-spa-flow.png)

| Steg | Beskrivning |
| --- | --- |
| 1 | `triggerView()` anropas i SPA för att återge en vy och använda åtgärder för att ändra visuella element som är kopplade till vyn. |
| 2 | Målinnehåll för vyn läses från cachen. |
| 3 | Målinriktat innehåll visas så snabbt som möjligt utan att man behöver flimra standardinnehållet. |
| 4 | En meddelandebegäran skickas till målprofilsarkivet för att räkna besökaren i aktiviteten och ökningsvärdena. |
| 5 | Analysdata skickas till datainsamlingsservrar. |
| 6 | Måldata matchas mot Analytics-data via SDID och bearbetas till lagringsplatsen för analysrapporter. Analysdata kan sedan visas både i Analytics och Target via A4T-rapporter. |

>[!NOTE]
>Om du inte vill skicka meddelanden till Adobe Analytics för att göra avtrycksräkning varje gång en vy aktiveras, skickar du `{page: false}` till `triggerView()` funktionen så att avtrycksräkning inte ökar när en vy aktiveras flera gånger för en komponent som återges kontinuerligt. Exempel:
>
>`adobe.target.triggerView(“PRODUCTS-PAGE-2”, {page:false})`

## Stödda aktiviteter

| Typ av aktivitet | Stöds? |
| --- | --- |
| [A/B-test](/help/c-activities/t-test-ab/test-ab.md) | Ja |
| [Recommendations som](/help/c-recommendations/recommendations-as-an-offer.md)<br>erbjudande inom A/B Test and Experience Targeting (XT) | Ja |
| [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Ja |
| [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) | Ja |
| [Multivariata tester](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | Nej |
| [Automatiskt mål](/help/c-activities/auto-target-to-optimize.md) | Nej |
| [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) | Nej |
| [Recommendations](/help/c-recommendations/recommendations.md) | Nej |

**Om vi installerade på .js 2.x och implementerade`triggerView()`på våra webbplatser, hur kör vi A/B-aktiviteter med Automatiskt mål eftersom SPA VEC inte stöder Auto-Target?**

Om du vill använda A/B-aktiviteter som mål automatiskt kan du flytta alla åtgärder som ska köras vid sidinläsningshändelse i VEC. Håll muspekaren över varje åtgärd och klicka på [!UICONTROL Move to Page Load Event] knappen. När du har gjort det kan du i nästa steg välja Automatiskt mål som metod för trafikallokering.

## Integrationer som stöds

| Integrering | Stöds? |
| --- | --- |
| [Analyser för mål (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | Ja |
| [Experience Cloud målgrupper](/help/c-integrating-target-with-mac/mmp.md) | Ja |
| [Kundattribut](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | Ja |
| [AEM Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md) | Ja |

## Funktioner som stöds {#supported-features}

| Funktion | Stöds? |
| --- | --- |
| [Arbetsytor och egenskaper](/help/administrating-target/c-user-management/property-channel/property-channel.md) | Ja |
| [QA-länkar](/help/c-activities/c-activity-qa/activity-qa.md) | Ja |
| [Formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md) | Nej |
| [Egen kod](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | Ja |
| [VEC-alternativ](/help/c-experiences/c-visual-experience-composer/viztarget-options.md) | Alla |
| [Klickspårning](/help/c-activities/r-success-metrics/click-tracking.md) | Ja |
| [Fleraktivitetsleverans](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) | Ja |

## Inställningar för sidleverans för SPA VEC {#page-delivery-settings}

[!UICONTROL Page Delivery] Med inställningar kan du konfigurera regler för att avgöra när en Target-aktivitet ska kvalificera sig och köras för en målgrupp.

Om du vill få tillgång till [!UICONTROL Page Delivery] alternativen i VEC:s tredelade guidade arbetsflöde för att skapa aktiviteter går du från **[!UICONTROL Experiences]** steget till **[!UICONTROL Configure]** (kugghjulsikonen) > **[!UICONTROL Page Delivery]**.

![Dialogrutan Alternativ för sidleverans](/help/c-experiences/assets/page-delivery.png)

Som definieras av [!UICONTROL Page Delivery] inställningarna ovan kvalificerar och körs en Target-aktivitet när en besökare når direkt på `https://www.adobe.com` eller *när en besökare når en URL som innehåller* `https://www.adobe.com/products`. Detta fungerar perfekt för alla flersidiga program där varje interaktion med sidan anropar en sidomladdning, där at.js hämtar de aktiviteter som är kvalificerade för den URL som användaren navigerar till.

Eftersom SPA-program fungerar på olika sätt måste dock [!UICONTROL Page Delivery] inställningarna konfigureras på ett sätt som gör att alla åtgärder kan tillämpas på vyerna enligt definitionen i SPA VEC-aktiviteten.

### Exempel på use-case

Här följer ett exempel på hur du använder gemener/VERSALER:

![SPA VEC Modifications-panelen](/help/c-experiences/assets/page-delivery-example.png)

Följande ändringar gjordes:

* Ändrad bakgrundsfärg i hemvyn, som finns under URL-adressen: [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* Knappfärgen har ändrats i produktvyn, som finns under URL-adressen: [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).

Med exemplet ovan i åtanke, vad som händer när vi konfigurerar [!UICONTROL Page Delivery] inställningarna så att de bara omfattar: [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/) i en SPA med at.js 2.*x*?

![Dialogrutan Sidleverans](/help/c-experiences/assets/spa-page-delivery.png)

Följande bild visar begäran om målflöde - sidinläsning i at.js 2.*x*:

![Målflöde - begäran om sidinläsning at.js 2.0](/help/c-experiences/assets/page-load-request.png)

**Användarresa nr 1**

* En användare navigerar direkt till [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* at.js 2.*x* skapar en fråga till Edge för att se om någon aktivitet behöver köras för URL:en: [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* I steg 6 returnerar Target Edge åtgärderna för hem- och produktvyn så att de cachas i webbläsaren.

**Resultat**: Användaren ser den gröna bakgrundsfärgen i hemvyn. När användaren sedan navigerar till [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products)visas knappens blå bakgrundsfärg eftersom åtgärden cachas i webbläsaren under produktvyn.

Obs! Användaren som navigerade till [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products) utlöste ingen sidinläsning.

**Användarresa nr 2**

* En användare navigerar direkt till [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* at.js 2.*x* skapar en fråga till Edge för att se om någon aktivitet behöver köras för URL:en: [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* Det finns inga aktiviteter som är kvalificerade för [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* Eftersom inga aktiviteter är kvalificerade finns det inga åtgärder och vyer att cachelagra för at.js 2.*x* att utlösa från.

**Resultat**: Även om du har definierat `triggerView()` för produktvyn och gjort en åtgärd för produktvyn via SPA VEC, kommer du inte att se den förväntade åtgärden eftersom du inte skapade en regel som inkluderade [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products) i inställningarna för sidleverans.

### Bästa praxis

Du ser att det kan vara svårt att hantera användarresan eftersom användarna kan landa på valfri URL i SPA och navigera till andra sidor. Därför är det bäst att ange en regel för sidleverans som innehåller bas-URL:en så att den omfattar hela ditt SPA-avtal. På så sätt behöver du inte tänka på alla olika resor och sökvägar som en användare kan ta för att komma till en sida där du vill visa en A/B-test- eller Experience Targeting-aktivitet (XT).

För att lösa problemet ovan kan vi till exempel ange bas-URL:en i inställningarna för sidleverans:

![Dialogrutan Sidleverans](/help/c-experiences/assets/conclusion.png)

Detta garanterar att de åtgärder som tillämpas visas när en besökare kommer till SPA och navigerar till antingen hemvyn eller sidvyn.

När du lägger till en åtgärd i en vy i SPA VEC visas nu följande popup-meddelande som påminner dig om hur du ska tänka på [!UICONTROL Page Delivery] reglerna.

![Meddelande om inställningar för sidleverans](/help/c-experiences/assets/pop-up-message.png)

Det här meddelandet visas när du lägger till den första åtgärden i en vy för varje ny aktivitet som du skapar. Det här meddelandet hjälper till att säkerställa att alla i organisationen lär sig att tillämpa dessa [!UICONTROL Page Delivery] regler korrekt.

## Utbildningsvideo: Använda VEC för SPA i Adobe Target

>[!VIDEO](https://video.tv.adobe.com/v/26249)

Mer information finns i [Använda Visual Experience Composer för Single Page Application (SPA VEC) i Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) .
