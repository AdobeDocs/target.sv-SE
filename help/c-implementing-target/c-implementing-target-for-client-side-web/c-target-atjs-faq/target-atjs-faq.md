---
keywords: at.js faq;at.js Vanliga frågor;faq;flimmer;loader;page loader;cross domain;file size;filesize;x domain;at.js and mbox.js;x only;cross domain;safari;single page app;missing selectors;selectors;single page application;tt.omtrdc.net;spa;Adobe Experience Manager;AEM;ip httponly;HTTPOnly;secure;ip;cookie domain
description: Läs svar på vanliga frågor om JavaScript-biblioteket Adobe [!DNL Target] at.js.
title: Vad är vanliga frågor och svar om at.js?
feature: at.js
role: Developer
exl-id: 937f880a-1842-4655-be44-0a5614c2dbcc
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '2500'
ht-degree: 0%

---

# at.js Frågor och svar

Svar på vanliga frågor om [!DNL Adobe Target] at.js JavaScript-biblioteket.

## Vilka är fördelarna med att använda at.js jämfört med mbox.js? {#section_FE30D01A577C46ACB0F787B85F5E0F6B}

Biblioteket [!DNL at.js] ersätter [!DNL mbox.js]. Biblioteket [!DNL mbox.js] stöds inte längre. För de flesta användare ger [!DNL at.js] dock fördelar jämfört med [!DNL mbox.js].

[!DNL at.js] förbättrar bl.a. sidinläsningstiden för webbimplementeringar, förbättrar säkerheten och ger bättre implementeringsalternativ för enkelsidiga program.

I följande diagram visas sidinläsningsprestanda med mbox.js jämfört med at.js.

![](assets/atjs_vesus_mboxjs.png)

Som framgår ovan började inte sidinnehåll läsas in med mbox.js förrän efter att anropet [!DNL Target] är slutfört. Med at.js börjar sidinnehållet att läsas in när anropet [!DNL Target] initieras och väntar inte tills anropet är klart.

## Hur påverkar at.js och mbox.js sidinläsningstiden? {#page-load}

Många kunder och konsulter vill veta hur [!DNL at.js] och [!DNL mbox.js] påverkar sidinläsningstiden, särskilt när det gäller nya användare och användare som returneras. Tyvärr är det svårt att mäta och ge konkreta siffror för hur [!DNL at.js] eller [!DNL mbox.js] påverkar sidladdningstiden på grund av varje kunds implementering.

Om besökar-API:t finns på sidan kan [!DNL Target] bättre förstå hur [!DNL at.js] och [!DNL mbox.js] påverkar sidinläsningstiden.

>[!NOTE]
>
>Besökar-API:t och [!DNL at.js] eller [!DNL mbox.js] påverkar bara sidinläsningstiden när du använder den globala mbox (på grund av tekniken för att dölja brödtext). Regionala kryssrutor påverkas inte av integreringen med Visitor API.

I följande avsnitt beskrivs åtgärdssekvensen för nya och återkommande besökare:

### Nya besökare

1. Besökar-API:t läses in, tolkas och körs.
1. at.js / mbox.js läses in, tolkas och körs.
1. Om den globala mbox-skaparen är aktiverad, JavaScript-målbiblioteket:

   * Instansierar Visitor-objektet.
   * [!DNL Target]-biblioteket försöker hämta [!DNL Experience Cloud Visitor ID]-data.
   * Eftersom den här besökaren är en ny besökare genererar besökar-API en korsdomänbegäran till demdex.net.
   * När [!DNL Experience Cloud Visitor ID]-data har hämtats utlöses en begäran till [!DNL Target].

### Returnerande besökare

1. Besökar-API:t läses in, tolkas och körs.
1. at.js / mbox.js läses in, tolkas och körs.
1. Om den globala mbox-skaparen är aktiverad, är JavaScript-biblioteket [!DNL Target]:

   * Instansierar Visitor-objektet.
   * [!DNL Target]-biblioteket försöker hämta [!DNL Experience Cloud Visitor ID]-data.
   * Besökar-API:t hämtar data från cookies.
   * När [!DNL Experience Cloud Visitor ID]-data har hämtats utlöses en begäran till [!DNL Target].

>[!NOTE]
>
>För nya besökare måste [!DNL Target] gå igenom tråden flera gånger när besökar-API:t finns för att se till att [!DNL Target]-begäranden innehåller [!DNL Experience Cloud Visitor ID]-data. För återkommande besökare går [!DNL Target] bara över tråden till [!DNL Target] för att hämta det anpassade innehållet.

## Varför verkar det som om jag ser längre svarstider efter en uppgradering från en tidigare version av at.js till version 1.0.0? {#section_DFBA5854FFD142B49AD87BFAA09896B0}

[!DNL at.js] version 1.0.0 och senare utlöser alla begäranden parallellt. I tidigare versioner körs förfrågningarna sekventiellt, vilket innebär att förfrågningarna placeras i kö och [!DNL Target] väntar på att den första förfrågningen ska slutföras innan du går vidare till nästa begäran.

Det sätt som tidigare versioner av [!DNL at.js] kör begäranden på är känsligt för den så kallade &quot;head of line blockering&quot;. I [!DNL at.js] 1.0.0 och senare växlade [!DNL Target] till parallell körning av begäran.

Om du till exempel kontrollerar vattenfallet på nätverksfliken för [!DNL at.js] 0.9.1 ser du att nästa [!DNL Target]-begäran inte startar förrän den föregående har slutförts. Den här sekvensen är inte fallet med [!DNL at.js] 1.0.0 och senare, där alla begäranden börjar samtidigt.

Från ett svarstidsperspektiv, matematiskt, kan den här sekvensen summeras så här

<ul class="simplelist"> 
 <li> at.js 0.9.1: Svarstid för alla [!DNL Target]-begäranden = summan av begäranden och svarstid </li> 
 <li> at.js 1.0.0 och senare: Svarstid för alla [!DNL Target]-begäranden = maximal svarstid för begäranden </li> 
</ul>

[!DNL at.js]-biblioteksversionen 1.0.0 slutför förfrågningarna snabbare. Dessutom är [!DNL at.js]-begäranden asynkrona, så [!DNL Target] blockerar inte sidåtergivning. Även om en begäran tar några sekunder att slutföra, ser du fortfarande den återgivna sidan, så är det bara vissa delar av sidan som döljs tills [!DNL Target] får ett svar från kanten [!DNL Target].

## Kan jag läsa in [!DNL Target]-biblioteket asynkront? {#section_AB9A0CA30C5440C693413F1455841470}

Med versionen at.js 1.0.0 kan du läsa in biblioteket [!DNL Target] asynkront.

Så här läser du in at.js asynkront:

* Det rekommenderade sättet är via taggar i [!DNL Adobe Experience Platform].
* Du kan också läsa in at.js asynkront genom att lägga till attributet async i script-taggen som läser in at.js. Använd något liknande:

   ```
   <script src="<URL to at.js>" async></script>
   ```

* Du kan också läsa in at.js asynkront med den här koden:

   ```
   var script = document.createElement('script'); 
   script.async = true; 
   script.src = "<URL to at.js>"; 
   document.head.appendChild(script);
   ```

Att läsa in at.js asynkront är ett bra sätt att undvika att blockera webbläsaren från återgivning. Den här tekniken kan dock leda till att webbsidan flimrar.

Du kan undvika flimmer genom att använda ett fragment som döljer sidan (eller vissa delar) och sedan visar den efter at.js och den globala begäran har lästs in. Utdraget måste läggas till innan at.js läses in.

Om du distribuerar at.js via en asynkron [!DNL Adobe Experience Platform]-implementering måste du ta med det föregående dolda fragmentet direkt på sidorna, innan implementeringen [!DNL Target] används med [!DNL Adobe Experience Platform] Embed-kod.

Om du distribuerar at.js via en synkron DTM-implementering kan det fördolda fragmentet läggas till via en sidinläsningsregel som aktiveras högst upp på sidan.

Mer information finns i [How at.js management flimmer](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md).

## Är at.js kompatibelt med [!DNL Adobe Experience Manager]-integreringen (Experience Manager)? {#section_6177AE10542344239753764C6165FDDC}

[!DNL Adobe Experience Manager] 6.2 med FP-11577 (eller senare) har nu stöd för  [!DNL at.js] implementeringar med dess  [!UICONTROL Adobe Target Cloud Services] integrering.

## Hur förhindrar jag sidinläsningsflimmer med at.js? {#section_4D78AAAE73C24E578C974743A3C65919}

I Target finns flera sätt att förhindra sidinläsningsflimmer. Mer information finns i [Förhindra flimmer med at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md#concept_AA168574397D4474B993EEAB90865EBA).

## Vilken är filstorleken för at.js? {#section_6A25C9A14C66441785A7635FEF5C4475}

Filen at.js är ungefär 109 kB när den hämtas. Eftersom de flesta servrar automatiskt komprimerar filer så att de blir mindre, är at.js ungefär 34 kB vid komprimering (med GZIP eller någon annan metod) på servern och laddas när användarna besöker webbplatsen. Komprimeringsinställningarna på servern där du installerade at.js avgör den faktiska komprimerade storleken.

## Varför är at.js större än mbox.js? {#section_AA1C43897E46448FA3E26EEC10ED7E51}

Vid implementeringar av at.js används ett bibliotek ( [!DNL at.js]), medan implementeringar av mbox.js faktiskt använder två bibliotek ( [!DNL mbox.js] och [!DNL target.js]). En rättvisare jämförelse är at.js jämfört med mbox.js *och* `target.js`. Jämförelse av de gzippade storlekarna för de två versionerna är at.js version 1.2 34 kB och mbox.js version 63 26,2 kB. &quot;

at.js är större eftersom det gör mycket mer DOM-analys jämfört med mbox.js. Detta är obligatoriskt eftersom at.js hämtar&quot;raw&quot;-data i JSON-svaret och måste förstå det. mbox.js använde `document.write()` och all tolkning gjordes av webbläsaren.

Trots den större filstorleken visar vår testning att sidorna läses in snabbare med at.js jämfört med mbox.js. At.js är dessutom överlägset ur säkerhetsperspektiv eftersom det inte läser in ytterligare filer dynamiskt eller använder `document.write`.

## Har At.js jQuery? Kan jag ta bort den här delen av at.js eftersom jag redan har jQuery på min webbplats? {#section_E4604E46E7B34460B8DD6A78D9B476F9}

at.js använder för närvarande delar av jQuery och därför visas MIT-licensmeddelandet högst upp i at.js. jQuery visas inte och påverkar inte det jQuery-bibliotek som du redan har på sidan, vilket kan vara en annan version. Det går inte att ta bort jQuery-koden i at.js.

## Stöder at.js Safari och korsdomäner som är inställda på endast x? {#section_114EC271A6E045E1B2183B66F1B71285}

Nej, om korsdomänen är inställd på endast x och Safari har inaktiverade cookies från tredje part, anger både [!DNL mbox.js] och at.js en inaktiverad cookie och inga mbox-begäranden körs för den aktuella klientens domän.

För att stödja Safari-besökare är en bättre X-Domain inaktiverad (anger endast en cookie från första part) eller aktiverad (anger endast en cookie från första part i Safari, medan cookies från första och tredje part anges i andra webbläsare).

## Kan jag använda [!DNL Target] Visual Experience Composer (VEC) i mina enkelsidiga program? {#section_459C1BEABD4B4A1AADA6CF4EC7A70DFB}

Ja, du kan använda VEC för din SPA om du använder at.js 2.x. Mer information finns i [Enkelsidig (SPA) Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md).

## Kan jag använda felsökningsprogrammet [!DNL Adobe Experience Cloud] med at.js-implementeringar? {#section_FF3CF4C5FD2F4DB1BF1A6B39DA161637}

Ja. Du kan också använda mboxTrace för felsökning eller webbläsarens utvecklingsverktyg för att granska nätverksförfrågningar och filtrera till mbox för att isolera mbox-anrop.

## Kan jag använda specialtecken i mbox-namn med at.js? {#section_8E31D2E8A27642098934D7DACFB2A600}

Ja, precis som med mbox.js.

## Varför skjuter inte mina lådor på mina webbsidor? {#section_4BA5DA424B734324AAB51E4588FA50F5}

[!DNL Target] kunder använder ibland molnbaserade instanser med  [!DNL Target] för testning eller enkla konceptbevis. Dessa domäner, och många andra, ingår i [Public Suffix List](https://publicsuffix.org/list/public_suffix_list.dat).

I moderna webbläsare sparas inte cookies om du använder dessa domäner om du inte anpassar inställningen `cookieDomain` med targetGlobalSettings(). Mer information finns i [Använda molnbaserade instanser med Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md).

## Kan IP-adresser användas som cookie-domän när du använder at.js? {#section_8BEEC91A3410459D9E442840A3C88AF7}

Ja, om du använder [at.js version 1.2 eller senare](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A). [!DNL Adobe] Vi rekommenderar dock att du håller dig uppdaterad med den senaste versionen.

>[!NOTE]
>
>Följande exempel är inte nödvändiga om du använder at.js version 1.2 eller senare.

Beroende på hur du använder [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) kan du behöva göra ytterligare ändringar i koden efter att ha hämtat at at at.js. Om du till exempel behövde lite olika inställningar för dina [!DNL Target]-implementeringar på olika webbplatser och inte kunde definiera dessa inställningar dynamiskt med anpassat JavaScript, gör du dessa anpassningar manuellt efter att du har hämtat filen och innan du överför den till respektive webbplats.

I följande exempel kan du använda funktionen `targetGlobalSettings()` at.js för att infoga ett kodfragment som stöder IP-adresser:

Det här exemplet gäller en enda IP-adress:

```
if (window.location.hostname === '123.456.78.9') { 
    window.targetGlobalSettings = window.targetGlobalSettings || {}; 
    window.targetGlobalSettings.cookieDomain = window.location.hostname; 
}
```

Det här exemplet gäller ett intervall av IP-adresser:

```
if (/^123\.456\.78\..*/g.test(window.location.hostname)) { 
    window.targetGlobalSettings = window.targetGlobalSettings || {}; 
    window.targetGlobalSettings.cookieDomain = window.location.hostname; 
}
```

## Varför visas varningsmeddelanden, till exempel&quot;åtgärder med väljare som saknas&quot;? {#section_C36BED5B16634361A1BA46FCB731489D}

Dessa meddelanden är inte relaterade till funktionen [!DNL at.js]. Biblioteket [!DNL at.js] försöker rapportera något som inte kan hittas i DOM.

Följande är möjliga rotorsaker om du ser det här varningsmeddelandet:

* Sidan byggs dynamiskt och at.js kan inte hitta elementet.
* Sidan byggs långsamt (på grund av ett långsamt nätverk) och at.js kan inte hitta väljaren i DOM.
* Sidstrukturen som används i[!UICONTROL y is running on has been changed. If you reopen the activity in the ]Visual Experience Composer (VEC) bör innehålla ett varningsmeddelande. Uppdatera aktiviteten så att alla nödvändiga element kan hittas.
* Den underliggande sidan är en del av en [!UICONTROL Single Page Application] (SPA) eller sidan innehåller element som visas längre ned på sidan och väljaravsökningsfunktionen [!DNL at.js] kan inte hitta dessa element. Om du ökar `selectorsPollingTimeout` kan det hjälpa. Mer information finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
* Alla klickspårningsmått försöker lägga till sig själv på varje sida, oavsett vilken URL som måttet har ställts in på. Även om det är ofarligt visas många av dessa meddelanden.

   Du får bäst resultat om du laddar ned och använder den senaste versionen av [!DNL at.js]. Mer information finns i [at.js Versionsinformation](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) och [Hämta på.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md).

## Vad är domänen tt.omtrdc.net som [!DNL Target] serveranrop går till? {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] är domännamnet för Adobe EDGE-nätverket, som används för att ta emot alla serveranrop för Target.

## Varför använder inte at.js alltid flaggorna HTTPOnly och Secure cookie? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly kan bara anges via kod på serversidan. [!DNL Target] cookies, t.ex. mbox, skapas och sparas via JavaScript-kod, så  [!DNL Target] det går inte att använda HTML-cookie-flaggan. [!DNL Target] använder set HttpOnly för cookies från tredje part som anges från serversidan när korsdomänen är aktiverad.

Säker kan bara ställas in via JavaScript när sidan har lästs in via HTTPS. Om sidan först läses in via HTTP kan JavaScript inte ange den här flaggan. Om du dessutom använder flaggan Secure är cookien bara tillgänglig på HTTPS-sidor. För sidor som läses in via HTTPS anger [!DNL Target] attributen Secure och SameSite=None.

För att [!DNL Target] ska kunna spåra användare korrekt och eftersom cookies genereras på klientsidan, använder [!DNL Target] inte någon av dessa flaggor förutom i de situationer som nämns ovan.

## Hur ofta skickar at.js en nätverksbegäran? {#section_57C5235DF7694AF093A845D73EABADFD}

[!DNL Target] verkställer alla sina beslut på serversidan. Det innebär att at.js utlöser en nätverksbegäran varje gång sidan läses in igen eller att ett at.js public API anropas.

## I det bästa fallet, kan vi förvänta oss att användaren inte upplever några synliga effekter på sidinläsningen som relaterar till att dölja, ersätta och visa innehåll? {#section_CB3C566AD61F417FAC0EC5AC706723EB}

at.js försöker undvika att i förväg dölja HTML BODY eller andra DOM-element under en längre period, men detta beror på nätverksvillkoren och aktivitetsinställningarna. at.js innehåller [inställningar](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) som du kan använda för att anpassa CSS-formatet BODY så att du i stället för att dölja hela HTML BODY bara kan dölja vissa delar av sidan i förväg. Förväntningen är att dessa delar innehåller DOM-element som måste vara&quot;personaliserade&quot;.

## Vilken händelsesekvens i ett genomsnittligt scenario där en användare kvalificerar sig för en aktivitet? {#section_56E6F448E901403FB77DF02F44C44452}

At.js-begäran är en asynkron `XMLHttpRequest`, så vi utför följande steg:

1. Sidan läses in.
1. at.js fördöljer HTML BODY. Det finns en inställning för att dölja en viss behållare i förväg i stället för HTML BODY.
1. AT.js-begäran utlöses.
1. När [!DNL Target]-svaret har tagits emot extraherar [!DNL Target] CSS-väljarna.
1. Med CSS-väljare skapar [!DNL Target] STYLE-taggar för att i förväg dölja de DOM-element som ska anpassas.
1. HTML BODY-FORMATMALLEN som döljs innan tas bort.
1. [!DNL Target] börjar avfråga DOM-element.
1. Om ett DOM-element hittas tillämpar [!DNL Target] DOM-ändringar och elementet före döljning av STYLE tas bort.
1. Om DOM-element inte hittas döljs elementen med en global tidsgräns, så att ingen bruten sida hittas.

## Hur ofta är sidans innehåll helt inläst och synligt när at.js äntligen tar bort elementet som aktiviteten ändras från? {#section_01AFF476EFD046298A2E17FE3ED85075}

Med tanke på ovanstående scenario, hur ofta är sidans innehåll helt inläst och synligt när at.js äntligen döljer elementet som aktiviteten ändras? Med andra ord är sidan helt synlig förutom aktivitetens innehåll, som sedan visas något efter resten av innehållet.

at.js blockerar inte sidan från återgivning. En användare kan lägga märke till några tomma områden på sidan som representerar element som är anpassade av [!DNL Target]. Om innehållet som ska användas inte innehåller många fjärrresurser, som SCRIPT eller IMG, bör allt återges snabbt.

## Hur skulle en helt cachelagrad sida påverka scenariot ovan? Skulle det vara troligare att aktivitetens innehåll blir synligt när resten av sidans innehåll har lästs in? {#section_CE76335A3E0B41CB8253DEE5E060FCDA}

Om en sida cache-lagras på ett CDN som ligger nära användarens plats, men inte nära kanten [!DNL Target], kan användaren se vissa förseningar. [!DNL Target] Kanterna är väl fördelade över hela världen, så det här är oftast inget problem.

## Kan en hjältebild visas och sedan bytas ut efter en kort fördröjning? {#section_C25B07B25B854AAE8DEE1623D0FA62A3}

Tänk på följande scenario:

Tidsgränsen för [!DNL Target] är fem sekunder. En användare läser in en sida som har en aktivitet för att anpassa en hjältebild. at.js skickar begäran för att avgöra om det finns en aktivitet att tillämpa, men det finns inget initialt svar. Anta att användaren ser det vanliga innehållet i hjältebilden eftersom inget svar togs emot från [!DNL Target] angående om det finns någon associerad aktivitet. Efter fyra sekunder returnerar [!DNL Target] ett svar med aktivitetsinnehållet.

Skulle det i det här skedet vara möjligt att visa den alternativa versionen? Så efter fyra sekunder kan hjältebilden bytas ut och användaren kan märka att bilden byts ut?

Till att börja med är bildhjälteelementet DOM dolt. När ett svar från [!DNL Target] har tagits emot tillämpar at.js DOM-ändringarna, som att ersätta IMG-filen och visa den anpassade hjältebilden.

## Vilken HTML-dokumenttyp kräver at.js?

at.js kräver dokumenttypen HTML 5.

Syntaxen är:

`<!DOCTYPE html>`

Dokumenttypen HTML 5 ser till att sidan läses in i standardläge. När du läser in i felsökningsläge inaktiveras vissa JS-API:er som at.js är beroende av. [!DNL Target] inaktiverar at.js i felsökningsläge.
