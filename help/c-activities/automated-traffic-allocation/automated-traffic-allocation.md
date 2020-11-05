---
keywords: automated traffic allocation;targeting;Increment Count and Keep User in Activity;traffic allocation
description: Automatisk tilldelning identifierar en vinnare bland två eller fler upplevelser och omfördelar automatiskt mer trafik till vinnaren för att öka antalet konverteringar medan testet fortsätter att köras och lära sig mer.
title: Automatisk allokering
feature: reports
topic: Standard
uuid: e8aee4d7-2b99-4e1f-8004-2efc820658b5
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '3344'
ht-degree: 0%

---


# Automatisk allokering - översikt

Automatisk tilldelning identifierar en vinnare bland två eller fler upplevelser och omfördelar automatiskt mer trafik till vinnaren för att öka antalet konverteringar medan testet fortsätter att köras och lära sig.

När du skapar en A/B-aktivitet med det guidade arbetsflödet i tre steg kan du välja [!UICONTROL Auto-Allocate to best experience] alternativet.

## Utmaningen {#section_85D5A03637204BACA75E19646162ACFF}

Standardtester av A/B har en inneboende kostnad. Man måste lägga ned trafik för att mäta prestanda för varje upplevelse och genom analyser ta fram den vinnande upplevelsen. Trafikfördelningen är fast även efter det att ni har insett att vissa upplevelser är bättre än andra. Det är dessutom komplicerat att ta reda på exempelstorleken, och aktiviteten måste gå hela kursen innan du kan agera på en vinnare. Efter att ha gjort allt detta finns det fortfarande en chans att den identifierade vinnaren inte är en riktig vinnare.

## Lösningen: Automatisk allokering {#section_98388996F0584E15BF3A99C57EEB7629}

Automatisk fördelning minskar kostnaderna och kostnaderna för att fastställa en vinnande upplevelse. Automatisk allokering övervakar målmätningsprestanda för alla upplevelser och skickar fler nya deltagare proportionellt till de högpresterande upplevelserna. Det finns tillräckligt med trafik för att utforska de andra upplevelserna. Du kan se fördelarna med testet på dina resultat, även när aktiviteten fortfarande körs: optimering sker parallellt med inlärning.

Automatisk tilldelning flyttar besökare mot vinnande upplevelser gradvis, i stället för att kräva att ni väntar tills en aktivitet upphör för att avgöra en vinnare. Ni tjänar på att lyfta snabbare eftersom aktivitetsdeltagare som skulle ha skickats till mindre framgångsrika upplevelser visas som potentiella vinnare.

Ett normalt A/B-test i Target visar endast parvisa jämförelser av utmanare med kontroll. Om en aktivitet till exempel har en upplevelse: A, B, C och D där A är kontrollen, skulle ett normalt A/B-test jämföra A mot B, A mot C och A mot D.

I sådana tester använder de flesta produkter, inklusive Target, en students t-test för att skapa p-value-based trust. Detta konfidensvärde används sedan för att avgöra om utmanaren är tillräckligt olik kontrollen. Target utför dock inte automatiskt de implicita jämförelser (B mot C, B mot D och C mot D) som krävs för att hitta den&quot;bästa&quot; upplevelsen. Därför måste marknadsföraren manuellt analysera resultaten för att fastställa den&quot;bästa&quot; upplevelsen.

Med Automatisk allokering utförs alla implicita jämförelser mellan upplevelser och skapar en&quot;sann&quot; vinnare. Det finns ingen uppfattning om&quot;kontroll&quot; i testet.

Automatisk allokering tilldelar nya besökare till upplevelser på ett intelligent sätt tills konfidensintervallet för den bästa upplevelsen inte överlappar den för någon annan upplevelse. Vanligtvis kan den här processen ge upphov till falska positiva resultat, men autoallokering använder konfidensintervall som baseras på [Bernstein-integriteten](https://en.wikipedia.org/wiki/Bernstein_inequalities_(probability_theory)) som kompenserar för upprepade utvärderingar. I nuläget har vi en sann vinnare. När autoallokering upphör, förutsatt att det inte finns något stort tidsberoende för besökare som kommer till sidan, finns det minst 95 % chans att autoallokering returnerar en upplevelse vars verkliga respons inte är sämre än 1 % (relativ) mindre än det verkliga svaret från den vinnande upplevelsen.

## Använd autofördelning jämfört med A/B eller Automated Personalization {#section_3F73B0818A634E4AAAA60A37B502BFF9}

* Använd **Automatisk fördelning** när du vill optimera din aktivitet från början och identifiera de vinnande upplevelserna så snabbt som möjligt. Genom att leverera högpresterande upplevelser oftare ökar den totala aktivitetsprestandan.
* Använd ett standardtest **[för](/help/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)** A/B när du vill karakterisera prestandan för alla upplevelser innan du optimerar webbplatsen. Ett A/B-test hjälper er att rangordna alla era upplevelser, medan Automated Traffic Allocation hittar de bästa resultaten men inte garanterar differentiering mellan de lägre prestandan.
* Använd [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) när du vill ha optimeringsalgoritmer av högsta komplexitet, till exempel maskininlärningsmodeller som bygger prognoser baserade på enskilda profilattribut. Automatiserad trafikallokering tittar på det sammanlagda beteendet för upplevelser (precis som standard-A/B-tester) och skiljer inte mellan besökarna.

## Viktiga fördelar {#section_0913BF06F73C4794862561388BBDDFF0}

* Bevarar skärpan i ett A/B-test
* Hittar en statistiskt signifikant vinnare snabbare än ett manuellt A/B-test
* Ger högre genomsnittlig kampanjlyft än ett manuellt A/B-test

## Terminologi {#section_670F8785BA894745B43B6D4BFF953188}

Följande termer är användbara när du diskuterar Automatisk allokering:

**Flerarmad bandit:** En [flerarmad bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit) -strategi för optimering balanserar det experimentella inlärningen och tillvaratagandet av det inlärningen.

## Så här fungerar algoritmen {#section_ADB69A1C7352462D98849F2918D4FF7B}

Den övergripande logiken bakom Automatisk allokering innefattar både uppmätta prestanda (t.ex. konverteringsgrad) och konfidensintervall för kumulativa data. Till skillnad från ett vanligt A/B-test där trafiken delas jämnt mellan upplevelser, ändrar Automatisk fördelning trafiktilldelningen mellan upplevelser.

* 80 % av besökarna tilldelas enligt den intelligenta logik som beskrivs nedan.
* 20 % av besökarna är slumpmässigt tilldelade till alla upplevelser för att anpassa sig till föränderligt besökarbeteende.

Den flerbeväpnade bankstrategin gör att vissa upplevelser blir fria att utforska samtidigt som upplevelserna som fungerar väl utnyttjas. Fler nya besökare får bättre prestanda samtidigt som de behåller möjligheten att reagera på förändrade förhållanden. Dessa modeller uppdateras minst en gång i timmen för att säkerställa att modellen reagerar på de senaste data.

När fler besökare går in i aktiviteten börjar vissa upplevelser bli mer framgångsrika och mer trafik skickas till de framgångsrika upplevelserna. 20 % av trafiken fortsätter att trafikeras slumpmässigt för att utforska alla upplevelser. Om en av de lågpresterande upplevelserna börjar prestera bättre tilldelas den upplevelsen mer trafik. Eller om framgången för en högpresterande aktivitet minskar, fördelas mindre trafik till den upplevelsen. Om en händelse till exempel får besökarna att leta efter olika uppgifter på mediewebbplatsen, eller om en helgförsäljning på din butikswebbplats ger olika resultat.

Följande bild visar hur algoritmen kan utföra ett test med fyra olika upplevelser:

![](assets/auto-allocate.png)

Bilden visar hur den trafik som tilldelats varje upplevelse fortskrider under flera omgångar av aktivitetens livstid tills en klar vinnare har fastställts.

| Ansökningstillfälle | Beskrivning |
|--- |--- |
| ![Varm rund](/help/c-activities/automated-traffic-allocation/assets/aa-phase-0.png) | **Varm rund (0)**: Under uppvärmningsomgången får varje upplevelse samma trafiktilldelning tills varje upplevelse i aktiviteten har minst 1 000 besökare och 50 konverteringar.<ul><li>Upplev A=25 %</li><li>Upplevelse B=25 %</li><li>Upplev C=25 %</li><li>Upplevelse D=25 %</li></ul>När varje upplevelse har fått 1 000 besökare och 50 konverteringar startar Target automatiserad trafiktilldelning. Alla allokeringar sker i runda och två upplevelser väljs ut för varje runda.<br>Endast två upplevelser går framåt i nästa runda: D och C.<br>Framgången innebär att de två upplevelserna fördelas lika mellan 80 % av trafiken, medan de två andra upplevelserna fortsätter att delta, men endast är en del av den 20 % slumpmässiga trafikfördelningen när nya besökare kommer in i aktiviteten.<br>Alla allokeringar uppdateras varje timme (visas med avrundningar längs x-axeln ovan). Efter varje omgång jämförs de kumulativa uppgifterna. |
| ![Ansökningstillfälle 1](/help/c-activities/automated-traffic-allocation/assets/aa-phase-1.png) | **Rund 1**: Under denna runda fördelas 80 % av trafiken till upplevelserna C och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt till upplevelserna A, B, C och D (5 % var). Under denna runda fungerar upplevelsen A bra.<ul><li>Algoritmen väljer upplevelsen D för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets lodräta skala).</li><li>Algoritmen väljer upplevelsen A för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna D och A går framåt. |
| ![Ansökningstillfälle 2](/help/c-activities/automated-traffic-allocation/assets/aa-phase-2.png) | **Rund 2**: Under denna runda fördelas 80 % av trafiken till upplevelserna A och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt, vilket innebär att A, B, C och D var och en får 5 % av trafiken. Under denna runda fungerar upplevelse B bra.<ul><li>Algoritmen väljer upplevelsen D för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets lodräta skala).</li><li>Algoritmen väljer upplevelsen B för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna D och B går framåt. |
| ![Ansökningstillfälle 3](/help/c-activities/automated-traffic-allocation/assets/aa-phase-3.png) | **Rund 3**: Under denna runda fördelas 80 % av trafiken till upplevelserna B och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt, vilket innebär att A, B, C och D var och en får 5 % av trafiken. Under denna runda fortsätter upplevelse D att fungera bra och upplevelsen C fungerar bra.<ul><li>Algoritmen väljer upplevelsen D för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets lodräta skala).</li><li>Algoritmen väljer upplevelsen C för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna D och C går framåt. |
| ![Ansökningstillfälle 4](/help/c-activities/automated-traffic-allocation/assets/aa-phase-4.png) | **Rund 4**: Under denna runda fördelas 80 % av trafiken till upplevelserna C och D (40 % vardera). 20 % av trafiken fördelas slumpmässigt, vilket innebär att A, B, C och D var och en får 5 % av trafiken. Under denna runda fungerar upplevelse C bra.<ul><li>Algoritmen väljer upplevelsen C för att gå vidare till nästa omgång eftersom den har den högsta konverteringsgraden (vilket anges i varje aktivitets lodräta skala).</li><li>Algoritmen väljer upplevelsen D för att gå vidare eftersom den har den högsta övre gränsen för Bernsteins 95-procentiga konfidensintervall för de återstående upplevelserna.</li></ul>Upplevelserna C och D går framåt. |
| ![Rund n](/help/c-activities/automated-traffic-allocation/assets/aa-phase-n.png) | **Rund n**: När aktiviteten utvecklas börjar en högpresterande upplevelse uppstå, och processen fortsätter tills det finns en vinnande upplevelse. När konfidensintervallet för den upplevelse som har den högsta konverteringsgraden inte överlappar andra upplevelsers konfidensintervall, kallas det vinnaren och ett [märke visas på aktivitetens sida](/help/c-activities/automated-traffic-allocation/determine-winner.md) och i aktivitetslistan.<ul><li>Algoritmen väljer upplevelsen C som klar vinnare</li></ul>I nuläget betjänar algoritmen 80 % av trafiken till upplevelsen C, medan 20 % av trafiken fortfarande betjänas slumpmässigt för alla upplevelser (A, B, C och D). C får totalt 85 % av trafiken. Om det osannolika skulle inträffa att vinnarens konfidensintervall börjar överlappa igen, kommer algoritmen att återgå till beteendet för runda 4 ovan.<br>**Viktigt**: Om du valde en vinnare manuellt tidigare i processen hade det varit enkelt att välja fel upplevelse. Av den anledningen är det bäst att vänta tills algoritmen bestämmer vinnarupplevelsen. |

>[!NOTE]
>
>Om en aktivitet bara har två upplevelser får båda upplevelserna samma trafik tills de [!DNL Target] hittar en vinnande upplevelse med 75 % förtroende. Då tilldelas vinnaren 2/3 av trafiken och 1/3 till förloraren. När upplevelsen når 95 % av förtroendet tilldelas vinnaren 90 % av trafiken och 10 % tilldelas förloraren. Vi upprätthåller alltid viss trafik som skickas till&quot;förlorande&quot; upplevelsen för att undvika falska positiva utfall i det långa loppet (d.v.s. bevara lite utforskande).

När en [!UICONTROL Auto-Allocate] aktivitet har aktiverats tillåts inte följande åtgärder från användargränssnittet:

* Växla läget&quot;Trafikallokering&quot; till&quot;Manuell&quot;
* Ändra målmåttstyp
* Ändra alternativ på panelen Avancerade inställningar

## Se hur Automatisk allokering fungerar

Mer information finns i [Automatisk allokering kan ge snabbare testresultat och högre intäkter än ett manuellt test](/help/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md)

## Caveats {#section_5C83F89F85C14FD181930AA420435E1D}

**Funktionen Automatisk allokering fungerar bara med en avancerad måttinställning: Öka antal och behåll användare i aktivitet**

Följande avancerade måttinställningar stöds inte: Ökningsantal, Frigör användare, Tillåt återinträde och ökning samt Frigör användare och fält från återinträde.

**Besökare som ofta återvänder kan öka konverteringsgraden.**

Om en besökare som ser upplevelsen A returnerar ofta och konverterar flera gånger, ökar konverteringsgraden (CR) för upplevelsen A artificiellt. Jämför detta med upplevelse B, där besökarna konverterar men inte återvänder ofta. Därför ser CR för A bättre ut än CR för B, så nya besökare är mer benägna att tilldelas A än B. Om du väljer att räkna en gång per deltagare kan CR för A och CR för B vara identiska.

Om besökarna är slumpmässigt utspridda är det troligare att deras inverkan på konverteringsgraden jämnas ut. Om du vill minska den här effekten bör du överväga att ändra metoden för målmåttet så att endast en gång per deltagare räknas.

**Skillnader mellan högpresterande, inte mellan lågpresterande.**

Automatisk fördelning är bra på att skilja mellan högpresterande upplevelser (och att hitta en vinnare). Det kan finnas tillfällen då ni inte har tillräckligt stor differentiering mellan de underpresterande upplevelserna.

Om du vill skapa statistiskt signifikanta skillnader mellan alla upplevelser kan du använda manuellt trafikallokeringsläge.

**Tidskorrelerade (eller sammanhangsberoende) konverteringsgrader kan förvränga allokeringsbelopp.**

Vissa faktorer som kan ignoreras under ett standard-A/B-test, eftersom de påverkar alla upplevelser lika, kan inte ignoreras i ett autoallokeringstest. Algoritmen är känslig för de konverteringsgrader som observeras. Nedan följer exempel på faktorer som kan påverka prestandan olika:

* Upplevelser med varierande kontextuella egenskaper (tid, plats, kön, osv.) relevans.

   Exempel:

   * &quot;Tack och lov att det är fredag&quot; resulterar i högre konverteringar på fredag
   * &quot;Snabbstart på måndag&quot; har högre konverteringsgrad på måndag
   * &quot;Redo för en öster-kustvinter&quot; ger större konvertering i öster-kusten eller vinterdrabbade platser

Dessa kan skeva resultaten i ett autofördelningstest mer än i ett A/B-test eftersom A/B-testet analyserar resultaten under en längre period.

* Upplevelser med varierande fördröjningar i konverteringen, möjligen på grund av meddelandets brådskande karaktär.

   &quot;30 % av försäljningen upphör idag&quot; signalerar till exempel att besökaren konverterar idag, men&quot;50 % rabatt på första köpet&quot; skapar inte samma känsla av snabbhet.

## Vanliga frågor {#section_0E72C1D72DE74F589F965D4B1763E5C3}

Se följande frågor och svar när du arbetar med [!UICONTROL Auto-Allocate] aktiviteter:

### Har Analytics for Target (A4T) stöd för Automatisk allokering av aktiviteter?

Ja. Mer information finns i [Analytics for Target (A4T)-stöd för Automatisk allokering av aktiviteter](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) när *aktiviteter skapas*.

### Omfördelas återkommande besökare automatiskt till högpresterande upplevelser?

Nej. Endast nya besökare tilldelas automatiskt. Återkommande besökare ser sin ursprungliga upplevelse. Detta skyddar A/B-testets giltighet.

### Hur behandlar algoritmen falska positiv?

Algoritmen garanterar 95 % konfidensgrad eller 5 % falskt positiv frekvens om du väntar tills vinnarmärket visas.

### När börjar den automatiska fördelningen av trafik?

Algoritmen börjar fungera efter att alla upplevelser i aktiviteten har minst 1 000 besökare och 50 konverteringar.

### Hur aggressivt utnyttjar algoritmen?

80 % av trafiken betjänas med autotilldelning och 20 % av trafiken betjänas slumpmässigt. När en vinnare har identifierats hamnar alla 80 % av trafiken på den, medan alla upplevelser fortsätter att få viss trafik som en del av 20 %, inklusive den vinnande upplevelsen.

### Visas förlorade upplevelser överhuvudtaget?

Ja. Den multiväpnade banken ser till att minst 20 % av trafiken reserveras för att utforska förändrade mönster eller konverteringsgrader för alla upplevelser.

### Vad händer med aktiviteter med långa konverteringsförseningar?

Så länge alla upplevelser som optimeras har liknande fördröjningar är beteendet detsamma som en aktivitet med snabbare konverteringscykel, även om det tar längre tid att nå tröskelvärdet på 50 konverteringar innan trafikallokeringsprocessen börjar.

### Hur skiljer sig Automatisk fördelning från Automated Personalization?

Automated Personalization använder varje besökares profilattribut för att fastställa den bästa upplevelsen. På så sätt optimeras inte bara aktiviteten, utan även personaliseras för användaren.

Auto-Allocate är å andra sidan ett A/B-test som skapar en sammanställd vinnare (den mest populära upplevelsen, men inte nödvändigtvis den mest effektiva upplevelsen för varje besökare).

### Ökar återkommande besökare konverteringsgraden på min framgångsstatistik?

För närvarande är logiken en fördel för besökare som snabbt konverterar eller besöker oftare. Detta beror på att besökarna tillfälligt ökar den totala konverteringsgraden för den upplevelse de tillhör. Algoritmen justerar sig ofta, så ökningen av konverteringsgraden förstärks vid varje ögonblicksbild. Om webbplatsen får många besökare kan deras konverteringar öka den totala konverteringsgraden för den upplevelse de tillhör. Det finns en bra möjlighet att återkommande besökare fördelas slumpmässigt, och i så fall jämnas den sammanlagda effekten (ökad lyft) ut. Om du vill minska den här effekten bör du överväga att ändra beräkningsmetoden för framgångsmåttet så att endast en gång per deltagare räknas.

### Kan jag använda beräkningsverktyget för provstorlek när jag använder Automatisk allokering för att beräkna hur lång tid aktiviteten tar för att identifiera vinnaren?

Du kan använda den befintliga [beräknaren](https://docs.adobe.com/content/target-microsite/testcalculator.html) för exempelstorlek för att få en uppskattning av hur länge testet kommer att köras. (Precis som vid traditionell A/B-testning ska du tillämpa Bonferroni-korrigering om du testar fler än två erbjudanden eller mer än ett konverteringsmått/-hypotes.) Observera att den här räknaren är utformad för traditionell A/B-testning med fast horisont och endast ger en uppskattning. Det är valfritt att använda beräkningsverktyget för en autoallokeringsaktivitet eftersom autoallokering deklarerar en vinnare åt dig - du behöver inte välja en fast tidpunkt för att kunna se testresultaten - de angivna värdena är alltid statistiskt giltiga. I våra experiment har vi hittat följande:
* När du testar exakt två upplevelser hittar Automatisk tilldelning en vinnare snabbare än en testning med fast horisont (d.v.s. den tidsram som anges av beräknaren för samplingsstorlek) när prestandaskalskillnaden mellan upplevelserna är stor, men det kan kräva extra tid för att identifiera en vinnare när prestandaskalskillnaden mellan upplevelserna är liten. I dessa fall skulle tester med fast horisont normalt ha avslutats utan ett statistiskt signifikant resultat.
* När du testar mer än två upplevelser hittar Automatisk tilldelning en vinnare snabbare än vid fasta tidsperioder (d.v.s. den tidsram som anges av beräknaren för provstorlek) när en upplevelse är helt perfekt för alla andra upplevelser. När två eller flera upplevelser båda&quot;vinner&quot; jämfört med andra upplevelser men är nära sammankopplade med varandra, kan Automatisk tilldelning kräva extra tid för att avgöra vilken som är bäst. I dessa fall skulle tester med fast horisont normalt ha avslutats genom att dra slutsatsen att de&quot;vinnande&quot; upplevelserna var bättre än de lågpresterande upplevelserna, men inte ha identifierat vilken som var bäst.

### Bör jag ta bort en underpresterande upplevelse från en autoallokeringsaktivitet för att snabba upp processen att fastställa en vinnare?

Det finns ingen anledning att ta bort en underpresterande upplevelse. Automatisk allokering ger automatiskt bättre prestanda och ger sämre prestanda. Att lämna en underpresterande upplevelse i aktiviteten påverkar inte i någon större utsträckning hastigheten för att avgöra en vinnare.

20 % av besökarna är slumpmässigt tilldelade till alla upplevelser. Mängden trafik som ger en underpresterande upplevelse är minimal (20 % dividerat med antalet upplevelser).

### Kan jag ändra målmåttet genom en autoallokeringsaktivitet? {#change-metric}

Vi rekommenderar inte att du ändrar målmåttet halvvägs genom en aktivitet. Även om det går att ändra målmåttet under en aktivitet med [!DNL Target] användargränssnittet bör du alltid starta en ny aktivitet. Vi garanterar inte vad som händer om du ändrar målmåttet i en aktivitet efter att den har körts.

Denna rekommendation gäller för [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target]och [!UICONTROL Automated Personalization] aktiviteter som använder antingen [!DNL Target] eller [!DNL Analytics] (A4T) som rapportkälla.

### Kan jag använda alternativet Återställ rapportdata när jag kör en autoallokeringsaktivitet?

Du bör inte använda alternativet [!UICONTROL Reset Report Data] för [!UICONTROL Auto-Allocate] aktiviteter. Även om det tar bort synliga rapportdata tas inte alla utbildningsposter bort från [!UICONTROL Auto-Allocate] modellen. I stället för att använda [!UICONTROL Reset Report Data] alternativet för [!UICONTROL Auto-Allocate] aktiviteter skapar du en ny aktivitet och inaktiverar den ursprungliga aktiviteten. (Obs! Denna vägledning gäller även [!UICONTROL Auto-Target] verksamhet och [!UICONTROL Automated Personalization] verksamhet.)

### Hur bygger Automatisk tilldelning modeller med hänsyn till miljöer?

[!UICONTROL Auto-Allocate] bygger modeller som bygger på trafik- och konverteringsbeteenden som registreras endast i standardmiljön. Som standard är [!UICONTROL Production] standardmiljön, men den kan ändras i [Måladministration > Miljöer](/help/administrating-target/environments.md).

Om en träff inträffar i en annan (icke-standardmiljö) kommer trafiken att fördelas enligt det observerade konverteringsbeteendet i standardmiljön. Resultatet av den träffen (konvertering eller icke-konvertering) registreras för rapportändamål men beaktas inte i [!UICONTROL Auto-Allocate] modellen.

När du väljer en annan miljö visar rapporten trafik och konverteringar för den miljön. Den standardmiljö som väljs för en rapport är alltid det kontoövergripande standardvärde som valts. Standardmiljön kan inte anges per aktivitet.

## Utbildningsvideor {#section_893E5B36DC4A415C9B1D287F51FCCB83}

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetsarbetsflöde - Målinriktning (2:14) ![självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller information om hur du ställer in trafikallokering.

* Tilldela en målgrupp till din aktivitet
* Begränsa trafiken uppåt eller nedåt
* Välj trafikallokeringsmetod
* fördela trafik mellan olika upplevelser

>[!VIDEO](https://video.tv.adobe.com/v/17385)

### Skapa A/B-tester (8:36) ![självstudiemärke](/help/assets/tutorial.png)

I den här videon visas hur du skapar ett A/B-test med det guidade arbetsflödet i tre steg för Target. Automatiserad trafikallokering diskuteras från 4:45.

* Skapa en A/B-aktivitet i Adobe Target
* Allokera trafik med manuell, delad eller automatisk trafikallokering

>[!VIDEO](https://video.tv.adobe.com/v/17391)
