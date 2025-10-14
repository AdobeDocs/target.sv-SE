---
keywords: spa vec;ereaktion;angular;reaktion.js;spa visual experience comser;spa experience composer options;single page apps;single page app;spa;mobile experience options;target view
description: Lär dig hur du använder SPA VEC i Adobe [!DNL Target]  för att skapa tester och personalisera innehåll i SPA på ett sätt som gör det själv utan kontinuerliga utvecklingsberoenden.
title: Hur använder jag SPA VEC (Single Page App Visual Experience Composer)?
feature: Visual Experience Composer (VEC)
exl-id: fd3dcfaa-e5c6-45a1-8229-9c206562e5b0
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '3569'
ht-degree: 0%

---

# Visual Experience Composer för Single Page App (SPA)

I [!DNL Adobe Target] ger [!UICONTROL Visual Experience Composer] (VEC) marknadsförarna möjlighet att skapa aktiviteter och personalisera upplevelser som kan levereras dynamiskt på traditionella flersidiga program via Adobe Target globala mbox. Detta är dock beroende av att du hämtar erbjudanden vid sidinläsning eller efterföljande serveranrop, vilket introducerar fördröjning, vilket visas i diagrammet nedan. Detta arbetssätt fungerar inte så bra med SPA (Single Page Applications) eftersom det försämrar användarupplevelsen och programmets prestanda.

![Traditionell livscykel jämfört med SPA-livscykel](/help/main/c-experiences/assets/trad-vs-spa.png)

I den senaste versionen presenterar vi nu VEC för SPA. Med VEC for SPA kan marknadsförarna skapa tester och personalisera innehåll på SPA på ett sätt som gör det själv utan kontinuerliga utvecklingsberoenden. VEC kan användas för att skapa [A/B-test](/help/main/c-activities/t-test-ab/test-ab.md) och [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md) (XT)-aktiviteter på populära ramverk som React och Angular.

## Adobe [!DNL Target]-vyer och program för en sida

Adobe Target VEC för SPA utnyttjar det nya konceptet Views: en logisk grupp visuella element som tillsammans utgör en SPA-upplevelse. En SPA kan därför betraktas som en övergång genom vyer i stället för URL-adresser, baserat på användarinteraktioner. En vy kan vanligtvis representera en hel plats eller grupperade visuella element inom en plats.

Om du vill förklara vad Vyer är kan du navigera på den hypotetiska e-handelsplatsen som implementeras i React och utforska några exempel på Vyer. Klicka på länkarna nedan för att öppna den här webbplatsen på en ny flik i webbläsaren.

**Länk: [Hemwebbplats](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/)**

![hemwebbplats](/help/main/c-experiences/assets/home.png)

När vi navigerar till hemsidan ser vi omedelbart en hjältebild som främjar en påskförsäljning samt de senaste produkterna som säljer på webbplatsen. I det här fallet kan en vy definieras som hela hemsidan. Detta är praktiskt att notera eftersom vi kommer att gå vidare med detta i avsnittet Implementera Adobe Target-vyer nedan.

**Länk: [Produktwebbplats](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products)**

![produktwebbplats](/help/main/c-experiences/assets/product-site.png)

När vi blir mer intresserade av produkterna väljer vi att klicka på länken Produkter. På samma sätt som hemsidan kan hela produktwebbplatsen definieras som en vy. Vi kan ge den här vyn namnet&quot;products&quot; precis som sökvägsnamnet i `https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products`.

![produktwebbplats 2](/help/main/c-experiences/assets/product-site-2.png)

I början av det här avsnittet definierade vi Vyer som hela webbplatsen eller till och med en grupp visuella element på webbplatsen. Som framgår ovan kan de fyra produkter som visas på webbplatsen också grupperas och betraktas som en vy. Om vi vill kalla den här vyn kan vi kalla den för&quot;produkter&quot;.

![produktwebbplats 3](/help/main/c-experiences/assets/product-site-3.png)

Vi väljer att klicka på knappen Läs in mer för att utforska fler produkter på webbplatsen. Webbplatsens URL ändras inte i det här fallet. Men en vy här kan bara representera den andra produktraden som visas ovan. Vynamnet kan heta &quot;PRODUCTS-PAGE-2&quot;.

**Länk: [Utcheckning](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/checkout)**

![utcheckningssida](/help/main/c-experiences/assets/checkout.png)

Eftersom vi tyckte om vissa produkter som visas på webbplatsen bestämde vi oss för att köpa ett par. På utcheckningssajten har vi fått möjlighet att välja normal leverans eller expressleverans. Eftersom en vy kan vara vilken grupp som helst av visuella element på en webbplats kan vi kalla den här&quot;Visa leveransinställningar&quot;.

Dessutom kan vykonceptet utökas betydligt mer än så. Om marknadsförarna vill anpassa innehållet på webbplatsen beroende på vilken leveransinställning som har valts, kan en vy skapas för varje leveransinställning. När vi väljer Normal leverans får du i så fall namnet&quot;Normal leverans&quot;. Om du väljer Express Delivery får du namnet &quot;Express Delivery&quot;.

Nu kanske marknadsförarna vill köra ett A/B-test för att se om en ändring av färgen från blå till röd när expressleverans är valt kan öka konverteringsgraden i stället för att behålla knappfärgen blå för båda leveransalternativen.

## Implementera Adobe [!DNL Target]-vyer

Nu när vi har täckt vad Adobe Target Views är kan vi utnyttja detta koncept i Target för att göra det möjligt för marknadsförare att köra A/B- och XT-tester på SPA-program via VEC. Detta kräver en engångsinstallation av utvecklare. Låt oss gå igenom stegen för att konfigurera detta.

1. Installera på .js 2.x.

   Först måste vi installera på .js 2.x. Den här versionen av at.js utvecklades med SPA i åtanke. Tidigare versioner av at.js och stöder inte Adobe Target Views och VEC for SPA.

   ![Dialogrutan Implementeringsinformation](/help/main/c-experiences/assets/imp-200.png)

   Hämta at.js 2.x via Adobe Target-gränssnittet i [!UICONTROL Administration > Implementation]. at.js 2.x kan också distribueras via taggar i [Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html?lang=sv-SE){target=_blank}. Adobe Target-tilläggen är dock för närvarande inte aktuella och stöds inte.

1. Implementera den senaste funktionen hos at.js 2.x: [triggerView()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-triggerview-atjs-2.html?lang=sv-SE){target=_blank} på dina webbplatser.

   När du har definierat vyerna för din SPA där du vill köra ett A/B- eller XT-test implementerar du funktionen `triggerView()` för at.js 2.x med vyerna skickade som en parameter. Detta gör att marknadsförarna kan använda VEC för att utforma och köra A/B- och XT-tester för de vyer som definierats. Om funktionen `triggerView()` inte har definierats för dessa vyer kommer VEC inte att identifiera vyerna och marknadsförarna kan därför inte använda VEC för att utforma och köra A/B- och XT-tester.

   **`adobe.target.triggerView(viewName, options)`**

   | Parameter | Typ | Obligatoriskt? | Validering | Beskrivning |
   | --- | --- | --- | --- | --- |
   | viewName | Sträng | Ja | &#x200B;1. Inga efterföljande blanksteg.<br>2. Kan inte vara tom.<br>3. Visningsnamnet måste vara unikt för alla sidor.<br>4. **Varning**: Visningsnamnet får inte börja eller sluta med `/`. Detta beror på att kunden vanligtvis extraherar visningsnamnet från URL-sökvägen. För oss är&quot;home&quot; och &quot;`/home`&quot; olika.<br>5. **Varning**: Samma vy ska inte aktiveras flera gånger i följd med alternativet `{page: true}`. | Ange valfritt namn som en strängtyp som du vill representera din vy. Det här visningsnamnet visas på panelen [!UICONTROL Modifications] i VEC så att marknadsförare kan skapa åtgärder och köra A/B- och XT-aktiviteter för dem. |
   | alternativ | Objekt | Nej |  |  |
   | alternativ > sida | Boolean | Nej |  | **TRUE**: Standardvärdet för sidan är true. När `page=true` skickas meddelanden till Edge-servrarna för ökat antal visningar.<br>**FALSE**: När `page=false` skickas inga meddelanden för ökat antal inläsningar. Detta bör användas när du endast vill återge en komponent på en sida med ett erbjudande. |

   Nu ska vi gå igenom några exempel på hur funktionen `triggerView()` kan anropas i React för vår hypotetiska e-handels-SPA:

   **Länk: [Hemwebbplats](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/)**

   ![home-response-1](/help/main/c-experiences/assets/react1.png)

   Om vi som marknadsförare vill köra A/B-tester på hela hemsidan kanske vi vill kalla vyn&quot;home&quot; som kan extraheras från webbadressen:

   ```javascript
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

   **Länk: [Produkter &#x200B;](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products)**

   Låt oss titta på ett exempel som är lite mer komplicerat. Som marknadsförare vill vi personalisera produktraden genom att ändra prisetikettens färg till röd efter att en användare klickat på knappen Läs in mer.

   ![reagerar-produkter](/help/main/c-experiences/assets/react4.png)

   ```javascript
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
       var page = this.state.page + 1; // assuming page number is derived from component's state
       this.setState({page: page});
       targetView('PRODUCTS-PAGE-' + page);
     }
   }
   ```

   **Länk: [Utcheckning](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/checkout)**

   ![reagerar utcheckning](/help/main/c-experiences/assets/react6.png)

   Om marknadsförarna vill anpassa innehållet på webbplatsen beroende på vilken leveransinställning som har valts, kan en vy skapas för varje leveransinställning. När vi väljer Normal leverans får du i så fall namnet&quot;Normal leverans&quot;. Om du väljer Express Delivery får du namnet &quot;Express Delivery&quot;.

   Nu kanske marknadsförarna vill göra ett A/B-test för att se om en ändring av färgen från blå till röd när expressleverans är valt kan öka konverteringen i stället för att behålla knappfärgen blå för båda leveransalternativen.

   ```javascript
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

   När `adobe.target.triggerView()` implementeras på din SPA med vynamn skickade som parametrar, kan VEC identifiera dessa vyer och tillåta användare att skapa åtgärder och ändringar för sina A/B- eller XT-aktiviteter.

   >[!NOTE]
   >
   >VEC för SPA är i själva verket samma VEC som du använder på vanliga webbsidor, men vissa ytterligare funktioner är tillgängliga när du öppnar en enkelsidig app med `triggerView()` implementerat.

Det finns två stora förbättringar av panelen [Modifications](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) och Åtgärder för VEC som gör att VEC kan fungera bra med SPA.

**Panelen Ändringar**

Panelen [!UICONTROL Modifications], som visas nedan, fångar funktionsmakron som har skapats för en viss vy. Observera att alla åtgärder för en vy grupperas under den vyn.

**Åtgärder**

Om du klickar på en åtgärd markeras elementet på platsen där den här åtgärden ska tillämpas. Varje VEC-åtgärd som skapas under en vy har följande ikoner, som visas nedan: Information, Redigera, Klona, Flytta och Ta bort.

![Ändringar](/help/main/c-experiences/assets/modifications.png)

I följande tabell beskrivs de olika åtgärderna:

| Sida | Beskrivning |
| --- | --- |
| Information | Visar information om åtgärden. |
| Redigera | Gör att du kan redigera åtgärdens egenskaper direkt. |
| Klona | Klona åtgärden till en eller flera vyer som finns på panelen [!UICONTROL Modifications] eller till en eller flera vyer som du har bläddrat till och navigerat till i VEC. Åtgärden behöver inte nödvändigtvis finnas på panelen [!UICONTROL Modifications].<br>**Obs!** När en klonåtgärd har utförts måste du navigera till vyn i VEC via [!UICONTROL Browse] för att se om den klonade åtgärden var en giltig åtgärd. Om åtgärden inte kan tillämpas på vyn visas ett fel. |
| Flytta | Flyttar åtgärden till en sidinläsningshändelse eller någon annan vy som redan finns på panelen Ändringar.<br>[!UICONTROL Page Load Event] - Alla åtgärder som motsvarar sidans load-händelse tillämpas på den första sidinläsningen i webbprogrammet.<br>**Obs!** När en flyttåtgärd har utförts måste du navigera till vyn i VEC via Browse för att se om flyttningen var en giltig åtgärd. Om åtgärden inte kan användas i vyn visas ett fel |
| Ta bort | Tar bort åtgärden. |

>[!NOTE]
>
>Du kan utföra många åtgärder innan sidan läses in i VEC, eller även om sidan inte läses in helt. Åtgärder som inte kan redigeras innan webbplatsen läses in inaktiveras i användargränssnittet.

**Exempel 1**

Vi hänvisar till exemplet ovan där vi skapade en hemvy. Vårt mål är tvåfaldigt:

1. Ändra knappen Lägg till i kundvagnen och knappen Gilla till en ljusare blå färg. Detta bör vara i en sidinläsning eftersom vi ändrar komponenterna i sidhuvudet.
1. Ändra etiketten&quot;Senaste produkter för 2019&quot; till&quot;Värdprodukter för 2019&quot; med textfärgen ändrad till lila.

Om du vill utföra de här målen klickar du på [!UICONTROL Compose] i VEC och tillämpar ändringarna i hemvyn.

![Exempel 1](/help/main/c-experiences/assets/example1.png)

**Exempel 2**

Vi hänvisar till exemplet ovan där vi skapade en PRODUCTS-PAGE-2-vy. Vårt mål är att ändra prisetiketten till&quot;Försäljningspris&quot; med etikettfärgen röd.

1. Klicka på [!UICONTROL Browse] och sedan på länken [!UICONTROL Products] i sidhuvudet.
1. Klicka [!UICONTROL Load More] en gång för att gå till den andra produktraden.
1. Klicka på [!UICONTROL Compose].
1. Använd åtgärder för att ändra textetiketten till&quot;Försäljningspris&quot; och färgen till röd.

![Exempel 2](/help/main/c-experiences/assets/example2.png)

**Exempel 3**

Slutligen kan vyer definieras på detaljnivå, som tidigare nämnts. Vyer kan vara ett läge eller till och med ett alternativ från en alternativknapp. Tidigare har vi skapat Vyer som CHECKOUT-EXPRESS och CHECKOUT-NORMAL. Vårt mål är att ändra knappfärgen till röd för CHECKOUT-EXPRESS-vyn.

1. Klicka på [!UICONTROL Browse].
1. Lägg några produkter i vagnen.
1. Klicka på kundvagnsikonen längst upp till höger.
1. Klicka på Checka ut din beställning.
1. Klicka på alternativknappen Express Delivery.
1. Klicka på [!UICONTROL Compose].
1. Ändra&quot;Betala&quot;-knappen till&quot;Slutför beställningen&quot; och ändra färgen till röd.

![Exempel 3](/help/main/c-experiences/assets/example3.png)

>[!NOTE]
>
>Vyn CHECKOUT-EXPRESS visas inte på ändringspanelen förrän du klickar på alternativknappen Express Delivery. Detta beror på att funktionen `triggerView()` aktiveras när alternativknappen Express Delivery är markerad och det här är bara när VEC vet att det finns en vy att visa på ändringspanelen.

## Djupdyka in i at.js och SPA

**Hur hämtar jag vyer för de senaste målgruppsdata som har hydrerats av åtgärder efter att den första sidan har lästs in på min SPA?**

Det typiska arbetsflödet för at.js 2.x är när webbplatsen läses in, alla vyer och åtgärder cachelagras så att efterföljande användaråtgärder på webbplatsen inte utlöser några serveranrop för att hämta erbjudanden. Om du vill hämta vyer beroende på de senaste profildata som kan ha uppdaterats beroende på efterföljande användaråtgärder, kan du anropa `getOffers()` och `applyOffers()` med de senaste målgruppsanvändar- eller profildata som skickas.

Anta till exempel att du är ett telekomföretag och har ett SPA som använder at.js 2.x. Som företag vill du uppnå följande mål:

* Visa den senaste företagskampanjen för en utloggad eller anonym användare, t.ex. ett hjälteerbjudande om att vara fri från första månaden på `http://www.telecom.com/home`.
* För en inloggad användare, visa ett uppgraderingserbjudande för användare vars kontrakt närmar sig, t.ex.&quot;Du är berättigad till en kostnadsfri telefon!&quot; på `http://www.telecom.com/loggedIn/home`.

Nu kan utvecklarna namnvisa och ringa `triggerView()` på följande sätt:

* Vynamnet för `http://www.telecom.com/home` är&quot;Utloggad hem&quot;
   * `triggerView("Logged Out Home")` har anropats.
* Vynamnet för `http://www.telecom.com/loggedIn/home` är&quot;Inloggad hemma&quot;
   * `triggerView("Logged In Home")` anropas vid vägändring.

Dina marknadsförare kör sedan följande A/B-aktiviteter via VEC:

* A/B-aktivitet med erbjudandet&quot;Gratis första månaden&quot; för målgrupper med parametern `loggedIn= false` som ska visas i `http://www.telecom.com/home`, där visningsnamnet är Utloggad Hem.
* A/B-aktivitet med&quot;Du är berättigad till en kostnadsfri telefon!&quot; erbjudande för målgrupper med parametern `loggedIn=true` som ska visas i `http://www.telecom.com/loggedIn/home`, där visningsnamnet är inloggat Hero Offer.

Låt oss nu tänka på det här användarflödet:

1. En anonym utloggad användare hamnar på din sida.
1. Eftersom du använder at.js 2.x skickar du parametern `loggedIn = false` vid sidinläsning för att hämta alla vyer som finns i aktiva aktiviteter som är kvalificerade för när målgruppen har parametern `loggedIn = false`.
1. at.js 2.x hämtar sedan vyn Utloggad hemsida och åtgärden som visar erbjudandet&quot;Fri första månaden&quot; och lagrar det i cache-minnet.
1. När `triggerView("Logged Out Home")` anropas hämtas erbjudandet&quot;Första månaden ledigt&quot; från cache och erbjudandet visas utan ett serveranrop.
1. Användaren klickar nu på Logga in och anger sina uppgifter.
1. Eftersom din webbplats är en SPA-fil utför du ingen sidinläsning och dirigerar i stället användaren till `http://www.telecom.com/loggedIn/home`.

Här är problemet. Användaren loggar in och `triggerView("Logged In Home")` upptäcks eftersom koden har placerats på en vägändring. Detta anger att at.js 2.x ska hämta vyn och åtgärderna från cachen, men den enda vy som finns i cachen är Utloggad Hem.

Så hur kan vi sedan hämta vår inloggade vy och visa&quot;Du är berättigad till en kostnadsfri telefon!&quot; erbjudandet? Och eftersom alla efterföljande åtgärder på din webbplats kommer från ett inloggat användarperspektiv, hur kan du se till att alla efterföljande åtgärder resulterar i personaliserade erbjudanden för inloggade användare?

Du kan använda de nya funktionerna `getOffers()` och `applyOffers()` som stöds i at.js 2.x:

```javascript
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

Skicka svaret från `getOffers()` till `applyOffers()`, och nu kommer alla vyer och åtgärder som är kopplade till loggedIn = true att uppdatera cache-minnet för at.js.

Med andra ord har at.js 2.x stöd för ett sätt att hämta vyer, åtgärder och erbjudanden med de senaste målgruppsdata på begäran.

**Stöder at.js 2.x A4T för Single Page-program?**

Ja, at.js 2.x stöder A4T för SPA via funktionen `triggerView()` eftersom du har implementerat Adobe Analytics och Experience Cloud Visitor ID Service. Se diagrammet nedan med stegvisa beskrivningar.

![Målflöde](/help/main/c-experiences/assets/atjs-spa-flow.png)

| Steg | Beskrivning |
| --- | --- |
| 1 | `triggerView()` anropas i SPA för att återge en vy och använda åtgärder för att ändra visuella element som är kopplade till vyn. |
| 2 | Målinnehåll för vyn läses från cachen. |
| 3 | Målinriktat innehåll visas så snabbt som möjligt utan att man behöver flimra standardinnehållet. |
| 4 | En meddelandebegäran skickas till målprofilsarkivet för att räkna besökaren i aktiviteten och ökningsvärdena. |
| 5 | Analysdata skickas till datainsamlingsservrar. |
| 6 | Måldata matchas mot Analytics-data via SDID och bearbetas till lagringsplatsen för analysrapporter. Analysdata kan sedan visas både i Analytics och Target via A4T-rapporter. |

>[!NOTE]
>Om du inte vill skicka meddelanden till Adobe Analytics för att göra avtrycksräkning varje gång en vy utlöses, skickar du `{page: false}` till funktionen `triggerView()` så att avtrycksräkningen inte ökar när en vy utlöses flera gånger för en komponent som återges kontinuerligt. Exempel:
>
>`adobe.target.triggerView("PRODUCTS-PAGE-2", {page:false})`

## Stödda aktiviteter

| Typ av aktivitet | Stöds? |
| --- | --- |
| [A/B-test](/help/main/c-activities/t-test-ab/test-ab.md) | Ja |
| [Rekommendationer som ett erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md)<br>i A/B Test and Experience Targeting-aktiviteter (XT) | Ja |
| [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Ja |
| [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md) | Ja |
| [Multivariattest](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Nej |
| [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Nej |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Nej |
| [Rekommendationer](/help/main/c-recommendations/recommendations.md) | Nej |

**Om vi installerade på .js 2.x och implementerade `triggerView()` på våra webbplatser, hur kör vi A/B-aktiviteter med Automatiskt mål eftersom SPA VEC inte stöder Automatiskt mål?**

Om du vill använda A/B-aktiviteter som mål automatiskt kan du flytta alla åtgärder som ska köras vid sidinläsningshändelse i VEC. Håll pekaren över varje åtgärd och klicka på knappen [!UICONTROL Move to Page Load Event]. När du har gjort det kan du i nästa steg välja Automatiskt mål som metod för trafikallokering.

## Integrationer som stöds

| Integrering | Stöds? |
| --- | --- |
| [Analyser för mål (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | Ja |
| [Experience Cloud-målgrupper](/help/main/c-integrating-target-with-mac/mmp.md) | Ja |
| [Kundattribut](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/customer-attributes.html?lang=sv-SE){target=_blank} | Ja |
| [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | Ja |

## Funktioner som stöds {#supported-features}

| Funktion | Stöds? |
| --- | --- |
| [Arbetsytor och egenskaper](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) | Ja |
| [QA-länkar](/help/main/c-activities/c-activity-qa/activity-qa.md) | Ja |
| [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) | Nej |
| [Anpassad kod](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | Ja |
| [VEC-alternativ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) | Alla |
| [Klickspårning](/help/main/c-activities/r-success-metrics/click-tracking.md) | Ja |
| [Fleraktivitetsleverans](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md) | Ja |

## Inställningar för sidleverans för SPA VEC {#page-delivery-settings}

Med inställningarna för [!UICONTROL Page Delivery] kan du konfigurera regler för att avgöra när en Target-aktivitet ska kvalificera sig och köras för en målgrupp.

Om du vill få tillgång till alternativen för [!UICONTROL Page Delivery] i VEC:s tredelade guidade arbetsflöde för att skapa aktivitet klickar du på **[!UICONTROL Experiences]** (kugghjulsikonen) > **[!UICONTROL Configure]** i **[!UICONTROL Page Delivery]** -steget.

![Dialogrutan Alternativ för sidleverans](/help/main/c-experiences/assets/page-delivery.png)

Som definieras av inställningarna för [!UICONTROL Page Delivery] ovan kvalificerar och körs en Target-aktivitet när en besökare får direktuppspelning på `https://www.adobe.com` *eller* när en besökare får direktuppspelning på en URL som innehåller `https://www.adobe.com/products`. Detta fungerar perfekt för alla flersidiga program där varje interaktion med sidan anropar en sidomladdning, där at.js hämtar de aktiviteter som är kvalificerade för den URL som användaren navigerar till.

Eftersom SPA fungerar annorlunda måste inställningarna för [!UICONTROL Page Delivery] konfigureras på ett sätt som gör att alla åtgärder kan tillämpas på vyerna enligt definitionen i SPA VEC-aktiviteten.

### Exempel på use-case

Här följer ett exempel på hur du använder gemener/VERSALER:

![SPA VEC Modifications-panelen](/help/main/c-experiences/assets/page-delivery-example.png)

Följande ändringar har gjorts:

* Bakgrundsfärgen har ändrats i hemvyn, som finns under URL-adressen: [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/).
* Knappfärgen har ändrats i produktvyn, som finns under URL:en: [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products).

Med exemplet ovan i åtanke, vad händer när vi konfigurerar [!UICONTROL Page Delivery]-inställningarna så att de bara innehåller: [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/) i en SPA med at.js 2.*x*?

![Dialogrutan Sidleverans](/help/main/c-experiences/assets/spa-page-delivery.png)

Följande bild visar begäran om målflöde - sidinläsning i at.js 2.*x*:

![Målflöde - at.js 2.0 Begäran om sidinläsning](/help/main/c-experiences/assets/page-load-request.png)

**Användarresa nr 1**

* En användare navigerar direkt till [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/).
* at.js 2.*x* skickar en fråga till Edge för att se om någon aktivitet behöver köras för URL:en: [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/).
* I steg 6 returnerar Target-Edge åtgärderna för hem- och produktvyn så att de cachas i webbläsaren.

**Resultat**: Användaren ser den gröna bakgrundsfärgen i hemvyn. När användaren sedan navigerar till [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products) visas knappens blå bakgrundsfärg eftersom åtgärden cachas i webbläsaren under produktvyn.

Obs! Användaren som navigerar till [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products) utlöste ingen sidinläsning.

**Användarresa nr 2**

* En användare navigerar direkt till [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products).
* at.js 2.*x* skickar en fråga till Edge för att se om någon aktivitet behöver köras för URL:en: [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products).
* Inga aktiviteter är kvalificerade för [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products).
* Eftersom inga aktiviteter är kvalificerade finns det inga åtgärder och vyer att cachelagra för at.js 2.*x* att utlösa från.

**Resultat**: Även om du har definierat `triggerView()` för produktvyn och gjort en åtgärd för produktvyn via SPA VEC, kommer du inte att se den förväntade åtgärden eftersom du inte skapade en regel som inkluderade [https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products](https://experienceleague.adobe.com/developer/ashop-react-demo/at-js/?lang=sv-SE#/products) i sidleveransinställningarna.

### Bästa praxis

Du ser att det kan vara svårt att hantera användarresan eftersom användarna kan landa på valfri URL i SPA och navigera till andra sidor. Därför är det bäst att ange en regel för sidleverans som innehåller bas-URL:en så att den omfattar hela ditt SPA-avtal. På så sätt behöver du inte tänka på alla olika resor och sökvägar som en användare kan ta för att komma till en sida där du vill visa en A/B-test- eller Experience Targeting-aktivitet (XT).

För att lösa problemet ovan kan vi till exempel ange bas-URL:en i inställningarna för sidleverans:

![Dialogrutan Sidleverans](/help/main/c-experiences/assets/conclusion.png)

Detta garanterar att de åtgärder som tillämpas visas när en besökare kommer till SPA och navigerar till antingen hemvyn eller sidvyn.

När du lägger till en åtgärd i en vy i SPA VEC visas nu följande popup-meddelande som påminner dig om reglerna för [!UICONTROL Page Delivery].

![Meddelande om inställningar för sidleverans](/help/main/c-experiences/assets/pop-up-message.png)

Det här meddelandet visas när du lägger till den första åtgärden i en vy för varje ny aktivitet som du skapar. Det här meddelandet hjälper till att säkerställa att alla i organisationen lär sig hur de här [!UICONTROL Page Delivery]-reglerna ska tillämpas korrekt.

## Utbildningsvideo: Använda VEC för SPA i Adobe Target

>[!VIDEO](https://video.tv.adobe.com/v/26249)

Mer information finns i [Använda Visual Experience Composer för Single Page-program (SPA VEC) i Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html).
