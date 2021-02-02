---
keywords: välkomstpaket;målvälkomstpaket;introduktion;komma igång
description: Välkomstkit för Adobe Target - Kapitel 2 - Ett ögonblick
title: Välkomstpaket - kapitel 2 - i korthet
feature: Overview
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '2464'
ht-degree: 0%

---


# Kapitel 2: Adobe Target i korthet

Innan du börjar använda [!DNL Adobe Target] kan det vara bra att få en översikt över lösningen på hög nivå. I det här kapitlet får du veta vilka nyckelfunktioner lösningen har, vilka kontaktytor du kan använda den på, implementeringsalternativ, viktiga funktioner och arbetsflöden i användargränssnittet, styrningsfunktioner och dess roll i den övergripande [!DNL Adobe Experience Cloud]. Om det inte anges som [!DNL Adobe Target Premium]-funktioner är de objekt som beskrivs i det här kapitlet tillgängliga med både [!DNL Adobe Target Premium] och [!DNL Adobe Target Standard]. Mer information finns i [Introduktion till Target](/help/c-intro/intro.md).

## Kapacitet och verksamhet

Testning och personalisering är de två vanligaste funktionerna som [!DNL Target] erbjuder och som du kan använda när du skapar en aktivitet i [!DNL Target]. termen&quot;testning&quot; används som en omväxlande funktion med&quot;optimering&quot; och&quot;personalisering&quot; som används omväxlande med&quot;målinriktning&quot;.

I en testaktivitet jämför du en variant av en digital upplevelse med en eller flera andra varianter för att upptäcka att en sådan som får de flesta besökare att vidta önskad åtgärd. [!DNL Target] erbjuder följande testfunktioner: A/B-testning, multivariata tester (MVT) och automatisk fördelning.

Med en personaliseringsaktivitet kan ni leverera en digital upplevelse som är skräddarsydd för en viss grupp besökare eller för varje enskild besökare. [!DNL Target] erbjuder följande personaliseringsfunktioner: Upplev Target, Auto-Target, Automated Personalization och Recommendations.

Mer information om när och hur du använder funktionerna finns i [Målaktivitetstyper](/help/c-activities/target-activities-guide.md).

| Typ av aktivitet | Detaljer |
| --- | --- |
| A/B-testning | Jämför två eller flera varianter av era upplevelser eller erbjudanden på er webbplats eller andra kontaktytor för digitala kunder för att se vilken variation som förbättrar de viktigaste affärsåtgärderna under en förspecificerad testperiod. A/B-tester är väl lämpade för stora förändringar, som nya webbsideslayouter, olika strategier för webbplatsnavigering eller drastiskt olika behandlingar av enskilda element i en digital upplevelse som kopiera, bilder och knappar för att ringa in. [Läs mer](/help/c-activities/t-test-ab/test-ab.md). |
| Automatisk allokering | Identifiera den bästa upplevelsen av två eller fler upplevelser och omfördela automatiskt mer trafik till vinnaren för att öka konverteringsgraden medan testet fortsätter att köras och lära sig mer. Använder artificiell intelligens som drivs av [!DNL Adobe Sensei]. [Läs mer](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| Automatiskt mål<br>(Premium) | Utnyttja Adobe Sensei AI i [!DNL Target] för att fastställa och leverera den bästa upplevelsen av flera till varje besökare baserat på hans eller hennes individuella kundprofil och beteendet hos tidigare besökare med liknande profiler. Automatisk målgruppsanpassning möjliggör personalisering i stor skala. [Läs mer](/help/c-activities/auto-target/auto-target-to-optimize.md). |
| Automated Personalization<br>(Premium) | Använd avancerade maskininlärningsalgoritmer och automatisering som bygger på [!DNL Adobe Sensei] för att granska olika kombinationer av bilder, text och andra element i ett erbjudande och leverera den bästa kombinationen till varje besökare baserat på vilka affärsmål som bäst uppnås, till exempel ökad konvertering eller intäkt per besökare. [Läs mer](/help/c-activities/t-automated-personalization/automated-personalization.md). |
| Experience Targeting (XT) | Leverera innehåll till en viss målgrupp baserat på en uppsättning användardefinierade regler och kriterier. **[!UICONTROL Experience Targeting]** är värdefullt för att rikta en specifik upplevelse eller innehåll till en viss målgrupp när ni förstår att en målgrupp är värdefull och har en bra uppfattning om vilken upplevelse som får genklang med dem. [Läs mer](/help/c-activities/t-experience-target/experience-target.md). |
| Multivariate Testing (MVT) | Jämför alla möjliga kombinationer av olika element på sidan eller i den digitala upplevelsen, till exempel tre olika bakgrundsbilder, två varianter av text och två olika knappfärger. MVT avgör vilken kombination som fungerar bäst för en viss målgrupp och vilka element som påverkar resultatet mest. [Läs mer](/help/c-activities/c-multivariate-testing/multivariate-testing.md). |
| Recommendations<br>(Premium) | Använd Adobe Sensei AI för att automatiskt föreslå produkter eller innehåll som kan intressera dina kunder baserat på deras tidigare och andra kunders aktivitet. [Läs mer](/help/c-recommendations/recommendations.md). |

## Kanaler

Du kan använda [!DNL Target] för att testa och personalisera digitala upplevelser nästan var som helst - traditionella digitala kontaktytor som din webbplats, mobilwebbplats och mobilapp, men också på kontaktytor som kioskdatorer, e-post, IoT-enheter, spelkonsoler och till och med röstassistenter som Alexa och Cortana. Många företag börjar använda [!DNL Target] på sin webbplats. Men den senaste forskningen tyder på att fler människor besöker varumärken från sina mobila enheter. Det är nu viktigt att optimera mobilkanalerna. Det bästa är att ni kopplar samman besökarens upplevelser över alla era kontaktytor för att leverera en sömlös, enhetlig upplevelse.

| Kanal | Detaljer |
| --- | --- |
| Webbplats | [!DNL Target] kan användas för att köra A/B-testning, Multivariate Testing, Experience Targeting, Auto-Allocate, Auto-Target, Automated Personalization och Recommendations på sidor av era flersidiga, single page-applikationer (SPA) och mobilsajter för att förbättra besökarens och kundens engagemang, öka konverteringarna och öka intäkterna. |
| Mobil webb | [!DNL Target] kan användas för att köra alla de aktivitetstyper som du kör på din webbplats på dina mobilsidor för att på liknande sätt förbättra besökares och kunders engagemang, öka konverteringarna och öka intäkterna. |
| Mobilapp | [!DNL Target] kan användas för att testa och personalisera mobilappsupplevelser baserat på användarbeteende och mobilsammanhang. [!DNL Target] Med kan ni leverera interaktioner som engagerar och konverterar genom iterativ testning samt Experience Targeting och AI-driven personalisering. Om du vill använda [!DNL Target] i din mobilapp måste du använda Adobe Mobile Services SDK. |
| IoT/Everywhere | [!DNL Target] erbjuder en implementering på serversidan så att du kan använda samma funktioner för testning och personalisering i aktiviteter som du använder på din traditionella webbplats, mobilwebbplats och mobilappar i e-postmeddelanden och på kontaktytor som saknar webbläsare eller som inte använder JavaScript-kod. Du kan till exempel testa och anpassa kioskdatorer, digitalboxar, spelkonsoler, röstassistenter och andra icke-traditionella kontaktytor. |

## Implementeringar

Många av er kanske vill använda [!DNL Target] för att testa och personalisera på era många olika digitala kontaktytor, inklusive traditionella webb- och mobilkontaktytor, men även kontaktytor som saknar webbläsare eller som inte använder JavaScript-kod. I vissa fall kräver den interna eller externa principen att du har ytterligare nivåer av kontroll och säkerhet. Det kan också finnas processer som av prestandaskäl måste köras på en serverdel. För att uppfylla detta stora antal användningsområden ger vi dig möjlighet att implementera [!DNL Target] på olika sätt: klientsidan, serversidan eller en kombination av båda.

| Implementeringstyp | Detaljer |
| --- | --- |
| Klientsidan | Med den här implementeringen av [!DNL Target] levererar [!DNL Target] upplevelserna som är kopplade till en aktivitet direkt till klientwebbläsaren. Webbläsaren avgör vilken upplevelse som ska visas och visar den. Med klientsidan kan du använda en WYSIWYG-redigerare, **[!UICONTROL Visual Experience Composer]** (VEC) eller ett icke-visuellt gränssnitt, **[!UICONTROL Form-based Experience Composer]**, för att skapa test- och personaliseringsupplevelser. [Läs mer](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). |
| Serversidan | I den här typen av [!DNL Target]-implementering gör en klientenhet en begäran om en upplevelse via servern, servern skickar begäran till [!DNL Target], [!DNL Target] skickar tillbaka svaret till servern och servern fattar beslut om vilken upplevelse som ska levereras till klientenheten för att den ska kunna återges. upplevelsen inte behöver visas i en webbläsare, den kan visas i ett e-postmeddelande eller i en kioskdator, via en röstassistent eller via någon annan icke-visuell upplevelse eller icke-webbläsarbaserad enhet. Eftersom servern finns mellan klienten och [!DNL Target] är den här typen av implementering också idealisk om du behöver större kontroll och säkerhet eller har komplexa serverprocesser som du vill köra på servern. [Läs mer](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Hybrid-implementering | I den här implementeringen väljer du den implementeringsmetod som fungerar bäst för ett visst användningsfall. Du kan till exempel använda en implementering på klienten för att A/B-testa ett erbjudande i en hjältebanderoll på startsidan, men även använda en implementering på serversidan för att avgöra vilka interna sökresultat som ska visas i en klientwebbläsare, upplevelsen som ska visas på en smart bildinstrumentpanel eller röstsvaret som ska visas från en röstassistent. |

## Aktivitetselement

I [!DNL Target] kan du skapa en personaliseringsaktivitet, en optimeringsaktivitet eller en aktivitet som optimerar din personaliseringsstrategi. Varje aktivitet har nyckelelement - de upplevelser eller erbjudanden ni testar eller personaliserar, de målgrupper eller individer ni levererar en upplevelse till, de mätvärden som ni mäter aktivitetens effekt med och de rapporter som visuellt visar den effekten.

| Elementtyp | Detaljer |
| --- | --- |
| Erfarenheter | Ett erbjudande, en bild, text, knapp, video, en kombination av dessa olika element på en sida, en hel webbsida eller en uppsättning sidor som kanske utgör en inköpstratt eller någon annan logisk sekvens av sidor. Det kan också vara svaret från en röstassistent, ett kundskript eller till och med en personlig smak från en dryckesmaskin. Du testar eller personaliserar upplevelser i [!DNL Target]-aktiviteter. [Läs mer](/help/c-experiences/experiences.md). |
| Erbjudanden | Ett block med innehåll som kan innehålla bilder, text, HTML, länkar, video, en knapp för att ringa in åtgärder, ett röstassistentsvar eller någon annan typ av innehåll. Erbjudandet kan omfatta rabatter, fri frakt och så vidare. Ett erbjudande kan visas på en webbsida, men det kan också visas på alla kundkontaktytor, som en röstassistent eller spelkonsol. När du testar ett erbjudande mäter du hur väl det lyckades jämfört med andra erbjudanden eller inget erbjudande. [Läs mer](/help/c-experiences/c-manage-content/manage-content.md). |
| Målgrupper | En grupp personer med samma egenskaper, till exempel en ny besökare, en återkommande besökare eller återkommande besökare från mellanvästern. Med funktionen Målgrupp kan ni rikta olika innehåll och upplevelser till specifika målgrupper för att optimera er digitala marknadsföring genom att visa rätt budskap till rätt personer vid rätt tidpunkt. Om en besökare identifieras som en del av en målpublik avgör [!DNL Target] vilken upplevelse som ska visas, baserat på kriterier som definieras när aktiviteten skapas. [Läs mer](/help/c-target/target.md). |
| Framgångsmått | Viktiga affärsåtgärder som gör att du kan avgöra om en viss upplevelse eller ett visst erbjudande i en [!DNL Target]-aktivitet är framgångsrik. Du kan till exempel bestämma om ett nytt erbjudande ökar intäkterna per besökare eller lägger till en artikel i en kundvagn. Framgångsstatistik kan vara användbar för att upptäcka problem med registrering, beställning eller inköpskanaler, men också helt enkelt med besökarens eller kundens engagemang. [Läs mer](/help/c-activities/r-success-metrics/success-metrics.md). |
| Rapporter | Information om förloppet och resultaten av dina aktiviteter som hjälper dig att fatta beslut baserat på dina data. Rapportdata kan hjälpa er att avgöra när ni ska avsluta ett test, visa er vilken upplevelse av erbjudandet som är vinnaren och ge er insikter eller inlärningar ni behöver för att avgöra nästa åtgärd. [Läs mer](/help/c-reports/reports.md). |

## Verktyg för att skapa aktiviteter

[!DNL Target] ger dig tre sätt att konfigurera dina testnings- och personaliseringsaktiviteter,  [!UICONTROL Visual Experience Composer] (VEC),  [!UICONTROL Form-based Experience Composer]och  [!UICONTROL Single Page Application (SPA) Visual Experience Composer]. Båda vägleder dig genom processen för aktivitetskonfiguration i tre steg - definiera upplevelser, välja ut eller definiera målgrupper och välja primära och sekundära framgångsmått som du kan använda för att mäta aktivitetens resultat.

| Verktyg | Detaljer |
| --- | --- |
| [!UICONTROL Visual Experience Composer] (VEC) | Ett WYSIWYG-användargränssnitt som gör det enkelt att skapa och testa personaliserade upplevelser och erbjudanden i webbplatskontexten. Du kan skapa upplevelser och erbjudanden för [!DNL Target]-aktiviteter genom att dra och släppa, byta och ändra layouten och innehållet på en webbsida (eller ett erbjudande) eller en mobilwebbsida. [Läs mer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md). |
| [!UICONTROL Form-based Experience Composer] | En icke-visuell upplevelse och ett gränssnitt som gör att du kan skapa upplevelser som kan användas i A/B-tester, Experience Targeting, Automated Personalization och Recommendations när Visual Experience Composer inte är tillgängligt eller praktiskt att använda. Du kan till exempel använda den formulärbaserade dispositionen för att skapa upplevelser och erbjudanden för e-post, kioskdatorer och röstassistenter. [Läs mer](/help/c-experiences/form-experience-composer.md). |
| [!UICONTROL Single Page Application (SPA) Visual Experience Composer] | Med VEC for SPA kan marknadsförarna skapa tester och personalisera innehåll på SPA på ett sätt som gör det själv utan kontinuerliga utvecklingsberoenden. VEC kan användas för att skapa A/B Test- och Experience Targeting-aktiviteter (XT) på populära ramverk som React och Angular. [Läs mer](/help/c-experiences/spa-visual-experience-composer.md). |

## Styrning och kontroll

För att ge rätt personer rätt roller och tillhörande åtkomstnivåer och behörigheter till [!DNL Target] har vi en administrationskonsol. För [!UICONTROL Target Premium]-användare erbjuder vi mer detaljerad styrning och kontroll
med [!UICONTROL Enterprise Permissions].

| Verktyg | Detaljer |
| --- | --- |
| [!UICONTROL Adobe Admin Console for Enterprise] | Lägg till användare i Adobe Target och tilldela behörigheter från Adobe Admin Console. [Läs mer](/help/administrating-target/c-user-management/c-user-management/user-management.md). |
| [!UICONTROL Enterprise Permission]s<br>(Premium) | Ett sätt att formellt administrera företagsövergripande användaråtkomst till [!DNL Target]. Lägg till användare i [!DNL Target], tilldela behörigheter baserat på deras roller och skapa arbetsytor för team baserat på olika avdelningar, globala platser, kanaler och andra logiska grupper. Du kan tilldela användare rollerna observatör, redigerare, utgivare och godkännare. [Läs mer](/help/administrating-target/c-user-management/property-channel/property-channel.md). |

## Integreringar

[!DNL Target] kan integreras med många första-, andra- och tredjepartssystem. Dessa
integreringar kan vara värdefulla för att ge er tillgång till besöks- och kunddata som är tillgängliga från dessa system och som kan användas för att skapa målgrupper för testning och personalisering. Som en del av [!DNL Adobe Experience Cloud] är [!DNL Target] nära integrerat med [!DNL Experience Cloud]-lösningar och dess bastjänster.

| Integrering | Detaljer |
| --- | --- |
| Adobe Experience Cloud | [!DNL Target] har inbyggda funktioner med andra  [!DNL Adobe Experience Cloud] lösningar för att personalisera upplevelser i stor skala. Utnyttja fördelarna med [!DNL Target] tillsammans med [Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md), [Experience Cloud Publiker](/help/c-integrating-target-with-mac/mmp.md), [Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md), [Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) (AAM) och [Adobe Experience Manager](/help/c-experiences/c-manage-content/aem-experience-fragments.md) (AEM). |
| Mål-API:er (Premium) | [!UICONTROL Target] erbjuder mer än 40 API:er som du kan använda för att integrera Adobe Target med första-, andra- och tredjepartssystem. [Läs mer](/help/api/api-overview.md). |

## Kom ihåg

Tänk på följande innan vi går vidare till nästa kapitel: &quot;Utveckla dina idéer om testning och personalisering.&quot;

### Bästa tillvägagångssätt för optimering

* **Bra strategi**: Vad är vår målsättning och hypotes? Är de justerade? Vi vill till exempel öka inskickandet av låneansökningar, så vi rekommenderar att en minskning av antalet fält i ansökningsformuläret gör det.
* **Disciplinerade** metoderBörjar vi testa på rätt ställen? Du behöver till exempel platser som har tillräckligt med trafik och som påverkar mätvärdena som är viktiga    till företaget.
* **Korrekt** uppställningÄr vår aktivitet inställd för att uppnå vårt mål? Om vi till exempel försöker öka inskickade låneansökningar bör vi rikta in oss på personer som är intresserade av lån och mäta klick på knappen&quot;Skicka&quot;.
* **Detaljerad analys**: Kördes testaktiviteten tills den var klar? Vad säger resultaten? Kör aktiviteten tills den uppnår mellan 95 % och 99 % statistisk säkerhet. Dokumentera varför du tror att den vinnande upplevelsen vinner och använd inlärningen någon annanstans.
* **Interaktiv testning**: Bygger vi på inlärningen av tidigare aktiviteter? Om du hittar en vinnande taktik kan du försöka förbättra den eller göra ändringar som fungerar med den för att ytterligare förbättra dina framgångsmått.

### Yttranden kan påverka dina resultat negativt

* Yttranden som kan påverka effekten negativt. Highest Paid Person’s Opinion (HIPPO), attityder, biases. VD:n vill t.ex. minska storleken på sökrutan för att få mer plats på varje sida. Vi bör testa att se till att det inte minskar antalet sökningar.
* Agerar du på åsikter? Jag tycker inte om hur testet ser ut. Kunden kommer inte alls att gilla den här upplevelsen. Intuition är användbar, men A/B-tester har gång på gång visat att det inte alltid fungerar.
* Eller har du en optimeringsmetod? Jag är glad att se vilken upplevelse som vinner. Har vi tillräckligt med alternativ för att testa?

### Antaganden kan också påverka resultatet negativt

* Antaganden som kan påverka effektiviteten negativt. Herd mentality (det är så våra konkurrenter gör det). Alla våra konkurrenter använder till exempel hjältebanners med roterande bilder, så vi bör också göra det.
* Anta att vi vet varför något fungerar eller inte. Anta att vi inte behöver testa någonting. Vi listar t.ex. alltid hotellrum i ordningen högst till lägst pris som standard.
* Agerar du utifrån antaganden? Vi behöver inte testa det, vi har kollat analyser. (Ja, men det kan finnas mer i berättelsen än vad analyserna visar.)
* Eller har du en optimeringsmetod? Vi testar allt.