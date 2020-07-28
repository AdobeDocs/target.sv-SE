---
keywords: auto-target;targeting;traffic allocation;frequently aske questions;faq;troubleshooting;trouble shooting
title: Auto-Target
topic: Standard
uuid: fce769d2-9e7f-4064-add7-76e1fc394b4f
translation-type: tm+mt
source-git-commit: 4695dbf2ecbd19be5589bfc63e2d947361d77fce
workflow-type: tm+mt
source-wordcount: '3423'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Auto-Target{#auto-target}

[!UICONTROL Auto-Target] använder avancerad maskininlärning för att välja bland flera högpresterande marknadsföringsdefinierade upplevelser för att personalisera innehåll och driva konverteringar. Auto-Target levererar den mest skräddarsydda upplevelsen till varje besökare baserat på hans eller hennes individuella kundprofil och beteendet hos tidigare besökare med liknande profiler.

>[!NOTE]
>
>[!UICONTROL Auto-Target] finns som en del av [!DNL Target Premium] lösningen. Den här funktionen är inte tillgänglig i [!DNL Target Standard] utan [!DNL Target Premium] licens. Mer information om de avancerade funktionerna i den här licensen finns i [Target Premium](/help/c-intro/intro.md).

När du [skapar en A/B-aktivitet med det guidade arbetsflödet](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)i tre steg kan du välja att fördela trafik med [!UICONTROL Auto-Target For Personalized Experiences] alternativet:

![Automatisk målgruppsanpassning för personaliserade upplevelser](/help/c-activities/assets/auto-target-ui-new.png)

## Översikt {#section_972257739A2648AFA7E7556B693079C9}

Med [!UICONTROL Auto-Target] alternativet i A/B-aktivitetsflödet kan ni utnyttja maskininlärning för att personalisera baserat på en uppsättning marknadsföringsdefinierade upplevelser med ett enda klick. [!UICONTROL Auto-Target] är utformat för att ge maximal optimering, jämfört med traditionell A/B-testning eller automatisk fördelning, genom att avgöra vilken upplevelse som ska visas för varje besökare. Till skillnad från en A/B-aktivitet där målet är att hitta en enskild vinnare avgör [!UICONTROL Auto-Target] automatiskt den bästa upplevelsen för en viss besökare (baserat på hans eller hennes profil och annan sammanhangsbaserad information) för att leverera en mycket personaliserad upplevelse.

På samma sätt som i Automated Personalization [!UICONTROL Auto-Target] används en slumpmässig skogsalgoritm, en metod som är unik för datavetenskap, för att fastställa den bästa upplevelsen som ska visas för en besökare. Eftersom [!UICONTROL Auto-Target] kan anpassa sig till förändringar i besökarnas beteende kan det köras permanent för att ge lyft. Detta kallas ibland för &quot;alltid på&quot;-läge.

Till skillnad från en A/B-aktivitet där upplevelseallokeringen för en viss besökare är snäv, [!UICONTROL Auto-Target] optimerar det angivna verksamhetsmålet för varje besök. Som i [!UICONTROL Auto Personalization]reserverar [!UICONTROL Auto-Target]som standard en del av aktivitetens trafik som en kontrollgrupp för att mäta lyft. Besökarna i kontrollgruppen får en slumpmässig erfarenhet av aktiviteten.

## Överväganden

Det finns några viktiga saker att tänka på när du använder [!UICONTROL Auto-Target]:

* Du kan inte växla en viss aktivitet från [!UICONTROL Auto-Target] till Automated Personalization, och vice versa.
* Du kan inte växla från manuell trafikallokering (traditionellt A/B-test) till [!UICONTROL Auto-Target], och vice versa, efter att en aktivitet är aktiv.
* En modell är byggd för att identifiera den personaliserade strategins prestanda jämfört med slumpvis betjänad trafik jämfört med att skicka all trafik till den övergripande vinnande upplevelsen. Den här modellen hanterar endast träffar och konverteringar i standardmiljön.

   Trafik från en andra uppsättning modeller byggs för varje modellgrupp (AP) eller upplevelse (AT). För var och en av dessa modeller beaktas träffar och konverteringar i alla miljöer.

   Förfrågningar kommer därför att hanteras enligt samma modell, oavsett miljö, men den stora trafikmångfalden bör komma från standardmiljön för att säkerställa att den identifierade övergripande vinnande upplevelsen överensstämmer med det verkliga beteendet.

* Ni måste använda minst två upplevelser.

## Terminologi {#section_A309B7E0B258467789A5CACDC1D923F3}

Följande termer är användbara vid diskussion [!UICONTROL Auto-Target]:

| Villkor | Definition |
|---|---|
| Flerarmad bandit | En flerarmad bandit-strategi för optimering balanserar undersökande inlärning och utnyttjande av det inlärningen. |
| Slumpmässig skog | Random Forest är en ledande maskininlärningsstrategi. I datavetenskap är det en ensemble klassificering, eller regressionsmetod, som fungerar genom att ett stort antal beslutsträd byggs utifrån besöks- och besöksattribut. Inom Target används Random Forest för att fastställa vilken erfarenhet som förväntas ha störst sannolikhet för konvertering (eller högsta intäkt per besök) för varje enskild besökare. Mer information om Slumpmässig skog i Target finns i [Slumpmässig skogsalgoritm](../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA). |
| Thompson Sampling | Målet för Thompson Sampling är att fastställa vilken upplevelse som är bäst totalt sett (icke-personaliserad), samtidigt som man minimerar&quot;kostnaden&quot; för att hitta den upplevelsen. Thompson-urvalet väljer alltid en vinnare, även om det inte finns någon statistisk skillnad mellan två upplevelser. Mer information finns i [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling). |

## Så här [!UICONTROL Auto-Target] fungerar {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Läs mer om underliggande data och algoritmer [!UICONTROL Auto-Target] och Automated Personalization på länkarna nedan:

| Villkor | Detaljer |
|--- |--- |
| [Slumpmässig skogsalgoritm](/help/c-activities/t-automated-personalization/algo-random-forest.md) | Target huvudsakliga personaliseringsalgoritm som används i både [!UICONTROL Auto-Target] och Automated Personalization är Slumpmässig skog. Ensemble-metoder som Slumpmässig skog använder flera inlärningsalgoritmer för att få bättre prediktiva prestanda än vad som kan uppnås med någon av de ingående inlärningsalgoritmerna. Algoritmen Random Forest i det automatiserade personaliseringssystemet är en klassificering, eller regressionsmetod, som fungerar genom att en mängd beslutsträd byggs ut under utbildningstiden. |
| [Överför data för Target personaliseringsalgoritmer](/help/c-activities/t-automated-personalization/algo-random-forest.md) | Det finns flera sätt att mata in data för [!UICONTROL Auto-Target] och Automated Personalization-modeller. |
| [Datainsamling för Target personaliseringsalgoritmer](/help/c-activities/t-automated-personalization/ap-data.md) | Target personaliseringsalgoritmer samlar automatiskt in en mängd olika data. |

## Bestämma trafikallokering {#section_AB3656F71D2D4C67A55A24B38092958F}

Beroende på vad din aktivitet har för mål kan du välja en annan trafikfördelning mellan kontroll och personaliserade upplevelser. Det bästa sättet är att fastställa det här målet innan du gör din aktivitet offentlig.

I den [!UICONTROL Custom Allocation] nedrullningsbara listan kan du välja mellan följande alternativ:

* Utvärdera personaliseringsalgoritm
* Maximera personaliseringstrafiken
* Anpassad allokering

![Listruta för allokeringsmål](/help/c-activities/assets/split-new.png)

| Aktivitetsmål | Föreslagen trafikallokering | Överlåtelser |
|--- |--- |--- |
| **Utvärdera personaliseringsalgoritm (50/50)**: Om målet är att testa algoritmen ska du använda en 50/50-procentig delning av besökare mellan kontrollen och målalgoritmen. Denna delning ger den mest korrekta uppskattningen av hissen. Föreslagna för användning med&quot;slumpmässiga upplevelser&quot; som er kontroll. | 50 % kontroll/50 % personlig upplevelsedelning | <ul><li>Maximerar lyften mellan kontroll och personalisering</li><li>relativt färre besökare får en personaliserad upplevelse</li></ul> |
| **Maximera personaliseringstrafiken (90/10)**: Om målet är att skapa en&quot;alltid aktiverad&quot; aktivitet ska 10 % av besökarna ha kontrollen för att säkerställa att det finns tillräckligt med data för att algoritmerna ska kunna fortsätta lära sig över tid. Observera att ni i utbyte mot att personalisera en större andel av trafiken har mindre precision i det exakta lyftet. Oavsett vilket mål du har är detta den rekommenderade trafikdelningen när du använder en specifik upplevelse som kontroll. | Det bästa sättet är att använda en 10-30 % kontroll/70-90 % personaliserad upplevelsedelning | <ul><li>Maximerar antalet besökare som har en personaliserad upplevelse</li><li>Maximerar lyft</li><li>Mindre noggrannhet vad hissen är för aktiviteten</li></ul> |
| **Anpassad allokering** | Dela procentandelen manuellt efter behov. | <ul><li>Du kanske inte uppnår det önskade resultatet. Om du är osäker kan du följa förslagen för något av de föregående alternativen</li></ul> |

Om du vill justera kontrollprocenten klickar du på ikonerna i kolumnen Allokering. Du kan inte minska kontrollgruppen till mindre än 10 %.

![Ändra automatisk trafikallokering för Target](/help/c-activities/assets/auto-target-control.png)

Du kan [välja en specifik upplevelse som ska användas som kontroll](/help/c-activities/t-automated-personalization/experience-as-control.md) eller så kan du använda alternativet Slumpmässig upplevelse.

## När ska du välja [!UICONTROL Auto-Target] framför Automated Personalization? {#section_BBC4871C87944DD7A8B925811A30C633}

Det finns flera scenarier där du kanske föredrar att använda [!UICONTROL Auto-Target] framför Automated Personalization:

* Om ni vill definiera hela upplevelsen i stället för enskilda erbjudanden som automatiskt kombineras för att skapa en upplevelse.
* Om du vill utnyttja alla funktioner i Visual Experience Composer (VEC) som inte stöds av [!UICONTROL Auto Personalization]: den anpassade kodredigeraren, flera olika upplevelsemålgrupper med mera.
* Om du vill göra strukturella ändringar på sidan i olika upplevelser. Om du t.ex. vill ändra ordningen på elementen på startsidan är det bättre att använda [!UICONTROL Auto-Target] dem än Automated Personalization.

## Vad har [!UICONTROL Auto-Target] jag gemensamt med Automated Personalization? {#section_2A601F482F9A44E38D4B694668711319}

**Algoritmen optimerar för ett positivt resultat vid varje besök.**

* Algoritmen förutser besökarens benägenhet för konvertering (eller beräknade intäkter från konvertering) för att ge bästa möjliga upplevelse.
* En besökare är berättigad till en ny upplevelse vid slutet av en befintlig session (såvida inte besökaren är i kontrollgruppen, i vilket fall den upplevelse som besökaren får vid sitt första besök förblir densamma för efterföljande besök).
* Under en session ändras inte förutsägbarheten, vilket ger en bättre visuell enhetlighet.

**Algoritmen anpassas till förändringar i besökarens beteende.**

* Multiarm bandit ser till att modellen alltid&quot;spenderar&quot; en liten fraktionstrafik som fortsätter att lära sig under aktivitetens livstid och för att förhindra att tidigare inlärda trender utnyttjas i alltför stor utsträckning.
* De underliggande modellerna byggs om var 24:e timme med hjälp av de senaste besökarbeteendedata för att säkerställa att Target alltid utnyttjar föränderliga besökarinställningar.
* Om algoritmen inte kan avgöra vilka vinnande upplevelser individen har, växlar den automatiskt till att visa den övergripande prestandaoptimerade upplevelsen samtidigt som den fortsätter att leta efter personaliserade vinnare. Den bästa upplevelsen med [Thompson-sampling](https://en.wikipedia.org/wiki/Thompson_sampling).

**Algoritmen optimerar kontinuerligt för ett enda målmått.**

* Detta kan vara konverteringsbaserat eller intäktsbaserat (mer specifikt Intäkter per besök).

**Algoritmen stöder inte användning[!DNL Analytics]som datakälla eller rapportslutpunkt.**

**Target samlar automatiskt in information om besökare för att skapa personaliseringsmodeller.**

* Mer information om parametrarna som används i [!UICONTROL Auto-Target] och Automated Personalization finns i [Automated Personalization Data Collection](../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

**Target använder automatiskt alla gemensamma målgrupper i Experience Cloud för att skapa personaliseringsmodeller.**

* Du behöver inte göra något specifikt för att lägga till målgrupper i modellen. Mer information om hur du använder Experience Cloud-målgrupper med Target finns i [Experience Cloud-målgrupper](../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969)

**Marknadsförarna kan överföra offlinedata, benägenhetspoäng eller andra anpassade data för att skapa personaliseringsmodeller.**

* Läs mer om [överföring av data för Auto-Target och Automated Personalization](../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

## Hur skiljer sig [!UICONTROL Auto-Target] det från Automated Personalization? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**[!UICONTROL Auto-Target]ofta kräver mindre trafik än Automated Personalization för att bygga en personaliserad modell.**

Även om mängden trafik *per upplevelse* som krävs för att bygga [!UICONTROL Auto-Target] eller [!UICONTROL Auto Personalization] modeller är densamma, finns det vanligtvis fler upplevelser i en Automated Personalization-aktivitet än i en [!UICONTROL Auto-Target] aktivitet. Om du till exempel har en [!UICONTROL Auto Personalization] aktivitet där du har skapat två erbjudanden per plats med två platser, skulle det finnas fyra (2 = 4) totala upplevelser i aktiviteten (utan undantag). Med [!UICONTROL Auto-Target]hjälp av kan ni ange upplevelse 1 som inkluderar erbjudande 1 på plats 1 och erbjudande 2 på plats 2, och upplevelse 2 som inkluderar erbjudande 1 på plats 1 och erbjudande 2 på plats 2. Eftersom [!UICONTROL Auto-Target] ni kan välja att göra flera ändringar i en upplevelse kan ni minska antalet totala upplevelser i er aktivitet.

Exempelvis [!UICONTROL Auto-Target]kan enkla reglage användas för att förstå trafikkraven:

* **När konverteringen är din framgångsfaktor:** 1 000 besök och minst 50 konverteringar per dag och upplevelse. Dessutom måste aktiviteten ha minst 7 000 besök och 350 konverteringar.
* **När intäkt per besök är ditt framgångsmått:** 1 000 besök och minst 50 konverteringar per dag och upplevelse. Dessutom måste aktiviteten ha minst 1 000 konverteringar per upplevelse. RPV kräver vanligtvis mer data för att bygga modeller på grund av den högre datavariationen som vanligtvis finns i besöksintäkterna jämfört med konverteringsgraden.

**[!UICONTROL Auto-Target]har fullständig konfigurationsfunktionalitet.**

* Eftersom [!UICONTROL Auto-Target] är inbäddad i A/B-aktivitetsarbetsflödet har det [!UICONTROL Auto-Target] bättre och mer kompletta visuella Experience Composer (VEC). Du kan också utnyttja [QA-länkar](../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) med [!UICONTROL Auto-Target].

**[!UICONTROL Auto-Target]har ett omfattande ramverk för onlinetestning.**

* Flerarmsbanken ingår i ett större ramverk för onlinetestning, som gör det möjligt för våra datavetare och forskare att förstå fördelarna med sina kontinuerliga förbättringar i verkliga förhållanden.
* I framtiden kommer denna testbädd att göra det möjligt för oss att öppna vår maskininlärningsplattform för våra datatillgängliga kunder så att de kan ta in sina egna modeller för att förstärka Target modeller.

## Rapportering och [!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

Mer information finns i [Sammanfattningsrapport](../c-reports/auto-target-summary-report.md#concept_E2171F7B57C1417DAAD7E7909A3FB073) för automatisk Target i [rapportavsnittet](../c-reports/reports.md#concept_B5077F5503AA4C98901AA99EDCE6CDE6) .

## Vanliga frågor och svar om Auto-Target {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Se följande frågor och svar när du arbetar med [!UICONTROL Auto-Target] aktiviteter:

### Vilka är de bästa sätten att konfigurera en [!UICONTROL Auto-Target] aktivitet?

* Bestäm om affärsvärdet för ett framgångsmått för Intäkter per besök är värt de extra trafikkraven. RPV behöver vanligtvis minst 1 000 konverteringar per upplevelse för att en aktivitet ska fungera jämfört med konvertering.
* Bestäm allokeringen mellan kontroll och personaliserade upplevelser innan du påbörjar aktiviteten utifrån era mål.
* Kontrollera om du har tillräckligt med trafik till den sida där din [!UICONTROL Auto-Target] aktivitet ska köras för att personaliseringsmodeller ska kunna byggas inom rimlig tid.
   * Om du testar personaliseringsalgoritmen bör du inte ändra upplevelser eller lägga till/ta bort profilattribut när aktiviteten är aktiv.

* Överväg att slutföra en A/B-aktivitet mellan de erbjudanden och platser som du planerar att använda i din [!UICONTROL Auto-Target] aktivitet för att se till att platserna och erbjudandena påverkar optimeringsmålet. Om en A/B-aktivitet inte uppvisar någon signifikant skillnad kommer den troligtvis inte heller att kunna generera någon lyft [!UICONTROL Auto-Target] .

   * Om ett A/B-test inte visar några statistiskt signifikanta skillnader mellan upplevelserna, är det troligt att de erbjudanden du överväger inte skiljer sig tillräckligt mycket från varandra, att de platser du valde inte påverkar framgångsmåttet eller att optimeringsmålet är för långt i konverteringsprocessen för att påverkas av dina valda erbjudanden.

* Försök att inte göra några större ändringar av upplevelserna under aktivitetens gång.

### Är kryssmarkeringarna som anger att en modell har skapats för den upplevelseuppdateringen om rapportens datumintervall ändras?

Nej, bockmarkeringar för modellgenerering visar endast de modeller som är byggda hittills. Det finns inget sätt att gå tillbaka och se när en modell är klar.

### Om en besökare INTE ser aktiviteten och konverterar, räknas konverteringen i min aktivitet? [!UICONTROL Auto-Target]

Nej, endast besökare som är kvalificerade för och visar [!UICONTROL Auto-Target] aktiviteten räknas i rapporteringen.

### Min [!UICONTROL Auto-Target] aktivitet verkar inte generera något lyft. Vad är det som pågår?

Det krävs fyra faktorer för att en aktivitet ska kunna generera en lyft: [!UICONTROL Auto-Target]

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

Det bästa sättet att agera är att först se till att det innehåll och de platser som utgör aktivitetsupplevelserna verkligen gör skillnad i den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar.

Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet kommer att fungera. Personalisering kan förstås fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på att erbjudandena/platserna inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

### När ska jag stoppa min [!UICONTROL Auto-Target] aktivitet?

[!UICONTROL Auto-Target] kan användas som&quot;alltid on&quot;-personalisering som hela tiden optimeras. Särskilt för omogna innehåll finns inget behov av att stoppa din [!UICONTROL Auto-Target] aktivitet.

Om du vill göra väsentliga ändringar i innehållet i din [!UICONTROL Auto-Target] aktivitet är det bästa sättet att starta en ny aktivitet så att andra användare inte förväxlar eller relaterar tidigare resultat med annat innehåll.

### Hur länge ska jag vänta på att modeller ska byggas?

Hur lång tid det tar för modeller att bygga in din [!UICONTROL Auto-Target] aktivitet beror vanligtvis på trafiken till de valda aktivitetsplatserna och hur framgångsrik aktiviteten är.

Exempelvis [!UICONTROL Auto-Target]kan enkla reglage användas för att förstå trafikkraven:

* **När konverteringen är din framgångsfaktor:** 1 000 besök och minst 50 konverteringar per dag och upplevelse. Dessutom måste aktiviteten ha minst 7 000 besök och 350 konverteringar.
* **När intäkt per besök är ditt framgångsmått:** 1 000 besök och minst 50 konverteringar per dag och upplevelse. Dessutom måste aktiviteten ha minst 1 000 konverteringar per upplevelse. RPV kräver vanligtvis mer data för att bygga modeller på grund av den högre datavariationen som vanligtvis finns i besöksintäkterna jämfört med konverteringsgraden.

### En modell är inbyggd i min aktivitet. Är besöken till den upplevelsen personaliserade?

Nej, det måste finnas minst två modeller i din aktivitet för att personaliseringen ska kunna börja.

### När kan jag börja titta på resultaten av min [!UICONTROL Auto-Target] aktivitet?

Du kan börja titta på resultatet av ditt [!UICONTROL Auto-Target] test när du har minst två upplevelser med modeller byggda (grön bock) för upplevelsen som har modeller skapade.

### Kan jag ange en specifik upplevelse som ska användas som kontroll?

Du kan välja en upplevelse som ska användas som kontroll när du skapar en [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) - (AP) eller [Auto-Target](/help/c-activities/auto-target-to-optimize.md) -aktivitet (AT).

Med den här funktionen kan du dirigera hela kontrolltrafiken till en viss upplevelse, baserat på den procentandel av trafikallokeringen som har konfigurerats i aktiviteten. Sedan kan ni utvärdera prestandarapparna för den personaliserade trafiken mot kontrolltrafiken till den upplevelsen.

Mer information finns i [Använda en viss upplevelse som kontroll](/help/c-activities/t-automated-personalization/experience-as-control.md).

### Kan jag ändra målmåttet genom en Auto-Target-aktivitet? {#change-metric}

Vi rekommenderar inte att du ändrar målmåttet halvvägs genom en aktivitet. Även om det går att ändra målmåttet under en aktivitet med [!DNL Target] användargränssnittet bör du alltid starta en ny aktivitet. Vi garanterar inte vad som händer om du ändrar målmåttet i en aktivitet efter att den har körts.

Denna rekommendation gäller för [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target]och [!UICONTROL Automated Personalization] aktiviteter som använder antingen [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

### Kan jag använda alternativet Återställ rapportdata när jag kör en Auto-Target-aktivitet?

Du bör inte använda alternativet [!UICONTROL Reset Report Data] för [!UICONTROL Auto-Target] aktiviteter. Även om det tar bort synliga rapportdata tas inte alla utbildningsposter bort från [!UICONTROL Auto-Target] modellen. I stället för att använda [!UICONTROL Reset Report Data] alternativet för [!UICONTROL Auto-Target] aktiviteter skapar du en ny aktivitet och inaktiverar den ursprungliga aktiviteten. (Obs! Denna vägledning gäller även [!UICONTROL Auto-Allocate] verksamhet och [!UICONTROL Automated Personalization] verksamhet.)

## Felsökning [!UICONTROL Auto-Target] {#section_23995AB813F24525AF294D20A20875C8}

Ibland blir aktiviteterna inte som förväntat. Här är några potentiella utmaningar du kan ställas inför när du använder [!UICONTROL Auto-Target]och några förslag på lösningar.

**Min[!UICONTROL Auto-Target]aktivitet tar för lång tid att skapa modeller.**

Det finns flera ändringar av aktivitetsinställningarna som kan minska den förväntade tiden att skapa modeller, bland annat antalet upplevelser i din [!UICONTROL Auto-Target] aktivitet, trafiken till din webbplats och det valda framgångsmåttet.

**Lösning:** Granska din aktivitetskonfiguration och se om det finns några ändringar du vill göra för att förbättra hastigheten som modellerna bygger på.

* Om mätvärdet för framgång är RPV, kan du ändra till konvertering? Konverteringsaktiviteter kräver ofta mindre trafik för att skapa modeller. Du kommer inte att förlora aktivitetsdata om du ändrar resultatmåttet från RPV till konvertering.
* Når er framgångsstatistik långt ned i säljprocessen från era aktivitetsupplevelser? En lägre aktivitetskonverteringsgrad kommer att öka de trafikkrav som krävs för modeller att bygga, eftersom ett minsta antal konverteringar krävs.
* Finns det några upplevelser du kan släppa från din aktivitet? Om du minskar antalet upplevelser i en aktivitet minskar tiden för att skapa modeller.
* Finns det någon sida med högre trafik där den här aktiviteten skulle bli mer framgångsrik? Ju mer trafik och konverteringar ni har på er aktivitetsplats, desto snabbare blir modellerna.

**Min[!UICONTROL Auto-Target]aktivitet genererar ingen hiss.**

Det krävs fyra faktorer för att en AP-aktivitet ska kunna generera lyft:

* Erbjudandena måste vara tillräckligt olika för att påverka besökarna.
* Erbjudandena måste finnas någonstans som gör skillnad för optimeringsmålet.
* Det skall finnas tillräckligt med trafik och statistisk &quot;effekt&quot; i provningen för att upptäcka hissen.
* Personaliseringsalgoritmen måste fungera bra.

**Lösning:** Kontrollera först att din aktivitet personaliserar trafik. Om du inte har skapat modeller för alla upplevelser är din [!UICONTROL Auto-Target] aktivitet fortfarande slumpvis tillgänglig för en stor del av besöken för att försöka skapa alla modeller så snabbt som möjligt. Om modeller inte byggs personaliserar [!UICONTROL Auto-Target] inte trafiken.

Se sedan till att erbjudandena och aktivitetsplatserna verkligen gör skillnad för den totala svarsfrekvensen med hjälp av ett enkelt, icke-personaliserat A/B-test. Se till att beräkna provstorlekarna i förväg för att säkerställa att det finns tillräckligt med kraft för att se en rimlig lyft och köra A/B-provningen under en fast varaktighet utan att stoppa den eller göra några ändringar. Om resultaten från ett A/B-test visar en statistiskt signifikant förbättring av en eller flera av upplevelserna är det troligt att en personaliserad aktivitet kommer att fungera. Personalisering kan förstås fungera även om det inte finns några skillnader i den totala svarsfrekvensen för upplevelserna. Vanligtvis beror problemet på att erbjudandena/platserna inte har tillräckligt stor inverkan på optimeringsmålet för att kunna identifieras med statistisk betydelse.

**Alla mätvärden som är beroende av konverteringsmått konverteras aldrig.**

Detta förväntas.

När ett konverteringsmått (vare sig optimeringsmål eller postmål) har konverterats i en [!UICONTROL Auto-Target] aktivitet frisläpps användaren från upplevelsen och aktiviteten startas om.

Det finns till exempel en aktivitet med ett konverteringsmått (C1) och ett ytterligare mått (A1). A1 är beroende av C1. När en besökare går in i aktiviteten för första gången och villkoren för konvertering av A1 och C1 inte konverteras, konverteras inte mätvärdena A1 på grund av beroendet av framgångsmått. Om besökaren konverterar C1 och sedan konverterar A1 konverteras A1 fortfarande inte eftersom besökaren släpps när C1 konverteras.

## Utbildningsvideo: Om ikonen ![Översikt över aktiviteter automatiskt i Target](/help/assets/overview.png)

I den här videon förklaras hur du konfigurerar en [!UICONTROL Auto-Target] A/B-aktivitet.

När du är klar med kursen bör du kunna:

* Definiera [!UICONTROL Auto-Target] testning
* Jämför och kontrast [!UICONTROL Auto-Target] med Automated Personalization
* Skapa [!UICONTROL Auto-Target] aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/18558)