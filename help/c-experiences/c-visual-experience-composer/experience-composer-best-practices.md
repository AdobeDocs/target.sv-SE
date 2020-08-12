---
keywords: visual experience composer;visual experience composer best practices;visual experience composer limitations;visual experience composer caveats;vec best practices;vec
description: Med hjälp av bästa praxis kan ni få era upplevelser att fungera som förväntat. Det finns även andra tips och begränsningar som du bör känna till när du använder Visual Experience Composer (VEC).
title: Visuell Experience Composer - bästa praxis och begränsningar
feature: null
topic: Classic
uuid: 8d1d199b-b3d7-4edb-ba05-bd97372a0b9e
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '2442'
ht-degree: 0%

---


# Visuell Experience Composer - bästa praxis och begränsningar{#visual-experience-composer-best-practices-and-limitations}

Med hjälp av bästa praxis kan ni få era upplevelser att fungera som förväntat. Det finns även andra tips och begränsningar som du bör känna till när du använder Visual Experience Composer (VEC).

Genom att följa dessa standarder är det mindre troligt att du får oväntade problem med de upplevelser du designar.

## Bästa praxis {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

**För mbox.js version 57 och senare, och för at.js, placerar du referensen mbox.js eller at.js högst upp på`<head>`sidan.**

Om du även använder Visitor API-tjänsten placerar du besökar-API-skriptet ovanför mbox.js eller at.js.

**För versioner av mbox.js före version 57 ska du placera mbox.js-koden så lågt som möjligt i sidans`<head>`avsnitt.**

Placera mbox.js i slutet av `<head>` avsnittet utan ytterligare deklarationer. I annat fall flyttas skript och länktaggar till `<body>` avsnittet.

**Du kan aktivera Förbättrad Experience Composer på kontonivå (aktiverat för alla aktiviteter som skapas i kontot) eller på den enskilda aktivitetsnivån.**

Om du vill aktivera Förbättrad Experience Composer på kontonivån klickar du på [!UICONTROL Administration > Visual Experience Composer]och växlar sedan till På-position.

Om du vill aktivera Förbättrad Experience Composer på aktivitetsnivå när du skapar en aktivitet i Visual Experience Composer klickar du på [!UICONTROL Configure > URL]och växlar sedan till På-position.

**Du kan tillåtslista vissa IP-adresser om Förbättrad Visual Experience Composer inte läses in på säkra sidor på din webbplats.**

Problem med att läsa in den utökade Visual Experience Composer kan lösas genom att du tillåtslista följande IP-adresser. De här IP-adresserna är för Adobe-servern som används som proxy för Enhanced Experience Composer. De behövs bara för aktivitetsredigering. Besökare på webbplatsen behöver inte tillåtslista dessa IP-adresser.

USA: 52.55.99.45, 54.80.158.92 och 54.204.197.253

Europa, Mellanöstern och Afrika (EMEA): 52.51.238.221, 52.210.199.44 och 54.72.56.50

Asien-Stillahavsområdet (APAC): 52.193.67.35, 54.199.198.109 och 54.199.241.57

**Använd unika ID:n för element på den översta nivån och andra element som kan vara bra test-/målinriktningssökande.**

Allt som finns omedelbart inuti body-elementet ska ha ett unikt ID. Om nya element infogas i brödtexten och koden flyttas runt, är det lättare att identifiera åtminstone de överordnade elementen.

Adobe Target behöver inga ID, men om du använder ID:n blir upplevelserna som skapas med upplevelsedispositionen tillförlitligare. Target använder CSS-väljare för att ändra innehållet när upplevelsen levereras. När du redigerar en upplevelse fäster Visual Experience Composer väljaren till det närmaste överordnade objektet med ett id-attribut som inte är null till det HTML-element som ändras. Därför är det inte tillrådligt att använda någon mekanism, inklusive JavaScript-bibliotek, som ställer in eller ändrar HTML ID-attribut. Dessa ID:n kan vara tillgängliga för Target Experience Composer för att skapa aktiviteter, men om JavaScript ändrar ID:n är det ID som användes när upplevelsen skapades kanske inte tillgängligt när upplevelsen körs. Om ett ID inte är tillgängligt misslyckas väljaren som är förankrad till ID:t.

**Namnge CSS-klasser så att de är lätta att identifiera.**

När du redigerar CSS-klasser i Visual Experience Composer kan det vara praktiskt att göra klasserna enkla att identifiera genom att använda beskrivande klassnamn. Detta säkerställer att du redigerar rätt CSS-klasser och att sidorna visas som förväntat.

Använd inte `!important` CSS-egenskapen när du döljer eller tar bort element.

Om CSS-egenskapen 1!important1 finns kommer ändringar som görs av target.js under leveransen att åsidosättas av webbplatsens CSS-regler.

**Undvik att använda HTML-tabeller för sidlayouter.**

Target Standard och Premium använder JavaScript för att formatera en sida. Det är svårt att ändra tabellbaserade layouter med JavaScript. Tabellbaserade layouter kanske inte visas på samma sätt i alla webbläsare. Du får bäst resultat om du använder CSS för att skapa sidlayouter.

**Minimera användningen av iFrames.**

Det är en god vana att minimera användningen av iFrames för att förenkla hantering av sidor och tester. Den visuella upplevelsedispositionen kan använda vissa åtgärder i en iFrame, men vissa åtgärder, som storleksändring, fungerar inte korrekt. Det är svårt att hantera och ändra storlek på sidor som använder flera iFrames. Det kan leda till problem om du testar stora iFrame-sidor.

**Försök att ordna alla dynamiska DOM-ändringar så snart DOM är klar.**

Om ändringarna inte tillämpas innan upplevelseprogrammet körs av target.js kan innehållsleveransen brytas. Detta händer bara när det finns en DOM-ändring i hierarkin för ett målelement.

**Använd endast oformaterad text eller en bildtagg i dina ankarelement.**

`<a>Anchor Text</a>`

ELLER

`<a href=""> <img src=""> </img> </a>`

**Undvik blocknivåelement inuti ett infogat element.**

Blocknivåelement ska inte användas i infogade element som ankarpunkter, omfång och så vidare. Om du gör det förlorar infogade element sin höjd och bredd, vilket innebär att övertäckningsverktyget i Visual Experience Composer kanske inte fungerar som förväntat.

**Använd inte bastaggen på webbplatsen för att lösa URL:er och länkar.**

Visual Experience Composer hanterar webbplatsen bakom scenerna med en proxyserver som uppdaterade länkarna. Om du lägger till en bastagg tolkas URL-adresserna som används av proxyservern igen av webbläsaren och visas som brutna.

**Om du använder REDIGERA HTML för att hantera DOM-strukturen kan väljarna brytas.**

Om du till exempel har vidtagit två åtgärder:

* En klass har lagts till i Element 1
* HTML för element 1 har redigerats

Varje ändring skapar ett nytt element i Visual Experience Composer. Eftersom den andra åtgärden ändrar element 1 har den andra åtgärden inte längre något att ändra om du tar bort element 1, så ändringen fungerar inte längre.

Om du lägger till ett element med text och sedan redigerar elementet med annan text i en separat åtgärd, visas båda åtgärderna som separata element i kodredigeraren. När du redigerade elementet skapade du ett nytt element som ändrar det ursprungliga elementet som du skapade och som innehåller den redigerade texten. Om du sedan tar bort det ursprungliga elementet kommer den redigerade texten inte att kunna hitta det element som redigerades och kommer inte att visas. Det andra elementet finns kvar i listan med element, men det påverkar inte sidan eftersom elementet det ändras inte längre finns.

Se [Elementväljare som används i Visual Experience Composer](../../c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337) .

**Använd`<b>`och`<i>`taggar när du formaterar textelement med textredigeraren.**

* Använd i stället `<b>` för fetstil `<strong>`.
* Använd `<i>` i stället för `<em>`för kursiv text.

`<strong>` och - `<em>` taggar kan ge oväntade resultat.

**Var försiktig när du tar bort formulärfält.**

Vissa formulärfält kan vara obligatoriska för att skickas. Om du tar bort de formulärfälten kan det påverka inskickade data.

**Inkludera inte`mboxCreate`skript.**

Eftersom `mboxCreate` används `document.write`bör du inte ta med `mboxCreate` i skript. Använd `mboxDefine` och `mboxUpdate` för samma ändamål.

**Uppdatera inte ett HTML-kodfragment med Target Standard om det kräver JavaScript-kod för initieringen.**

När en åtgärd (Redigera HTML) utförs på sidkomponenter (t.ex. skjutreglage, Carousel) kan leveransen visas som bruten. Visual Experience Composer utför åtgärden efter att sidkomponenten har instansierats av JavaScript.

När sidans innehåll levereras till besökare tillämpas åtgärden innan komponenten instansieras. På grund av detta kan den här komponentens funktionalitet sluta fungera vid leveranstillfället. Funktionaliteten beror på vilken typ av skript som används på den här sidan för att definiera komponenten.

Om du testar leveransen och den fungerar första gången är det inte säkert att den kommer att fortsätta fungera. Det kan finnas (eller inte vara) ett konkurrenstillstånd.

* Om det finns ett tävlingsvillkor fungerar leveransen då och då.
* Om det inte finns något tävlingsvillkor kommer det alltid att fungera.

Testa sidan flera gånger för att säkerställa att leveransen fungerar som förväntat.

**Använd inte en bastagg på webbplatsen för att lösa URL:er och länkar.**

När du använder Förbättrad Experience Composer hanteras webbplatsen bakom kulisserna av en proxyserver som uppdaterar alla länk-URL:er så att de fungerar i proxyn. Om du lägger till en bastagg tolkas alla dessa URL:er av webbläsaren så att de ser brutna ut.

**Viktig text på webbplatsen som kan användas för målinriktning bör behållas i HTML-kod i ett -element.**

Du kan t.ex. inte ange text i kundvagnen som mål i VEC om koden är som följer:

```
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

I det här exemplet markeras hela ankarelementet i VEC, vilket påverkar andra element negativt om du väljer målinriktning.

**Använd inte`top`variabler eller`self`variabler i JavaScript-kod.**

När Förbättrad Experience Composer är aktiverat uppdateras värdet för de översta variablerna och självvariablerna för att inaktivera iframe-publicering. Använd ett X-frame-options-huvud för att lägga till iframe busting i stället för anpassade JavaScript-koder.

**Testa alltid webbplatsen om parametrar läggs till när sidan läses in.**

Om du till exempel vill öppna www.abc.com används följande URL-parametrar:

`www.abc.com?mboxEdit=1&mboxDisable=1`

Dessa parametrar gör det möjligt att redigera i en iframe.

Kontrollera att webbplatsen läses in som förväntat när du har lagt till parametrar som dessa.

**Kontrollera att sidan öppnas som förväntat i en iframe.**

Stäng av felsökningstekniker för iframe på webbplatsen och kontrollera om den öppnas som förväntat i en iframe på en dummy-sida. Exempel:

```
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

## Caveats {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

Tänk på följande när du använder Visual Experience Composer för att utforma din aktivitet.

**Funktionen Flytta stöder inte z-index.**

Eftersom det inte finns någon z-index-funktion kan det flyttade elementet inte flyttas över ett annat element. Mer information finns i [Begränsningar](../../c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721) .

**Om du ändrar ordning på elementen påverkas klickspårningen.**

Om ett element som är markerat för klickspårning ordnas om ändras sökvägarna för de omordnade elementen. Det innebär att elementet på den plats där det ursprungliga elementet fanns innan det sorterades om är det vars klick spåras.

Detta beror på att både koden för att leverera aktivitetsinnehållet och koden för att spåra klickningar ingår i en del kod som levereras till sidan. Om du bläddrar till en annan sida och ställer in klickspårning skickas aktivitetsinnehållskoden och klickspårningskoden till den sidan. Om klickspårningssidan har en liknande sidstruktur som den sida där testet körs, kan testinnehållet också visas på klickspårningssidan.

**Det är inte säkert att infogning av ett element fungerar i en mbox`<div>`som är en.**

Om en mbox innehåller ett erbjudande kan infogning av ett element visas som insertBefore och inte insertAfter, om mbox implementeras felaktigt.

**När du redigerar både ett överordnat och ett underordnat element redigerar du det överordnade först.**

Om du byter ut en bildåtgärd mot ett element och sedan redigerar texten eller HTML-koden i det överordnade elementet kan leveransproblem uppstå. Det bästa arbetsflödet är att redigera det överordnade elementet innan bilden byts ut mot det underordnade elementet.

**Det går inte att markera sidelement som innehåller en mbox som underordnat element.**

Om sidan till exempel innehåller:

```
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

Den yttre diven ska inte väljas i en upplevelse eftersom mbox som är hårdkodad på sidan fortfarande anropar Target och får ett svar. Detta svar stör det svar som är avsett för det större sidelementet.

**Proxy-IP:n kan blockeras i kundmiljön.**

Om du använder Förbättrad upplevelsedisposition på en icke-aktiv webbplats, till exempel en staging-miljö, kan du se timeout och få åtkomst till nekade fel om webbplatsen blockerar RIP.

**När du lägger till flera sidor öppnas både upplärningslisten och sidlisten samtidigt. Det här minskar till slut bredden på Visual Experience Composer så att webbplatsen visas för optimeringar. Därför kan omflödningsbara platser börja se annorlunda ut än väntat i det reducerade utrymmet.**

Du kan kringgå problemet genom att komprimera upplevelsefältet och sidlisten genom att klicka på de vänstra ikonerna överst.

## Begränsningar {#section_F33C2EA27F2E417AA036BC199DD6C721}

**Flytta funktion**

Ett element kan inte flyttas utanför en behållare som följs av en CSS-egenskap.

**Endast utbyteserbjudanden är tillgängliga för mboxes.**

Åtgärder som Redigera klass och Ändra ordning tillåts inte i en mbox. Mbox-innehåll hanteras av mbox.js.

**Du bör inte ordna om och flytta samma element.**

Om ett element har flyttats till en annan plats, och du väljer den överordnade behållaren och försöker att ordna om de underordnade elementen, påverkas inte det flyttade elementet, utan behåller sin plats. Omordningen kanske inte ser ut som du önskar.

**Växla bildåtgärd fungerar inte på en bild i en karusell.**

Om sidan till exempel innehåller en karusell med sex bilder och du vill byta ut en bild mot den andra bilden i karusellen, fungerar inte åtgärden Växla bild.

Du kan lösa problemet genom att välja den överordnade behållaren och använda åtgärden Redigera HTML för att redigera HTML-koden för karusellen för att uppdatera bildkällan för den önskade bilden.

**Det går inte att ändra storlek på bilder i en mbox.**

Om du byter ut en bild i ett mbox-element och sedan försöker ändra storlek på bilden enligt mbox-elementets storlek, tillåts inte storleksändring.

**När du har bytt ut en bild kan du inte välja åtgärden Redigera.**

När du har bytt bild kan du inte redigera Scene7-URL:en.

**HTML-element med extern källa kan inte redigeras.**

Till exempel: video, ljudtaggar, inbäddning, iFrames, bildrutor.

**Klickspårning fungerar inte för fästpunktselement som innehåller något annat än oformaterad text eller bildtaggar.**

Klickspårning fungerar till exempel inte om elementet innehåller JavaScript.

**Sidorna måste acceptera URL-parametrar för att Visual Experience Composer ska fungera.**

Vissa webbplatser tar bort URL-parametrar för sina sidor. Visual Experience Composer kräver dock dessa parametrar.

**När du använder ett skript som en del av html ska alla variabler och funktioner som är åtkomliga utifrån deklareras under fönstrets namnutrymme.**

Skriptet körs inom omfånget för target.js efter att sidan har lästs in. Därför går det inte att komma åt variabeln eller funktionen som deklarerats lokalt utanför skriptblocket.

*Felaktigt:*

```
<script> 
  var myVar = 123; 
  function myFunc() { 
    // 
  } 
</script>`
```

*Korrekt:*

```
<script> 
  window.myVar = 123; 
  window.myFunc = function() { 
    // 
  }; 
</script>
```

**Om du infogar en bild från innehållsbiblioteket (Scene7) och redigerar HTML bryts bildens URL.**

Lägg till ett ankarpunktselement i diven customHeaderMessage med lite dummy-text:

```
<a href="#"> 
<span> Dummy text </span>
</a>
```

Markera den här diven med åtgärden Infoga element om du vill infoga en bild som en jämställd bild i den här diven med dummy-text.

När bilden har infogats ser den ut så här:

```
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

Ta bort det tomma textintervallet.

**Åtgärden customCode i Visual Experience Composer fungerar inte med Internet Explorer 8.**

På grund av begränsningar i IE8 vid hantering av skriptinnehåll stöder inte target.js detta i IE8. Om sidan innehåller jQuery och visas i fönsterobjektet globalt kan target.js använda åtgärden customCode för att lösa problemet. Kontrollera att window.jQuery och window.jQuery.fn.prepend är definierade.

**Klickspårning stöds bara på den sida där upplevelser skapas eller på den omdirigerade sidan.**

Även om bläddringsläget är tillgängligt i Click Track VEC kan det inte användas för att lägga till klickspårning på en sida.
