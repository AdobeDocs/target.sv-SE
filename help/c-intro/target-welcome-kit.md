---
keywords: welcome kit;target welcome kit;intro;introduction;getting started
description: Välkomstpaket från Adobe Target.
title: Adobe Target welcome kit
feature: intro
translation-type: tm+mt
source-git-commit: 1bcf2263c2f507b9775a0d009f05baf9a83b1891
workflow-type: tm+mt
source-wordcount: '6330'
ht-degree: 0%

---


# Adobe Target welcome kit

Välkommen till Adobe Target. Detta välkomstpaket från Adobe Target presenterar

## Kapitel 1: Introduktion

Om ni är som de flesta företag idag har ni moderniserat era era digitala marknadsföringskanaler. Nu letar ni efter sätt att särskilja ert varumärke - att bryta er loss från paketet och på så sätt öka intäkterna, konverteringsgraden och andra viktiga affärsvärden. Ett sätt att göra detta är att optimera och personalisera de digitala upplevelser ni levererar till era kunder genom att använda det ni vet om dem för att få ut så mycket som möjligt av deras interaktioner på er webbplats, mobilsajt, mobilapp eller någon annan kontaktyta. Ni kanske till och med vill utöka denna optimering och personalisering utöver era traditionella digitala kontaktytor till kontaktytor som kioskdatorer, sakernas internet (IoT), callcenters interaktioner och röstassistenter som Alexa. Varumärken som har använt [!DNL Target] för att testa och personalisera sina digitala upplevelser har uppnått otroliga resultat.

Exempel:

* En stor bank testade och effektiviserade ett låneansökningsformulär. Programmet börjar tredubblas och programmets slutförande ökar med mer än 50 procent.
* Ett stort B2B-teknikföretag som personaliserade produktsidor med material som guider och rapporter. Resursklicken ökade med mer än 25 procent.
* Ett stort hotellföretag personaliserade sitt mobilappsinnehåll. Konverteringsgraden fördubblades jämfört med mobilsajten, och appen körde över 1,5 miljarder dollar i bokningar.

För att kunna interagera med kunderna på det här sättet krävs en lösning som kan användas på praktiskt taget alla kontaktytor och som använder nästan alla datakällor för att förstå dem. [!DNL Adobe Target]är en del av [!DNL Adobe Experience Cloud]den lösningen. [!DNL Target] ger er de optimerings- och personaliseringsfunktioner ni behöver för att ge era kunder de ytterst relevanta och vältajmade upplevelser som ger större intäkter och högre konverteringsgrad.

Om du granskar detta välkomstpaket har du redan beslutat att bygga ditt optimerings- och personaliseringsprogram på [!DNL Adobe Target]. Vi är glada att du gjorde det.

Nu vill vi se till att du börjar använda det på rätt sätt, direkt.

Vi har skapat ett välkomstpaket med viktig information, verktyg och resurser som hjälper dig att förbereda dig för och starta din första [!DNL Target] aktivitet. På lång sikt utgör innehållet också grunden för ett framgångsrikt optimerings- och personaliseringsprogram.

## Kapitel 2: Adobe Target i korthet

Innan du börjar använda [!DNL Adobe Target]kan det vara bra att få en översikt över lösningen på hög nivå. I det här kapitlet får du veta vilka nyckelfunktioner lösningen har, vilka kontaktytor du kan använda den på, implementeringsalternativ, viktiga funktioner och arbetsflöden i användargränssnittet, styrningsfunktioner och dess roll i det övergripande [!DNL Adobe Experience Cloud]. Om inget annat anges som [!DNL Adobe Target Premium] funktioner är de objekt som beskrivs i det här kapitlet tillgängliga med både [!DNL Adobe Target Premium] och [!DNL Adobe Target Standard]. Mer information finns i [Introduktion till Mål](/help/c-intro/intro.md).

### Kapacitet och verksamhet

Testning och personalisering är de två vanligaste funktionerna som [!DNL Target] finns och som du kan använda när du skapar en&quot;aktivitet&quot; i [!DNL Target]. termen&quot;testning&quot; används omväxlande med&quot;optimering&quot; och&quot;personalisering&quot; som används omväxlande med&quot;målinriktning&quot;.

I en testaktivitet jämför du en variant av en digital upplevelse med en eller flera andra varianter för att upptäcka att en sådan som får de flesta besökare att vidta önskad åtgärd. [!DNL Target] erbjuder följande testfunktioner: A/B-testning, multivariata tester (MVT) och automatisk fördelning.

Med en personaliseringsaktivitet kan ni leverera en digital upplevelse som är skräddarsydd för en viss grupp besökare eller för varje enskild besökare. [!DNL Target] erbjuder följande personaliseringsfunktioner: Upplev Target, Auto-Target, Automated Personalization och Recommendations.

Mer information om när och hur du använder varje funktion finns i [Verksamhetstyper](/help/c-activities/target-activities-guide.md)för mål.

| Typ av aktivitet | Detaljer |
| --- | --- |
| Experience Targeting (XT) | Leverera innehåll till en viss målgrupp baserat på en uppsättning användardefinierade regler och kriterier. **[!UICONTROL Experience Targeting]** är värdefullt för att rikta en specifik upplevelse eller innehåll till en viss målgrupp när ni förstår att en målgrupp är värdefull och har en bra uppfattning om vilken upplevelse som får genklang med dem. [Läs mer](/help/c-activities/t-experience-target/experience-target.md). |
| A/B-testning | Jämför två eller flera varianter av era upplevelser eller erbjudanden på er webbplats eller andra kontaktytor för digitala kunder för att se vilken variation som förbättrar de viktigaste affärsåtgärderna under en förspecificerad testperiod. A/B-tester är väl lämpade för stora förändringar, som nya webbsideslayouter, olika strategier för webbplatsnavigering eller drastiskt olika behandlingar av enskilda element i en digital upplevelse som kopia, bilder och knappar för att anropa åtgärder. [Läs mer](/help/c-activities/t-test-ab/test-ab.md). |
| Multivariate Testing (MVT) | Jämför alla möjliga kombinationer av olika element på sidan eller i den digitala upplevelsen, till exempel tre olika bakgrundsbilder, två varianter av text och två olika knappfärger. MVT avgör vilken kombination som fungerar bäst för en viss målgrupp och vilka element som påverkar resultatet mest. [Läs mer](/help/c-activities/c-multivariate-testing/multivariate-testing.md). |
| Automatisk allokering | Identifiera den bästa upplevelsen av två eller fler upplevelser och omfördela automatiskt mer trafik till vinnaren för att öka konverteringsgraden medan testet fortsätter att köras och lära sig mer. Använder artificiell intelligens från [!DNL Adobe Sensei]. [Läs mer](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| Automatiskt mål<br>(Premium) | Utnyttja Adobe Sensei AI i [!DNL Target] för att fastställa och leverera den bästa upplevelsen av flera till varje besökare baserat på hans eller hennes individuella kundprofil och beteendet hos tidigare besökare med liknande profiler. Automatisk målgruppsanpassning möjliggör personalisering i stor skala. |
| Automated Personalization<br>(Premium) | Använd avancerade maskininlärningsalgoritmer och automatisering som bygger på [!DNL Adobe Sensei] att granska olika kombinationer av bilder, text och andra element i ett erbjudande och leverera den bästa kombinationen till varje besökare baserat på vilka affärsmål som bäst uppnås, till exempel ökad konvertering eller intäkt per besökare. [Läs mer](/help/c-activities/t-automated-personalization/automated-personalization.md). |
| Recommendations<br>(Premium) | Använd Adobe Sensei AI för att automatiskt föreslå produkter eller innehåll som kan intressera dina kunder baserat på deras tidigare och andra kunders aktivitet. [Läs mer](/help/c-recommendations/recommendations.md). |

### Kanaler

Du kan använda [!DNL Target] för att testa och personalisera digitala upplevelser nästan var som helst - traditionella digitala kontaktytor som din webbplats, mobilsajt och mobilapp, men också på kontaktytor som kioskdatorer, e-post, IoT-enheter, spelkonsoler och till och med röstassistenter som Alexa och Cortana. Många företag börjar använda [!DNL Target] på sin webbplats. Men den senaste forskningen tyder på att fler människor besöker varumärken från sina mobila enheter. Det är nu viktigt att optimera mobilkanalerna. Det bästa är att ni kopplar samman besökarens upplevelser över alla era kontaktytor för att leverera en sömlös, enhetlig upplevelse.

| Kanal | Detaljer |
| --- | --- |
| Webbplats | [!DNL Target] kan användas för att köra A/B-testning, Multivariate Testing, Experience Targeting, Auto-Allocate, Auto-Target, Automated Personalization och Recommendations på sidor av era flersidiga, SPA-baserade (Single page application) och mobilwebbplatser för att förbättra besökarens och kundens engagemang, öka konverteringarna och öka intäkterna. |
| Mobil webb | [!DNL Target] kan användas för att köra alla de aktivitetstyper som du kör på din webbplats på dina mobilsidor för att på liknande sätt förbättra besökares och kunders engagemang, öka konverteringarna och öka intäkterna. |
| Mobilapp | [!DNL Target] kan användas för att testa och personalisera mobilappsupplevelser baserat på användarbeteende och mobilsammanhang. [!DNL Target] Med kan ni leverera interaktioner som engagerar och konverterar genom iterativ testning samt Experience Targeting och AI-driven personalisering. Om du vill använda [!DNL Target] i din mobilapp måste du använda Adobe Mobile Services SDK. |
| IoT/Everywhere | [!DNL Target] erbjuder en implementering på serversidan så att du kan använda samma funktioner för testning och personalisering i aktiviteter som du använder på din traditionella webbplats, mobilwebbplats och mobilappar i e-postmeddelanden och på kontaktytor som saknar webbläsare eller som inte använder JavaScript-kod. Du kan till exempel testa och anpassa kioskdatorer, digitalboxar, spelkonsoler, röstassistenter och andra icke-traditionella kontaktytor. |

### Implementeringar

Många av er kanske vill använda [!DNL Target] för att testa och personalisera på era många olika digitala kontaktytor, inklusive traditionella webb- och mobilkontaktytor, men även kontaktytor som saknar webbläsare eller som inte använder JavaScript-kod. I vissa fall kräver den interna eller externa principen att du har ytterligare nivåer av kontroll och säkerhet. Du kan också ha processer som måste köras på en serverdel av prestandaskäl. För att klara den här typen av användningsområden ger vi dig möjlighet att implementera [!DNL Target] på olika sätt: klientsidan, serversidan eller en kombination av båda.

| Implementeringstyp | Detaljer |
| --- | --- |
| Klientsidan | Med den här implementeringen av [!DNL Target]kan [!DNL Target] leverera upplevelser som är kopplade till en aktivitet direkt till klientwebbläsaren. Webbläsaren avgör vilken upplevelse som ska visas och visar den. Med klientsidan kan du använda en WYSIWYG-redigerare, **[!UICONTROL Visual Experience Composer]** (VEC) eller ett icke-visuellt gränssnitt, **[!UICONTROL Form-based Experience Composer]** för att skapa test- och personaliseringsupplevelser. [Läs mer](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). |
| Serversidan | I den här typen av [!DNL Target] implementering gör en klientenhet en begäran om en upplevelse via servern, servern skickar begäran till [!DNL Target], [!DNL Target] skickar tillbaka svaret till servern och servern bestämmer vilken upplevelse som ska levereras till klientenheten för att den ska kunna återges. upplevelsen inte behöver visas i en webbläsare, den kan visas i ett e-postmeddelande eller i en kioskdator, via en röstassistent eller via någon annan icke-visuell upplevelse eller icke-webbläsarbaserad enhet. Eftersom servern sitter mellan klienten och [!DNL Target]är den här typen av implementering också idealisk om du behöver större kontroll och säkerhet eller har komplexa serverprocesser som du vill köra på servern. [Läs mer](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Hybrid-implementering | I den här implementeringen väljer du den implementeringsmetod som fungerar bäst för ett visst användningsfall. Du kan till exempel använda en implementering på klienten för att A/B-testa ett erbjudande i en hjältebanderoll på startsidan, men även använda en implementering på serversidan för att avgöra vilka interna sökresultat som ska visas i en klientwebbläsare, upplevelsen som ska visas på en smart bildinstrumentpanel eller röstsvaret som ska visas från en röstassistent. |

### Aktivitetselement

I [!DNL Target]kan ni skapa en personaliseringsaktivitet, en optimeringsaktivitet eller en aktivitet som optimerar er personaliseringsstrategi. Varje aktivitet har nyckelelement - de upplevelser eller erbjudanden ni testar eller personaliserar, de målgrupper eller individer ni levererar en upplevelse till, de mätvärden som ni mäter aktivitetens effekt med och de rapporter som visuellt visar den effekten.

| Elementtyp | Detaljer |
| --- | --- |
| Erfarenheter | Ett erbjudande, en bild, text, knapp, video, en kombination av dessa olika element på en sida, en hel webbsida eller en uppsättning sidor som kanske utgör en inköpstratt eller någon annan logisk sekvens av sidor. Det kan också vara svaret från en röstassistent, ett kundskript eller till och med en personlig smak från en dryckesmaskin. Ni testar eller personaliserar upplevelser i [!DNL Target] aktiviteter. [Läs mer](/help/c-experiences/experiences.md). |
| Erbjudanden | Ett block med innehåll som kan innehålla bilder, text, HTML, länkar, video, en knapp för att ringa in åtgärder, ett röstassistentsvar eller någon annan typ av innehåll. Erbjudandet kan omfatta rabatter, fri frakt och så vidare. Ett erbjudande kan visas på en webbsida, men det kan också visas på alla kundkontaktytor, som en röstassistent eller spelkonsol. När du testar ett erbjudande mäter du hur väl det lyckades jämfört med andra erbjudanden eller inget erbjudande. [Läs mer](/help/c-experiences/c-manage-content/manage-content.md). |
| Målgrupper | En grupp personer med samma egenskaper, till exempel en ny besökare, en återkommande besökare eller återkommande besökare från mellanvästern. Med funktionen Målgrupp kan ni rikta olika innehåll och upplevelser till specifika målgrupper för att optimera er digitala marknadsföring genom att visa rätt budskap till rätt personer vid rätt tidpunkt. Om en besökare identifieras som en del av en målpublik, avgör [!DNL Target] vilken upplevelse som ska visas, baserat på kriterier som definieras när aktiviteter skapas. [Läs mer](/help/c-target/target.md). |
| Framgångsmått | Viktiga affärsåtgärder som gör det möjligt att avgöra hur framgångsrik en viss upplevelse eller ett visst erbjudande är i en [!DNL Target] aktivitet. Du kan till exempel bestämma om ett nytt erbjudande ökar intäkterna per besökare eller lägger till en artikel i en kundvagn. Framgångsstatistik kan vara användbar för att upptäcka problem med registrering, beställning eller inköpskanaler, men också helt enkelt med besökarens eller kundens engagemang. [Läs mer](/help/c-activities/r-success-metrics/success-metrics.md). |
| Rapporter | Information om förloppet och resultaten av dina aktiviteter som hjälper dig att fatta beslut baserat på dina data. Rapportdata kan hjälpa er att avgöra när ni ska avsluta ett test, visa er vilken upplevelse av erbjudandet som är vinnaren och ge er insikter eller inlärningar ni behöver för att avgöra nästa åtgärd. [Läs mer](/help/c-reports/reports.md). |

### Verktyg för att skapa aktiviteter

[!DNL Target] ger dig tre sätt att konfigurera dina testnings- och personaliseringsaktiviteter, [!UICONTROL Visual Experience Composer] (VEC), [!UICONTROL Form-based Experience Composer]och [!UICONTROL Single Page Application (SPA) Visual Experience Composer]. Båda vägleder dig genom processen för aktivitetskonfiguration i tre steg - definiera upplevelser, välja ut eller definiera målgrupper och välja primära och sekundära framgångsmått som du kan använda för att mäta aktivitetens resultat.

| Verktyg | Detaljer |
| --- | --- |
| [!UICONTROL Visual Experience Composer] (VEC) | Ett WYSIWYG-användargränssnitt som gör det enkelt att skapa och testa personaliserade upplevelser och erbjudanden i webbplatskontexten. Du kan skapa upplevelser och erbjudanden för aktiviteter genom att dra och släppa, byta och ändra layouten och innehållet på en webbsida (eller ett erbjudande) eller en mobilwebbsida. [!DNL Target] [Läs mer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md). |
| [!UICONTROL Form-based Experience Composer] | En icke-visuell upplevelse och ett gränssnitt som gör att du kan skapa upplevelser som kan användas i A/B-tester, Experience Targeting, Automated Personalization och Recommendations när Visual Experience Composer inte är tillgängligt eller praktiskt att använda. Du kan till exempel använda den formulärbaserade dispositionen för att skapa upplevelser och erbjudanden för e-post, kioskdatorer och röstassistenter. [Läs mer](/help/c-experiences/form-experience-composer.md). |
| [!UICONTROL Single Page Application (SPA) Visual Experience Composer] | Med VEC for SPA kan marknadsförarna skapa tester och personalisera innehåll på SPA på ett sätt som gör det själv utan kontinuerliga utvecklingsberoenden. VEC kan användas för att skapa A/B Test- och Experience Targeting-aktiviteter (XT) på populära ramverk som React och Angular. [Läs mer](/help/c-experiences/spa-visual-experience-composer.md). |

### Styrning och kontroll

För att ge rätt personer rätt roller och tillhörande åtkomstnivåer och behörigheter till [!DNL Target]har vi en administrationskonsol. För [!UICONTROL Target Premium] användarna erbjuder vi mer detaljerad styrning och kontroll [!UICONTROL Enterprise Permissions].

| Verktyg | Detaljer |
| --- | --- |
| [!UICONTROL Adobe Admin Console for Enterprise] | Lägg till användare i Adobe Target och tilldela behörigheter från Adobe Admin Console. [Läs mer](/help/administrating-target/c-user-management/c-user-management/user-management.md). |
| [!UICONTROL Enterprise Permission]s<br>(Premium) | Ett formellt sätt att administrera åtkomst för användare i hela företaget [!DNL Target]. Lägg till användare [!DNL Target], tilldela behörigheter baserat på deras roller och skapa arbetsytor för team baserat på olika avdelningar, globala platser, kanaler och andra logiska grupper. Du kan tilldela användare rollerna observatör, redigerare, utgivare och godkännare. [Läs mer](/help/administrating-target/c-user-management/property-channel/property-channel.md). |

### Integreringar

[!DNL Target] kan integreras med många första-, andra- och tredjepartssystem. Dessa integreringar kan vara värdefulla för att ge er tillgång till besöks- och kunddata som är tillgängliga från dessa system och som kan användas för att skapa målgrupper för testning och personalisering. Som en del av [!DNL Adobe Experience Cloud]det är [!DNL Target] nära integrerat med [!DNL Experience Cloud] lösningar och dess bastjänster.

| Integrering | Detaljer |
| --- | --- |
| Adobe Experience Cloud | [!DNL Target] har inbyggda funktioner med andra [!DNL Adobe Experience Cloud] lösningar för att personalisera upplevelser i stor skala. Utnyttja möjligheterna [!DNL Target] tillsammans med [Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md), [Experience Cloud Publiker](/help/c-integrating-target-with-mac/mmp.md), [Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md), [Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) (AAM) och [](/help/c-experiences/c-manage-content/aem-experience-fragments.md) Adobe Experience Manager (AEM). |
| Mål-API:er (Premium) | [!UICONTROL Target] erbjuder mer än 40 API:er som du kan använda för att integrera Adobe Target med första-, andra- och tredjepartssystem. [Läs mer](/help/api/api-overview.md). |

### Kom ihåg

Tänk på följande innan vi går vidare till nästa kapitel: &quot;Utveckla dina idéer om testning och personalisering.&quot;

#### Bästa tillvägagångssätt för optimering

* **Bra strategi**: Vad är vår målsättning och hypotes? Är de justerade? Vi vill till exempel öka inskickandet av låneansökningar, så vi rekommenderar att en minskning av antalet fält i ansökningsformuläret gör det.
* **Disciplinerade metoder** Börjar vi testa på rätt ställen? Ni behöver till exempel platser som har tillräckligt med trafik och som påverkar de mätvärden som är viktiga för företaget.
* **Korrekt konfiguration** Är vår aktivitet inställd för att uppnå vårt mål? Om vi till exempel försöker öka inskickade låneansökningar bör vi rikta in oss på personer som är intresserade av lån och mäta klick på knappen&quot;Skicka&quot;.
* **Detaljerad analys**: Kördes testaktiviteten tills den var klar? Vad säger resultaten? Kör aktiviteten tills den uppnår mellan 95 % och 99 % statistisk säkerhet. Dokumentera varför du tror att den vinnande upplevelsen vinner och använd inlärningen någon annanstans.
* **Interaktiv testning**: Bygger vi på inlärningen av tidigare aktiviteter? Om du hittar en vinnande taktik kan du försöka förbättra den eller göra ändringar som fungerar med den för att ytterligare förbättra dina framgångsmått.

#### Yttranden kan påverka dina resultat negativt

* Yttranden som kan påverka effekten negativt. Highest Paid Person’s Opinion (HIPPO), attityder, biases. VD:n vill t.ex. minska storleken på sökrutan för att få mer plats på varje sida. Vi bör testa att se till att det inte minskar antalet sökningar.
* Agerar du på åsikter? Jag tycker inte om hur testet ser ut. Kunden kommer inte alls att gilla den här upplevelsen. Intuition är användbar, men A/B-tester har gång på gång visat att det inte alltid fungerar.
* Eller har du en optimeringsmetod? Jag är glad att se vilken upplevelse som vinner. Har vi tillräckligt med alternativ för att testa?

#### Antaganden kan också påverka resultatet negativt

* Antaganden som kan påverka effektiviteten negativt. Herd mentality (det är så våra konkurrenter gör det). Alla våra konkurrenter använder till exempel hjältebanners med roterande bilder, så vi bör också göra det.
* Anta att vi vet varför något fungerar eller inte. Anta att vi inte behöver testa någonting. Vi listar t.ex. alltid hotellrum i ordningen högst till lägst pris som standard.
* Agerar du utifrån antaganden? Vi behöver inte testa det, vi har kollat analyser. (Ja, men det kan finnas mer i berättelsen än vad analyserna visar.)
* Eller har du en optimeringsmetod? Vi testar allt.

## Kapitel 3: Utveckla dina idéer om testning och personalisering

För den första aktiviteten kan du testa något superenkelt som att ändra färg eller kopiera på en åtgärdsknapp. Bara för att bli blöt. På lång sikt kommer ni dock att vilja skapa en formell, upprepningsbar process för att komma fram till idéer för testning och personalisering som hjälper er att utveckla ert optimerings- och personaliseringsprogram. I följande sex steg beskrivs en beprövad process för att göra just det, tillsammans med information om vad du ska göra i varje steg.

![Interaktivt genomförande av strategidiagram för optimering och personalisering](/help/c-intro/assets/six-steps.png)

### Steg 1: Strategize

Identifiera möjligheter för aktiviteter som är anpassade till affärsmålen.

Gör detta genom att:

* Brainstorming potential [!DNL Target] actions based on site performance data, Competitor analysis, and previous test results.
* Utveckla idéer för aktiviteter för granskning, feedback och godkännande.

Du kan till exempel leta efter en sida på webbplatsen med hög avhoppsfrekvens, fundera över vad som kan orsaka problemet och brainstorma sätt att minska avhoppsfrekvensen.

### Steg 2: Prioritera

Rankning och schemaläggning av aktiviteter baserade på anpassning av verksamheten, ansträngningsnivå och potentiella effekter.

Gör detta genom att:

* Rankar potentiella aktiviteter baserat på flera kriterier för att öka chanserna till framgång och anpassa sig till affärsmålen.
* Utforska tidigare testresultat för att fastställa potentialen för uppföljningstester.
* Granska och dela den prioriterade testplanen med interna intressenter.

Du kan till exempel prioritera en aktivitet som är enkel att implementera och som kan ge bra resultat baserat på tidigare liknande aktiviteter, jämfört med en aktivitet som kan ge bra resultat, men som kräver stora insatser och tekniska resurser eller som kan ge vika från intressenter.

### Steg 3: Design

Utforma och utveckla en verksamhetsplan med detaljerad information och godkända visuella upplevelser.

Gör detta genom att:

* Slutför aktivitetspostkriterier och mått som krävs för att fastställa aktivitetens prestanda.
* Fylla i och godkänna färdiga designer för aktivitetsupplevelser.
* Dokumentationskrav för [!DNL Target] aktiviteten, inklusive kriterier för testinträde, rapporteringsmått och upplevelseförändringar.

Använd aktivitetsplaneraren, som finns senare i välkomstpaketet, för att dokumentera aktivitetens detaljer, inklusive de mätvärden du ska använda för att mäta aktivitetsprestanda, till exempel klick på en åtgärdsknapp, videostarter eller genererade intäkter. Ta med skärmbilder eller bilder av de upplevelsedesigner du tänker testa eller personalisera.

### Steg 4: Bygg och kör

Bygg och kör aktiviteten inifrån, [!DNL Target]utveckla kod om det behövs, genomför QA-tester och starta aktiviteten.

Gör detta genom att:

* Bygga en aktivitet, tillämpa en målgrupp, utveckla kod om det behövs och tillämpa mätvärden på din aktivitet.
* Säkra signering från alla intressenter som behövs.
* Starta aktiviteten och granska mätvärden en timme, vid 24 timmar och periodvis under aktivitetens varaktighet.

Om du till exempel vill rikta in dig på nya besökare med ett ljuslådeerbjudande som ger 10 % rabatt på deras första beställning, får dina kreatörer att ta fram ljuslådedesign och -text, få en signering från intressenter på designen, låta utvecklarna skriva koden för den, köra QA i en testmiljö och sedan starta aktiviteten. Därefter övervakar du aktiviteten för att vara säker på att den inte orsakar någon större negativ påverkan.

### Steg 5: Analysera

Analysera aktivitetsprestanda och sammanfatta aktivitetsresultat, insikter och rekommendationer.

Gör detta genom att:

* Utnyttja dataanalys och bästa metoder för att förstå aktivitetsresultaten.
* Analysera målgruppsprestanda för att hitta värdefulla besökarsegment.
* Dokumentera insikter, resultat och rekommendationer.

Du kan till exempel upptäcka att de återkommande besökarna föredrar en annan upplevelse än de nya besökarna.

### Steg 6: Agera och iterera

Använd vinnande upplevelser för att få affärsvärde och få nya insikter.

Gör detta genom att:

* kommunicera aktivitetsinsikter, resultat och rekommendationer till intressenter,
* Godkänna intressenter som verkställer aktivitetsrekommendationer.
* Definiera och genomföra planen för att implementera den vinnande upplevelsen.

Om ljuslådeaktiviteten till exempel lyckades öka förstagångsköp av besökare kanske du vill fortsätta med den här aktiviteten. Var noga med att förmedla det värde som testet gav upphov till till intressenter och chefer med den mall för sammanfattning av ledningen som ingår i välkomstpaketet. Och fundera över hur ni kan återanvända detta lärande; kanske ni kan inrikta er på förstagångsköparna med ett andra erbjudande för att få ut mer av varje kund.

## Kapitel 4: Tips för att använda Target

Baserat på vårt arbete med många [!DNL Target] användare har vi observerat hur ni kan få ut mer av er [!DNL Target] lösning. Vi har sammanställt alla de tips vi har tagit med i det här kapitlet. Även om du inte är redo att använda alla dessa idéer med en gång, så håll fast vid den här listan. Ju mer du får en lösning och ju mer programmet mognar desto mer får du se hur dessa tips kan hjälpa dig att uppnå mer med [!DNL Target].

### Tips 1: Öka personaliseringen genom att utöka besökarprofilen med ytterligare data.

Ni kan personalisera upplevelser med [!DNL Target] data direkt vid leverans. Men personalisera djupare genom att lägga in egna data i mixen. Ni kan utöka er profil med historiska data från [!DNL Adobe Analytics] och realtidsdata utifrån [!DNL Adobe Audience Manager]. Du kan också använda kundattribut, en funktion i persontjänsten i [!DNL Adobe Experience Cloud], för att enkelt hämta CRM-data, data från andra leverantörer och data som köpts från tredje part till [!DNL Target].

Du kan till exempel koppla inköpsdata från ditt butikssystem till en besökarprofil. Det gör du genom att skapa en CSV-fil med upp till 200 offlinevariabler och antingen överföra den direkt till [!DNL Adobe Experience Cloud] via en filöverföring, eller använda FTP för att lagra och schemalägga filen så att den uppdateras regelbundet. När era kundattribut finns tillgängliga kan ni mappa dem till [!DNL Adobe Experience Cloud]lösningar som [!DNL Experience Cloud] och [!DNL Adobe Analytics] [!DNL Target] var de finns tillgängliga för analys, testning och personalisering.

I [Anpassade attribut](https://docs.adobe.com/content/help/en/target/using/audiences/visitor-profiles/working-with-customer-attributes.html) finns stegvisa instruktioner.

**Bra att veta**: Eftersom [!DNL Target] är en öppen och agnostisk plattform som fungerar bra med olika tekniker kan du lägga till CRM- eller köpta data på många olika sätt. Det innebär att du kan välja en metod som fungerar bäst för din organisation.

Mer information finns i [Metoder för att hämta data till Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md) .

### Tips 2: Personalisera djupare genom att blanda målgrupper med andra Adobe Experience Cloud-målgrupper.

Att blanda målgrupper som lever i olika [!DNL Adobe Experience Cloud] lösningar kan ge er en mycket bredare förståelse för era kunder, liksom möjligheten att personalisera mer ingående. Till exempel, även om [!DNL Target] data om målgrupper i realtid finns med, [!DNL Adobe Analytics] innehåller historiska målgruppsdata. Genom att kombinera de två kan ni identifiera när en kunds beteende är konsekvent och när det kan finnas en möjlighet att agera på ett nytt beteende. Klicka bara på listrutan bredvid&quot;Alla besökare&quot; när du skapar en aktivitet. Markera sedan rutorna för upp till tjugo målgrupper, klicka på Kombinera flera målgrupper och klicka på Spara.

Se [Kombinera flera målgrupper](/help/c-target/combining-multiple-audiences.md) för stegvisa instruktioner.

**Bra att veta**: [!DNL Adobe Audience Manager] målgrupper är tillgängliga i [!DNL Target] automatiskt. Men för målgruppsdelning krävs [!DNL Adobe Analytics] lite manuell konfiguration. Markera bara rutan&quot;Make this an Experience Cloud)&quot; under målgruppsprocessen i [!DNL Analytics]. Klicka sedan på Importera målgrupper i Experience Cloud [!DNL Target].

### Tips 3: Exportera data från Target för användning med verktyg från tredje part.

Med svarstoken kan administratörer enkelt hämta data från [!DNL Target] och in i tredjepartsverktyg. Detta kan vara praktiskt när du vill lägga till data till data som samlats in med ett undersökningsverktyg. Om en undersökning till exempel visar ett urval av en population som fick upplevelsen &quot;9&quot; och en annan fick upplevelsen &quot;4&quot;, kan du använda dina data för att se vem som fick upplevelsen A och vem som såg upplevelsen B. Du kan också använda svarstoken för att exportera [!DNL Target] data till din interna data warehouse. Klicka bara på&quot;Administration&quot; och växla sedan till den aktuella positionen bredvid den önskade svarstoken. Skapa sedan en aktivitet. Data kan sedan överföras till tredjepartsleverantören. Du kan verifiera att [!DNL Target] exporterar data med felsökningsverktygen.

Se [Svarstoken](/help/administrating-target/response-tokens.md) för steg-för-steg-instruktioner.

**Användbar ledtråd**: Innan en administratör kan aktivera en svarstoken som är associerad med en tredje part måste en utvecklare skapa ett partnerskap med det tredjepartsföretaget.

Se [Svarstoken](/help/administrating-target/response-tokens.md) för steg-för-steg-instruktioner.

**Gör detta först**: Kontrollera att du använder at.js version 1.1 eller senare. Om du använder en tidigare version kommer du att se svarstoken, men at.js kommer inte att kunna använda den.

### Tips 4: Bygg målgrupper utifrån dessa nyckelvariabler för att öka värdet av er aktivitet.

När du skapar målgrupper för målinriktning eller testning av kampanjer och erbjudanden ska du först ta hänsyn till följande variabler:

* Beteende. Mönster för webbplatsbesök och inköpsmönster
* Referent. Referera till webbplatser och kampanjer
* Tidsbestämd. Dagstid, veckodagar och säsongsrelaterade faktorer
* Offline. Besök och köp i fysiska butiker
* Miljö. Ursprungsland, operativsystem, webbläsartyp

### Tips 5: Ge användarna den åtkomstnivå de behöver för att kunna utföra sitt jobb.

Gör det enkelt att arbeta med organisationens data samtidigt som de är säkra. [!DNL Target Premium] ger administratörer möjlighet att styra åtkomstnivån för olika interna och externa team.

Mer information finns i [Enterprise-användarbehörigheter](/help/administrating-target/c-user-management/property-channel/property-channel.md) .

**Användbar ledtråd**: När du lägger till användare och namnet på en teammedlem inte har lagts till i organisationen tidigare, vilket kan vara fallet med en tredjepartsanställd, utlöses en e-postinbjudan om att gå med i teamets arbetsyta om du anger deras e-postadress och lösenord.

Använder du målstandard? Du kan fortfarande [tilldela tre åtkomstnivåer](/help/administrating-target/c-user-management/c-user-management/user-management.md) till dina användare med skrivskyddade roller, redigeringsroller och godkännarroller!

### Tips 6: Upptäck hur ett erbjudande fungerar under en kundresa genom att testa det på alla sidor i resan.

Se hur ett erbjudande, till exempel fri frakt, fungerar under en kundresa som äger rum på flera sidor på er webbplats.

Se [Flersidig aktivitet](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) för stegvisa instruktioner.

**Användbar ledtråd**: Om du ändrar URL:en efter att du har angett ett sidintervall återställs upplevelsen. Det innebär att de angivna variationerna inte visas längre. Kom ihåg att definiera om upplevelsen om du behöver ändra URL-adressen.

### Tips 7: Testa ett erbjudande med olika målgrupper för att se om målgrupperna har olika preferenser.

Med Experience Versions kan ni göra ett test med variationer för så många målgrupper ni vill. Du kan t.ex. skapa en banner-annons som erbjuder fri frakt - med bild- och valutavariationer för kunder i USA, Storbritannien och USA - utan att behöva göra tester för tre olika målgrupper.

I en [rapport om A/B Test](/help/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) and [Experience versions i Adobe Target](https://helpx.adobe.com/target/how-to/experience-versions.html?playlist=/ccx/v1/collection/product/target/seg-%20ment/business-practitioners/explevel/beginner-adls/applaunch/how-to-2/collection.ccx.js?ref=helpx.adobe.com) finns stegvisa instruktioner.

### Tips 8: Spara tid genom att replikera aktivitetsupplevelser på liknande sidor.

Skapa en variant på en webbsida, till exempel en ny knappfärg, och tillämpa den automatiskt på alla sidor som delar samma mall. Du kan ange sidor eller använda variationerna på alla liknande sidor på webbplatsen.

Se [Inkludera samma upplevelse på liknande sidor](/help/c-experiences/c-visual-experience-composer/temtest.md) för steg-för-steg-instruktioner.

### Tips 9: Minska störande detaljer i målgruppsbiblioteket genom att skapa engångspubliker.

Om ni riktar in er på ett segment som ni vet inte riktar in er på igen - till exempel kunder som drabbats av ett oväntat väderläge - kan ni få jobbet gjort utan att ni behöver lära er mer om målgruppsbiblioteket. Det gör det enklare att hitta målgrupper som du använder om och om igen.

Se [Skapa en målgrupp](/help/c-target/creating-activity-only-audience.md) som endast kan användas för aktivitet för stegvisa instruktioner.

**Mycket önskad kapacitet**: Våra kunder bad oss att göra det möjligt att förhindra att enstaka målgrupper sparas automatiskt i målgruppsbiblioteket. Nu behöver de inte längre ta bort målgrupper manuellt för att hålla sina bibliotek organiserade.

### Tips 10: Kör enkla tester snabbare genom att inte använda standardprocessen för kvalitetssäkring.

Det finns inget värre än att ha en aktivitet redo att gå och sedan vänta veckor på att den ska slutföra den vanliga kvalitetssäkringsprocessen. Du kan använda QA-funktioner i de flesta fall genom att bara skicka runt några QA-länkar till kollegor och testa dem i olika webbläsare. Du kommer troligen att vilja göra fler kvalitetstester för att få saker som förändrar webbplatsens funktion dramatiskt, men i verkligheten bör du ha färre av dessa aktiviteter och mycket mer av de mer grundläggande aktiviteterna. Genom att lägga till bättre behörighetskontroller så att färre personer kan ge liv åt saker och ting får du också meningsfulla begränsningar och kan uppnå det du behöver utan att offra hastighet och effektivitet. Ett annat alternativ är att ha en utsedd IT-resurs för att ge snabb överblick över QA-processen.

I [Activity QA](/help/c-activities/c-activity-qa/activity-qa.md) finns stegvisa instruktioner.

### Tips 11: Kör tester på sidor med hög trafik så att de blir statistiskt signifikanta snabbare.

Många marknadsförare lanserar optimeringsprogram för målgruppssegmentering och målgruppsanpassning utan att kontrollera om trafiknivåerna och målgrupperna som representeras ger betydande resultat inom testtidsramen för optimerings- och konverteringsmålen. För att undvika detta vanliga misstag ska du besvara följande frågor i förväg:

* Hur många unika besökare har sidan dagligen?
* Vilken konverteringsgrad har sidan?
* Hur länge tror du att du behöver köra testet innan du kan kalla det fullständigt?

**Tips**: Använd måtträknaren [för målets](https://docs.adobe.com/content/target-microsite/testcalculator.html) exempelstorlek för att avgöra vilken provstorlek som behövs för att testet ska lyckas.

### Tips 12: Utforma enklare tester för att vara säker på att du kan skapa och implementera dem.

Efter att ha övervägt alla aspekter av hur du utformar ett test kan en plan bli mycket komplex. Baserat på var ert företag är med testning och er grupps förmåga att utforma, koda, genomföra och analysera resultaten, kan ni avgöra om testet verkar för ambitiöst. Om så är fallet, var beredd att minska dess omfattning och komplexitet. Bättre att börja litet än att inte göra testet alls. Du kan inte ge en slagkraftig lyft om du aldrig startar testet. Det är viktigt att balansera teamets ambitioner med realiteterna i era resurser och förmågor.

### Tips 13: Dela upp komplexa tester i mindre testaktiviteter så att de blir möjliga att genomföra.

I stället för att utveckla ett stort test med flera variabler och komplex utveckling, kan du utveckla en mindre komplex serie med mindre tester med minimala variabler. Detta ger en djupare förståelse för testprestanda baserat på specifika variabler. Det minskar också eventuella tekniska problem som kan uppstå vid utveckling av större projekt.

![Bryt komplexa tester, illustration](/help/c-intro/assets/break-complex-tasks.png)

### Tips 14: Maximera testets påverkan genom att testa närmare slutet av konverteringsprocessen.

Testning så nära sidan där besökarna klickar på Complete Purchase, Submit Application eller på annat sätt slutför en konvertering tenderar att ge mest effektiva resultat. Besökare som kommer till slutet av processen är mer kvalificerade, har investerat mer tid och är redo att köpa, så att ni kan testa insikter om deras preferenser och åtgärder och göra lönsamma ändringar. Eftersom sidorna på köpbanan är avgörande för konverteringsgraden, bör testerna som utförs på dessa sidor integreras med viktiga intressenter innan de distribueras.

![Illustration av konverteringsprocessen](/help/c-intro/assets/conversion-funnel.png)

### Tips 15: Uppdatera testerna kontinuerligt och gör iterativa förbättringar.

Om din hypotes inte visar sig vara sann, tänk på sätt att förbättra testet. Tänk på att även om ingen av de testade upplevelserna fungerade bättre så var ditt experiment inte slöseri med tid. Ett lyckat test innebär inte alltid en ökning av intäkter eller konverteringar. Om testet faktiskt stödde er hypotes är ni på väg att utveckla en allmän teori. Men även om ni får ett tydligt vinnande resultat, sluta där. Alltför ofta gör marknadsförarna misstaget att testa en gång och sedan satsa på resultaten utan att förstå vad som ledde till framgången. I stället kan du iterera på dessa resultat för att ta reda på varför den främre körningsdelen var i framkanten. Detta kommer att leda till djupare insikter som ni kan använda i framtida kampanjer.

### Tips 16: Jämför tester och personaliseringsaktiviteter för idéer för att förbättra målinriktningen.

Genom att jämföra konverteringsresultatet för olika målgrupper i olika tester på olika platser kan du fokusera och förfina ett företags optimeringsstrategi. Använd testjämförelser för att identifiera vilka målgrupper som är mest värdefulla för att testa, vilka som ska få målinriktade upplevelser och vilka typer av upplevelser som mest sannolikt ger ett svar.

En kund inom finanssektorn har t.ex. kört en reklamkampanj för ett kreditkort som innefattade professionella sportevenemang. Genom partiell, faktoriell multivariattestning av landningssidorna kunde kunden optimalt balansera budskapen om kreditkortsförmåner med sporttjänster för att rikta distinkta målgrupper från kundbasen. På så sätt kunde företaget dra nytta av och maximera konverteringsgraden under ett tidskänsligt fönster runt ett stort idrottsevenemang.

### Tips 17: Gör tester användbara genom att bara starta dem om du vet att du kan agera med data.

Ett test är meningslöst om du inte är säker på hur du ska agera på data. Detta innefattar att känna till era viktigaste framgångsmått, vad som behöver hända för att pressa en vinnare, hur ni kommer att följa upp testresultaten och vad ni ska göra med målgruppsinformationen. För ett snabbt och framgångsrikt test är det av största vikt att alla grupper som deltar i testet (utvecklare, kreatörer, testspecialister och andra) är medvetna om dess roll innan teststarten.

### Tips 18: Innan du startar ett test bör du vara säker på att företaget stöder vinnaren.

Framgångsrika optimeringsorganisationer tror på begreppet testning och förstår att deras yrkesmässiga åsikter om vilken upplevelse som vinner testet inte alltid visar sig vara sanna. De avgör vinnaren baserat på en stabil grund av data och är angelägna och villiga att publicera den vinnande upplevelsen när resultatet är inne, även om det inte är i linje med deras förväntningar eller verkar vara kontraintuitivt.

En Adobe-vårdkund visade till exempel nyligen värdet av testning genom att visa hur en hjältebanderoll som teamet hade ansett vara en nedbantad bild faktiskt påverkade konverteringen negativt. Om ni ännu inte helt har accepterat testning är det bäst att först utföra enklare, mindre tester så att förändringar från testresultaten kan göras stegvis.

### Tips 19: Informera alla om att du har startat ett test för att undvika problem när webbplatsen ändras.

En av fördelarna med att konfigurera dina aktiviteter så att de använder QA-parametrar är att du kan dela länkarna med alla i teamet. Du gör fler människor medvetna om aktiviteten och ser till att de inte antar att webbplatsen inte fungerar som den ska när de träffar en testvariant.

När du är klar med testerna kan du öka medvetenheten om och intresset för testresultaten genom att kommunicera kampanjer, testresultat och särskilt lärdomar. Genom att dela resultaten med alla i organisationen undviker du också att testa en hypotes på nytt, utbildar alla om vad som fungerar och hjälper dem att i grunden utmana sina egna idéer om vad som fungerar baserat på vad ni har hittat. Det är en bra idé att ta fram en mall som du använder varje gång för att dela med dig av dina resultat och viktiga inlärningar.
Överväg sedan att skapa en delbar bok eller ett Microsoft PowerPoint-kassettdäck som kumulativt fångar dessa inlärningar.

### Tips 20: Utnyttja mobilfunktionerna för att skapa mer innovativa mobilaktiviteter.

Användarupplevelserna för surfplattor och smarttelefoner måste fokusera på pekstyrda kontroller som den primära besökarinteraktionen i stället för musklick och tangentbordskontroller. Dra nytta av mobila skärmkontroller, som att svepa, peka, dra, nypa och zooma med fingret. Använd enkla, stora knappar för att ange interaktioner och navigering, till exempel en stor kundvagn eller videouppspelningsknapp. Om du designar för mobilbutiker kan du använda avancerad produktvisualisering som är optimerad för enhetstypen. Leta alltid efter möjligheter att flytta fokus på användarupplevelsen till inbäddade, stora visningsprogram eller interaktiv zoom och panorering i helskärmsläge, 360-gradersrotation och utökade videofunktioner.

### Tips 21: Hjälp mobilbesökarna att hitta det de vill ha genom att optimera mobilsökningen.

Mobila användare har hög återgivning. De flesta använder sökningar innan de gör något annat på e-handelsplatser, vilket gör optimering av sökningar på mobilsajter avgörande. Om du vill förbättra sökmotoroptimeringen (SEO) för mobilen använder du explicita navigeringsmetoder för enkel surfning. Implementera också automatisk förslag och automatisk korrigering i sökrutor för att åtgärda svårigheterna med mobiltypning. Tillhandahåll övertygande, relevanta sökresultat optimerade för skärmstorlek och plats.

### Tips 22: Nå ut bättre till mobilmålgrupperna med tidsbaserad anpassning för mobila SEM-kampanjer.

Förstå hur och när ni ska nå era målgrupper och hur ni bättre ska hantera era dagliga annonser genom att&quot;dela&quot; era mobilkampanjer i olika segment under dagen.

Många marknadsförare gör misstag genom att inte tilldela tillräckligt med budget för att fånga upp den delen av rösten under de timmar då användningen av vissa enheter är tyngst, vilket ger stora intäkter och leder till bordet.

Till exempel ökar surfplatteanvändningen vanligen på kvällen och många användare surfar när de tittar på tv. Smarttelefonanvändare får däremot vanligtvis tillgång till innehåll var de än är. De högsta konverteringstiderna varierar också beroende på bransch, så det är viktigt att förstå när era unika kunder är mest benägna att agera.

### Kom ihåg

Tänk på följande innan vi går vidare till nästa kapitel: &quot;Inspiration for testing and personalization activity.&quot;

#### När du skapar testerna, dekorera inte, var avsiktlig.

* Styr flödet med avsiktliga ögonbanor med fokus på konverteringspunkter.
* Försäkra dig om att du använder din fastighet till din fördel.
* Utnyttja bildfokus för att säkerställa att bilderna inte är dekorationer, utan fungerar för dig.
* Minska oskärpa, skärpa och oskärpa med förenklad kopia.
* Se till att du har effektiva anrop till funktionsmakron när du behöver att användaren gör något.
* Öka trovärdigheten genom användargenererat innehåll där det är möjligt.

#### Förenkla er webbplats.

* Få inte kunderna att läsa. De kommer inte att göra det.
* Gör det enkelt att skanna.
* Använd punktlistor.
* Se till att texten följer en tydlig och sekventiell tankeprocess.

#### Använda effektivt anrop till åtgärder

* Ställ dig själv i kundens skor.
* Använd åtgärdsorienterat språk.
* Tänk på motivation för konvertering.
* Åtgärda resultatet av konverteringen.
* Se till att CTA:er syns!
