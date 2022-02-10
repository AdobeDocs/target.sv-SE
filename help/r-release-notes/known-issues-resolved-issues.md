---
keywords: kända problem;lösta problem;versionsinformation;fel;problem;korrigeringar
description: Hitta information om kända fel i Adobe Target, inklusive tillfälliga lösningar. När problem har lösts flyttas de till avsnittet Lösta.
title: Var hittar jag information om kända fel och lösta problem?
feature: Release Notes
exl-id: 6eb854f7-ed46-4673-afeb-0b44970598cd
source-git-commit: a7854c30ac1ed5212a0f56f188bc83aa564814dc
workflow-type: tm+mt
source-wordcount: '4677'
ht-degree: 0%

---

# Kända problem och lösta problem

Information om kända fel för [!DNL Adobe Target]. Innehåller även information om problem som har lösts.

>[!NOTE]
>
>Utgivningsnumren inom parentes är avsedda för Adobe.

## Kända fel {#section_AEDC98B67CF24C9F8E0CF0D2EB9ACAEF}

I följande avsnitt listas kända problem för [!DNL Target]:

### Visual Experience Composer (VEC) läser in webbplatser med Service Workers

Det finns vissa begränsningar när du försöker använda VEC för att öppna en webbplats som använder [Servicearbetare](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API){target=_blank} (SW).

En SWF-fil är en webbteknik som kan användas för att avlyssna begäranden för den domän som de är installerade på av en webbsida. Programvaran överlever sidbesöket och aktiverar sig själv vid efterföljande besök. Svartvyn avgör vilka förfrågningar som går igenom och vilka som fångas upp och hanteras från ett cacheminne istället.

Programvaran kan styra cachningen. kan cachelagra själva webbsidan, statiska resurser som JS, CSS, IMG, AJAX, deras innehåll och deras svarshuvuden, inklusive de som [VEC Helper-tillägg för mål](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) försöker ta bort, som X-Frame-Options: SAMEORIGIN, CSP (Content-Security-Policy) eller Set-Cookie.

Tyvärr tar Chrome-tilläggets API:er som fångar upp webbförfrågningar inte emot förfrågningar som fångats upp och hanterats av en SWF-fil. Tillägget kan därför inte åtgärda sidhuvuden och cookies om webbsidesbegäran hanterades från ett cacheminne av en SWF-fil eftersom webbsidan inte läses in i VEC på grund av X-Frame-Options eller CSP-rubriker som också cache-lagrades.

Som en möjlig tillfällig lösning kan du inaktivera Service Workers på fliken Chrome Developer Tools > Application (Verktyg för Chrome-utvecklare) och sedan aktivera kryssrutan&quot;Bypass for network&quot; (Kringgå för nätverk) under avsnittet Service Workers (Servicearbetare). (KB-2006)

### Trafikfördelning av aktiviteter automatiskt med A4T {#aa-a4t}

I vissa fall är trafikfördelningen [!UICONTROL Auto-Allocate] aktiviteter använda [!UICONTROL Analytics for Target] (A4T) kan variera från vad som ska ske baserat på den rapporterade konverteringsgraden för varje upplevelse. Detta inträffar oftare för aktiviteter med en hög andel av besökstrafiken för återvändande. Berörda kunder meddelas om vilka aktiviteter som påverkas.

Använd [!UICONTROL Auto-Allocate] med standard [!DNL Target] rapportera eller använda standardtester A/B med [!DNL Analytics] rapportering som ett alternativ till [!UICONTROL Auto-Allocate] med [!DNL Analytics] rapportering. (TOP-131)

### Analyser för Adobe Target-värden (A4T) för automatisk fördelning och automatisk målaktiviteter

The [!DNL Target] Med användargränssnittet kan användare välja engagemangs- och intäktsmått som inte stöds som det primära målmåttet för optimering i [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet. Konverteringsmått stöds. interaktions- och intäktsstatistik är *not* stöds. Om du väljer målstatistik för engagemang eller intäkter skapas ingen optimeringsmodell.

En lista över målvärden som stöds och som inte stöds finns på [A4T-stöd för Automatisk allokering och Automatiskt mål-aktiviteter](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md). (TNT-38409)

### Enhanced Experience Composer (EEC) stöder inte förfrågningar från PUT.

Ett problem med EEG förhindrar för närvarande att det stöder förfrågningar från PUT och leder till ett 504-timeout-fel. (TGT-41493)

### [!DNL Adobe Experience Platform] segmentnamn inte visas i [!UICONTROL Important Attributes] rapport.

[!DNL Adobe Experience Platform] segmentnamn inte visas i [!UICONTROL Important Attributes] rapport för [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] (AT) verksamhet. (TOP-3813)

### Arkivering [!UICONTROL Auto Target] aktiviteter kan orsaka synkroniseringsproblem

Försöker arkivera inaktivt [!UICONTROL Auto-Target] aktiviteter kan leda till synkroniseringsproblem. Arkivera inte förrän problemet är åtgärdat [!UICONTROL Auto-Target] verksamhet. Lämna dem i [!UICONTROL Inactive] tillstånd. (TGT-40885)

### Sidleverans {#page-delivery}

Om du lägger till en mallregel, t.ex. URL:en innehåller (/checkout, /cart) i [sidleverans](/help/c-activities/t-experience-target/t-xt-create/xt-activity-url.md)läggs extra blanksteg till före reglerna. De här extra utrymmena är kosmetiska och påverkar inte målgruppsdefinitionsskapande och leverans av erbjudanden. (TGT-35920)

### Länkar för QA-förhandsgranskning

Länkar för förhandsgranskning av aktivitet för sparade aktiviteter läses kanske inte in om det finns för många sparade aktiviteter på ditt konto. Försök med förhandsgranskningslänkarna igen. Arkivera sparade aktiviteter som inte längre används aktivt för att förhindra att problemet fortsätter att inträffa. (TNT-37294)

### QA-läge för Recommendations-aktiviteter

Ett känt fel förhindrar förhandsgranskning om villkoren som används i aktiviteten är artikelbaserade eller kategoribaserade. (TNT-37455)

### Omdirigeringserbjudanden {#redirect}

Följande är kända problem med omdirigeringserbjudanden:

* Ett begränsat antal kunder har rapporterat större variationsgrader i trafikdistributionen när omdirigeringserbjudanden används i aktiviteter som konfigurerats med Analytics for Target (A4T).
* Omdirigeringsaktiviteter i at.js-implementeringar kan få URL:en för förhandsgranskning att gå in i en loop (erbjudandet levereras upprepade gånger). Du kan använda [QA-läge](/help/c-activities/c-activity-qa/activity-qa.md) i stället för att utföra förhandsgranskning och kvalitetskontroll. Problemet påverkar inte den faktiska leveransen av erbjudandet. (TGT-23019)

### Avbryt inläsning av en sida i Visual Experience Composer (VEC) {#cancel}

* Följande kända fel inträffar för närvarande när inläsningen av ett [!UICONTROL A/B Test] eller [!UICONTROL Experience Targeting] (XT) aktivitet i VEC som innehåller en omdirigerings-URL.

   När du avbryter sidinläsningen i steg ett av de guidade arbetsflödena för VEC visas [!UICONTROL Modifications] i VEC-skärmar och omdirigering till URL-mallen används på upplevelsen (till exempel &quot;Experience B&quot;). När du går vidare till steg två eller tre och sedan går tillbaka till steg ett, inträffar följande situation.

   I&quot;Experience B&quot; återges som standard den avbrutna webbplatsens inläsningsmall och [!UICONTROL Modifications] -panelen är tillgänglig, vilket inte ska vara fallet eftersom en omdirigering till URL-mallen används. Omdirigering till URL-mallen ska visas.

   Så här visar du det korrekta tillståndet för upplevelsen i VEC:

   Om du byter till en annan upplevelse och sedan byter tillbaka till&quot;Experience B&quot;, [!DNL Target] visar omdirigering till URL-mallen som används för den här upplevelsen och [!UICONTROL Modifications] panelen är inte tillgänglig. (TGT-32138)

* Om du avbryter inläsningen för SPA-webbplatser (Single Page Application) kan du inte redigera åtgärder under [!UICONTROL Modifications] -panelen.

### Recommendations

Följande är kända problem med [!UICONTROL Recommendations] verksamhet:

* Vid kopiering av en [!UICONTROL Recommendation] aktivitet med en aktiv befordran, påverkar alla ändringar i dubblettaktiviteten för närvarande även den ursprungliga aktiviteten, och omvänt. (TGT-39155)

   Som tillfällig lösning:

   * Inaktivera aktivitetskampanjer
   * Duplicera aktiviteten
   * Aktivera kampanjer igen i varje aktivitet

* När [!DNL Target] returnerar ett JSON-erbjudande med getOffer(), som returneras med typen JSON. Om du returnerar en JSON Recommendations-design returneras den emellertid med en typ av HTML.
* Enheterna har gått ut korrekt efter 60 dagar efter det att inga uppdateringar har tagits emot via feed eller API. men de enheter som har gått ut tas inte bort från katalogens sökindex efter att de har gått ut. (IRI-857)
* Övertäckningarna &quot;Användningsinformation&quot; för villkor och design återspeglar inte deras användning i A/B- och Experience Targeting-aktiviteter (TGT-34331)
* Recommendations-erbjudanden i A/B- och Experience Targeting-aktiviteter visar inte någon visuell förhandsvisning av Recommendations-fältet (TGT-33426)
* Samlingar, uteslutningar, villkor och designer som skapas via API är inte synliga i Target-användargränssnittet och kan bara redigeras via API. Om du skapar något av dessa objekt i målgränssnittet och sedan redigerar dem via API, återspeglas inte ändringarna i målgränssnittet. Objekt som redigeras via API bör fortsätta att redigeras via API för att undvika att ändringar går förlorade. (TGT-35777)
* Recommendations-aktiviteter som skapas via API kan visas i användargränssnittet, men kan bara redigeras via API.
* Den feed-status för anpassade kriterier som visas i kriterielistan (kortvyn) uppdateras var tionde minut och kan i sällsynta fall vara mer än tio minuter gammal. Statusen som visas i redigeringsvyn för anpassade kriterier hämtas i realtid och är alltid uppdaterad. (TGT-35896, TGT-36173)
* Kriterier och designkort visar inte korrekt antal aktiviteter som de används i. Om kriterierna eller designen används i en A/B-aktivitet kan kortet felaktigt visa att designen eller kriterierna inte används, även när designen eller kriterierna används i aktiviteten. (TGT-36621, TGT-37217)

### Multivariata testaktiviteter (MVT)

I en MVT-aktivitet är vinnaren som visas i tabellen och diagrammet inte konsekvent när mätvärden kontrolleras. Detta inträffar om en användare växlar från Sammanfattning till Diagram, sedan växlar tillbaka till Sammanfattningsvy, ändrar ett mätvärde och sedan växlar till Diagramvy. När detta problem uppstår visas alltid rätt vinnare i sammanfattningsvyn. Om användaren aldrig växlar diagramvyn mellan sammanfattningsvyer visas rätt vinnare i diagramvyn.

### at.js {#atjs}

Följande är kända problem med at.js:

* Om du använder at.js-versioner före 2.2.0 rapporterar click tracking inte konverteringar i Analytics for Target (A4T) om det inte finns någon Adobe Analytics-kod i sidelement (till exempel knappar). En korrigering av problemet introducerades i kl. 2.2.0. [Uppgradera till den senaste versionen, at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) om du upplever detta problem.
* Om du skapar en upplevelse utan ändringar med at.js 2.1.1 eller tidigare (till exempel en standardupplevelse) kanske inte upplevelsen räknas med i rapporter, analyser för mål (A4T), Adobe Analytics eller Google Analytics. Dessutom kanske plug-in-programmet ttMeta inte fungerar som det ska.

   Du kan lösa det genom att använda ett mellanrum i upplevelseinnehållet. (TNT-33366)

   >[!NOTE]
   >
   >En korrigering av problemet fanns i at.js 2.2.0. Uppgradera till [senaste versionen eller at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) eller använd den tillfälliga lösning som nämns ovan endast för tidigare version av at.js än 2.2.0.

* När en sida läses in i Visual Experience Composer (VEC) måste Target avgöra om den globala mbox-inställningen är aktiverad eller inaktiverad och om entityID eller categoryID finns på den plats där användaren försöker tillämpa rekommendationen i VEC. Baserat på denna information filtreras kriterielistan. Standardlistan innehåller filtrerade algoritmer, men [Kryssrutan Kompatibel](/help/c-recommendations/t-create-recs-activity/algo-select-recs.md) I kan du visa den fullständiga algoritmlistan.

   När du använder at.js är kryssrutan Kompatibilitet dold, så du kan inte se inkompatibla algoritmer.

   Problemet gäller endast Recommendations-aktiviteter som använder VEC.

   **Tillfällig lösning**: Inaktivera [!UICONTROL Filter Incompatible Criteria] alternativ i [!UICONTROL Recommendations > Settings]. När du har inaktiverat den här inställningen visas alla villkor (kompatibla och inkompatibla) i sökaren. (TGT-25949)

* Mboxes som inte aktiveras i Microsoft Explorer 11-webbläsare efter uppgradering till at.js version 1.0 på grund av interaktionen mellan at.js och Visitor API 2.2.0. Problemet berör at.js version 0.9.6 och senare. (TNT-27600)
* at.js kanske inte fungerar med Cordova/Hybrid-appar eftersom cookies från första part inte stöds i dem för närvarande. (TNT-26166)

   **Tillfällig lösning**: Konfigurera at.js med alternativet &quot;x-only&quot; aktiverat och skicka `mboxThirdPartyId` i samtal för att hantera användare.

### Framgångsmått

Framgångsmått med det avancerade alternativet &quot;Hur kommer antalet att ökas&quot; inställt på &quot;varje intryck&quot; eller &quot;varje intryck (exklusive uppdateringar)&quot; kan inte användas som ett framgångsmått som ett annat mätvärde är beroende av.

När ett framgångsmått ställs in på ökning för varje intryck räknas besökaren igen varje gång besökaren besöker detta framgångsmått. Target återställer sedan resultatmåttet&quot;medlemskap&quot; till 0 så att det kan räknas igen vid nästa intryck. Om ett annat mått kräver att det här måttet har setts först, kommer Target alltså aldrig ihåg att användaren har sett det första måttet.

### Analyser för [!DNL Target] (A4T)

När du använder Target-aktivitetsuttryck och -konverteringar i Analysis Workspace ska du använda samma Touch-modell för mätvärdena för att säkerställa korrekt räkning. Använda en [icke-standardattribueringsmodell](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html), högerklicka på måttet för att **Ändra kolumninställningar > aktivera Använd icke-standardattribueringsmodell > välj samma Touch-modell**. Om den här modellen inte används överskattas mätvärdena.

Alla aktuella Analytics-paket kan lägga till den här modellen med Attribution IQ. Om du inte har tillgång till Attribution IQ kan du lita på A4T-data i Rapporter och analyser.

### Mål-API:er

Kunder kan inte utföra CRUD-åtgärder på Automatisk allokering av aktiviteter via v3-versionen av API:t för A/B-aktiviteter på Adobe I/O.

### Målinriktning för GEO

Den 10 maj 2020 uppdaterade Adobe GEO-providerfilerna, som innehöll vissa inkonsekvenser. Vissa värden som innehåller kommatecken lades till. Även om värden i befintliga målgrupper inte hade något kommatecken. Alla Adobe-leveransservrar påverkades inte av den här ändringen. Därför har de målgrupper som använder sådana värden kanske inte kvalificerat alla korrekta besökare mellan 10 maj och 22 juli 2020.

### Rapportering - Inkonsekventa data i den hämtningsbara CSV-rapporten jämfört med den rapport som visas i [!DNL Target] Gränssnitt. {#csv}

Rapporter som genererats för hämtning som CSV-filer är inkonsekventa om aktiviteten använder mer än ett mätvärde. Den hämtningsbara rapporten genereras endast baserat på rapportinställningarna och tar hänsyn till samma värde för andra mätvärden som används.

Sanningens källa är alltid den rapport som visas i [!DNL Target] Gränssnitt.

## Lösta problem {#section_FD2FC86E7C734D60B1EDC9DEF60E1014}

Eftersom kända problem ovan har lösts flyttas de till följande avsnitt.Ytterligare anteckningar läggs till om det behövs.

### Bild med etiketten &quot;Bearbetar&quot;

Bilderbjudandena på sidan Erbjudanden kan ibland behålla&quot;bearbetningsetiketten&quot; i flera timmar efter att bilderna har överförts. I de flesta fall är detta bara ett problem med etiketten: bilderbjudandena kan fortfarande användas i aktiviteter och levereras. (MCUI-10264, TGT-37458)

Problemet har åtgärdats i Target Standard/Premium 20.10.1.

### Analyser för Adobe Target-rapportering (A4T)

Följande problem relaterade till A4T har åtgärdats:

* Ett problem som påverkade A4T-aktiviteter med en [!DNL Analytics] målmått som fick A4T-rapporter att visa en oväntad trafikdelning eller artificiellt uppblåsta konverteringar.

   Detta problem påverkade A4T-rapportering under följande förhållanden:

   * Aktiviteten skapades eller sparades mellan 15 september och 5 november 2020 (4:00 PST), och
   * Aktiviteten hade en [!DNL Analytics] Mått valt som målmått.

   [!DNL Target] korrekt uppdelad trafik under denna tid. En delning på 50/50 i aktivitetsinställningarna kan dock visas, till exempel som en delning på 90/10 i A4T-rapporter.

   För aktiviteter som påverkas är rätt trafikdelning synlig för förstagångsbesökare av aktiviteten efter 5 november (4.00 PST). Nya aktiviteter som skapats eller sparats efter den här tiden kommer att rapportera trafikuppdelningen korrekt.

* Ett problem som påverkade A4T-aktiviteter med en [!DNL Target] målmått som fick A4T-rapporter att rapportera låga eller inga konverteringar.

   >[!NOTE]
   >
   >Detta problem påverkade endast A4T-rapportering. Det påverkade inte aktivitetsleveransen.

   Detta problem påverkade A4T-rapportering under följande förhållanden:

   * A4T-aktiviteten var aktiv mellan 22 september och 11 november 2020 (2:30 PST) och
   * Aktiviteten hade en [!DNL Target] mått som valts som målmått, och
   * När en besökare når målhändelsen för aktiviteten (t.ex. [!UICONTROL Clicked an Element]) fanns det också en lägre prioritet för icke-A4T-aktivitet som matchade konverteringshändelsen. Detta kan inträffa om aktiviteten som inte är A4T antingen har konfigurerats med samma mått som A4T-aktiviteten eller om den har konfigurerats med &quot;any mbox&quot;-måttet.

   Detta problem påverkade rapporteringen av A4T-aktiviteter som var aktiva mellan 22 september och 11 november 2020 (2:30 PST). Rapportering för påverkade A4T-aktiviteter visar konverteringar korrekt utanför det här datumintervallet. Rapportering för icke-A4T-aktiviteter påverkades inte.

Om du har ytterligare frågor kan du kontakta din Customer Success Manager (CSM) eller [Adobe kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). (CSO 20201110016)

### Automatisk målrapportering {#at-metrics}

Ett problem som påverkade har åtgärdats [!DNL Adobe Target Premium] användare [!UICONTROL Auto-Target] från och med 15 september 2:30 (PDT) till 6 oktober kl. 9.25. (PDT). Vid visning av rapporter för påverkad konverteringsstatistik (konfigurerad med antingen[!UICONTROL Viewed a page]&quot; eller &quot;[!UICONTROL Clicked on mbox]&quot;option) rapporteras konverteringsgraden felaktigt. Det finns för närvarande inget känt leveransproblem.

Så här synkroniserar du om och korrigerar din rapportering:

1. Kopiera och spara de påverkade [!UICONTROL Auto-Target] verksamhet.
1. Aktivera de nyligen sparade aktiviteterna (om de påverkade aktiviteterna var aktiva).
1. Ta bort de ursprungliga (påverkade) aktiviteterna.

(TGT-38522, CSO 20201006007)

### Rapportering {#conversions-audiences}

Konverteringar ökar för närvarande på olika sätt beroende på vilken målgrupp som används.

Om antalet konverteringar till exempel är inställt på ökningen &quot;En gång per post:&quot; för samma besökare

* Målgrupp: &quot;Alla kvalificerade besökare&quot; för konverteringar på besöksnivå ökar endast en gång. Detta är det förväntade beteendet.
* Målgrupp: &quot;Nya besökare&quot; för konverteringar på besöksnivå ökar felaktigt varje gång, i stället för att bara öka en gång. Detta är inte det förväntade beteendet.

Om antalet konverteringar är inställt på ökning &quot;Vid varje intryck:&quot;

* Målgrupp: &quot;Alla kvalificerade besökare&quot; för konverteringar på besökarnivå ökar felaktigt bara en gång i stället för att öka varje gång. Detta är inte det förväntade beteendet.
* Målgrupp: &quot;Nya besökare&quot; ökar antalet konverteringar på besökarnivå varje gång. Detta är det förväntade beteendet.

Observera att det här problemet är relaterat till [!DNL Target] enbart rapportering. Detta är inte något problem när du använder [!UICONTROL Analytics for Target] (A4T)-rapportering.

Problemet löstes.

### Sidor som inte läses in i Visual Experience Composer (VEC) eller Enhanced Experience Composer (EEC) när du använder Google Chrome version 80+

Det här kända problemet gäller Google beslut att ändra standardbeteendet för cookies utan attributet SameSite med början i Chrome version 80. Innan ändringen av Chrome gjorde standardvärdet för alla cookies utan attributet SameSite till&quot;SameSite=None&quot;, och nu är standardvärdet&quot;SameSite=Lax&quot; och det här ändrar sättet på vilket cookies skickas vid GET- och POST-begäranden. Se [Uppdateringar för samma webbplats](https://www.chromium.org/updates/same-site).

Mer information och en korrigering finns i&quot;Hur påverkar den nyligen lanserade policyn för tillämpning av cookies i Google Chrome SameSite hur VEC och EEC fungerar?&quot; in [Felsökning av problem relaterade till Visual Experience Composer och Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

### Diagramrapporten för en Automatisk målaktivitet kan inte återges när en anpassad upplevelse används som kontroll

Diagramrapporten för en Auto-Target-aktivitet kan inte återges för&quot;differentiella&quot; lägen (genomsnittlig Lyft och daglig lyft) om det inte finns några data (0 besök) för någon upplevelse. Detta kan inträffa under det första steget i en aktivitet om kontrollupplevelsen är anpassad. För de andra lägena (Running Average Control och Targeted, Daily Control och Targeted samt Visits) fungerar det bra. Så snart det finns vissa data (besök som inte är noll) återges rapporten som förväntat.

Problemet har åtgärdats i version 19.7.1 av Target.

### Implementering: Automatisk generering av global mbox

På fliken Implementering ([!UICONTROL Administration > Implementation]) [!UICONTROL Global Mbox Auto Create] som standard är fältet&quot;false&quot; för en nyligen etablerad klientorganisation.

När at.js laddas ned för första gången efter etablering visas [!UICONTROL Global Mbox Auto Create] fältet är inställt på &quot;true&quot; i den hämtade at.js-filen och i [!DNL Target] backend, men den visas som &quot;false&quot; på [!UICONTROL Implementation] sidan i användargränssnittet tills sidan uppdateras (när sidan har uppdaterats blir statusen&quot;true&quot;).

at.js hämtas med `global_mbox_autocreate = false` för en nyligen etablerad klientorganisation. Om mbox.js (nu utgått) laddades ned först ställs global\_mbox\_autocreate in &quot;true&quot; och at.js laddas också ned med `global_mbox_autocreate = true`. (TGT-15929)

### Enterprise Permissions support in [!DNL Target] API:er {#api}

Koderbjudanden som skapas från målgränssnittet i offertbiblioteket kan visas på standardarbetsytan om listan med erbjudanden hämtas med GET-API:er. Detta problem kommer att åtgärdas under den första veckan i mars 2019. När den här korrigeringen är på plats visas koderbjudanden på lämplig arbetsyta när de hämtas från API:er. Den här utgåvan har *not* påverka erbjudanden som skapats från API:er. Koderbjudanden som skapats från API:er visas till exempel i den arbetsyta som de skapades i, oavsett om de hämtas med GET-API:er eller från målgränssnittet.

### Rapportering och extrema order

Från 25 november 2019 till 26 april 2020 uppstod ett problem på en målserver som ledde till att extrema ordervärden räknades in i intäktsbaserade rapportvärden (AOV, RPV). Från 19 december 2019 till 23 april 2020 har en annan server drabbats av samma problem. Problemet påverkade inte alla Target-servrar eller alla Target-kunder.

Du var *not* påverkas om:

* Målimplementeringen använder olika servrar.
* Dina rapporter uteslöt inte extrema order.
* Du använde ett konverteringsmått för att mäta dina aktiviteter.
* Dina målaktiviteter använder Analytics för Target (A4T).
* Du bor i Asien-Stillahavsområdet (APAC).

Om du vill ta reda på om det här problemet påverkar din Target-rapportering kan du kontakta [Kundtjänst](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB).

### Recommendations

* Recommendations-flödesindex kan visa&quot;Väntar på index&quot; om objekten i flödet är desamma som i föregående körning. Produktens intag påverkas inte. (RECS-6663)

   Problemet har åtgärdats i version 19.4.2 av Target.

* Det tar längre tid än förväntat att bearbeta Recommendations-flöden. (COR-2836)

   Åtgärdat i version 16.10.1 av Target.

* Gränssnittet för rekommendationsfeeds visar inte rätt indexeringsstatus. Serverdelsjobben fungerar korrekt, men gränssnittet kan inte hämta och visa det aktuella läget.

   Detta korrigerades i version 17.10.1.

### Omdirigeringserbjudanden

Ett tävlingsvillkor på sidan kan göra att sidvyer på den ursprungliga sidan och på omdirigeringssidan räknas. Uppdateringar planeras för implementeringen av at.js för att säkerställa att detta konkurrensvillkor kan undvikas.

Problemet korrigerades i kl. 1.6.3.

### Uteslutningsgrupper

* När automatisk borttagning används efter att exkluderingsgrupper har skapats kan antalet i aktivitetsdiagrammet vara felaktigt i användargränssnittet.
* När befintlig aktivitet med exkluderingsgrupp redigeras kanske de manuella inkluderingarna inte visas korrekt i användargränssnittet.

De här problemen löstes.

### Mål-API:er

v1-versionen av erbjudandets API:er på Adobe I/O behandlar alla erbjudanden som skapats via Target så att de ligger i standardarbetsytan. (TTTEAM-41957)

Problemet löstes.

### at.js {#at-js-2}

Mboxes som inte aktiveras i Microsoft Explorer 11-webbläsare efter uppgradering till at.js version 1.0 på grund av interaktionen mellan at.js och Visitor API 2.2.0. Problemet berör at.js version 0.9.6 och senare. (TNT-27600)

Åtgärdat med version av API 2.3.0 eller senare.

### Målinriktning

Det går för närvarande inte att söka efter en sträng som innehåller specialtecken (t.ex. ett mellanslag eller kommatecken) när målgrupper med geomål skapas. Det här problemet har ytor, till exempel när man skapar målgrupper baserade på städer, stater, länder osv. Om du t.ex. söker efter &quot;nytt arbete&quot; returnerar sökningen inte giltiga resultat.

Fastställd i november 2018.

### at.js {#at-js-3}

När du använder at.js version 1.6.0 sker omdirigeringar av Analytics for Target (A4T), men utan aktivitetskvalificering.

Åtgärdat med versionen av at.js 1.6.2.

### Aktiviteter, arbetsytor och API för borttagning av aktivitet

Aktiviteter i standardarbetsytan som tagits bort via API visas fortfarande i målgränssnittet. Du kan lösa det genom att ta bort alla aktiviteter på standardarbetsytan med hjälp av målgränssnittet. (TGT-31315)

Fastställd 25 oktober 2018

### Automated Personalization (AP) rapportering på erbjudandenivå

När du klickar på den riktade upplevelsen i en Automated Personalization-aktivitetsrapport (AP) för att visa rapporter på erbjudandenivå visas för närvarande tomma resultat, ett felmeddelande eller en snurrande ikon. (TNT-30695)

Fastställd 27 september 2018.

### Kodredigeraren

Om du läser in VEC på nytt i steg 1 i det guidade arbetsflödet i tre steg medan du arbetar med kodredigeraren i Firefox och Internet Explorer, återges inte fliken Ändringar korrekt. VEC-funktionen påverkas dock inte. (TGT-28730)

Detta korrigerades i version 18.9.1.

### Recommendations-aktivitet som använder en regel för attributbefordran

När du redigerar eller kopierar en Recommendations-aktivitet som använder en attributbefordringsregel visas felet&quot;Saknat fält&quot; när du klickar på Spara.

Detta korrigerades i version 17.8.1.

### Säkerhetskopiera Recommendations

Rekommendationer för säkerhetskopiering visar felaktigt Aktiverat på kort för nyligen visade objekt i målgränssnittet. (TGT-29308)

Detta korrigerades i version 18.4.1 så att &quot;Inaktiverad&quot; visas.

### Automatisk målgruppsaktiviteter och rapportmålgrupper

När en rapporterande målgrupps namn som används i en Automatiskt mål-aktivitet ändras, kan ytterligare uppdateringar från Target för den aktiviteten misslyckas med ett felmeddelande.

Problemet korrigerades i Target 18.5.1 (22 maj 2018).

### at.js {#at-js-4}

Algoritmen för extrahering av toppnivådomänen som ska användas när cookies sparas har ändrats i at.js version 0.9.6. På grund av den här ändringen kan cookies inte sparas i adresser som använder IP. För det mesta används IP-adresser i testsyfte, men som tillfälliga lösningar kan du använda DNS-poster, justera värdfilen i en lokal ruta eller använda funktionen targetGlobalSettings() at.js för att infoga ett kodfragment som stöder IP-adresser.

Problemet har åtgärdats i version 1.2 av at.js.

### Enterprise-användarbehörigheter för [!DNL Target] Premium

Som en del av migreringen av företagsbehörigheter flyttades all användarhantering för Target Premium från Adobe Target-gränssnittet till Adobe Admin Console.

Som ett resultat av migreringen finns det två möjliga problem du bör vara medveten om:

* Användare som inte är administratörer har fått ett e-postmeddelande som anger att de nu har tillgång till Adobe Target. Detta anger att migreringen har slutförts för din organisation. Själva e-postmeddelandet kan ignoreras.
* Efter migreringen har det förekommit rapporter om att tidigare inaktiverade användare återkommer i Adobe Admin Console. Detta kan vara ett problem för din organisation om användare med funktionshinder i Adobe Admin Console fortfarande fanns med i din användarlista i Target före migreringen. Vi rekommenderar att administratörer granskar listan över användare i Admin Console för att validera åtkomsten.

Problemet korrigerades den 30 augusti 2017

### Skapa aktivitet

Ett problem med version 17.6.2 kan ha påverkat aktiviteter som skapats och/eller uppdaterats mellan 22 juni 2017 och 29 juni 2017. Aktiviteter med följande påverkades:

* Alla upplevelser som ordnats om i Experience Targeting (XT) skulle ha återgått till den ursprungliga ordningen
* Alla segmentregler som är lokala för aktiviteten (inte sparade inom en målgrupp) skulle ha gått förlorade: kombinerade målgrupper, platsförbättringar och regler för framgångsmått.

Inga andra aktiviteter påverkades.

**Viktigt**: Problemet åtgärdas inte automatiskt. Du måste spara om alla aktiviteter som har påverkats för att åtgärda problemet.

Problemet korrigerades den 29 juni 2017

### Formulärbaserad Experience Composer

Följande kända fel har rapporterats när formulärbaserad Experience Composer används:

* Om du använder den formulärbaserade Experience Composer med en annan ruta än den automatiskt skapade globala mbox (target-global-mbox) och sedan väljer ett interaktionsmått som framgångsmått ökas måttet bara på sidor där mbox används i aktiviteten. Om din mbox till exempel är homepage\_mbox är måttet Pages per Visit antalet träffar på hemsidan\_mbox under det besöket. (TGT-22789)
* Ett JavaScript-undantag genereras när du tar bort en upplevelse i en XT-aktivitet (Experience Targeting) när du använder den formulärbaserade Experience Composer under steg 1 i processen. (TGT-24366)

Den första utgåvan korrigerades i Target 17.3.1-utgåvan (mars 2017).

Den andra utgåvan korrigerades i Target 17.6.1-versionen (juni 2017).

### at.js {#at-js-5}

Sedan Target 17.4.1 släpptes (27 april 2017) levereras inte erbjudandeinnehållet när du använder åtgärden Infoga bild i Visual Experience Composer (VEC) när du använder biblioteket at at.js.

En korrigering för det här problemet har gjorts i version 0.9.7 av at.js som släpptes 22 maj 2017.

### Rapportering: A/B- och Experience Targeting-aktiviteter (XT)

Mellan 27 april kl. 21.00 PST och 5 maj kl. 6.00 PST, kan A/B- och XT-aktiviteter som skapats eller redigerats med någon statistik med hjälp av konverteringsåtgärden &quot;Viewed a Page&quot; (som inte baserats på andra mätvärden) ha fått felaktigt inspelade konverteringar. Problemet är nu löst; Däremot är det inte säkert att rapporteringen av konverteringsåtgärden &quot;Visa en sida&quot; för dessa aktiviteter under den påverkade tidsperioden är korrekt och kan tyvärr inte korrigeras. Vi rekommenderar att du endast förlitar dig på data som registrerats före eller efter den period som påverkas för beslut som baseras på konverteringsåtgärderna &quot;Visa en sida&quot; för dessa aktiviteter.

Rapporteringsdata för andra mätvärden kan fortfarande användas eftersom de inte påverkades.

Åtgärdat i målsnabbkorrigering 17.4.3.

### Erbjudanden: A/B- och Experience Targeting-aktiviteter (XT)

Leveransen och förhandsgranskningen påverkades för erbjudanden i A/B- och XT-aktiviteter som har minst två upplevelser och som antingen har skapats eller redigerats med formulärbaserad Experience Composer mellan fredagen den 28 april (kl. 19.00 PT) och måndagen den 1 maj (kl. 21.15 PT). Endast erbjudanden med standardinnehåll visades.

Åtgärdat i målsnabbkorrigering 17.4.3.

### at.js {#at-js-6}

Följande åtgärder gjorde att erbjudandet inte kunde levereras när du använde Visual Experience Composer (VEC) och at.js: Flytta och ordna om.

En korrigering av problemet gjordes i version 0.9.6 av at.js.

### Rapporter

Möjligheten att visa flera mätvärden i en rapport, som ingår i Target 17.3.1 (30 mars 2017), har tagits bort på grund av oväntat beteende. Den här funktionen kommer att vara tillgänglig igen i en kommande version.

Möjligheten att visa flera mätvärden i en rapport ingick i Target 17.4.1 (27 april 2017).

### Erbjudanden

Bilder som tas bort från bilderbjudandebiblioteket ( Erbjudanden \> Bilderbjudanden ) visas fortfarande i användargränssnittet. I en kommande version kommer dessa borttagna bilder inte längre att visas. Under tiden visas borttagna bilder i användargränssnittet, men har statusen Borttaget. (TGT-23793)

Fixed in the Target 17.4.1 release (27 april 2017).

### Omdirigeringserbjudanden

För nyligen visade villkor leder entitetsbaserade dynamiska regler inte till någon rekommendation om parametern entity.id inte skickas i mbox-begäran. (RECS-6241)

Problemet har åtgärdats efter Recommendations-utgåvan (22 mars 2018). Efter Recommendations-versionen hoppar Target över entitetsbaserade dynamiska regler om entity.id inte skickas i mbox-begäran.

### at.js {#at-js-7}

När användare försöker hämta at.js från sidan med information om implementeringar efter att ha uppdaterat at.js-inställningarna hämtas den i stället för at.js. (TGT-23069)

Fixed in the Target 17.3.1 release (30 mars 2017).

### Globala undantagsregler

Det tar 10-20 minuter att sprida globala undantagsregler till Premium Recommendations. (RECS-5270)

Fixed in the Recommendations 17.2.2.0 release (6 mars 2017).

### Analyser för Adobe Target-rapportering (A4T)

Rapporterna uppdateras inte när rapportmåttet ändras. Problemet påverkar bara användargränssnittet. Det påverkar inte datainsamling eller leverans av rapporter. (TGT-22970)

Fixed in the Target 17.2.2.0 release (24 februari 2017).

### CSV-rapporter

Hämtade rapporter följer inte inställningen Extreme Orders (Extreme Orders). (TGT-21871)

Åtgärdat i version 17.2.1.0 av Target.
