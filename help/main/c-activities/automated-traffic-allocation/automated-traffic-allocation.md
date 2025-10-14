---
keywords: automatiserad trafikallokering;mål;Öka antal och behåll användare i aktivitet;trafikallokering;automatisk allokering;automatisk allokering
description: Lär dig hur du använder en [!UICONTROL Auto-Allocate]-aktivitet i [!DNL Adobe Target]  som identifierar en vinnare bland två eller fler upplevelser och automatiskt omfördelar mer trafik till vinnaren.
title: Vad är en [!UICONTROL Auto-Allocate]-aktivitet?
feature: Auto-Allocate
exl-id: 2d1ddd71-2ca6-4f00-9d0c-eb25ede8fdb8
source-git-commit: 1b1b2271738d12f8da4e695900b70e280f50d8cf
workflow-type: tm+mt
source-wordcount: '3502'
ht-degree: 0%

---

# [!UICONTROL Auto-Allocate] - översikt

En [!UICONTROL Auto-Allocate]-aktivitet i [!DNL Adobe Target] identifierar en vinnare bland två eller fler upplevelser och omfördelar automatiskt mer trafik till vinnaren för att öka antalet konverteringar medan testet fortsätter att köras och lära sig.

När du [skapar en A/B-aktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) med det guidade arbetsflödet i tre steg, väljer du alternativet **[!UICONTROL Auto-Allocate to best experience]** på sidan **[!UICONTROL Targeting]** (steg 2).

## Utmaningen {#section_85D5A03637204BACA75E19646162ACFF}

Standardtester av A/B har en inneboende kostnad. Ni måste spendera trafik för att mäta prestanda för varje upplevelse och med hjälp av analyser räkna ut den vinnande upplevelsen. Trafikfördelningen är fast även efter det att ni har insett att vissa upplevelser är bättre än andra. Det är dessutom komplicerat att ta reda på exempelstorleken, och aktiviteten måste gå hela kursen innan du kan agera på en vinnare. Och det finns fortfarande en chans att den identifierade vinnaren inte är en riktig vinnare.

## Lösningen: [!UICONTROL Auto-Allocate] {#section_98388996F0584E15BF3A99C57EEB7629}

En [!UICONTROL Auto-Allocate]-aktivitet minskar den här kostnaden och de totala kostnaderna för att fastställa en vinnande upplevelse. [!UICONTROL Auto-Allocate] övervakar målmätningsprestanda för alla upplevelser och skickar fler nya deltagare proportionellt till de högpresterande upplevelserna. Det finns tillräckligt med trafik för att utforska de andra upplevelserna. Du kan se fördelarna med testet på dina resultat, även medan aktiviteten fortfarande körs: optimering sker parallellt med inlärning.

[!UICONTROL Auto-Allocate] flyttar besökare mot vinnande upplevelser gradvis, i stället för att kräva att du väntar tills en aktivitet avslutas för att avgöra en vinnare. Ni tjänar på att lyfta snabbare eftersom aktivitetsdeltagare som skulle ha skickats till mindre framgångsrika upplevelser visas som potentiella vinnare upplevelser.

Ett normalt A/B-test i [!DNL Target] visar endast parvisa jämförelser av utmanare med kontrollen. Om en aktivitet till exempel har upplevelser: A, B, C och D där A är kontrollen, skulle ett normalt [!DNL Target] A/B-test jämföra A med B, A mot C och A mot D.

I sådana tester använder de flesta produkter, inklusive [!DNL Target], en [Welch&#39;s t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} för att skapa ett p-value-baserat förtroende. Detta konfidensvärde används sedan för att avgöra om utmanaren är tillräckligt olik kontrollen. [!DNL Target] utför dock inte automatiskt de implicita jämförelser (B jämfört med C, B jämfört med D och C jämfört med D) som krävs för att hitta den bästa upplevelsen. Därför måste marknadsföraren manuellt analysera resultaten för att fastställa den&quot;bästa&quot; upplevelsen.

[!UICONTROL Auto-Allocate] utför alla implicita jämförelser mellan upplevelser och skapar en&quot;true&quot;-vinnare. Det finns ingen uppfattning om&quot;kontroll&quot; i testet.

[!UICONTROL Auto-Allocate] tilldelar nya besökare på ett intelligent sätt till upplevelser tills konfidensintervallet för den bästa upplevelsen inte överlappar konfidensintervallet för någon annan upplevelse. Vanligtvis kan den här processen generera falskt positiva resultat, men [!UICONTROL Auto-Allocate] använder konfidensintervall baserat på [Bernstein Innequality](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29){target=_blank} som kompenserar för upprepade utvärderingar. I nuläget finns det en sann vinnare. När [!UICONTROL Auto-Allocate] stoppas, förutsatt att det inte finns något stort tidsberoende för besökarna som kommer till sidan, finns det minst 95 % chans att [!UICONTROL Auto-Allocate] returnerar en upplevelse vars verkliga svar inte är sämre än 1 % (relativt) mindre än det verkliga svaret för den vinnande upplevelsen.

## När [!UICONTROL Auto-Allocate] ska användas jämfört med [!UICONTROL A/B Test] eller [!UICONTROL Automated Personalization] aktiviteter {#section_3F73B0818A634E4AAAA60A37B502BFF9}

* Använd **[!UICONTROL Auto-Allocate]** när du vill optimera din aktivitet från början och identifiera de vinnande upplevelserna så snabbt som möjligt. Genom att leverera högpresterande upplevelser oftare ökar den totala aktivitetsprestandan.
* Använd ett **[A/B-test](/help/main/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)** som standard när du vill karakterisera prestandan för alla upplevelser innan du optimerar webbplatsen. Ett A/B-test hjälper dig att rangordna alla dina upplevelser, medan [!UICONTROL Auto-Allocate] hittar topprestanda, men inte garanterar differentiering mellan de lägre prestandorna.
* Använd [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) när du vill ha optimeringsalgoritmer av högsta komplexitet, till exempel maskininlärningsmodeller som bygger förutsägelser baserat på enskilda profilattribut. [!UICONTROL Auto-Allocate] tittar på det sammanlagda beteendet för upplevelser (precis som standard-A/B-tester) och skiljer inte mellan besökare.

## Viktiga fördelar med [!UICONTROL Auto-Allocate] {#section_0913BF06F73C4794862561388BBDDFF0}

* Bevarar skärpan i ett A/B-test
* Hittar en statistiskt signifikant vinnare snabbare än ett manuellt A/B-test
* Ger högre genomsnittlig kampanjlyft än ett manuellt A/B-test

## Terminologi {#section_670F8785BA894745B43B6D4BFF953188}

Följande termer är användbara när du diskuterar [!UICONTROL Auto-Allocate]:

**Flerarmad bandit:** En [flerarmad bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank}-metod för optimering balanserar undersökande inlärning och utnyttjande av inlärningen.

## Så här fungerar algoritmen {#section_ADB69A1C7352462D98849F2918D4FF7B}

Den övergripande logiken bakom [!UICONTROL Auto-Allocate] innefattar både uppmätta prestanda (till exempel konverteringsgrad) och konfidensintervall för kumulativa data. Till skillnad från ett standard-A/B-test där trafiken delas jämnt mellan upplevelser, ändrar [!UICONTROL Auto-Allocate] trafiktilldelningen mellan upplevelser.

* 80 % av besökarna tilldelas enligt den intelligenta logik som beskrivs nedan.
* 20 % av besökarna är slumpmässigt tilldelade till alla upplevelser för att anpassa sig till föränderligt besökarbeteende.

Den flerbeväpnade bankstrategin gör att vissa upplevelser blir fria att utforska samtidigt som upplevelserna som fungerar väl utnyttjas. Fler nya besökare får bättre prestanda samtidigt som de behåller möjligheten att reagera på förändrade förhållanden. Dessa modeller uppdateras minst en gång i timmen för att säkerställa att modellen reagerar på de senaste data.

När fler besökare går in i aktiviteten börjar vissa upplevelser bli mer framgångsrika och mer trafik skickas till de framgångsrika upplevelserna. 20 % av trafiken fortsätter att trafikeras slumpmässigt för att utforska alla upplevelser. Om en av de lågpresterande upplevelserna börjar prestera bättre tilldelas den upplevelsen mer trafik. Eller om framgången för en högpresterande aktivitet minskar, fördelas mindre trafik till den upplevelsen. Om en händelse till exempel får besökarna att leta efter olika uppgifter på mediewebbplatsen, eller om en helgförsäljning på din butikswebbplats ger olika resultat.

Följande bild visar hur algoritmen kan fungera under ett test med fyra upplevelser (klicka för att expandera teckningen):

![autoallokera bild](assets/auto-allocate.png){width="600" zoomable="yes"}

Bilden visar hur den trafik som tilldelats varje upplevelse fortskrider under flera omgångar av aktivitetens livstid tills en klar vinnare har fastställts.

| Ansökningstillfälle | Beskrivning |
|--- |--- |
| ![Varm rund](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-0.png){width="200" zoomable="yes"} | **Varmrunda (0)**: Under uppvärmningsomgången tilldelas varje upplevelse lika mycket trafik tills varje upplevelse i aktiviteten har minst 1 000 besökare och 50 konverteringar.<ul><li>Upplev A=25 %</li><li>Upplevelse B=25 %</li><li>Upplev C=25 %</li><li>Upplevelse D=25 %</li></ul>När varje upplevelse har fått 1 000 besökare och 50 konverteringar startar [!DNL Target] automatisk trafikallokering. Alla allokeringar sker i runda och två upplevelser väljs ut för varje runda.<br>Bara två upplevelser går vidare till nästa runda: D och C.<br>Att gå framåt innebär att de två upplevelserna tilldelas 80 % av trafiken. De andra två upplevelserna fortsätter att delta, men får endast en del av den slumpmässiga trafiktilldelningen på 20 % när nya besökare kommer in i aktiviteten.<br>Alla allokeringar uppdateras varje timme (visas med avrundningar längs x-axeln ovan). Efter varje omgång jämförs de kumulativa uppgifterna. |
| ![Rund 1](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-1.png){width="200" zoomable="yes"} | **Rund 1**: Under denna runda tilldelas 80 % av trafiken till upplevelserna C och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt till upplevelserna A, B, C och D (5 % var). Under denna runda fungerar upplevelsen A bra.<ul><li>Algoritmen väljer upplevelsen D för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets vertikala skala).</li><li>Algoritmen väljer upplevelsen A för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna D och A går framåt. |
| ![Rund 2](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-2.png){width="200" zoomable="yes"} | **Rund 2**: Under denna runda tilldelas 80 % av trafiken till upplevelserna A och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt, vilket innebär att A, B, C och D var och en får 5 % av trafiken. Under denna runda fungerar upplevelse B bra.<ul><li>Algoritmen väljer upplevelsen D för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets vertikala skala).</li><li>Algoritmen väljer upplevelsen B för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna D och B går framåt. |
| ![Rund 3](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-3.png){width="200" zoomable="yes"} | **Rund 3**: Under denna runda tilldelas 80 % av trafiken till upplevelserna B och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt, vilket innebär att A, B, C och D var och en får 5 % av trafiken. Under denna runda fortsätter upplevelse D att fungera bra och upplevelsen C fungerar bra.<ul><li>Algoritmen väljer upplevelsen D för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets vertikala skala).</li><li>Algoritmen väljer upplevelsen C för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna D och C går framåt. |
| ![Rund 4](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-4.png){width="200" zoomable="yes"} | **Rund 4**: Under denna runda tilldelas 80 % av trafiken till upplevelserna C och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt, vilket innebär att A, B, C och D var och en får 5 % av trafiken. Under denna runda fungerar upplevelse C bra.<ul><li>Algoritmen väljer upplevelsen C för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets vertikala skala).</li><li>Algoritmen väljer upplevelsen D för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna C och D går framåt. |
| ![Rund n](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-n.png){width="200" zoomable="yes"} | **Rund *n***: När aktiviteten utvecklas börjar en högpresterande upplevelse uppstå och processen fortsätter tills det finns en vinnande upplevelse. När konfidensintervallet för upplevelsen med den högsta konverteringsgraden inte överlappar något annat upplevelseintervall, kallas det vinnaren. Ett [märke visas på den vinnande aktivitetens sida &#x200B;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) och i listan [!UICONTROL Activity].<ul><li>Algoritmen väljer upplevelsen C som den tydliga vinnaren.</li></ul>I nuläget betjänar algoritmen 80 % av trafiken till upplevelsen C, medan 20 % av trafiken fortfarande betjänas slumpmässigt för alla upplevelser (A, B, C och D). C får totalt 85 % av trafiken. Om det osannolika skulle inträffa att vinnarens konfidensintervall börjar överlappa igen, kommer algoritmen att återgå till beteendet för runda 4 ovan.<P>**Viktigt**: Om du valde en vinnare manuellt tidigare i processen hade det varit enkelt att välja fel upplevelse. Av den anledningen är det bäst att vänta tills algoritmen bestämmer vinnarupplevelsen. |

>[!NOTE]
>
>Om en aktivitet bara har två upplevelser får båda upplevelserna samma trafik tills [!DNL Target] hittar en vinnande upplevelse med 75 % förtroende. Då fördelas två tredjedelar av trafiken till vinnaren och en tredjedel till förloraren. När upplevelsen når 95 % av förtroendet tilldelas vinnaren 90 % av trafiken och 10 % tilldelas förloraren. [!DNL Target] skickar alltid viss trafik till den&quot;förlorade&quot; upplevelsen för att undvika falskt positiva resultat i slutet (d.v.s. upprätthålla utforskande).

När en [!UICONTROL Auto-Allocate]-aktivitet har aktiverats tillåts inte följande åtgärder från gränssnittet Taget:

* Växla läget&quot;Trafikallokering&quot; till&quot;Manuell&quot;
* Ändra målmåttstyp
* Ändra alternativ på panelen [!UICONTROL Advanced Settings]

## Se hur Automatisk allokering fungerar

Mer information finns i [Automatisk fördelning kan ge dig snabbare testresultat och högre intäkter än ett manuellt test](/help/main/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md).

## Caveats {#section_5C83F89F85C14FD181930AA420435E1D}

Tänk på följande information när du arbetar med [!UICONTROL Auto-Allocate]:

### Funktionen [!UICONTROL Auto-Allocate] fungerar bara med en avancerad måttinställning: [!UICONTROL Increment Count and Keep User in Activity]

Följande avancerade måttinställningar stöds inte: [!UICONTROL Increment Count], [!UICONTROL Release User], [!UICONTROL Allow Reentry and Increment Count] och [!UICONTROL Release User and Bar from Reentry].

### Besökare som ofta återvänder kan öka upplevelsekonverteringsgraden.

Om en besökare som ser upplevelsen A returnerar ofta och konverterar flera gånger, ökar konverteringsgraden (CR) för upplevelsen A artificiellt. Jämför detta resultat med upplevelse B, där besökarna konverterar men inte återvänder ofta. Därför ser upplevelsen A bättre ut än upplevelsen B, så nya besökare är mer benägna att tilldelas A än B. Om du väljer att räkna en gång per deltagare kan CR för A och CR för B vara identiska.

Om besökarna är slumpmässigt utspridda är det troligare att deras inverkan på konverteringsgraden jämnas ut. Om du vill minska den här effekten bör du överväga att ändra metoden för målmåttet så att endast en gång per deltagare räknas.

### Skillnader mellan högpresterande, inte mellan lågpresterande.

[!UICONTROL Auto-Allocate] är bra på att skilja mellan högpresterande upplevelser (och att hitta en vinnare). Det kan finnas tillfällen då ni inte har tillräckligt stor differentiering mellan de underpresterande upplevelserna.

Om ni vill skapa statistiskt signifikanta skillnader mellan alla upplevelser kanske ni bör överväga att använda det manuella trafiktilldelningsläget.

### Tidskorrelerade (eller sammanhangsberoende) konverteringsgrader kan förvränga allokeringsbelopp.

Vissa faktorer som kan ignoreras under ett standard-A/B-test eftersom de påverkar alla upplevelser lika, kan inte ignoreras i en [!UICONTROL Auto-Allocate]-aktivitet. Algoritmen är känslig för de konverteringsgrader som observeras.

Nedan följer exempel på faktorer som kan påverka prestandan olika:

* Upplevelser med varierande sammanhangsberoende relevans (tid, plats, kön och så vidare).

  Exempel:

   * &quot;Tack och lov att det är fredag&quot; resulterar i högre konverteringar på fredag.
   * &quot;Snabbstart på måndag&quot; har högre konverteringsgrad på måndag.
   * &quot;Redo för en vinter på östkusten&quot; ger högre konverteringsgrad i öster- och vinterdrabbade platser.

  Om du använder upplevelser med varierande kontextuell relevans kan du skeva resultatet i ett [!UICONTROL Auto-Allocate]-test mer än i ett A/B-test eftersom A/B-testet analyserar resultaten under en längre period.

* Upplevelser med varierande fördröjningar i konverteringen, möjligen på grund av meddelandets brådskande karaktär.

  &quot;30 % av försäljningen upphör idag&quot; signalerar till exempel att besökaren konverterar idag, men&quot;50 % rabatt på första köpet&quot; skapar inte samma känsla av snabbhet.

## Vanliga frågor {#section_0E72C1D72DE74F589F965D4B1763E5C3}

Ta del av följande frågor och svar när du arbetar med [!UICONTROL Auto-Allocate]-aktiviteter:

### Har [!UICONTROL Analytics for Target] (A4T) stöd för [!UICONTROL Auto-Allocate] aktiviteter?

Ja. Mer information finns i [Stöd för A4T för aktiviteter som automatisk allokering och automatisk målning](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

### Omfördelas återkommande besökare automatiskt till högpresterande upplevelser?

Nej. Endast nya besökare tilldelas automatiskt. Återkommande besökare ser sin ursprungliga upplevelse för att skydda A/B-testets giltighet.

### Hur behandlar algoritmen falska positiva resultat?

Algoritmen garanterar 95 % konfidensgrad eller 5 % falskt positiv frekvens om du väntar tills vinnarmärket visas.

### När börjar [!UICONTROL Auto-Allocate] allokera trafik?

Algoritmen börjar fungera efter att alla upplevelser i aktiviteten har minst 1 000 besökare och 50 konverteringar.

### Hur aggressivt utnyttjar algoritmen?

80 % av trafiken betjänas med [!UICONTROL Auto-Allocate] och 20 % av trafiken betjänas slumpmässigt. När en vinnare har identifierats går 80 % av trafiken till det, medan alla upplevelser fortsätter att få viss trafik som en del av 20 %, inklusive den vinnande upplevelsen.

### Visas förlorade upplevelser överhuvudtaget?

Ja. Den multiväpnade banken ser till att minst 20 % av trafiken reserveras för att utforska förändrade mönster eller konverteringsgrader för alla upplevelser.

### Vad händer med aktiviteter med långa konverteringsförseningar?

Så länge alla upplevelser som optimeras har liknande fördröjningar är beteendet detsamma som en aktivitet med en snabbare konverteringscykel. Det tar dock längre tid att nå tröskelvärdet på 50 konverteringar innan trafikallokeringsprocessen börjar.

### Hur skiljer sig [!UICONTROL Auto-Allocate] från [!UICONTROL Automated Personalization]?

[!UICONTROL Automated Personalization] använder varje besökares profilattribut för att fastställa den bästa upplevelsen. På så sätt optimeras inte bara aktiviteten, utan även personaliseras för den användaren.

[!UICONTROL Auto-Allocate] är å andra sidan ett A/B-test som skapar en sammanställd vinnare (den mest populära upplevelsen, men inte nödvändigtvis den mest effektiva upplevelsen för varje besökare).

### Ökar återkommande besökare konverteringsgraden på min framgångsstatistik?

För närvarande gynnar logiken besökare som snabbt konverterar eller besöker besökare oftare eftersom besökarna tillfälligt ökar den totala konverteringsgraden för den upplevelse de tillhör. Algoritmen justerar sig ofta, så ökningen av konverteringsgraden förstärks vid varje ögonblicksbild. Om webbplatsen får många besökare kan deras konverteringar öka den totala konverteringsgraden för den upplevelse de tillhör. Det finns en bra möjlighet att återkommande besökare fördelas slumpmässigt, och i så fall jämnas den sammanlagda effekten (ökad lyft) ut. Om du vill minska den här effekten bör du överväga att ändra beräkningsmetoden för framgångsmåttet så att endast en gång per deltagare räknas.

### Kan jag använda beräkningsverktyget för provstorlek när jag använder [!UICONTROL Auto-Allocate] för att beräkna hur lång tid det tar för aktiviteten att identifiera vinnaren?

Du kan använda den befintliga [!DNL Adobe Target] [beräkningen av provstorlek](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) för att få en uppskattning av hur länge testet körs. (Precis som vid traditionell A/B-testning ska du tillämpa Bonferroni-korrigering om du testar fler än två erbjudanden eller mer än ett konverteringsmått/-hypotes.) Den här räknaren är utformad för traditionell A/B-testning med fast horisont och ger endast en uppskattning. Det är valfritt att använda beräkningsverktyget för en [!UICONTROL Auto-Allocate]-aktivitet eftersom [!UICONTROL Auto-Allocate] deklarerar en vinnare åt dig. Du behöver inte välja en fast tidpunkt för att se på testresultaten. De angivna värdena är alltid statistiskt giltiga.

Följande interna [!DNL Adobe]-experiment har påträffats:

* När [!UICONTROL Auto-Allocate] testar exakt två upplevelser hittar  en vinnare snabbare än en testning med fast horisont (det vill säga den tidsram som anges av beräknaren för provstorlek) när prestandaskalskillnaden mellan upplevelserna är stor. [!UICONTROL Auto-Allocate] kan dock kräva extra tid för att identifiera en vinnare när prestandaskillnaden mellan upplevelserna är liten. I dessa fall skulle tester med fast horisont normalt ha avslutats utan ett statistiskt signifikant resultat.
* När [!UICONTROL Auto-Allocate] testar mer än två upplevelser hittar  en vinnare snabbare än en testning med fast horisont (d.v.s. den tidsram som anges av beräknaren för samplingsstorlek) när en upplevelse är helt oberoende av andra upplevelser. När två eller flera upplevelser båda är&quot;vinnande&quot; jämfört med andra upplevelser, men har en nära motsvarighet till varandra, kan [!UICONTROL Auto-Allocate] kräva extra tid för att avgöra vilken som är överlägsen. I dessa fall skulle tester med fast horisont normalt ha avslutats genom att dra slutsatsen att de&quot;vinnande&quot; upplevelserna var bättre än de lågpresterande upplevelserna, men inte ha identifierat vilken som var bäst.

### Ska jag ta bort en underpresterande upplevelse från en [!UICONTROL Auto-Allocate]-aktivitet för att snabba upp processen att fastställa en vinnare?

Det finns ingen anledning att ta bort en underpresterande upplevelse. [!UICONTROL Auto-Allocate] levererar automatiskt högpresterande upplevelser oftare och ger sämre prestanda. Att lämna en underpresterande upplevelse i aktiviteten påverkar inte i någon större utsträckning hastigheten för att avgöra en vinnare.

20 % av besökarna tilldelas slumpmässigt alla upplevelser. Mängden trafik som ger en underpresterande upplevelse är minimal (20 % delat med antalet upplevelser).

### Kan jag ändra målmåttet genom en [!UICONTROL Auto-Allocate]-aktivitet? {#change-metric}

[!DNL Adobe] rekommenderar inte att du ändrar målmåttet genom en aktivitet. Även om det går att ändra målmåttet under en aktivitet med användargränssnittet för [!DNL Target] bör du alltid starta en ny aktivitet. [!DNL Adobe] garanterar inte vad som händer om du ändrar målmåttet i en aktivitet efter att den har körts.

Den här rekommendationen gäller [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] aktiviteter som använder antingen [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

### Kan jag ändra rapportkällan mitt i vägen genom en [!UICONTROL Auto-Allocate]-aktivitet? {#change-reporting}

[!DNL Adobe] rekommenderar inte att du ändrar rapportkällan mitt i vägen genom en aktivitet. Även om det är möjligt att ändra rapportkällan (från [!DNL Target] till A4T eller tvärtom) under en aktivitet med [!DNL Target]-gränssnittet, bör du alltid starta en ny aktivitet. [!DNL Adobe] garanterar inte vad som händer om du ändrar rapportkällan i en aktivitet efter att den har körts.

Den här rekommendationen gäller [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] aktiviteter som använder antingen [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

### Kan jag använda alternativet [!UICONTROL Reset Report Data] när jag kör en [!UICONTROL Auto-Allocate]-aktivitet?

Du bör inte använda alternativet [!UICONTROL Reset Report Data] för [!UICONTROL Auto-Allocate]-aktiviteter. Även om synliga rapportdata tas bort, tas inte alla utbildningsposter bort från modellen [!UICONTROL Auto-Allocate]. I stället för att använda alternativet [!UICONTROL Reset Report Data] för [!UICONTROL Auto-Allocate]-aktiviteter skapar du en ny aktivitet och inaktiverar den ursprungliga aktiviteten. (Den här vägledningen gäller även för [!UICONTROL Auto-Target]- och [!UICONTROL Automated Personalization]-aktiviteter.)

### Hur bygger [!UICONTROL Auto-Allocate] modeller med hänsyn till miljöer?

[!UICONTROL Auto-Allocate] bygger modeller baserat på trafik- och konverteringsbeteenden som bara registrerats i standardmiljön. Som standard är [!UICONTROL Production] standardmiljön, men standardmiljön kan ändras i [!DNL Target] ([Administration > Miljöer](/help/main/administrating-target/environments.md)).

Om en träff inträffar i en annan (icke-standardmiljö) fördelas trafiken enligt det observerade konverteringsbeteendet i standardmiljön. Resultatet av den träffen (konvertering eller icke-konvertering) registreras för rapportändamål men beaktas inte i modellen [!UICONTROL Auto-Allocate].

När du väljer en annan miljö visar rapporten trafik och konverteringar för den miljön. Den standardmiljö som valts för en rapport är det kontoövergripande standardvärde som valts. Standardmiljön kan inte anges per aktivitet.

### Kan en [!UICONTROL Auto-Allocate]-aktivitet justera uppslagsfönstret under ett test för att överväga att ändra trender över tid?

Kan aktiviteten till exempel ta hänsyn till december-månaden för att avgöra hur trafiken ska fördelas, i stället för att titta på besöksdata från september (när testet inleddes)?

Nej, [!UICONTROL Auto-Allocate] utvärderar prestanda för hela aktiviteten.

### Visar [!UICONTROL Auto-Allocate] en vinnande upplevelse för en återkommande besökare om den vinnande upplevelsen skiljer sig från vad besökaren såg när han kvalificerade sig för aktiviteten?

[!UICONTROL Auto-Allocate] använder fast beslutsfattande av samma skäl som [!UICONTROL A/B Test]-aktiviteter är kladdiga. Trafiktilldelningen fungerar endast för nya besökare.

## Utbildningsvideor {#section_893E5B36DC4A415C9B1D287F51FCCB83}

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetsarbetsflöde - Målinriktning (2:14) ![Självstudiekurs](/help/main/assets/tutorial.png)

Den här videon innehåller information om hur du ställer in trafikallokering.

* Tilldela en målgrupp till din aktivitet
* Begränsa trafiken uppåt eller nedåt
* Välj trafikallokeringsmetod
* Fördela trafik mellan olika upplevelser

>[!VIDEO](https://video.tv.adobe.com/v/17385)

### Skapa A/B-tester (8:36) ![Självstudiemärke](/help/main/assets/tutorial.png)

I den här videon visas hur du skapar ett A/B-test med det guidade arbetsflödet i tre steg för Target. [!UICONTROL Auto-Allocate] diskuteras från 4:45.

* Skapa en A/B-aktivitet i [!DNL Adobe Target]
* Allokera trafik med manuell, delad eller automatisk trafikallokering

>[!VIDEO](https://video.tv.adobe.com/v/17391)
