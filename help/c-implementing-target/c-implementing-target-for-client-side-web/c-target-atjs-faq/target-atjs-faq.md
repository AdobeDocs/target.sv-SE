---
keywords: at.js faq;at.js frequently asked questions;faq;flicker;loader;page loader;cross domain;file size;filesize;x-domain;at.js and mbox.js;x only;cross domain;safari;single page app;missing selectors;selectors;single page application;tt.omtrdc.net;spa;Adobe Experience Manager;AEM;ip address;httponly;HttpOnly;secure;ip;cookie domain
description: Svar på vanliga frågor om Adobe Target JavaScript-bibliotek at.js.
title: Adobe Target at.js Frågor och svar
feature: client-side
subtopic: Getting Started
uuid: 1fcd3984-7c6d-4619-953e-3e28eb0d015a
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '2648'
ht-degree: 0%

---


# at.js Frågor och svar{#at-js-frequently-asked-questions}

Svar på vanliga frågor om at.js.

## Vilka är fördelarna med att använda at.js jämfört med mbox.js? {#section_FE30D01A577C46ACB0F787B85F5E0F6B}

Ersätter [!DNL at.js] men [!DNL mbox.js][!DNL mbox.js] stöds fortfarande. För de flesta har dock [!DNL at.js] fördelar framför [!DNL mbox.js].

Bland andra fördelar finns [!DNL at.js] förbättrad sidladdningstid för webbimplementeringar, förbättrad säkerhet och bättre implementeringsalternativ för enkelsidiga program.

I följande diagram visas sidinläsningsprestanda med mbox.js jämfört med at.js.

![](assets/atjs_vesus_mboxjs.png)

Som framgår ovan börjar inte sidinnehållet att läsas in med mbox.js förrän [!DNL Target] anropet har slutförts. Med at.js börjar sidinnehållet att läsas in när [!DNL Target] anropet initieras och väntar inte tills anropet är klart.

## Hur påverkar at.js och mbox.js sidinläsningstiden? {#page-load}

Många kunder och konsulter vill veta hur stor påverkan [!DNL at.js] och [!DNL mbox.js] hur stor tid det tar att läsa in sidor, särskilt när det gäller nya användare och användare som återvänder. Tyvärr är det svårt att mäta och ge konkreta siffror för hur [!DNL at.js] eller [!DNL mbox.js] hur påverkar sidladdningstiden på grund av varje kunds implementering.

Om besökar-API:t finns på sidan kan vi bättre förstå hur [!DNL at.js] och [!DNL mbox.js] hur sidinläsningstiden påverkas.

>[!NOTE]
>
>Besökar-API:t och [!DNL at.js] eller [!DNL mbox.js] påverkar bara sidinläsningstiden när du använder den globala mbox-filen (på grund av tekniken för att dölja brödtext). Regionala kryssrutor påverkas inte av integreringen med Visitor API.

I följande avsnitt beskrivs åtgärdssekvensen för nya och återkommande besökare:

### Nya besökare

1. Besökar-API:t läses in, tolkas och körs.
1. at.js / mbox.js läses in, tolkas och körs.
1. Om den globala mbox-skaparen är aktiverad, JavaScript-målbiblioteket:

   * Instansierar Visitor-objektet.
   * Målbiblioteket försöker hämta Experience Cloud Visitor-ID-data.
   * Eftersom det här är en ny besökare skickar Visitor-API:t en korsdomänbegäran till demdex.net.
   * När data för Experience Cloud Visitor-ID har hämtats skickas en begäran till Target.

### Returnerande besökare

1. Besökar-API:t läses in, tolkas och körs.
1. at.js / mbox.js läses in, tolkas och körs.
1. Om den globala mbox-skaparen är aktiverad, JavaScript-målbiblioteket:

   * Instansierar Visitor-objektet.
   * Målbiblioteket försöker hämta Experience Cloud Visitor-ID-data.
   * Besökar-API:t hämtar data från cookies.
   * När data för Experience Cloud Visitor-ID har hämtats skickas en begäran till Target.

>[!NOTE]
>
>För nya besökare måste Target gå igenom tråden flera gånger när besökar-API:t finns för att se till att Target-begäranden innehåller data för Experience Cloud Visitor-ID:t. För återkommande besökare går Target bara till Target för att hämta det personaliserade innehållet.

## Varför verkar det som om jag ser längre svarstider efter en uppgradering från en tidigare version av at.js till version 1.0.0? {#section_DFBA5854FFD142B49AD87BFAA09896B0}

[!DNL at.js] version 1.0.0 och senare utlöser alla begäranden parallellt. I tidigare versioner körs förfrågningarna sekventiellt, vilket innebär att förfrågningarna placeras i kö och Target väntar på att den första begäran ska slutföras innan nästa begäran går vidare.

Det sätt som tidigare versioner av begäranden som [!DNL at.js] verkställs är känsligt för den så kallade &quot;head of line blockering&quot;. I [!DNL at.js] 1.0.0 och senare växlade Target till parallell körning av begäran.

Om du till exempel kontrollerar vattenfallet på nätverksfliken för [!DNL at.js] 0.9.1 ser du att nästa Target-begäran inte börjar förrän den föregående har slutförts. Detta är inte fallet med [!DNL at.js] 1.0.0 och senare, där alla begäranden börjar samtidigt.

Matematiskt sett kan detta summeras så här från svarstidsperspektiv

<ul class="simplelist"> 
 <li> at.js 0.9.1: Svarstid för alla Target-begäranden = summan av begäranden och svarstid </li> 
 <li> at.js 1.0.0 och senare: Svarstid för alla Target-begäranden = maximal svarstid för begäranden </li> 
</ul>

Som du ser kommer [!DNL at.js] 1.0.0 att slutföra förfrågningarna snabbare. Dessutom är [!DNL at.js] begäranden asynkrona, så Target blockerar inte sidåtergivning. Även om det tar några sekunder att slutföra en begäran kommer du fortfarande att se den återgivna sidan, men bara vissa delar av sidan kommer att tas bort tills Target får ett svar från målkanten.

## Kan jag läsa in målbiblioteket asynkront? {#section_AB9A0CA30C5440C693413F1455841470}

Med versionen at.js 1.0.0 kan du läsa in målbiblioteket asynkront.

Så här läser du in at.js asynkront:

* Det rekommenderade sättet är via en tagghanterare som Adobe Launch eller Adobe Dynamic Tag Manager (DTM). Mer information finns i lektionen [Lägg till Adobe Target](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) i [Implementera Experience Cloud på webbplatser med Launch](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/index.html) .
* Du kan också läsa in at.js asynkront genom att lägga till attributet async i script-taggen som läser in at.js. Du bör använda något sådant:

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

Du kan undvika flimmer genom att använda ett fragment som döljer sidan (eller vissa delar) och sedan visar den efter at.js och den globala begäran har lästs in helt. Utdraget måste läggas till innan at.js läses in.

Om du distribuerar at.js via en asynkron Launch-implementering måste du se till att inkludera det preddolda fragmentet direkt på dina sidor, före koden Launch Embed (Starta inbäddning), enligt beskrivningen i avsnittet [Lägg till fragmentet](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html#add-the-target-pre-hiding-snippet) för fördöljning av mål i [Implementera Experience Cloud på webbplatser med startsjälvstudiekursen](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/index.html).

Om du distribuerar at.js via en synkron DTM-implementering kan det fördolda fragmentet läggas till via en sidinläsningsregel som aktiveras högst upp på sidan.

Mer information finns i [Hantera flimmer](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md).

## Är at.js kompatibelt med Adobe Experience Manager (AEM)? {#section_6177AE10542344239753764C6165FDDC}

[!DNL Adobe Experience Manager] 6.2 med FP-11577 (eller senare) har nu stöd för [!DNL at.js] implementeringar med [!UICONTROL Adobe Target Cloud Services] integrering. Mer information finns i [Funktionspaket](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html) och [Integrera med Adobe Target](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html) i dokumentationen för *Adobe Experience Manager 6.2* .

## Hur förhindrar jag sidinläsningsflimmer med at.js? {#section_4D78AAAE73C24E578C974743A3C65919}

I Target finns flera sätt att förhindra sidinläsningsflimmer. Mer information finns i [Förhindra flimmer med at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md#concept_AA168574397D4474B993EEAB90865EBA).

## Vilken är filstorleken för at.js? {#section_6A25C9A14C66441785A7635FEF5C4475}

Filen at.js är ungefär 109 kB när den hämtas. Eftersom de flesta servrar automatiskt komprimerar filer så att de blir mindre, är at.js ungefär 34 kB vid komprimering (med GZIP eller någon annan metod) på servern och laddas när användarna besöker webbplatsen. Komprimeringsinställningarna på servern där du installerade at.js avgör den faktiska komprimerade storleken.

## Varför är at.js större än mbox.js? {#section_AA1C43897E46448FA3E26EEC10ED7E51}

Vid implementering av at.js används ett bibliotek ( [!DNL at.js]), medan implementeringar av mbox.js faktiskt använder två bibliotek ( [!DNL mbox.js] och [!DNL target.js]). En rättvisare jämförelse är at.js jämfört med mbox.js *och* `target.js`. Jämförelse av de gzippade storlekarna för de två versionerna är at.js version 1.2 34 kB och mbox.js version 63 26,2 kB. &quot;

at.js är större eftersom det gör mycket mer DOM-analys jämfört med mbox.js. Detta är obligatoriskt eftersom at.js hämtar&quot;raw&quot;-data i JSON-svaret och måste förstå det. mbox.js använder `document.write()` och all tolkning görs i webbläsaren.

Trots den större filstorleken visar vår testning att sidorna läses in snabbare med at.js jämfört med mbox.js. Dessutom är at.js överlägset ur säkerhetsperspektiv eftersom det inte läser in ytterligare filer dynamiskt eller använder `document.write`.

## Har At.js jQuery? Kan jag ta bort den här delen av at.js eftersom jag redan har jQuery på min webbplats? {#section_E4604E46E7B34460B8DD6A78D9B476F9}

at.js använder för närvarande delar av jQuery och därför visas MIT-licensmeddelandet högst upp i at.js. jQuery visas inte och påverkar inte det jQuery-bibliotek som du redan har på sidan, vilket kan vara en annan version. Det går inte att ta bort jQuery-koden i at.js.

## Stöder at.js Safari och korsdomäner som är inställda på endast x? {#section_114EC271A6E045E1B2183B66F1B71285}

Nej, om korsdomänen är inställd på endast x och Safari har tredjepartcookies inaktiverade, kommer både [!DNL mbox.js] och at.js att ange en inaktiverad cookie och inga mbox-begäranden kommer att köras för den aktuella klientens domän.

För att stödja Safari-besökare är en bättre X-Domain inaktiverad (anger endast en cookie från första part) eller aktiverad (anger endast en cookie från första part i Safari, medan cookies från första och tredje part anges i andra webbläsare).

## Kan jag köra at.js och mbox.js sida vid sida? {#section_4DCAF38DBAEB430CA486FAEFAE0E0A29}

Inte på samma sida. När du implementerar och testar [!DNL at.js]kan du dock köra [!DNL at.js] på vissa sidor och [!DNL mbox.js] på andra sidor tills du har validerat allt [!DNL at.js].

## Kan jag använda Target Visual Experience Composer i mina enkelsidiga program? {#section_459C1BEABD4B4A1AADA6CF4EC7A70DFB}

Ja, du kan använda VEC för SPA om du använder at.js 2.x. Mer information finns i [Enkelsidig (SPA) visuell Experience Composer](/help/c-experiences/spa-visual-experience-composer.md).

## Kan jag använda Adobe Experience Cloud Debugger med at.js-implementeringar? {#section_FF3CF4C5FD2F4DB1BF1A6B39DA161637}

Ja. Du kan också använda mboxTrace för felsökning eller webbläsarens utvecklingsverktyg för att granska nätverksförfrågningar och filtrera till mbox för att isolera mbox-anrop.

## Kan jag använda specialtecken i mbox-namn med at.js? {#section_8E31D2E8A27642098934D7DACFB2A600}

Ja, precis som med mbox.js.

## Varför skjuter inte mina lådor på mina webbsidor? {#section_4BA5DA424B734324AAB51E4588FA50F5}

Målgrupper använder ibland molnbaserade instanser med [!DNL Target] för testning eller enkla konceptbevis. Dessa domäner, och många andra, ingår i [Public Suffix List](https://publicsuffix.org/list/public_suffix_list.dat).

I moderna webbläsare sparas inte cookies om du använder dessa domäner om du inte anpassar inställningen med targetGlobalSettings(). `cookieDomain` Mer information finns i [Använda molnbaserade instanser med Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566).

## Kan IP-adresser användas som cookie-domän när du använder at.js? {#section_8BEEC91A3410459D9E442840A3C88AF7}

Ja, om du använder [at.js version 1.2 eller senare](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A). Vi rekommenderar dock att du håller dig uppdaterad med den senaste versionen.

>[!NOTE]
>
>Följande exempel är inte nödvändiga om du använder at.js version 1.2 eller senare.

Beroende på hur du använder [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)kan du behöva göra ytterligare ändringar i koden efter att ha hämtat at at at.js. Om du till exempel behövde lite olika inställningar för dina [!DNL Target] implementeringar på olika webbplatser och inte kunde definiera dessa inställningar dynamiskt med anpassat JavaScript, gör du anpassningarna manuellt efter att du har hämtat filen och innan du överförde den till respektive webbplats.

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

Det här meddelandet är inte relaterat till [!DNL at.js] funktionen. Biblioteket försöker rapportera något som inte går att hitta i DOM. [!DNL at.js]

Följande är möjliga rotorsaker om du ser det här varningsmeddelandet:

* Sidan byggs dynamiskt och at.js kan inte hitta elementet.
* Sidan byggs långsamt (på grund av ett långsamt nätverk) och at.js kan inte hitta väljaren i DOM.
* Sidstrukturen som aktiviteten körs på har ändrats. Om du öppnar aktiviteten igen i Visual Experience Composer (VEC) bör du få ett varningsmeddelande. Du bör uppdatera aktiviteten så att alla nödvändiga element kan hittas.
* Den underliggande sidan är en del av ett Single Page-program (SPA) eller sidan innehåller element som visas längre ned på sidan och [!DNL at.js] &quot;väljaravsökningsfunktionen&quot; kan inte hitta dessa element. Om du ökar `selectorsPollingTimeout` kan det hjälpa. Mer information finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
* Alla klickspårningsmått försöker lägga till sig själv på varje sida, oavsett vilken URL som måttet har ställts in på. Även om det är ofarligt visas många av dessa meddelanden.

   Du får bäst resultat om du laddar ned och använder den senaste versionen av [!DNL at.js]. Mer information finns [i versionskommentarerna](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A) at.js och [Hämta på.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_1E1F958F9CCC4E35AD97581EFAF659E2).

## Vad är domänen tt.omtrdc.net som anrop från målservern går till? {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] är domännamnet för Adobe EDGE-nätverket, som används för att ta emot alla serveranrop för Target.

## Varför använder inte at.js och mbox.js flaggorna HttpOnly och Secure cookie? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly kan bara anges via kod på serversidan. Målcookies, som mbox, skapas och sparas via JavaScript-kod, så Target kan inte använda HTML-cookie-flaggan.

Säker kan bara ställas in via JavaScript när sidan har lästs in via HTTPS. Om sidan först läses in via HTTP kan JavaScript inte ange den här flaggan. Om du dessutom använder flaggan Secure är cookie bara tillgänglig på HTTPS-sidor.

För att garantera att Target kan spåra användare på rätt sätt och eftersom cookies genereras på klientsidan, använder inte Target någon av dessa flaggor.

## Hur ofta skickar at.js en nätverksbegäran? {#section_57C5235DF7694AF093A845D73EABADFD}

Adobe Target verkställer alla sina beslut på serversidan. Det innebär att at.js utlöser en nätverksbegäran varje gång sidan läses in igen eller att ett at.js public API anropas.

## I det bästa fallet, kan vi förvänta oss att användaren inte upplever några synliga effekter på sidinläsningen som relaterar till att dölja, ersätta och visa innehåll? {#section_CB3C566AD61F417FAC0EC5AC706723EB}

at.js försöker undvika att i förväg dölja HTML BODY eller andra DOM-element under en längre tidsperiod, men detta beror på nätverksvillkoren och aktivitetsinställningarna. at.js innehåller [inställningar](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) som du kan använda för att anpassa CSS-formatet BODY så att du bara kan dölja vissa delar av sidan i förväg i stället för att dölja hela HTML BODY. Förväntningen är att dessa delar innehåller DOM-element som måste vara&quot;personaliserade&quot;.

## Vilken händelsesekvens i ett genomsnittligt scenario där en användare kvalificerar sig för en aktivitet? {#section_56E6F448E901403FB77DF02F44C44452}

AT.js-begäran är asynkron `XMLHttpRequest`så följande steg utförs:

1. Sidan läses in.
1. at.js fördöljer HTML BODY. Det finns en inställning för att dölja en viss behållare i förväg i stället för HTML BODY.
1. AT.js-begäran utlöses.
1. När Target-svaret har tagits emot extraherar Target CSS-väljarna.
1. Med CSS-väljare skapar Target STYLE-taggar för att i förväg dölja de DOM-element som ska anpassas.
1. HTML BODY-FORMATMALLEN som döljs innan tas bort.
1. Målet börjar avfråga DOM-element.
1. Om ett DOM-element hittas tillämpar Target DOM-ändringar och elementet före döljning tas bort.
1. Om DOM-element inte hittas döljs elementen med en global tidsgräns, så att ingen bruten sida hittas.

## Hur ofta är sidans innehåll helt inläst och synligt när at.js till slut tar bort elementet som aktiviteten ändras från? {#section_01AFF476EFD046298A2E17FE3ED85075}

Med tanke på ovanstående scenario, hur ofta är sidans innehåll helt inläst och synligt när at.js äntligen tar bort elementet som aktiviteten ändras från? Med andra ord är sidan helt synlig förutom aktivitetens innehåll, som sedan visas något efter resten av innehållet.

at.js blockerar inte sidan från återgivning. En användare kan lägga märke till några tomma områden på sidan som representerar element som kommer att anpassas av Target. Om innehållet som ska användas inte innehåller många fjärrresurser, som SCRIPT eller IMG, bör allt återges snabbt.

## Hur skulle en helt cachelagrad sida påverka scenariot ovan? Skulle det vara troligare att aktivitetens innehåll blir synligt när resten av sidans innehåll har lästs in? {#section_CE76335A3E0B41CB8253DEE5E060FCDA}

Om en sida cache-lagras på ett CDN som ligger nära användarens plats, men inte nära målkanten, kan det hända att vissa fördröjningar inträffar. Målkanterna är väl spridda över hela världen, så det här är oftast inget problem.

## Kan en hjältebild visas och sedan bytas ut efter en kort fördröjning? {#section_C25B07B25B854AAE8DEE1623D0FA62A3}

Tänk på följande scenario:

Timeout för mål är fem sekunder. En användare läser in en sida som har en aktivitet för att anpassa en hjältebild. at.js skickar begäran för att avgöra om det finns en aktivitet att tillämpa, men det finns inget initialt svar. Anta att användaren ser det vanliga innehållet i hjältebilden eftersom inget svar togs emot från Target angående huruvida det finns någon associerad aktivitet. Efter fyra sekunder returnerar Target ett svar med aktivitetsinnehållet.

Skulle det i det här skedet vara möjligt att visa den alternativa versionen? Så efter fyra sekunder kan hjältebilden bytas ut och användaren kan märka att bilden byts ut?

Till att börja med är bildhjälteelementet DOM dolt. När ett svar från Target har tagits emot tillämpar at.js DOM-ändringarna, som att ersätta IMG-filen och visa den anpassade hjältebilden.

## Vilken HTML-dokumenttyp kräver at.js?

at.js kräver dokumenttypen HTML 5.

Syntaxen är:

`<!DOCTYPE html>`

Dokumenttypen HTML 5 ser till att sidan läses in i standardläge. När du läser in i felsökningsläge inaktiveras vissa JS-API:er som at.js är beroende av. Målet inaktiverar at.js i felsökningsläge.
