---
keywords: mbox.js changes;mbox.js versions
description: Läs om den gamla implementeringen av mbox.js i Adobe Target. Migrera till Adobe Experience Platform Web SDK (AEP Web SDK) eller till den senaste versionen av at.js.
title: Vad ingår i varje version av mbox.js?
feature: at.js
role: Utvecklare
exl-id: 4e95de13-2848-497a-9d06-41e9cbd98b42
translation-type: tm+mt
source-git-commit: 60c3dfe28f3618113d4d03da538e4d0e4ac2feb8
workflow-type: tm+mt
source-wordcount: '2407'
ht-degree: 0%

---

# mbox.js versionsinformation{#mbox-js-version-details}

På den här sidan visas ändringar för varje version av mbox.js.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Migrera till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

>[!NOTE]
>
>Adobe rekommenderar att alla användare av mbox.js uppgraderar till version 57 eller senare. En del användare har stött på timeoutproblem när `target.js` inte kunde läsas in. Version 57 åtgärdade problemet. Om du använder tjänsten [!DNL Experience Cloud Visitor ID] krävs dock version 58 eller senare.

Hur Target svarar på samtal från din sida beror på vilken version av målbiblioteket du använder, om implementeringen av besökar-ID finns och om besökar-ID finns. Mer information finns i [Target Call Responses by Library Version](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/call-responses-library-version.md#concept_A95A4758A1E7405D947E9B4BCB5D62F0).

>[!NOTE]
>
>Biblioteket mbox.js utvecklas inte längre. Alla kunder bör migrera från mbox.js till at.js. Mer information finns i [Migrera till at.js från mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## mbox.js version 63 {#section_ED8EFCF653A845ED8927F759578C4A33}

**Målversion:** 17.7.1

[!DNL mbox.js] version 63 är nu tillgänglig. Mer information finns i [Hämta mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/target-download-config-mbox.md).

Följande förbättringar och korrigeringar ingår i version 63 av [!DNL mbox.js]:

* Korrigerar ett problem med SDID-generering när `mboxDefine()` och `mboxUpdate()` används. Problemet berör endast klienter som har Visitor API på sidan.

## mbox.js version 62 {#section_723A9119FE204183847D3B0929A99B41}

* Flimmerproblem i omdirigeringsaktiviteter som visas i Google Chrome-webbläsare har korrigerats.
* `secureOnly`-inställningen som anger om mbox.js ska använda enbart HTTPS eller tillåtas växla mellan HTTP och HTTPS baserat på sidprotokollet. Den här inställningen är en avancerad inställning som har standardvärdet Falskt.

## mbox.js version 61 {#section_F3B59C5578B64883AE013B9342151193}

**Målversion:** 16.7.2

**Releasedatum:28** juli 2016

mbox.js version 61 innehåller följande förbättringar:

* Genereringsalgoritmen för mboxSession ID i JavaScript-API:t genererar nu en slumpmässig sträng i stället för att använda en tidsstämpel plus en slumpmässig sträng.
* Följande information gäller bara om du har Visitor API på sidan:

   * [!DNL mbox.js] version 61 åsidosätter inte  `loadTimeout` egenskapen för Visitor API. Klienter kan använda `visitorApiTimeout` + `visitorApiPageDisplayTimeout` för att styra integreringen av Visitor API.
   * En `optoutEnabled`-inställning har lagts till som stöd för framtida avanmälningsfunktioner för Adobe Experience Cloud. Standardvärdet är false. Om den här egenskapen är aktiverad körs alla begäranden asynkront mot [!DNL /ajax]-slutpunkten, precis som version 60.
   * Dölj brödtext är inaktiverat som standard. Målet använder endast dolt innehåll när den globala mbox-autoskapa är aktiverad och dolt innehåll är aktiverat.
   * Om det inte finns några Experience Cloud Visitor ID-cookies körs alla begäranden asynkront mot [!DNL /ajax] vid första sidinläsningen. Vid inläsning av den andra sidan använder Target det normala flödet eftersom det redan finns Visitor-ID-värden.
   * Om du använder Adobe Analytics som aktivitetens rapportkälla behöver du inte ange en spårningsserver när du skapar en aktivitet om du använder mbox.js version 61 (eller senare) eller at.js version 0.9.1 (eller senare). Mbox.js- eller at.js-biblioteket skickar automatiskt spårningsservervärden till [!DNL Target]. När aktiviteten skapas kan du lämna fältet [!UICONTROL Tracking Server] tomt på sidan [!UICONTROL Goals & Settings].

## mbox.js version 60 {#section_3BDAB885FA13444A8D35940A4BFF5825}

**Målversion:** 16.4.1

**Releasedatum:21** april 2016

Som standard är sidinnehåll inte dolt. Version 60 döljer endast sidinnehåll när alternativet&quot;skapa global mbox automatiskt&quot; är aktiverat. CSS-egenskapen `opacity:0` används för att dölja sidor i stället för `display:none`. Den här egenskapen säkerställer korrekt leverans för responsiva webbplatser och är anpassad efter [!DNL at.js].

Du kan aktivera dold text med två inställningar:

* `bodyHidingEnabled` Standardvärdet är false, vilket betyder att HTML BODY inte är dold.

* bodyHiddenStyle

   Standardvärdet är `body{opacity:0}`. Värdet kan ändras till något annat, som `body{display:none}`.

De här inställningarna kan åsidosättas genom att du inkluderar något som:

```
<script> 
window.targetGlobalSettings = { 
 bodyHidingEnabled: true, 
 bodyHiddenStyle: "body{opacity:0}", 
 visitorApiPageDisplayTimeout: 2000 
}; 
</script>
```

När du döljer sidan används formatmärkord för att lägga till och ta bort format. Med den här tekniken ser du till att webbplatsens format inte ändras när sidan döljer kod körs.

**DTM-användare:** Den här tekniken förhindrar att du använder alternativet för automatisk import eftersom det inte finns något sätt att spara ovanstående konfiguration i målgränssnittet. Du måste använda instruktionerna ovan och sedan klistra in innehållet i kodrutan i alternativet Anpassad värdtjänst.

Om filen [!DNL visitorAPI.js] finns för Experience Cloud Visitor ID-tjänsten i version 60 begärs även alla kryssrutor via en AJAX slutpunkt. Den här processen krävs eftersom API-metoder för Visitor är asynkrona. En fördel med det här arbetssättet är att startåtergivningstiden minskar dramatiskt, eftersom mbox-begäranden inte blockerar återgivningen. Den här metoden innebär dock också att allt [!DNL Target]-innehåll körs asynkront, så all erbjudandekod måste skrivas i enlighet med detta. Erbjudanden som innehåller `document.write` och annan kod som antar att den körs vid den inledande sidinläsningen körs inte som förväntat.

* asynkrona V60-anrop

   När du använder v60 med besökar-id-tjänsten görs alla mbox-anrop asynkront. Det här är en förändring från hur kryssrutor alltid har fungerat, så var försiktig om du uppgraderar till den här versionen. Granska avsnittet [Asynkrona överväganden](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#section_B586360A3DD34E2995AE25A18E3FB953) i [!DNL at.js]-dokumentationen ( [!DNL at.js] använder även asynkrona anrop) för att förstå några av riskerna.
* Nya besökarscenarier kan ha flimmer

   När du använder v58 till v60 med besökar-id-tjänsten, anropar mbox väntan på att besökar-ID:t ska anges innan utlösen (eller tills en timeout har inträffat). Detta sker vid inläsning av första sidan för en ny besökare.

## mbox.js version 59 {#section_FF0E70C4C17E402D8374DE428C5D996E}

**Målversion:** 16.2.1

**Releasedatum:17** februari 2016

mbox.js version 59 innehåller följande förbättringar:

* Mbox inaktiverad har sänkts till 30 minuter
* Ett problem med att dölja/visa sidor har åtgärdats

   I stället för att använda `display:none` för att dölja sidan som i version 58, används `opacity:0`. Detta löser problem med responsiva webbplatser som skapats med den tidigare metoden att dölja sidan.

## mbox.js version 58 {#section_5070B0D1C87F4937BB97727923DD36C7}

**Målversion:** 15.7.1

**Releasedatum:30** juli 2015

Den här versionen av mbox.js krävs om du använder Analytics som rapportkälla för Target och rekommenderas för profiler och målgrupper.

Version 58 av mbox.js ser till att Experience Cloud Visitor ID-tjänsten returneras med ett besökar-ID innan Target-anrop görs. Detta garanterar att målgruppsdata som delas via huvudtjänsten Profiler och Publiker är tillgängliga för det första Target-anropet under besökarens session. För att undvika flimmer av standardinnehållet innan testinnehållet returneras döljs `<BODY>` tills besökar-ID-tjänsten returnerar. `display:none` används för att dölja sidan.

Uppdateringen åtgärdar också ett problem när Analytics används som rapportkälla för Target som gjorde att ett stort antal besökare rapporterades i Analytics för besök som bara innehöll en sida.

Mbox.js anger timeout-värden om besökar-ID-tjänsten inte returnerar. Standardtimeout för besökar-ID-tjänsten är 500 ms (0,5 sekunder). En extra timeout anger den övre gränsen för hur länge taggen `<BODY>` är dold. Standardvärdet är 500 ms (0,5 sekunder). Dessa timeout-värden kan ändras genom att följande kod infogas före referensen mbox.js på varje sida:

```
<script> 
window.targetGlobalSettings = { 
 visitorApiTimeout: 500, 
 visitorApiPageDisplayTimeout: 500 
}; 
</script> 
```

Mbox.js version 58 och senare kör icke-JavaScript-innehåll för den globala mbox direkt efter att HTML-taggen `BODY` finns. JavaScript-innehåll i `<script>`-taggar för den globala mbox körs efter att händelsen `DOMContentLoaded` har utlösts. Den här ordningen för innehållsleverans säkerställer att JavaScript-innehåll för den globala mbox levereras och återges korrekt.

## mbox.js version 57 {#section_6BA1CDBF75B14A94B59E8624ACF583D4}

**Målversion:** 15.4.1

**Releasedatum:21** april 2015

Följande ändringar har gjorts i den här versionen:

* Automatiskt skapat globalt mbox-svar för Target Standard använder inte längre document.write() eller skapar ett `<div>`-element.

   Den här ändringen tar bort kravet på att filen mbox.js ska vara det sista objektet i `<head>` på sidan. Stark QA rekommenderas vid uppgradering till den nya versionen.

   Den här förändringen kan leda till beteendeförändringar när vissa erbjudandetyper levereras. Här följer de särskilda villkor som måste beaktas:

   * HTML-innehåll som returneras som en del av ett plug-in-erbjudande återges inte korrekt, men JavaScript i erbjudandena körs som förväntat.
   * JavaScript-erbjudanden som returneras till den globala mbox-filen kan ha JavaScript-koden inbäddad i taggen `<script>`, eller refereras av ett `src`-attribut.

      Lägg till attributet `async` i skriptanropet enligt följande:

      `<script src='external-url' async='true'></script>`

      Attributet `async` har begränsat stöd i Internet Explorer (se informationen här: [https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility](https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility)) så att du inte ska ta med besökare som använder äldre IE-versioner från tester som innehåller dessa skript från tredje part.

* Åtgärdade problem som rapporterades i version 56 på grund av ändringar i Extra JavaScript-avsnittet i mbox.js. All kod i avsnittet Extra JavaScript är tillgänglig igen i det globala omfånget.

Följande funktionalitet stöds inte i mbox.js version 57:

* En automatiskt skapad global ruta som genererats i Target Standard fungerar inte med värdbaserade erbjudandetyper från Target Classic. Erbjudandetyper som finns på webben är&quot;offer on your site&quot; och&quot;offer outside Test&amp;Target&quot;.

   Det innebär att i Target Classic får du inte välja den automatiskt skapade globala mbox från Target Standard när något av dessa erbjudanden krävs.
* Endast JavaScript-plugin-program stöds.

   Om ett plugin-program erbjuder både JavaScript-kod och HTML körs JavaScript-koden men HTML-innehållet visas inte.

mbox.js version 57 innehåller även viktiga korrigeringar:

* Korrigerade ett problem som gjorde att plugin-programmet SiteCatalyst inte fungerade i mbox.js v56.
* Korrigerade ett problem som resulterade i extra JavaScript-fel på grund av omfångsändring.
* Återställ ändringar i konstruktorn för mboxFactory.

## mbox.js version 56 {#section_C4F4A53584B741FF9FD907D81CB7E164}

**Målversion:** 15.1.2

**Releasedatum:17** februari 2015

>[!NOTE]
>
>En del användare har stött på timeoutproblem när `target.js` inte kunde läsas in. Version 57 åtgärdade problemet. Om du använder tjänsten [!DNL Experience Cloud Visitor ID] krävs dock version 58 eller senare.

Följande ändringar har gjorts i den här versionen:

* Ändringar för Premium Recommendations som har stöd för att skicka parametrar till global mbox
* Lägger till en 5-sekunderstimeout i inläsningsanropet för target.js. Om filen inte läses in återges sidan och inga Target Standard-aktiviteter visas.
* Flyttade &quot;extra JavaScript&quot; som skulle köras före global mbox

   Alla inställningar i v56+ har namnavstånd. Om det finns funktioner som deklarerats i &quot;extra JavaScript&quot; måste de ha prefixet `window`.

   Exempel:

   `function foo {`

   `}`

   Bli:

   `window.foo = function() {`

   `}`

   Alla variabler som ska vara globalt tillgängliga måste också ha ett prefix med `window`.

* En cookie med namnet&quot;em-disabled&quot; som mbox.js ger användaren om target.js inte kan läsas in under leveransen har lagts till. Denna cookie förhindrar att erbjudanden som skapats med Visual Experience Composer återges på webbplatsen. Användare med den här cookie-filen kan varken se testinnehållet eller räknas in i aktivitetsrapporterna. Allt annat innehåll (från kampanjer i till exempel Target Classic) fortsätter att läsas in. Cookien har en livstid på 30 min från tidpunkten då inläsningen misslyckades.

## mbox version 55

**Målversion:** 15.1

**Releasedatum:** 19 januari 2015

Ändrar version 53 med IE-korrigeringar.

## mbox version 54

**Målversion:** 14.9.2

**Releasedatum:30** september 2014

Ändrar den globala mbox-implementeringen till AJAX från document.write. Den här ändringen tar bort kravet på att mbox.js-filen ska vara det sista objektet i sidans `<head>`-avsnitt. Den här versionen är bara tillgänglig via API. Kunderna kan hämta den och använda den här mbox.js-filen. Vissa webbplatser använder innehållsflimmer med den här implementeringen, så validera integreringen på din webbplats.

## mbox version 53

**Målversion:** 14.9.1

**Releasedatum:14** september 2014

Korrigerade ett problem där målsidans parametrar inte utlöstes korrekt i Internet Explorer.

## mbox version 52

**Målversion:** 14.8

**Releasedatum:14** augusti 2014

Funktionen mboxParameter fungerar nu i Target Standard och Premium.

Korrigerade ett problem som innebar att Analytics inte kunde användas i IE 9 &amp; 11. Ändringen påverkar bara användare av Analytics.

Nu kan du [skicka in parametrar](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) som en array, som ett JSON-objekt eller som en kommaavgränsad lista (som tidigare stöds) till target-global-mbox med funktionen targetPageParams().

Namnet på M2PcId har ändrats och allt som rör VisitorId har ändrats.

Tillåt att defaultDiv för en registrerad mbox rensas.

## mbox version 51

**Målversion:** 14.6

**Releasedatum:25** juni 2014

Korrigerade ett fel som angav en felaktig cookie på webbplatser med två tecken i domänen på den översta nivån.

Korrigerade ett mindre fel i mbox.js som orsakade att hashtaggsvärden returnerades.

## mbox version 50

Förbättrad synkronisering mellan Target Standard och Target Classic.

## mbox version 49

Förbättrat stöd för kapslade kryssrutor i Internet Explorer 10.

## mbox version 48

Stöd för Adobe Analytics har lagts till som rapportkälla för Target.

## mbox version 47

mbox.js har nu stöd för att använda ett anpassat globalt mbox-namn för Target Standard.

## mbox version 46

Komplett stöd för Experience Cloud besökar-ID-tjänsten för Target Standard-implementering med en enda kodrad. Detta möjliggör integrering av Adobe Analytics på serversidan och den delade Experience Cloud-profilen.

Ett problem med att leverera innehåll i IE10 i dokumentläge har korrigerats.

## mbox version 45

Fullt stöd för besökar-ID-tjänsten i Experience Cloud har lagts till. Detta möjliggör integrering av Adobe Analytics på serversidan och den delade Experience Cloud-profilen.

## mbox version 44

En ny parameter har lagts till i URL av mboxVizTarget:

mboxDOMLoaded

## mbox version 43

Stöd för Target Standard har lagts till.

## mbox version 42

Utökat initialt stöd för Experience Cloud delad besökar-ID-tjänst.

## mbox version 41

* Inaktivera cookie-filen från första part även om du bara anger x-värdet för att förbättra inläsningstiden och förhindra kontinuerliga siduppdateringar

   En timeout-cookie anges om anropet till Target inte returneras i tid. Det här är en snabbare metod än att bara använda cookie från tredje part. Med bara en cookie från tredje part uppdateras sidan kontinuerligt i väntan på ett bra svar från Target-servrarna.

* Trafikbegränsningen är fast och inträffar endast när mbox.js är aktiverad

   Problemet uppstod om en kund hade en trafikbegränsning för mbox.js, vilket gjorde att timeout-inställningen inte fungerade. Detta ledde till att sidan uppdaterades i väntan på ett bra svar från målservrarna.

* Fast SiteCalyst-plugin som alltid ska använda Ajax-fogaren

   Före den här ändringen fanns det vissa situationer för användare av plugin-programmet Test&amp;Target till SiteCatalyst där ett dokument.write som skulle kunna tömma sidan skulle kunna utlösas, beroende på när plugin-programmet lästes in.

## mbox version 38

Stöd för sidbaserad integrering mellan SiteCatalyst och Test&amp;Target (måste vara aktiverat)

## mbox version 37

Kodade URL-nycklar

## mbox version 36

Ändrad mbox till att använda tt.omtrdc.net

## mbox version 35

* Mbox-felsökning är nu alltid fjärransluten
* Parametern mboxTime har lagts till. Den här parametern är tiden som användaren ser den, i ms sedan epoken, GMT. Detta beräknas bara en gång.

## mbox version 34

* Försök alltid att hämta den senaste standard-diven i stället för att referera till en cachelagrad version.

   Det här åtgärdar ett problem med att en cache-lagrad standardinnehålls-div inte finns i DOM på grund av en mboxUpdate , som tillhandahåller innehållet för standard-div .

* mbox.getDefaultDiv har en ny valfri boolesk parameter. Om true returneras aktuell standard-div. Om värdet är false returneras den sista cachelagrade standard-diven.
* Uppdaterad mbox.loaded för stöd av Ajax-inläsning
* Parametern mboxURL är nu kodad med encodeURIComponent i stället för escape
* Testa om encodeURIComponent stöds av webbläsaren och visa standardinnehåll om det inte stöds. Följande konfigurationsalternativ för mbox.js har också tagits bort:
   * encode\_mbox\_parameters
   * mbox\_signal\_support
