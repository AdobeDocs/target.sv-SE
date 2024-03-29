---
keywords: automatiserad trafikallokering;mål;Öka antal och behåll användare i aktivitet;trafikallokering;automatisk allokering;automatisk allokering
description: Lär dig använda en [!UICONTROL Auto-Allocate] aktivitet i [!DNL Adobe Target] som identifierar en vinnare bland två eller fler upplevelser och automatiskt omfördelar mer trafik till vinnaren.
title: Vad är en [!UICONTROL Auto-Allocate] Aktivitet?
feature: Auto-Allocate
exl-id: 2d1ddd71-2ca6-4f00-9d0c-eb25ede8fdb8
source-git-commit: 1b1b2271738d12f8da4e695900b70e280f50d8cf
workflow-type: tm+mt
source-wordcount: '3452'
ht-degree: 0%

---

# [!UICONTROL Auto-Allocate] översikt

An [!UICONTROL Auto-Allocate] aktivitet i [!DNL Adobe Target] identifierar en vinnare bland två eller fler upplevelser och omfördelar automatiskt mer trafik till vinnaren för att öka antalet konverteringar medan testet fortsätter att köras och lära sig mer.

while [skapa en A/B-aktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) i det guidade arbetsflödet i tre steg väljer du **[!UICONTROL Auto-Allocate to best experience]** på **[!UICONTROL Targeting]** sida (steg 2).

## Utmaningen {#section_85D5A03637204BACA75E19646162ACFF}

Standardtester av A/B har en inneboende kostnad. Ni måste spendera trafik för att mäta prestanda för varje upplevelse och med hjälp av analyser räkna ut den vinnande upplevelsen. Trafikfördelningen är fast även efter det att ni har insett att vissa upplevelser är bättre än andra. Det är dessutom komplicerat att ta reda på exempelstorleken, och aktiviteten måste gå hela kursen innan du kan agera på en vinnare. Och det finns fortfarande en chans att den identifierade vinnaren inte är en riktig vinnare.

## Lösningen: [!UICONTROL Auto-Allocate] {#section_98388996F0584E15BF3A99C57EEB7629}

An [!UICONTROL Auto-Allocate] -aktiviteten minskar kostnaderna och kostnaderna för att fastställa en vinnande upplevelse. [!UICONTROL Auto-Allocate] övervakar målmätresultaten för alla upplevelser och skickar fler nya deltagare till högpresterande upplevelser proportionerligt. Det finns tillräckligt med trafik för att utforska de andra upplevelserna. Du kan se fördelarna med testet på dina resultat, även medan aktiviteten fortfarande körs: optimering sker parallellt med inlärning.

[!UICONTROL Auto-Allocate] flyttar besökarna mot vinnande upplevelser gradvis i stället för att kräva att ni väntar tills en aktivitet upphör för att avgöra en vinnare. Ni tjänar på att lyfta snabbare eftersom aktivitetsdeltagare som skulle ha skickats till mindre framgångsrika upplevelser visas som potentiella vinnare upplevelser.

Ett normalt A/B-test [!DNL Target] visar endast parvisa jämförelser av utmanare med kontrollen. Om en aktivitet till exempel har en upplevelse: A, B, C och D där A är kontrollen, är en normal [!DNL Target] A/B-test skulle jämföra A med B, A mot C och A mot D.

I sådana tester omfattar de flesta produkter, inklusive [!DNL Target], använd en [Welch&#39;s t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} för att skapa p-value-based trust. Detta konfidensvärde används sedan för att avgöra om utmanaren är tillräckligt olik kontrollen. Men [!DNL Target] utför inte automatiskt de implicita jämförelser (B mot C, B mot D och C mot D) som krävs för att hitta den&quot;bästa&quot; upplevelsen. Därför måste marknadsföraren manuellt analysera resultaten för att fastställa den&quot;bästa&quot; upplevelsen.

[!UICONTROL Auto-Allocate] utför alla implicita jämförelser mellan upplevelser och skapar en&quot;sann&quot; vinnare. Det finns ingen uppfattning om&quot;kontroll&quot; i testet.

[!UICONTROL Auto-Allocate] Tilldela på ett intelligent sätt nya besökare till upplevelser tills konfidensintervallet för den bästa upplevelsen inte överlappar konfidensintervallet för någon annan upplevelse. Vanligtvis kan den här processen ge upphov till falskt positiva effekter, men [!UICONTROL Auto-Allocate] använder konfidensintervall baserat på [Bernstein Inequality](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29){target=_blank} som kompenserar för upprepade utvärderingar. I nuläget finns det en sann vinnare. När [!UICONTROL Auto-Allocate] stopp, förutsatt att det inte finns något större tidsberoende för besökarna som kommer till sidan, finns det minst 95 % chans att [!UICONTROL Auto-Allocate] returnerar en upplevelse vars verkliga svar inte är sämre än 1 % (relativ) än det verkliga svaret för den vinnande upplevelsen.

## När ska du använda [!UICONTROL Auto-Allocate] kontra [!UICONTROL A/B Test] eller [!UICONTROL Automated Personalization] verksamhet {#section_3F73B0818A634E4AAAA60A37B502BFF9}

* Använd **[!UICONTROL Auto-Allocate]** när ni vill optimera er aktivitet från början och identifiera de vinnande upplevelserna så snabbt som möjligt. Genom att leverera högpresterande upplevelser oftare ökar den totala aktivitetsprestandan.
* Använd en standard **[A/B-test](/help/main/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)** när ni vill karakterisera prestandan för alla upplevelser innan ni optimerar er webbplats. Ett A/B-test hjälper er att rangordna alla era upplevelser, medan [!UICONTROL Auto-Allocate] hittar topprestandare men inte säkerställer differentiering mellan de lägre presterande.
* Använd [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) när ni vill ha optimeringsalgoritmer av högsta komplexitet, till exempel modeller för maskininlärning som bygger upp prognoser baserade på enskilda profilattribut. [!UICONTROL Auto-Allocate] tittar på det samlade beteendet för upplevelser (precis som standard-A/B-tester) och skiljer inte mellan besökare.

## Viktiga fördelar med [!UICONTROL Auto-Allocate] {#section_0913BF06F73C4794862561388BBDDFF0}

* Bevarar skärpan i ett A/B-test
* Hittar en statistiskt signifikant vinnare snabbare än ett manuellt A/B-test
* Ger högre genomsnittlig kampanjlyft än ett manuellt A/B-test

## Terminologi {#section_670F8785BA894745B43B6D4BFF953188}

Följande termer är användbara vid diskussion [!UICONTROL Auto-Allocate]:

**Flerarmad bandit:** A [multiväpnad bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} en strategi för optimering som ger en balans mellan undersökande och utnyttjande av det inlärningen.

## Så här fungerar algoritmen {#section_ADB69A1C7352462D98849F2918D4FF7B}

Den övergripande logiken bakom [!UICONTROL Auto-Allocate] innehåller både uppmätta prestanda (t.ex. konverteringsgrad) och konfidensintervall för kumulativa data. Till skillnad från ett vanligt A/B-test där trafiken delas jämnt mellan upplevelser, [!UICONTROL Auto-Allocate] förändrar trafikfördelningen mellan upplevelser.

* 80 % av besökarna tilldelas enligt den intelligenta logik som beskrivs nedan.
* 20 % av besökarna är slumpmässigt tilldelade till alla upplevelser för att anpassa sig till föränderligt besökarbeteende.

Den flerbeväpnade bankstrategin gör att vissa upplevelser blir fria att utforska samtidigt som upplevelserna som fungerar väl utnyttjas. Fler nya besökare får bättre prestanda samtidigt som de behåller möjligheten att reagera på förändrade förhållanden. Dessa modeller uppdateras minst en gång i timmen för att säkerställa att modellen reagerar på de senaste data.

När fler besökare går in i aktiviteten börjar vissa upplevelser bli mer framgångsrika och mer trafik skickas till de framgångsrika upplevelserna. 20 % av trafiken fortsätter att trafikeras slumpmässigt för att utforska alla upplevelser. Om en av de lågpresterande upplevelserna börjar prestera bättre tilldelas den upplevelsen mer trafik. Eller om framgången för en högpresterande aktivitet minskar, fördelas mindre trafik till den upplevelsen. Om en händelse till exempel får besökarna att leta efter olika uppgifter på mediewebbplatsen, eller om en helgförsäljning på din butikswebbplats ger olika resultat.

Följande bild visar hur algoritmen kan fungera under ett test med fyra upplevelser (klicka för att expandera teckningen):

![autoallokera bild](assets/auto-allocate.png){width="600" zoomable="yes"}

Bilden visar hur den trafik som tilldelats varje upplevelse fortskrider under flera omgångar av aktivitetens livstid tills en klar vinnare har fastställts.

| Ansökningstillfälle | Beskrivning |
|--- |--- |
| ![Varm rund](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-0.png){width="200" zoomable="yes"} | **Varm rund (0)**: Under uppvärmningsomgången får varje upplevelse samma trafiktilldelning tills varje upplevelse i aktiviteten har minst 1 000 besökare och 50 konverteringar.<ul><li>Upplev A=25 %</li><li>Upplevelse B=25 %</li><li>Upplev C=25 %</li><li>Upplevelse D=25 %</li></ul>Efter att varje upplevelse fått 1 000 besökare och 50 konverteringar, [!DNL Target] startar automatisk trafikallokering. Alla allokeringar sker i runda och två upplevelser väljs ut för varje runda.<br>Det är bara två upplevelser som går vidare till nästa runda: D och C.<br>Framåt innebär att de två upplevelserna fördelas lika mellan 80 % av trafiken. De andra två upplevelserna fortsätter att delta, men får endast en del av den slumpmässiga trafiktilldelningen på 20 % när nya besökare kommer in i aktiviteten.<br>Alla allokeringar uppdateras varje timme (visas med avrundningar längs x-axeln ovan). Efter varje omgång jämförs de kumulativa uppgifterna. |
| ![Ansökningstillfälle 1](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-1.png){width="200" zoomable="yes"} | **Ansökningstillfälle 1**: Under denna runda fördelas 80 % av trafiken till upplevelserna C och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt till upplevelserna A, B, C och D (5 % var). Under denna runda fungerar upplevelsen A bra.<ul><li>Algoritmen väljer upplevelsen D för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets vertikala skala).</li><li>Algoritmen väljer upplevelsen A för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna D och A går framåt. |
| ![Ansökningstillfälle 2](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-2.png){width="200" zoomable="yes"} | **Ansökningstillfälle 2**: Under denna runda fördelas 80 % av trafiken till upplevelserna A och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt, vilket innebär att A, B, C och D var och en får 5 % av trafiken. Under denna runda fungerar upplevelse B bra.<ul><li>Algoritmen väljer upplevelsen D för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets vertikala skala).</li><li>Algoritmen väljer upplevelsen B för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna D och B går framåt. |
| ![Ansökningstillfälle 3](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-3.png){width="200" zoomable="yes"} | **Ansökningstillfälle 3**: Under denna runda fördelas 80 % av trafiken till upplevelserna B och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt, vilket innebär att A, B, C och D var och en får 5 % av trafiken. Under denna runda fortsätter upplevelse D att fungera bra och upplevelsen C fungerar bra.<ul><li>Algoritmen väljer upplevelsen D för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets vertikala skala).</li><li>Algoritmen väljer upplevelsen C för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna D och C går framåt. |
| ![Ansökningstillfälle 4](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-4.png){width="200" zoomable="yes"} | **Ansökningstillfälle 4**: Under denna runda fördelas 80 % av trafiken till upplevelserna C och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt, vilket innebär att A, B, C och D var och en får 5 % av trafiken. Under denna runda fungerar upplevelse C bra.<ul><li>Algoritmen väljer upplevelsen C för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets vertikala skala).</li><li>Algoritmen väljer upplevelsen D för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna C och D går framåt. |
| ![Rund n](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-n.png){width="200" zoomable="yes"} | **Ansökningstillfälle *n***: När aktiviteten utvecklas börjar en högpresterande upplevelse uppstå, och processen fortsätter tills det finns en vinnande upplevelse. När konfidensintervallet för upplevelsen med den högsta konverteringsgraden inte överlappar något annat upplevelseintervall, kallas det vinnaren. A [emblem visas på den vinnande aktivitetens sida](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) och i [!UICONTROL Activity] lista.<ul><li>Algoritmen väljer upplevelsen C som den tydliga vinnaren.</li></ul>I nuläget betjänar algoritmen 80 % av trafiken till upplevelsen C, medan 20 % av trafiken fortfarande betjänas slumpmässigt för alla upplevelser (A, B, C och D). C får totalt 85 % av trafiken. Om det osannolika skulle inträffa att vinnarens konfidensintervall börjar överlappa igen, kommer algoritmen att återgå till beteendet för runda 4 ovan.<P>**Viktigt**: Om du valde en vinnare manuellt tidigare i processen hade det varit enkelt att välja fel upplevelse. Av den anledningen är det bäst att vänta tills algoritmen bestämmer vinnarupplevelsen. |

>[!NOTE]
>
>Om en aktivitet bara har två upplevelser får båda upplevelserna samma trafik fram till [!DNL Target] hittar en vinnande upplevelse med 75 % självförtroende. Då fördelas två tredjedelar av trafiken till vinnaren och en tredjedel till förloraren. När upplevelsen når 95 % av förtroendet tilldelas vinnaren 90 % av trafiken och 10 % tilldelas förloraren. [!DNL Target] skickar alltid trafik till&quot;förlorande&quot; upplevelsen för att i slutänden undvika falska positiva resultat (d.v.s. upprätthålla utforskande).

Efter en [!UICONTROL Auto-Allocate] Aktiviteten aktiveras, följande åtgärder från Tjärna[!DNL]get-gränssnittet tillåts inte:

* Växla läget&quot;Trafikallokering&quot; till&quot;Manuell&quot;
* Ändra målmåttstyp
* Ändra alternativ i[!UICONTROL Advanced Settings]&quot;-panel

## Se hur Automatisk allokering fungerar

Mer information finns i [Automatisk allokering kan ge snabbare testresultat och högre intäkter än ett manuellt test](/help/main/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md).

## Caveats {#section_5C83F89F85C14FD181930AA420435E1D}

Tänk på följande när du arbetar med [!UICONTROL Auto-Allocate]:

### The [!UICONTROL Auto-Allocate] fungerar med endast en avancerad måttinställning: [!UICONTROL Increment Count and Keep User in Activity]

Följande avancerade måttinställningar stöds inte: [!UICONTROL Increment Count], [!UICONTROL Release User], [!UICONTROL Allow Reentry and Increment Count]och [!UICONTROL Release User and Bar from Reentry].

### Besökare som ofta återvänder kan öka upplevelsekonverteringsgraden.

Om en besökare som ser upplevelsen A returnerar ofta och konverterar flera gånger, ökar konverteringsgraden (CR) för upplevelsen A artificiellt. Jämför detta resultat med upplevelse B, där besökarna konverterar men inte återvänder ofta. Därför ser upplevelsen A bättre ut än upplevelsen B, så nya besökare är mer benägna att tilldelas A än B. Om du väljer att räkna en gång per deltagare kan CR för A och CR för B vara identiska.

Om besökarna är slumpmässigt utspridda är det troligare att deras inverkan på konverteringsgraden jämnas ut. Om du vill minska den här effekten bör du överväga att ändra metoden för målmåttet så att endast en gång per deltagare räknas.

### Skillnader mellan högpresterande, inte mellan lågpresterande.

[!UICONTROL Auto-Allocate] är bra på att skilja mellan högpresterande upplevelser (och att hitta en vinnare). Det kan finnas tillfällen då ni inte har tillräckligt stor differentiering mellan de underpresterande upplevelserna.

Om ni vill skapa statistiskt signifikanta skillnader mellan alla upplevelser kanske ni bör överväga att använda det manuella trafiktilldelningsläget.

### Tidskorrelerade (eller sammanhangsberoende) konverteringsgrader kan förvränga allokeringsbelopp.

Vissa faktorer som kan ignoreras under ett standard-A/B-test eftersom de påverkar alla upplevelser lika, kan inte ignoreras i en [!UICONTROL Auto-Allocate] aktivitet. Algoritmen är känslig för de konverteringsgrader som observeras.

Nedan följer exempel på faktorer som kan påverka prestandan olika:

* Upplevelser med varierande sammanhangsberoende relevans (tid, plats, kön och så vidare).

  Exempel:

   * &quot;Tack och lov att det är fredag&quot; resulterar i högre konverteringar på fredag.
   * &quot;Snabbstart på måndag&quot; har högre konverteringsgrad på måndag.
   * &quot;Redo för en vinter på östkusten&quot; ger högre konverteringsgrad i öster- och vinterdrabbade platser.

  Om du använder upplevelser med varierande kontextuell relevans kan du skeva resultatet i [!UICONTROL Auto-Allocate] testa mer än i ett A/B-test eftersom A/B-testet analyserar resultaten under en längre period.

* Upplevelser med varierande fördröjningar i konverteringen, möjligen på grund av meddelandets brådskande karaktär.

  &quot;30 % av försäljningen upphör idag&quot; signalerar till exempel att besökaren konverterar idag, men&quot;50 % rabatt på första köpet&quot; skapar inte samma känsla av snabbhet.

## Vanliga frågor {#section_0E72C1D72DE74F589F965D4B1763E5C3}

Se följande frågor och svar när du arbetar med [!UICONTROL Auto-Allocate] verksamhet:

### Gör [!UICONTROL Analytics for Target] Stöd för (A4T) [!UICONTROL Auto-Allocate] aktiviteter?

Ja. Mer information finns i [A4T-stöd för Automatisk allokering och Automatiskt mål-aktiviteter](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

### Omfördelas återkommande besökare automatiskt till högpresterande upplevelser?

Nej. Endast nya besökare tilldelas automatiskt. Återkommande besökare ser sin ursprungliga upplevelse för att skydda A/B-testets giltighet.

### Hur behandlar algoritmen falska positiva resultat?

Algoritmen garanterar 95 % konfidensgrad eller 5 % falskt positiv frekvens om du väntar tills vinnarmärket visas.

### När gör [!UICONTROL Auto-Allocate] Vill du tilldela trafik?

Algoritmen börjar fungera efter att alla upplevelser i aktiviteten har minst 1 000 besökare och 50 konverteringar.

### Hur aggressivt utnyttjar algoritmen?

80 % av trafiken betjänas med [!UICONTROL Auto-Allocate] och 20 % av trafiken sker slumpmässigt. När en vinnare har identifierats går 80 % av trafiken till det, medan alla upplevelser fortsätter att få viss trafik som en del av 20 %, inklusive den vinnande upplevelsen.

### Visas förlorade upplevelser överhuvudtaget?

Ja. Den multiväpnade banken ser till att minst 20 % av trafiken reserveras för att utforska förändrade mönster eller konverteringsgrader för alla upplevelser.

### Vad händer med aktiviteter med långa konverteringsförseningar?

Så länge alla upplevelser som optimeras har liknande fördröjningar är beteendet detsamma som en aktivitet med en snabbare konverteringscykel. Det tar dock längre tid att nå tröskelvärdet på 50 konverteringar innan trafikallokeringsprocessen börjar.

### Hur [!UICONTROL Auto-Allocate] skiljer från [!UICONTROL Automated Personalization]?

[!UICONTROL Automated Personalization] använder varje besökares profilattribut för att fastställa den bästa upplevelsen. På så sätt optimeras inte bara aktiviteten, utan även personaliseras för den användaren.

[!UICONTROL Auto-Allocate]å andra sidan är ett A/B-test som ger en sammanlagd vinnare (den mest populära upplevelsen, men inte nödvändigtvis den mest effektiva upplevelsen för varje besökare).

### Ökar återkommande besökare konverteringsgraden på min framgångsstatistik?

För närvarande gynnar logiken besökare som snabbt konverterar eller besöker besökare oftare eftersom besökarna tillfälligt ökar den totala konverteringsgraden för den upplevelse de tillhör. Algoritmen justerar sig ofta, så ökningen av konverteringsgraden förstärks vid varje ögonblicksbild. Om webbplatsen får många besökare kan deras konverteringar öka den totala konverteringsgraden för den upplevelse de tillhör. Det finns en bra möjlighet att återkommande besökare fördelas slumpmässigt, och i så fall jämnas den sammanlagda effekten (ökad lyft) ut. Om du vill minska den här effekten bör du överväga att ändra beräkningsmetoden för framgångsmåttet så att endast en gång per deltagare räknas.

### Kan jag använda beräkningsverktyget för provstorlek när jag använder [!UICONTROL Auto-Allocate] för att uppskatta hur lång tid det tar att identifiera vinnaren?

Du kan använda den befintliga [!DNL Adobe Target] [Beräkna samplingsstorlek](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) för att få en uppskattning av hur länge testet körs. (Precis som vid traditionell A/B-testning ska du tillämpa Bonferroni-korrigering om du testar fler än två erbjudanden eller mer än ett konverteringsmått/-hypotes.) Den här räknaren är utformad för traditionell A/B-testning med fast horisont och ger endast en uppskattning. Använda kalkylatorn för en [!UICONTROL Auto-Allocate] aktiviteten är valfri eftersom [!UICONTROL Auto-Allocate] förklarar en vinnare för dig. Du behöver inte välja en fast tidpunkt för att se på testresultaten. De angivna värdena är alltid statistiskt giltiga.

Intern [!DNL Adobe] Experimenten har hittat följande:

* När du testar exakt två upplevelser [!UICONTROL Auto-Allocate] hittar en vinnare snabbare än en testning med fast horisont (d.v.s. den tidsram som anges av beräknaren för provstorlek) när prestandaskalskillnaden mellan upplevelserna är stor. Men [!UICONTROL Auto-Allocate] kan kräva extra tid för att identifiera en vinnare när skillnaden mellan upplevelserna är liten. I dessa fall skulle tester med fast horisont normalt ha avslutats utan ett statistiskt signifikant resultat.
* När du testar mer än två upplevelser, [!UICONTROL Auto-Allocate] hittar en vinnare snabbare än en testning med fast horisont (d.v.s. den tidsram som anges av beräkningsverktyget för samplingsstorlek) när en upplevelse är helt perfekt för alla andra upplevelser. När två eller flera upplevelser både&quot;vinner&quot; mot andra upplevelser men är nära sammankopplade med varandra, [!UICONTROL Auto-Allocate] kan kräva extra tid för att avgöra vilken som är överlägsen. I dessa fall skulle tester med fast horisont normalt ha avslutats genom att dra slutsatsen att de&quot;vinnande&quot; upplevelserna var bättre än de lågpresterande upplevelserna, men inte ha identifierat vilken som var bäst.

### Ska jag ta bort en underpresterande upplevelse från en [!UICONTROL Auto-Allocate] för att snabba upp processen att fastställa en vinnare?

Det finns ingen anledning att ta bort en underpresterande upplevelse. [!UICONTROL Auto-Allocate] levererar automatiskt högpresterande upplevelser oftare och ger sämre prestanda. Att lämna en underpresterande upplevelse i aktiviteten påverkar inte i någon större utsträckning hastigheten för att avgöra en vinnare.

20 % av besökarna tilldelas slumpmässigt alla upplevelser. Mängden trafik som ger en underpresterande upplevelse är minimal (20 % delat med antalet upplevelser).

### Kan jag ändra målmåttet genom en [!UICONTROL Auto-Allocate] aktivitet? {#change-metric}

[!DNL Adobe] rekommenderar inte att du ändrar målmåttet på halvvägs genom en aktivitet. Även om det är möjligt att ändra målmåttet under en aktivitet med [!DNL Target] Gränssnittet, du bör alltid starta en ny aktivitet. [!DNL Adobe] garanterar inte vad som händer om du ändrar målmåttet i en aktivitet efter att den har körts.

Denna rekommendation gäller [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target]och [!UICONTROL Automated Personalization] aktiviteter som använder [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

### Kan jag ändra rapporteringskällan halvvägs genom en [!UICONTROL Auto-Allocate] aktivitet? {#change-reporting}

[!DNL Adobe] rekommenderar inte att du ändrar rapportkällan mitt i vägen genom en aktivitet. Även om det är möjligt att ändra rapportkällan (från [!DNL Target] till A4T eller tvärtom) under en aktivitet med [!DNL Target] Gränssnittet, du bör alltid starta en ny aktivitet. [!DNL Adobe] garanterar inte vad som händer om du ändrar rapportkällan i en aktivitet efter att den har körts.

Denna rekommendation gäller [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target]och [!UICONTROL Automated Personalization] aktiviteter som använder [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

### Kan jag använda [!UICONTROL Reset Report Data] alternativ när en [!UICONTROL Auto-Allocate] aktivitet?

Använda [!UICONTROL Reset Report Data] alternativ för [!UICONTROL Auto-Allocate] aktiviteter föreslås inte. Även om det tar bort synliga rapportdata, tas inte alla utbildningsposter bort från [!UICONTROL Auto-Allocate] modell. I stället för att använda [!UICONTROL Reset Report Data] alternativ för [!UICONTROL Auto-Allocate] skapar du en ny aktivitet och inaktiverar den ursprungliga aktiviteten. (Denna vägledning gäller även för [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] verksamhet.)

### Hur [!UICONTROL Auto-Allocate] bygga modeller med avseende på miljöer?

[!UICONTROL Auto-Allocate] bygger modeller som bygger på trafik- och konverteringsbeteenden som registreras endast i standardmiljön. Som standard [!UICONTROL Production] är standardmiljön, men standardmiljön kan ändras i [!DNL Target] ([Administration > Miljöer](/help/main/administrating-target/environments.md)).

Om en träff inträffar i en annan (icke-standardmiljö) fördelas trafiken enligt det observerade konverteringsbeteendet i standardmiljön. Resultatet av träffen (konvertering eller icke-konvertering) registreras för rapportändamål men beaktas inte i [!UICONTROL Auto-Allocate] modell.

När du väljer en annan miljö visar rapporten trafik och konverteringar för den miljön. Den standardmiljö som valts för en rapport är det kontoövergripande standardvärde som valts. Standardmiljön kan inte anges per aktivitet.

### Kan [!UICONTROL Auto-Allocate] Vill du att aktiviteten ska justera uppslagsfönstret under ett test för att överväga att ändra trender över tid?

Kan aktiviteten till exempel ta hänsyn till december-månaden för att avgöra hur trafiken ska fördelas, i stället för att titta på besöksdata från september (när testet inleddes)?

Nej, [!UICONTROL Auto-Allocate] tar hänsyn till hur hela aktiviteten fungerar.

### Gör [!UICONTROL Auto-Allocate] visa en vinnande upplevelse för en återkommande besökare om den vinnande upplevelsen skiljer sig från vad besökaren såg när han kvalificerade sig för aktiviteten?

[!UICONTROL Auto-Allocate] använder klisterlappsbeslut av samma skäl som [!UICONTROL A/B Test] aktiviteter är kladdiga. Trafiktilldelningen fungerar endast för nya besökare.

## Utbildningsvideor {#section_893E5B36DC4A415C9B1D287F51FCCB83}

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetsarbetsflöde - målinriktning (2:14) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller information om hur du ställer in trafikallokering.

* Tilldela en målgrupp till din aktivitet
* Begränsa trafiken uppåt eller nedåt
* Välj trafikallokeringsmetod
* Fördela trafik mellan olika upplevelser

>[!VIDEO](https://video.tv.adobe.com/v/17385)

### Skapa A/B-tester (8:36) ![Självstudiemärke](/help/main/assets/tutorial.png)

I den här videon visas hur du skapar ett A/B-test med det guidade arbetsflödet i tre steg för Target. [!UICONTROL Auto-Allocate] behandlas från 4:45.

* Skapa en A/B-aktivitet i [!DNL Adobe Target]
* Allokera trafik med manuell, delad eller automatisk trafikallokering

>[!VIDEO](https://video.tv.adobe.com/v/17391)
