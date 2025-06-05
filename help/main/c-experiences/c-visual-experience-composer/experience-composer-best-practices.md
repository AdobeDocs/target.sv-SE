---
keywords: dispositionsverktyg för visuell upplevelse;bästa praxis för kompositör för visuell upplevelse;begränsningar för kompositör för visuell upplevelse;vec best practices;vec
description: Lär dig de bästa sätten att få dina upplevelser att fungera som förväntat när du använder [!UICONTROL Visual Experience Composer] (VEC).
title: Vad är [!UICONTROL Visual Experience Composer] bästa praxis och begränsningar?
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
source-git-commit: 1f2c6bbabf0158672e5f926ffdf9662637cd8416
workflow-type: tm+mt
source-wordcount: '2435'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer] bästa praxis och begränsningar

Följ bästa praxis när du använder [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) för att försäkra dig om att dina upplevelser fungerar som de ska. Tänk på viktiga tips och begränsningar för att maximera prestanda och undvika vanliga problem.

## Bästa praxis {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

Nedan följer god praxis när du använder VEC:

### Placera at.js-referensen högst upp i avsnittet `<head>` på sidan.

+++Se information
Om du även använder [!UICONTROL Visitor API Service] placerar du besökar-API-skriptet ovanför at.js.

+++

### Du kan aktivera [!UICONTROL Enhanced Experience Composer] på kontonivån (aktiverad för alla aktiviteter som skapas i kontot) eller på den enskilda aktivitetsnivån.

+++Se information
Om du vill aktivera [!UICONTROL Enhanced Experience Composer] på kontonivån klickar du på [!UICONTROL [!UICONTROL Administration] > [!UICONTROL Visual Experience Composer]] och växlar sedan [!UICONTROL Enable Enhanced Experience Composer] till På-positionen.

Om du vill aktivera [!UICONTROL Enhanced Experience Composer] på aktivitetsnivå när du skapar en aktivitet i [!UICONTROL Visual Experience Composer] klickar du på [!UICONTROL Configure > [!UICONTROL Page Delivery]] och växlar sedan [!UICONTROL Enable Enhanced Experience Composer] till På-position.

+++

### Du kan tillåtslista vissa IP-adresser om [!UICONTROL Enhanced Experience Composer] inte läses in på säkra sidor på din webbplats.

+++Se information
Problem med att läsa in [!UICONTROL Enhanced Experience Composer] kan åtgärdas genom att du tillåtslista följande IP-adresser. Dessa IP-adresser är för [!DNL Adobe] servrar som används för proxyn [!UICONTROL Enhanced Experience Composer]. De behövs bara för aktivitetsredigering. Besökare på webbplatsen behöver inte tillåtslista dessa IP-adresser.

Mer information finns i [EEG läser inte in en intern QA-URL som inte är tillgänglig på offentlig IP](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md) i *Felsökning av problem med Förbättrad Experience Composer*.

+++

### Använd unika ID:n för element på den översta nivån och andra element som kan vara bra test-/målinriktningssökande.

+++Information
Allt som finns omedelbart inuti body-elementet ska ha ett unikt ID. Om nya element infogas i brödtexten och koden flyttas runt, är det lättare att identifiera åtminstone de överordnade elementen.

[!DNL Target] behöver inga ID, men om du använder ID:n blir upplevelserna som skapas med upplevelsedispositionen mer tillförlitliga. [!DNL Target] använder CSS-väljare för att ändra ditt innehåll när upplevelsen levereras. När du redigerar en upplevelse kopplar [!UICONTROL Visual Experience Composer] väljaren till det närmaste överordnade objektet med ett ID-attribut som inte är null till det HTML-element som ändras. Därför är det inte tillrådligt att använda någon mekanism, inklusive JavaScript-bibliotek, som ställer in eller ändrar HTML ID-attribut. Även om dessa ID:n kan vara tillgängliga för [!DNL Target] Experience Composer för att skapa aktiviteter, kanske ID:n som användes när upplevelsen skapades inte är tillgängliga när upplevelsen körs om JavaScript ändrar ID:n. Om ett ID inte är tillgängligt misslyckas väljaren som är förankrad till ID:t.

+++

### Namnge CSS-klasser så att de är lätta att identifiera.

+++Information
När du redigerar CSS-klasser i [!DNL Visual Experience Composer] kan det vara bra att göra det enkelt att identifiera klasserna med hjälp av beskrivande klassnamn. Detta säkerställer att du redigerar rätt CSS-klasser och att sidorna visas som förväntat.

Använd inte CSS-egenskapen `!important` när du döljer eller tar bort element.

Om CSS-egenskapen `!important` finns med åsidosätts de ändringar som görs av `target.js` under leveransen av webbplatsens CSS-regler.

+++

### Undvik att använda HTML-tabeller för sidlayouter.

+++Information
[!DNL Target] använder JavaScript för att formatera en sida. Det är svårt att ändra tabellbaserade layouter med JavaScript. Tabellbaserade layouter kanske inte visas på samma sätt i alla webbläsare. Du får bäst resultat om du använder CSS för att skapa sidlayouter.

+++

### Minimera användningen av iFrames.

+++Information
Det är en god vana att minimera användningen av iFrames för att förenkla hantering av sidor och tester. Visuell Experience Composer kan använda vissa åtgärder i en iFrame, men vissa åtgärder, som storleksändring, fungerar inte korrekt. Det är svårt att hantera och ändra storlek på sidor som använder flera iFrames. Det kan leda till problem om du testar stora iFrame-sidor.

+++

### Försök att ordna alla dynamiska DOM-ändringar så snart DOM är klar.

+++Information
Om dina ändringar inte tillämpas innan upplevelseprogrammet används av `target.js` kan innehållsleveransen brytas. Detta händer bara när det finns en DOM-ändring i hierarkin för ett målelement.

+++

### Använd endast oformaterad text eller en bildtagg i dina ankarelement.

+++Information
`<a>Anchor Text</a>`

ELLER

`<a href=""> <img src=""> </img> </a>`

+++

### Undvik blocknivåelement inuti ett infogat element.

+++Information
Blocknivåelement ska inte användas i infogade element som ankarpunkter, omfång och så vidare. Om du gör det förlorar infogade element sin höjd och bredd, vilket innebär att övertäckningsverktyget i [!UICONTROL Visual Experience Composer] kanske inte fungerar som förväntat.

+++

### Använd inte bastaggen på webbplatsen för att lösa URL:er och länkar.

+++Information
VEC hanterar webbplatsen bakom kulisserna med en proxyserver som uppdaterar länkarna. Om du lägger till en bastagg tolkas URL-adresserna som används av proxyservern igen av webbläsaren och visas som brutna.

+++

### Om du använder EDIT HTML för att hantera DOM-strukturen kan väljarna brytas.

+++Information
Om du till exempel har vidtagit två åtgärder:

* En klass har lagts till i Element 1
* Redigerade HTML för Element 1

Varje ändring skapar ett nytt element i VEC. Eftersom den andra åtgärden ändrar element 1 har den andra åtgärden inte längre något att ändra om du tar bort element 1, så ändringen fungerar inte längre.

Om du lägger till ett element med text och sedan redigerar elementet med annan text i en separat åtgärd, visas båda åtgärderna som separata element i kodredigeraren. När du redigerade elementet skapade du ett nytt element som ändrar det ursprungliga elementet som du skapade och som innehåller den redigerade texten. Om du sedan tar bort det ursprungliga elementet kommer den redigerade texten inte att kunna hitta det element som redigerades och kommer inte att visas. Det andra elementet finns kvar i listan med element, men det påverkar inte sidan eftersom elementet det ändras inte längre finns.

Se [Elementväljare i [!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337).

+++

### Använd taggarna `<b>` och `<i>` när du formaterar textelement med textredigeraren.

+++Information
* Använd `<b>` i stället för `<strong>` för fetstil.
* Använd `<i>` i stället för `<em>` för kursiv text.

`<strong>`- och `<em>`-taggar kan ge oväntade resultat.

+++

### Var försiktig när du tar bort formulärfält.

+++Information
Vissa formulärfält kan vara obligatoriska för att skickas. Om du tar bort de formulärfälten kan det påverka inskickade data.

+++

### Inkludera inte `mboxCreate` i skript.

+++Information
Eftersom `mboxCreate` använder `document.write` bör du inte ta med `mboxCreate` i skript. Använd i stället `mboxDefine` och `mboxUpdate` för samma syfte.

+++

### Uppdatera inte ett HTML-fragment med [!DNL Target] om det kräver JavaScript-kod för initieringen.


+++Information
När en åtgärd (Redigera HTML) utförs på sidkomponenter (t.ex. skjutreglage, karuseller) kan leveransen visas som bruten. VEC utför åtgärden efter att sidkomponenten har instansierats av JavaScript.

När sidans innehåll levereras till besökare tillämpas åtgärden innan komponenten instansieras. På grund av detta kan den här komponentens funktionalitet sluta fungera vid leveranstillfället. Funktionaliteten beror på vilken typ av skript som används på den här sidan för att definiera komponenten.

Om du testar leveransen och den fungerar första gången är det inte säkert att den kommer att fortsätta fungera. Det kan finnas (eller inte vara) ett konkurrenstillstånd.

* Om det finns ett tävlingsvillkor fungerar leveransen ibland.
* Om det inte finns något tävlingsvillkor fungerar alltid leveransen.

Testa sidan flera gånger för att säkerställa att leveransen fungerar som förväntat.

+++

### Använd inte en bastagg på webbplatsen för att lösa URL:er och länkar.

+++Information
När du använder [!UICONTROL Enhanced Experience Composer] ändras webbplatsen bakom scenerna av en proxyserver som uppdaterar alla länk-URL:er så att de fungerar i proxyn. Om du lägger till en bastagg tolkas alla dessa URL:er av webbläsaren så att de ser brutna ut.

+++

### Viktig text på webbplatsen som kan användas för målinriktning bör finnas i HTML-koden i ett -element.

+++Information
Du kan t.ex. inte ange text i kundvagnen som mål i VEC om koden är som följer:

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart"> 
   <img alt="Shopping Cart"src="/images/ico-cart.gif"></img> 
   Shopping Cart: 
   <span id="HeaderCartQtyTotal">
      0 
  </span> 
  Items 
  <span id="HeaderCartPriceTotal"></span> 
</a>
```

I det här exemplet är hela ankarelementet markerat i VEC, vilket påverkar andra element negativt om mål utförs.

+++

### Använd inte `top`- eller `self`-variabler i JavaScript-kod.

+++Information
När [!UICONTROL Enhanced Experience Composer] är aktiverat uppdateras värdet för de översta variablerna och självvariablerna för att inaktivera iframe-publicering. Använd en rubrik för X-frame-options för att lägga till iframe busting i stället för anpassade JavaScript-koder.

+++

### Testa alltid webbplatsen om parametrar läggs till när sidan läses in.

+++Information
Om du till exempel vill öppna `www.abc.com` används följande URL-parametrar:

`www.abc.com?mboxEdit=1&mboxDisable=1`

Med de här parametrarna kan du redigera i en iframe.

Kontrollera att webbplatsen läses in som förväntat när du har lagt till parametrar som dessa.

+++

### Kontrollera att sidan öppnas som förväntat i en iframe.

+++Information
Stäng av felsökningstekniker för iframe på din webbplats och kontrollera om webbplatsen öppnas som förväntat i en iframe på en dummy-sida. Exempel:

```html
<!DOCTYPE 
<html> 
<html> 
<head> 
  <meta charset="utf-8"> 
  <meta name="viewport" content="width=device-width"> 
  <title>JS Bin</title> 
</head> 
<body> 
  <iframe src="https://www.homedepot.com"</iframe> 
</body> 
</html>
```

+++

## Caveats {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

Tänk på följande kavattningar när du använder [!UICONTROL Visual Experience Composer] för att utforma din aktivitet.

### Funktionen [!UICONTROL Move] stöder inte z-index.

+++Information
Eftersom det inte finns någon z-index-funktion kan det flyttade elementet inte flyttas över ett annat element. Mer information finns i [Begränsningar](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

+++

### Om du ändrar ordning på elementen påverkas klickspårningen.

+++Information
Om ett element som är markerat för klickspårning ordnas om ändras sökvägarna för de omordnade elementen. Det innebär att elementet på den plats där det ursprungliga elementet fanns innan det sorterades om är det vars klick spåras.

Detta beror på att både koden för att leverera aktivitetsinnehållet och koden för att spåra klickningar ingår i en del kod som levereras till sidan. Om du bläddrar till en annan sida och ställer in klickspårning skickas aktivitetsinnehållskoden och klickspårningskoden till den sidan. Om klickspårningssidan har en liknande sidstruktur som den sida där testet körs, kan testinnehållet också visas på klickspårningssidan.

+++

### Det är inte säkert att infogning av ett element fungerar i en `<div>` som är en mbox.

+++Information
Om en mbox innehåller ett erbjudande kan infogning av ett element visas som `insertBefore` och inte `insertAfter`, om mbox implementeras felaktigt.

+++

### När du redigerar både ett överordnat och ett underordnat element redigerar du det överordnade först.

+++Information
Om du byter ut en bildåtgärd mot ett element och sedan redigerar texten eller HTML i det överordnade elementet kan leveransproblem uppstå. Det bästa arbetsflödet är att redigera det överordnade elementet innan bilden byts ut mot det underordnade elementet.

+++

### Det går inte att markera sidelement som innehåller en mbox som underordnat element.

+++Information
Om sidan innehåller:

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

Den yttre diven ska inte väljas i en upplevelse eftersom mbox som är hårdkodad på sidan fortfarande anropar [!DNL Target] och får ett svar. Detta svar stör det svar som är avsett för det större sidelementet.

+++

### Proxy-IP:n kan blockeras i kundmiljön.

+++Information
Om du använder [!UICONTROL Enhanced Experienced Composer] på en icke-aktiv webbplats, till exempel en staging-miljö, kan du se timeout och nekad åtkomst om webbplatsen blockerar RIP.

+++

## Begränsningar {#section_F33C2EA27F2E417AA036BC199DD6C721}

Tänk på följande begränsningar när du arbetar med VEC:

### Hanterar VEC-kompatibilitet med ändringar av tilläggsprincipen för [!DNL Chrome]. {#ext}

+++Information
På grund av uppdaterade [V3-manifestprinciper i Google Chrome](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank} kan tillägg inte längre ändra den ursprungliga DOM-filen innan den tolkas av webbläsaren. Därför kan vissa säkerhetsskript, som implementeringar av iframe-busting, blockera sidor från att läsas in i VEC.

För att säkerställa kompatibilitet bör dessa skript inaktiveras villkorligt när sidan läses in inuti iframe [!DNL Target]. Den här processen kan utföras på ett säkert sätt genom att kontrollera om objektet `window.adobeVecExtension` finns, vilket injiceras av [!DNL Target] under VEC-inläsning.

Följande kodfragment är exempel på iframe-busting-kod som kan leda till att webbsidan inte läses in i VEC:

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

En enkel kontroll kan användas för att verifiera när en webbsida är inbäddad i [!DNL Target]. Ett kodfragment bör se ut så här:

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

### Du kan inte flytta ett element utanför en behållare följt av en CSS-egenskap.

+++Information
Ett element kan inte flyttas utanför en behållare som följs av en CSS-egenskap.

+++

### Du kan inte välja elementet [!UICONTROL Button] för att ordna om.

+++Information
[!UICONTROL Button] element kan inte väljas direkt för att sortera om. Om du vill aktivera omsortering placerar du knappar i en större behållare.

+++

### Endast utbyteserbjudanden är tillgängliga för mboxes.

+++Information
Åtgärder som [!UICONTROL Edit Class] och [!UICONTROL Rearrange] tillåts inte i en mbox.

+++

### Du bör inte ordna om och flytta samma element.

+++Information
Om ett element har flyttats till en annan plats, och du väljer den överordnade behållaren och försöker att ordna om de underordnade elementen, påverkas inte det flyttade elementet, utan behåller sin plats. Omordningen kanske inte ser ut som du vill ha den.

+++

### Åtgärden [!UICONTROL Change Image] fungerar inte på en bild i en karusell.

+++Information
Om sidan till exempel innehåller en karusell med sex bilder och du vill byta ut en bild mot den andra bilden i karusellen, fungerar inte åtgärden [!UICONTROL Change Image].

Du kan lösa problemet genom att välja den överordnade behållaren och använda åtgärden [!UICONTROL Edit HTML] för att redigera HTML för karusellen för att uppdatera bildkällan för den önskade bilden.

+++

### Det går inte att ändra storlek på bilder i en mbox.

+++Information
Om du byter ut en bild i ett mbox-element och sedan försöker ändra storlek på bilden enligt mbox-elementets storlek, tillåts inte storleksändring.

+++

### När du har bytt ut en bild kan du inte välja åtgärden [!UICONTROL Edit].

+++Information
När du har bytt bild kan du inte redigera Scene7-URL:en.

+++

### Det går inte att redigera HTML-element med en extern källa.

+++Information
Exempel: Video, ljudtaggar, embed, iFrames, frames.

+++

### Klickspårning fungerar inte för fästpunktselement som innehåller något annat än oformaterad text eller bildtaggar.

+++Information
Klickspårning fungerar till exempel inte om elementet innehåller JavaScript.

+++

### Sidorna måste acceptera URL-parametrar för att VEC ska fungera.

+++Information
Vissa webbplatser tar bort URL-parametrar för sina sidor. VEC kräver dock dessa parametrar.

+++

### När du använder ett skript som en del av HTML, ska alla variabler och funktioner som är åtkomliga utifrån deklareras under fönstrets namnutrymme.

+++Information
Skriptet körs inom omfånget `target.js` efter att sidan har lästs in. Därför går det inte att komma åt variabeln eller funktionen som deklarerats lokalt utanför skriptblocket.

*Felaktigt:*

```html
<script> 
  var myVar = 123; 
  function myFunc() { 
    // 
  } 
</script>`
```

*Korrekt:*

```html
<script> 
  window.myVar = 123; 
  window.myFunc = function() { 
    // 
  }; 
</script>
```

+++

### Om du infogar en bild från [!UICONTROL Content]-biblioteket (Scene7) och redigerar HTML bryts bildens URL.

+++Information
Lägg till ett ankarpunktselement i diven customHeaderMessage med lite dummy-text:

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

Välj den här diven med åtgärden [!UICONTROL Insert Element] om du vill infoga en bild som en jämställd bild i den här dummy-texten div.

När bilden har infogats ser den ut så här:

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

Ta bort det tomma textintervallet.

+++

### Åtgärden `customCode` i VEC fungerar inte med [!DNL Internet Explorer] 8.

+++Information
På grund av begränsningar i IE8 vid hantering av skriptinnehåll stöder `target.js` inte detta i IE8. Om sidan innehåller jQuery och visas i fönsterobjektet globalt kan `target.js` som en tillfällig lösning använda åtgärden `customCode`. Kontrollera att `window.jQuery` och `window.jQuery.fn.prepend` är definierade.

+++

### Klickspårning stöds bara på den sida där upplevelser skapas eller på den omdirigerade sidan.

+++Information
Visserligen är läget [!UICONTROL Browse] tillgängligt för klickspårning i VEC, men [!UICONTROL Browse] kan inte användas för att lägga till klickspårning på en sida.

+++
