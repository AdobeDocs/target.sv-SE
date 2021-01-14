---
keywords: at.js releases;at.js versions;release notes
description: Information om ändringarna i varje version av Adobe Target at.js.
title: versionsinformation för at.js
feature: at.js
translation-type: tm+mt
source-git-commit: 98914eaa894f7b6e60ebb3e7229be0c35570c281
workflow-type: tm+mt
source-wordcount: '4027'
ht-degree: 0%

---


# versionsinformation för at.js

Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js.

>[!IMPORTANT]
>
>Target-teamet stöder både at.js 1.** xand at.js 2.*x*. Uppgradera till den senaste uppdateringen av någon större version av at.js för att säkerställa att du kör en version som stöds.
>
>[Adobe Experience Platform ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) Launchis är förstahandsvalet när man uppgraderar at.js. Tilläggsutvecklare lägger ständigt till nya funktioner i sina tillägg och åtgärdar ofta fel. Dessa uppdateringar paketeras i nya versioner av ett tillägg och görs tillgängliga i [!DNL Launch]-katalogen som uppgraderingar. Mer information finns i [Tilläggsuppgradering](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/extensions/extension-upgrade.html) i *användarhandboken för Experience Platform Launch*.

## at.js 2.4.0 (14 januari 2021)

Den här versionen av at.js är en underhållsrelease och innehåller följande korrigeringar:

* Lägger till stöd för ett enhetligt profil-/plattforms-ID i leverans-API customerIds.
* Korrigerar ogiltig stiltaggsinmatning.

## kl. 2.3.3 (13 november 2020)

Den här versionen av at.js är en underhållsversion och innehåller följande korrigering:

* Korrigerade ett problem relaterat till lådklicksspårning och A4T.

## .js 2.3.2 (24 juli 2020)

Den här versionen av at.js är en underhållsversion och innehåller följande korrigering:

* Korrigerade ett fel när ett skript eller en kod lägger till standardegenskap i fönstret eller dokumentet.

## kl. 1.8.2 (15 juni 2020)

Den här versionen av at.js är en underhållsversion och innehåller följande korrigering:

* Korrigerade ett problem vid användning av CNAME och kantåsidosättning, at.js 1.*Serverdomänen kan* skapas felaktigt av xx, vilket resulterade i att  [!DNL Target] begäran misslyckades. (TNT-35064)

## kl. 2.3.1 (15 juni 2020)

Den här versionen av at.js är en underhållsrelease och innehåller följande förbättringar och korrigeringar:

* Inställningen `deviceIdLifetime` kunde åsidosättas via [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). (TNT-36349)
* Korrigerade ett problem vid användning av CNAME och kantåsidosättning, at.js 2.*Serverdomänen kan* skapas felaktigt av xx, vilket resulterade i att  [!DNL Target] begäran misslyckades. (TNT-35065)
* Ett problem har korrigerats när tillägget [!DNL Target] [!DNL Launch] v2 och tillägget [!DNL Adobe Analytics] [!DNL Launch] användes, [!DNL Target] fördröjde [!DNL Analytics]-anropet. `sendBeacon` (TNT-36407, TNT-35990, TNT-36000)

## at.js version 2.3.0 (25 mars 2020)

Den här versionen av at.js är en underhållsrelease och innehåller följande förbättringar och korrigeringar:

* Stöd för inställning av innehållets säkerhetspolicyundantag för SCRIPT- och STYLE-taggar som läggs till på sidan DOM när levererade Target-erbjudanden tillämpas. Kunder kan ange `targetGlobalSettings.cspScriptNonce` och `targetGlobalSettings.cspStyleNonce` så att at.js kan ställa in motsvarande skript och style tag-noces för tillämpade erbjudanden. Mer information finns i [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
* Ett problem har korrigerats vid kompilering av at.js med Google Closure-kompilatorn för Google Tag Manager-distribution.
* Namnet på checkcookien at.js ändrades från `check` till `at_check` för att undvika kollisioner med kundernas implementeringar.

## at.js version 1.8.1 (25 mars 2020)

Den här versionen av at.js är en underhållsrelease och innehåller följande förbättringar och korrigeringar:

* Namnet på checkcookien at.js ändrades från `check` till `at_check` för att undvika kollisioner med kundernas implementeringar.

## at.js version 2.2.0 (10 oktober 2019)

Den här versionen av at.js innehåller följande förbättringar och korrigeringar:

* Korrigerade ett problem där klickspårning inte rapporterade konverteringar i A4T (Analytics for Target) när Adobe Analytics-kod inte fanns på sidelement.
* Förbättrade prestanda när du använder både Experience Cloud ID Service (ECID) v4.4 och at.js 2.2 på dina webbsidor.
* Tidigare gjorde ECID två blockerande anrop innan at.js kunde hämta upplevelser. Detta har reducerats till ett enda samtal, vilket avsevärt förbättrar prestandan.

   >[!NOTE]
   >
   >Uppgradera ditt ECID Launch-tillägg till v4.4 för att utnyttja prestandaförbättringarna.

* at.js version 2.2 innehåller även en ny inställning med namnet `serverState`. Den här inställningen kan användas för att optimera sidprestanda när en blandad integrering av Target implementeras. Hybrid-integrering innebär att du använder både at.js v2.2+ på klientsidan och leverans-API:t eller en Target SDK på serversidan för att leverera upplevelser. `serverState` ger at.js v2.2+ möjlighet att tillämpa upplevelser direkt från innehåll som hämtas på serversidan och returneras till klienten som en del av den sida som skickas. Mer information finns i &quot;serverState&quot; i [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).

## at.js version 1.8.0 (10 oktober 2019)

Den här versionen av at.js innehåller följande förbättringar och korrigeringar:

* Förbättrade prestanda när du använder både Experience Cloud ID Service (ECID) v4.4 och at.js 1.8 på dina webbsidor.
* Tidigare gjorde ECID två blockerande anrop innan at.js kunde hämta upplevelser. Detta har reducerats till ett enda samtal, vilket avsevärt förbättrar prestandan.

>[!NOTE]
>
>Uppgradera ditt ECID Launch-tillägg till v4.4 för att utnyttja prestandaförbättringarna.

## at.js version 2.1.1 (24 juli 2019)

Den här versionen av at.js är en underhållsrelease och innehåller följande förbättringar och korrigeringar:

(Numren inom parentes är avsedda för Adobe.)

* Korrigerade ett problem som gjorde att flera fyrar stacks när användaren använde metoden för klickspårning på sidan Mål och inställningar i Visual Experience Composer (VEC). (TNT-32812)
* Korrigerade ett problem som gjorde att `triggerView()` inte återgav erbjudanden mer än en gång. (TNT-32780)
* Korrigerade ett problem med `triggerView()` för att säkerställa att begäran innehåller Marketing Cloud ID-information (MCID). (TNT-32776)
* Korrigerade ett problem som förhindrade `triggerView()`-meddelandet att utlösas även om det inte finns några sparade vyer. (TNT-32614)
* Korrigerade ett problem som orsakade ett fel på grund av användningen av decodeURIcomponent som orsakade problem när URL:en innehåller en felformaterad frågesträngsparameter. (TNT-32710)
* Beacon-flaggan är nu inställd på &quot;true&quot; när leveransbegäranden skickas via API:t `Navigator.sendBeacon()`. (TNT-32683)
* Korrigerade ett problem som hindrade Recommendations erbjudanden från att visas på webbplatser för ett fåtal kunder. Kunderna kunde se erbjudandeinnehållet i API-anropet, men erbjudandet tillämpades inte på webbplatsen. (TNT-32680)
* Korrigerade ett problem som gjorde att klickspårning över flera upplevelser inte fungerade som förväntat. (TNT-32644)
* Korrigerade ett problem som förhindrade at at at.js från att använda det andra måttet efter att återgivningen av det första måttet misslyckades. (TNT-32628)
* Korrigerade ett problem när `mboxThirdPartyId` skickades med funktionen `targetPageParams` som gjorde att nyttolasten för begäran inte fanns i frågeparametrarna eller i nyttolasten för begäran. (TNT-32613)
* Korrigerade ett problem som gjorde att visnings- och klickmeddelanderesvar blockerades i Chromium-baserade webbläsare (inklusive Google Chrome). (TNT-32290)

## at.js version 2.1.0 (3 juni 2019)

Den här versionen innehåller följande funktioner och förbättringar:

* **Stöd** för deltagande i Adobe: Adobe Opt-In är ett sätt att förenkla integreringen av Adobe-lösningar med plattformar för samtyckeshantering. Mer information om Adobe-deltagande finns i [Sekretess och allmänna dataskyddsförordningen (GDPR)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md).

* **Branschstandard-CSP-kompatibel**: at.js använder inte längre eval() för att köra JavaScript.

* **Loggning** av analys på klientsidan: Ge kunderna full kontroll över hur de vill skicka analysdata till Adobe Analytics, oavsett om det gäller klient- eller serversidan.

   Mer information finns i [Logga analyser på klientsidan](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) i *Innan du implementerar*.

* **Skicka meddelanden**: Tillåt utvecklare att skicka meddelanden när en upplevelse återges av koden i stället för att använda  `applyOffer()` eller  `applyOffers()`.

   Mer information finns i [adobe.target.sendNotifications(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).

* **at.js-storleken reducerad med ~24%**: Storleken på at.js reduceras med cirka 24 %. Den mindre filstorleken förbättrar sidans inläsningsprestanda och minskar tiden för att ladda ned at.js på sidan.

## at.js version 2.0.1 (19 mars 2019)

Det här är en underhållsrelease och innehåller följande förbättringar och korrigeringar:

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

* Korrigerade ett konkurrensvillkor i DOM-avsökningskoden som orsakade JavaScript-undantag för vissa kunder. (TNT-31869)
* Meddelanden om att vyer har renderats har kopplats bort från händelsehanterare för klickspårning. Inledningsvis skickade inte Target meddelanden om klickhändelsehanterare som tillhör en återgiven vy inte kunde bifogas. Målet skickar nu ett vymeddelande även när klickelementen inte hittas. (TNT-31969)
* Korrigerade ett problem som gjorde att omdirigeringsflaggan för händelsen som slutfördes alltid hade angetts till true. (TNT-31907)
* Korrigerade ett problem som gjorde att VEC-ändringsåtgärden loggades som lyckad, även när element saknades. (TNT-31924)
* Korrigerade ett problem som gjorde att meddelanden till vissa kunder inte innehöll egenskapstoken för företagsbehörigheter. (TNT-31999)

## at.js version 1.7.1 (19 mars 2019)

Detta är en underhållsrelease och innehåller följande korrigering:

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

* Korrigerade ett konkurrensvillkor i DOM-avsökningskoden som orsakade JavaScript-undantag för vissa kunder. (TNT-31869)

## at.js Version 2.0.0 {#at-js-200}

at.js 2.x innehåller funktionsrika uppsättningar som gör det möjligt för företaget att utföra personalisering på nästa generations klienttekniker. Den nya versionen fokuserar på att uppgradera at.js för att få harmonisk interaktion med applikationer för en sida (SPA).

Här är några fördelar med att använda at.js 2.x som inte finns i tidigare versioner:

* Möjligheten att cachelagra alla erbjudanden vid sidinläsning för att minska antalet serveranrop till ett enda serveranrop.
* Förbättra slutanvändarnas upplevelser enormt på er webbplats, eftersom erbjudandena visas direkt via cachen utan den fördröjning som traditionella serversamtal ger.
* Enkel kodrad och engångsinstallation av utvecklare så att era marknadsförare kan skapa och köra A/B- och Experience-aktiviteter (XT) via Visual Experience Composer (VEC) i era single page-applikationer.

at.js 2.x innehåller följande nya funktioner:

* getOffers()
* applyOffers()
* triggerView()

Följande funktioner har tagits bort i och med introduktionen av at.js 2.x:

* mboxCreate()
* mboxDefine
* registerExtension()

Mer information finns i [Uppgradera från at.js 1.x till at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) och [at.js-funktioner](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

>[!NOTE]
>
>Om du behöver stöd för Adobe Opt-in för [Allmänna dataskyddsförordningen](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) (GDPR) måste du för närvarande använda at.js 1.7.0 eller at.js 2.1.0.

## at.js Version 1.7.0 {#at-js-170}

at.js 1.7.0 har stöd för Adobe Opt-In. Adobe Opt-In är ett sätt att förenkla integreringen av Adobe-lösningar med plattformar för samtyckeshantering.

Mer information om Adobe-deltagande finns i [Sekretess och allmänna dataskyddsförordningen](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) (GDPR).

Den här versionen åtgärdar också ett problem där Target kan åsidosätta omdirigerings-URL-parametrar med parametrar som kommer från omdirigerings-URL:en.

>[!NOTE]
>
>Om du behöver stöd för Adobe-deltagande för GDPR måste du för närvarande använda at.js 1.7.0 eller 2.1.0.<br>En lista över alla versioner finns i [at.js versionsinformation](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## at.js Version 1.6.4 {#at-js-164}

at.js 1.6.4 är en underhållsrelease som åtgärdar följande problem:

* Korrigerade ett tävlingsvillkorsmanifest i Microsoft Internet Explorer 11 som gjorde att dubblerade erbjudanden tillämpades.

## at.js Version 1.6.3 {#section_484A56774E004282B98FFFF851E4E670}

at.js version 1.6.3 innehåller följande korrigeringar och förbättringar:

* Väljarna är nu CSS-escape-konverterade om de innehåller ID:n eller CSS-klasser som börjar med en siffra, två bindestreck eller ett bindestreck följt av en siffra (till exempel #-123). (TNT-31061)
* Korrigerade ett fel som introducerades i punkt 1.6.2 där VEC (Visual Experience Composer) erbjuder från olika aktiviteter som gäller för samma CSS-väljare inte respekterade aktivitetsprioriteten. (TNT-31052)
* Korrigerade ett problem med timing out a promise i miljöer där det inte fanns något inbyggt stöd för löften. (TNT-30974)
* Problem registreras nu korrekt och rapporteras via händelsen misslyckad innehållsåtergivning. Tidigare kunde JavaScript ha körts korrekt, även om så inte var fallet. (TNT-30599)

## at.js Version 1.6.2 {#section_88BE2F69943D4280B8170F377886B58E}

Detta är en underhållsrelease som åtgärdar följande problem:

* Korrigerade ett problem som på vissa kundsajter ledde till en oändlig asynkron slinga.

>[!IMPORTANT]
>
>Dessutom innehåller version 1.6.2 av at.js även alla förbättringar och korrigeringar som ingår i version 1.6.1 och 1.6.0 av at.js. Dessa versioner är inte längre tillgängliga för hämtning. Vi rekommenderar att du uppgraderar till version 1.6.2 om du använder 1.6.1 eller 1.6.0

Här är förbättringarna och korrigeringarna som ingick i at.js version 1.6.1:

* Korrigerade ett fel i at.js 1.6.0 som gjorde att rekommendationsupplevelserna duplicerades i Microsoft Internet Explorer 11. (TNT-30593)
* at.js ser nu till att logiken för att åsidosätta kanter kontrollerar om det finns en edge-klustercookie, så att ett annat kantnummer undviks om användaren trycker på kanterna under en session. (TNT-30563)
* Korrigerade ett problem som hindrade at.js från att köra efterföljande åtgärder om HTML-innehållet innehöll ogiltig JS-kod. at.js loggar nu felet och återger de återstående åtgärderna utan problem. (TNT-30546)
* Ändras så att det finns ett undantag när en omdirigeringssida kvalificerar sig för en omdirigeringsaktivitet. (TNT-30532)
* Korrigerade ett problem som förhindrade att rätt tidsgräns för begäran spreds från API-begäran getOffer(). (TNT-30498)
* Korrigerade ett fel som förhindrade att cookies sparades i .js 1.6.0 när filprotokollet användes. (TNT-30454)
* Korrigerade ett problem som fick det att verka som om inte alla upplevelser levererades med omdirigeringar när Analytics for Target (A4T) användes. (TNT-30444)
* Korrigerade ett problem som gjorde att sidan doldes efter att Target-anropet lyckades. (TNT-30358)

Här är förbättringarna och korrigeringarna som ingår i at.js version 1.6.0:

* Omdirigeringserbjudanden stöds nu automatiskt i integreringen med Analytics for Target (A4T). Klientsidans lösning har tagits bort. (TNT-30247)
* Klientsidans kantroutning är nu aktiverat som standard. (TNT-30261)
* Korrigerade ett problem med VEC-åtgärdsåtergivning (Visual Experience Composer) när det finns beroenden mellan åtgärder. (TNT-30248)

## at.js Version 1.5.0 {#section_128C6761884C4DA8AE50D6A605FF6F55}

at.js version 1.5.0 finns nu att köpa.

* Information om händelsen `at-request-succeeded` innehåller omdirigeringsflaggan. Den här flaggan kan användas för att avgöra om sidan kommer att omdirigeras till en annan URL-adress. Om du vill veta URL:en prenumererar du på `at-content-rendering-redirect`. (TNT-29834)
* Korrigerade ett problem som gjorde att `window.targetGlobalSettings.enabled` misslyckades med ett körningsundantag om värdet var false. (TNT-29829)
* Korrigerade ett problem som gjorde att sidan inte kunde läsas in i Visual Experience Composer (VEC) om anpassad kod användes i en global mbox-begäran och brödtext gömdes. (TNT-29795)
* Stöd för `screenOrientation`, `devicePixelRatio` och `webGLRenderer` har lagts till. Dessa nya parametrar för Target-begäran används för iPhone X och annan modern enhetsidentifiering. Mer information finns i [Mobil](/help/c-target/c-audiences/c-target-rules/mobile.md#concept_2A794199DC1A4D349FFFBC7DCF1FEB89). (TNT-29781)
* Ett problem har korrigerats där platstipset för Adobe Audience Manager (AAM) inte alltid skickades. (TNT-29695)
* För webbläsare som har stöd för det växlar at.js 1.5.0 till MutationObserver för avsökning av väljare. Versioner före at.js 1.0.0 använde en MutationObserver-polyfill, som visade sig vara problematisk. För att undvika problem med polyfyllning använder version 1.5.0 följande pseudokod för att avgöra vilken schemaläggningsmekanism som ska användas:

   ```
   if MutationObserver is supported
     scheduler = MutationObserver
   else if document is visible
     scheduler = requestAnimationFrame
   else
     scheduler = setTimeout
   ```

## at.js Version 1.3.0 {#section_24EAAE1CFA814EF8B19E61842F4D8321}

at.js version 1.3.0 finns nu att köpa.

* Följande nya händelser är tillgängliga för att hjälpa dig att spåra, felsöka och anpassa interaktion med at.js:

   * LIBRARY_LOADED
   * REQUEST_START
   * CONTENT_RENDERING_START
   * CONTENT_RENDERING_NO_OFFERS
   * CONTENT_RENDERING_REDIRECT

   Mer information finns i [at.js anpassade händelser](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md).

* Du kan utöka en at.js-begäran med ytterligare parametrar från dataleverantörer. Dataleverantörer bör läggas till i `window.targetGlobalSettings` under `dataProviders key`.

   Mer information finns i [Data Providers](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

* at.js-begäranden använder nu GET, men den växlar till POST när URL-storleken överstiger 2 048 tecken. Det finns en ny egenskap med namnet `urlSizeLimit` där du kan öka storleksgränsen om det behövs. Med den här ändringen kan Target justera at.js mot AppMeasurement, som använder samma teknik.
* Målet framtvingar nu att nyckeln `mbox` i funktionen `adobe.target.applyOffer(options)` används. Den här nyckeln har krävts tidigare, men Target använder den nu för att säkerställa att Target har korrekt validering och att kunderna använder funktionen korrekt.
* at.js har förbättrat funktionerna för händelsespårning och klickning. at.js använder `navigator.sendBeacon()` för att skicka händelsespårningsdata och kommer att återgå till synkron XHR när `navigator.sendBeacon()` inte stöds. Detta gäller oftast Internet Explorer 10 och 11 samt vissa versioner av Safari. Safari kommer att lägga till stöd för `navigator.sendBeacon()` i den kommande iOS 11.3-versionen.
* at.js kan nu återge erbjudanden även när en sida öppnas i bakgrundsflikar. Vissa målkunder stötte på ett problem när `requestAnimationFrame()` inaktiverades på grund av webbläsarbegränsningsbeteendet för bakgrundsflikar.
* Den här versionen innehåller många prestandaförbättringar, bland annat kortare anropsstackar vid inspektion av en Chrome CPU-profil.
* at.js 1.3.0 stöder inte längre innehållsleverans i Microsoft Internet Explorer 9. En lista över webbläsare som stöds finns i [Webbläsare som stöds](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100). Framöver utförs alla begäranden via `XMLHttpRequest` med CORS-stöd utan JSONP-begäranden. Den här förändringen förbättrar säkerheten avsevärt.

## at.js Version 1.2.3 {#section_CE4D14AF00D04F4C8A2F0513F5EA1A84}

[!DNL at.js] version 1.2.3 är nu tillgänglig.

* Lägger till stöd för JSON-erbjudanden. JSON-erbjudanden stöds endast i aktiviteter som skapats med den formulärbaserade Experience Composer. För närvarande är det enda sättet att använda JSON-erbjudanden via direkta API-anrop. Se [Skapa JSON-erbjudanden](/help/c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D).

## at.js Version 1.2.2 {#section_4E96D13F2DFE4F1F81A1089877D53649}

[!DNL at.js] version 1.2.2 finns nu tillgänglig.

* Korrigerade ett problem som returnerade ett JavaScript-fel när målbiblioteket lästes in på en sida i QUIRKS-läge. (TNT-28312)
* Korrigerade ett problem som gjorde att klickspårning i Target bröt samtalet om insamling av analysdata. (TNT-28261)
* Korrigerade ett problem som gjorde att `getOffer() params` misslyckades när `targetPageParams()` returnerade en tom sträng. (TNT-28359)
* Ett problem med generering av sessions-ID har korrigerats när endast x användes. (TNT-28361)

## at.js Version 1.2.1 {#section_F757C8174BBA4F68AC5524ADC3D9C5E3}

[!DNL at.js] version 1.2.1 finns nu tillgänglig.

* Ett problem har korrigerats när klickspårning på en länk med target=&quot;_blank&quot; förhindrade att Target öppnade länken på en ny flik.

## at.js Version 1.2.0 {#section_1C3A18C595C34B25A14A440D213F3B9C}

[!DNL at.js] version 1.2 finns nu som en underhållsrelease som innehåller de flesta felkorrigeringar.

* Korrigerade ett problem som förhindrade standardåtgärder för specialfall för klickspårning. (TNT-28089)
* Korrigerade ett problem när klickspårning på en länk med `target="_blank"` som förhindrade Target från att öppna länken på en ny flik. (TNT-28072)
* IP-adresser kan användas som cookie-domän. (TNT-28002)
* Korrigerade ett problem som orsakade flimmer i omdirigeringserbjudanden med en global mbox eller andra regionala mbox. (TNT-27978)
* Korrigerade ett problem i konfigurationen av Experience Targeting-aktivitet som misslyckades i VEC vid växling mellan Browse och Compose. (TNT-27942)
* Felaktig hantering av flimmerstilklasser för klickspårselement har korrigerats. (TNT-27896)
* Korrigerade ett problem som gjorde att globala mbox-parametrar blandades ihop med alla mbox-parametrar. (TNT-27846)
* Ändringarna har gjorts för att säkerställa att hanterarfält, Mustache och andra mallbibliotek på klientsidan hanteras korrekt av [!DNL at.js]. (TNT-27831)
* Ändringarna har gjorts för att säkerställa att `sdidParamExpiry` initieras korrekt och skickas till besökar-API:t. Detta är en regression som har lagts till i `at.js 1.1.0`. Tidigare [!DNL at.js]-versioner påverkas inte. Detta påverkar bara klienter som använder omdirigeringserbjudanden och A4T. (TNT-27791)
* Gör ändringar för att säkerställa att `SCRIPT` körs oavsett vilket typattribut som används. (TNT-27865)

## at.js Version 1.1.0 {#section_8F494E1EA94E48A9B169F5CF9FE6DC56}

**Datum:2** augusti 2017

Följande förbättringar och korrigeringar finns i [!DNL at.js] version 1.1:

* Förbättrad hantering av svarstoken. Mer information finns i [Svarstoken](/help/administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4).
* Problemet har lösts så att `document.currentScript polyfill` inte stör vinkeln 1.X.
* Ändringarna görs för att säkerställa att klickspårning inte stör synlighetsegenskapen. Klickspårningselement markeras med CSS-klassen `at-element-click-tracking` i stället för `at-element-marker`.

## at.js Version 1.0.0 {#section_37A3D23FC4AD42A68AA831B89E03E725}

**Datum:7** juli 2017

Följande förbättringar och korrigeringar ingår i .js version 1.0:

* Stöd för asynkron inläsning av at.js för snabbare sidinläsning.
* Stöd för att fördölja sidinnehåll när at.js läses in asynkront.
* Bättre felmeddelanden när innehållsleverans är inaktiverad.
* Prestandaförbättringar när du levererar flera aktiviteter.
* Stöd för YUI-kompressor.
* Fel-/felrapportering för anpassade händelser under aktivitetsleverans.
* Åtgärda prestandaproblem i Microsoft Internet Explorer 11.
* Korrigera funktionen `getOffer()` som genererar ett fel på vissa webbplatser.
* Läs in målbiblioteket asynkront. Mer information finns i [at.js Vanliga frågor](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769).

## at.js Version 0.9.7 {#section_6C7B698BE21E40E495FD2850EFBF3E80}

**Datum:22** maj 2017

Följande förbättringar och korrigeringar finns i [!DNL at.js] version 0.9.7:

* Korrigerade ett problem relaterat till en resursnyckel som saknades i `insertAfter` och `insertBefore` åtgärder i Visual Experience Composer (VEC). Dessa problem gällde migreringen från visuella erbjudanden till mallar.

## at.js Version 0.9.6 {#section_EEFA6413F2F947AD8C4A88128B90245D}

**Datum:13** april 2017

Följande förbättringar och korrigeringar finns i [!DNL at.js] version 0.9.6:

* Stöd för omdirigeringserbjudande för A4T. När du har hämtat och installerat [!DNL at.js] version 0.9.6 kan du använda omdirigeringserbjudanden i aktiviteter som använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Target] (A4T). Förutom [!DNL at.js] version 0.9.6 finns det andra minimikrav som din implementering måste uppfylla för att kunna använda omdirigeringserbjudanden och A4T. Mer information och ytterligare viktig information som du bör känna till finns i [Omdirigeringserbjudanden - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* Före [!DNL at.js] 0.9.6, när besökar-API:t fanns på sidan och `visitorApiTimeout`-inställningen var för aggressiv, kunde Target hamna i en situation när inga MCID-data skickades i [!DNL Target]-begäran. Detta kan leda till problem som osydda träffar i [!DNL Analytics] när A4T används.

   Detta beteende har ändrats i [!DNL at.js] 0.9.6, även om `visitorApiTimeout` är inställt på 1 ms, försöker Target samla in SDID-, spårningsservrar och kund-ID:n och skicka dessa i Target-begäran.

* Inställningen `selectorsPollingTimeout` har lagts till. Mer information finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
* Svarets format från `getOffer()` har ändrats. Mer information finns i [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md).
* Konsolloggning har lagts till för `<!DOCTYPE>`-deklarationer som inte stöds.
* Korrigerade ett problem där [!DNL Target Classic]-plugin-program inte tillämpades korrekt när flera standarderbjudanden levererades till en enda mbox. (TGT-22664)
* Förbättrad cookie-inställning för två TLD-domäner (top-level-domains) för två bokstäver för att säkerställa att mbox-cookien är korrekt inställd för dessa domäner (t.ex. [!DNL test.no], [!DNL autodrives.ca] o.s.v.).
* Algoritmen för extrahering av toppnivådomänen som ska användas när cookies sparas har ändrats i at.js version 0.9.6. På grund av den här ändringen kan cookies inte sparas i adresser som använder IP. För det mesta används IP-adresser i testsyfte, men som tillfälliga lösningar kan du använda DNS-poster eller justera värdfilen i en lokal ruta.
* Åtgärdade flytt- och omarrangeringsåtgärder när egenskaper är strängvärden i stället för heltal.

## at.js Version 0.9.4 {#section_A15B12F12CD94F07B3F56613A79A815F}

**Datum:19** januari 2017

* mbox-namn kan nu innehålla specialtecken, inklusive et-tecken ( &amp; ), för att vara i linje med namnkraven för mbox-namn med mbox.js.

   En lista med tillåtna specialtecken finns i [at.js Configurations](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_2FA0456607D04F82B0539C5BF5309812).

* `secureOnly`-inställningen som anger om at.js endast ska använda HTTPS eller tillåtas växla mellan HTTP och HTTPS baserat på sidprotokollet. Det här är en avancerad inställning som har standardvärdet False och kan åsidosättas via `targetGlobalSettings`.
* Alternativet [!UICONTROL Legacy Browser Support] är tillgängligt i version 0.9.3 och tidigare av at.js. Det här alternativet togs bort i at.js version 0.9.4.

## at.js Version 0.9.3 {#section_DF13BC1D7C994AE7A36B81937A699DF4}

**Datum:10** oktober 2016

* Ser till att mbox-anrop utlöses i Microsoft Internet Explorer 11 när äldre webbläsare är inaktiverade i at.js-inställningarna.
* Ser till att standardinnehåll återges om ett dynamiskt fjärrerbjudande misslyckas (till exempel om URL:en är felaktig och returnerar ett 404-fel).
* Ser till att element snabbt visas när VEC-klickningsspårningsväljare inte kan hittas i DOM.

## at.js Version 0.9.2 {#section_148549CBB4F046BAA8F79C79B64EC889}

**Datum:21** september 2016

* En `optoutEnabled`-inställning har lagts till för att aktivera eller inaktivera avanmälan av enhetsdiagram. Om den här inställningen är `true` och besökaren har valt att inte spåra, kommer besökarens webbläsare inte att göra några mbox-anrop. Device Graph är för närvarande i Beta. Den här inställningen är som standard `false`, men måste anges till `true` om du använder Device Graph. Ett liknande alternativ är en del av mbox.js v61.
* `CustomEvent`-stöd för meddelandefunktionen har lagts till. Tidigare kunde inte händelsemeddelandefunktionen at.js användas via vanliga DOM-API:er, som `document.addEventListener()`. Nu kan du använda `document.addEventListener()` för att prenumerera på at.js-händelser, som request-händelser och innehållsrenderingshändelser.
* Ett problem som rör erbjudanden som har skapats i Visual Experience Composer (VEC) har korrigerats. Före den här versionen dolde Target väljarna och gömde dem bara när alla väljare matchade. I at.js 0.9.2 Target tas väljarna bort så snart de matchar.

## at.js Version 0.9.1 {#section_DAFB99114D604CFB8416C1BC7DEEAEEE}

**Datum:14** juli 2016

* Tillhandahåller en timeout för besökar-ID-tjänsten på at.js, som är oberoende av tjänstens egen timeout.
* Korrigerar ett fel i 0.9.0 som påverkade implementeringar med at.js på vissa sidor och mbox.js på andra sidor.
* Om du använder Adobe Analytics som aktivitetens rapportkälla behöver du inte ange en spårningsserver när du skapar en aktivitet om du använder mbox.js version 61 (eller senare) eller at.js version 0.9.1 (eller senare). Mbox.js- eller at.js-biblioteket skickar automatiskt spårningsservervärden till [!DNL Target]. När aktiviteten skapas kan du lämna fältet [!UICONTROL Tracking Server] tomt på sidan [!UICONTROL Goals & Settings].

## at.js Version 0.9.0 {#section_2981CC9792F245389B39BB5B69F84C4E}

**Målversion:** 16.6.1

**Datum:23** juni 2016

* Korrigerar ett problem med vita skärmar när VEC-erbjudanden används. Alla som använder [!DNL at.js] bör uppgradera till den nya versionen.
* Nytt `registerExtension`-API.

   Detta nya API ger utvecklare åtkomst till vissa jQuery-moduler som används i [!DNL at.js] för att utveckla tillägg (även plugin-program) för biblioteket. Den här förändringen har vissa konsekvenser. Detta påverkar endast de användare som använder dessa funktioner:

   * `getSettings()` API har tagits bort, men samma funktioner är tillgängliga med  `registerExtension()`.
   * `getTracking()` API har tagits bort, men samma funktioner är tillgängliga med  `registerExtension()`.

   * Befintliga tillägg (t.ex. AngularJS-tillägg) måste uppdateras för att metoden `registerExtension()` ska kunna användas.

* Nytt meddelande-API för at.js.

   Målet med det här meddelandesystemet är att ge mer insikt i vad [!DNL at.js] gör på sidan och när det uppstår problem. Ett vanligt problem med VEC är att en IT-release ändrar sidan, en VEC-väljare avbryter och att testet slutar leverera innehållet korrekt. Ett mål med det här meddelandesystemet är att göra det här leveransproblemet tillgängligt för sidan, så att utvecklare kan komma åt informationen, skicka den till ett system som [!DNL Adobe Analytics], och varningar kan skickas till företagsägarna om att testet har gått ut.

* Ny API-metod för `targetGlobalSettings()`.

   Du kan åsidosätta inställningarna i at.js-biblioteket i stället för att konfigurera inställningarna i [!DNL Target Standard/Premium UI]eller genom att använda REST API:er.

## at.js Version 0.8.0 {#section_E1C7B08EC0494388A022C28A8B8FE807}

**Datum:5** maj 2016.

Detta är den första officiella versionen av [!DNL at.js]-biblioteket.

[!DNL at.js] är ett nytt implementeringsbibliotek som  [!DNL Target] är utformat för både vanliga webbimplementeringar och enkelsidiga applikationer.

[!DNL at.js] ersätts  [!DNL mbox.js] för  [!DNL Adobe Target] implementeringar.

>[!NOTE]
>
>Även om [!DNL at.js] ersätter [!DNL mbox.js] stöds mbox.js även i fortsättningen. För de flesta har [!DNL at.js] fördelar framför [!DNL mbox.js]. Detta ger dig tid att testa [!DNL at.js] och att ändra implementeringen på dina sidor.

[!DNL at.js] förbättrar bl.a. sidinläsningstiderna för webbimplementeringar, förbättrar säkerheten och ger bättre implementeringsalternativ för enkelsidiga program.

[!DNL at.js] innehåller komponenterna som ingick i  [!DNL target.js]så det finns inte längre något anrop till  [!DNL target.js].

Tänk på följande när du implementerar [!DNL at.js]:

* Tidigare versioner än 8 av Internet Explorer stöds inte.
* Asynkron implementering innebär att äldre integreringar som plugin-programmet [!DNL Test&Target] till [!DNL SiteCatalyst] kanske inte fungerar.
* [!DNL Target] plugin-program som refererar till  [!DNL mbox.js] objekt och metoder stöds inte.
* Alla anrop till [!DNL Target] görs via XMLHTTPRequest och innehållet returneras via JSON.
