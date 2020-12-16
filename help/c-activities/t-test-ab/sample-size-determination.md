---
keywords: AB;A/B;AB...n;sample size;sample size calculator;auto-allocate;auto allocate;calculator
description: Ett lyckat A/B-test kräver ett tillräckligt antal besökare (provstorlek) för att förbättra konverteringsgraden, men hur vet du hur länge ett A/B-test ska köras? Den här artikeln innehåller information om Automatisk allokering och Adobe Target Sample Size Calculator som hjälper dig att se till att din aktivitet har tillräckligt många besökare för att uppnå dina mål.
title: Hur länge ska du köra ett A/B-test?
feature: ab
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '3081'
ht-degree: 0%

---


# Hur länge ska du köra ett A/B-test?

En lyckad [!UICONTROL A/B Test]-aktivitet kräver ett tillräckligt antal besökare (provstorlek) för att förbättra konverteringsgraden, men hur vet du hur länge ett A/B-test ska köras? Den här artikeln innehåller information om [!UICONTROL Auto-Allocate]-aktiviteter och [!UICONTROL Adobe Target] Sample Size Calculator som hjälper dig att se till att din aktivitet har tillräckligt många besökare för att uppnå dina mål.

Det är frestande att stoppa en aktivitet om ett av erbjudandena fungerar mycket bättre eller sämre än de andra under de första dagarna i aktiviteten. När antalet observationer är lågt är det dock en stor sannolikhet att en positiv eller negativ lyft kan observeras av en slump, eftersom konverteringsgraden är ett medelvärde för ett lågt antal besökare. När aktiviteten samlar in fler datapunkter konvergerar konverteringsgraden till sina sanna långsiktiga värden.

>[!IMPORTANT]
>
>Att stoppa en aktivitet i förtid är en av de tio största fallgropar som kan uppstå när du utför A/B-tester. Mer information finns i [Tio vanliga A/B-testfall och hur du undviker dem](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md#concept_578A7947C9554868B30F12DFF9E3F8E3).

[!DNL Target] innehåller verktyg som hjälper dig att se till att din aktivitet har en tillräckligt stor samplingsstorlek för att du ska kunna uppnå dina konverteringsmål: Automatisk allokering.

## Allokera automatiskt {#auto-allocate}

En [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)-aktivitet är en typ av A/B-test som identifierar en vinnare bland två eller fler upplevelser och automatiskt omfördelar mer trafik till vinnaren för att öka konverteringarna medan testet fortsätter att köras och lära sig.

Standardtester av A/B har en inneboende kostnad. Ni måste spendera trafik för att mäta prestanda för varje upplevelse och med hjälp av analyser räkna ut den vinnande upplevelsen. Trafikfördelningen är fast även efter det att ni har insett att vissa upplevelser är bättre än andra. Det är dessutom komplicerat att ta reda på exempelstorleken, och aktiviteten måste gå hela kursen innan du kan agera på en vinnare. Efter att ha gjort allt detta finns det fortfarande en chans att den identifierade vinnaren inte är en riktig vinnare.

Lösningen är [!UICONTROL Auto-Allocate]. [!UICONTROL Auto-Allocate] minskar kostnaderna och kostnaderna för att fastställa en vinnande upplevelse. [!UICONTROL Auto-Allocate] övervakar målmätresultaten för alla upplevelser och skickar fler nya deltagare till högpresterande upplevelser proportionerligt. Det finns tillräckligt med trafik för att utforska de andra upplevelserna. Du kan se fördelarna med aktiviteten på dina resultat, även när aktiviteten fortfarande körs: optimering sker parallellt med inlärning.

[!UICONTROL Auto-Allocate] flyttar besökarna mot vinnande upplevelser gradvis i stället för att kräva att ni väntar tills en aktivitet upphör för att avgöra en vinnare. Ni tjänar på att lyfta snabbare eftersom aktivitetsdeltagare som skulle ha skickats till mindre framgångsrika upplevelser visas som potentiella vinnare.

När du använder funktionen [!UICONTROL Auto-Allocate] visar [!DNL Target] ett märke längst upp på aktivitetens sida som anger &quot;Ingen vinnare än&quot; tills aktiviteten når det minsta antalet konverteringar med tillräcklig säkerhet. [!DNL Target] deklarerar den vinnande upplevelsen genom att visa ett märke högst upp på aktivitetens sida.

Mer information finns i [Översikt över automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

## Beräkna exempelstorlek för Adobe Target {#section_6B8725BD704C4AFE939EF2A6B6E834E6}

Om du väljer att använda en manuell [!UICONTROL A/B Test]-aktivitet i stället för [!UICONTROL Auto-Allocate], kan du med [!DNL Target] Sample Size Calculator avgöra vilken provstorlek som behövs för att testet ska lyckas. Ett manuellt A/B-test är ett fast horisonttest, så beräkningsverktyget är mycket användbart. Det är valfritt att använda beräkningsverktyget för en [!UICONTROL Auto-Allocate]-aktivitet eftersom [!UICONTROL Auto-Allocate] deklarerar en vinnare åt dig. Beräkningsverktyget ger en ungefärlig uppskattning av den samplingsstorlek som behövs. Fortsätt läsa om du vill ha mer information om hur du använder beräkningsverktyget.

Gå till Adobe Target [exempel på storlekskalkylator](https://docs.adobe.com/content/target-microsite/testcalculator.html) innan du konfigurerar A/B-testet.

![Beräkna exempelstorlek för Adobe Target](/help/c-activities/t-test-ab/assets/sample_size_calculator-new.png)

Det är viktigt att fastställa en lämplig provstorlek (antal besökare) innan A/B-tester utförs för att fastställa den tid som aktiviteten ska köras innan resultaten utvärderas. Genom att helt enkelt övervaka aktiviteten tills statistisk signifikans uppnås, underskattas konfidensintervallet avsevärt, vilket gör testet otillförlitligt. Det intuitiva bakom detta resultat är att om ett statistiskt signifikant resultat påträffas stoppas testet och en vinnare deklareras. Om resultatet inte är statistiskt signifikant får testet dock fortsätta. Detta förfarande gynnar starkt det positiva resultatet, vilket ökar den falskt positiva frekvensen och därmed förvränger testets effektiva signifikansnivå.

Detta kan leda till ett stort antal falska positiva effekter, vilket leder till implementering av erbjudanden som inte ger en förväntad lyft på lång sikt. Dålig lyft i sig är ett otillfredsställande resultat, men en ännu allvarligare följd är att oförmågan att med tiden förutsäga lyft urholkar organisationens förtroende för att testa som en metod.

I den här artikeln beskrivs de faktorer som måste balanseras när en samplingsstorlek har bestämts, och en kalkylbladskalkylator som används för att beräkna en lämplig samplingsstorlek introduceras. Genom att beräkna provstorleken med hjälp av beräkningsverktyget för provstorlek (länken ovan) innan ett A/B-test börjar, säkerställs att du alltid kör A/B-tester av hög kvalitet som uppfyller statistiska standarder.

Det finns fem användardefinierade parametrar som definierar ett A/B-test. Dessa parametrar är sammanlänkade så att när fyra av dem är fastställda kan den femte beräknas:

* Statistisk betydelse
* Statistisk styrka
* Påvisbar minimihiss
* Baslinjekonvertering
* Antal besökare

För ett A/B-test fastställs analytikern av den statistiska signifikansen, statistisk styrka, minsta tillförlitliga lyft som kan detekteras och baslinjekonverteringsgraden, och därefter beräknas det antal besökare som krävs utifrån dessa värden. I den här artikeln beskrivs dessa element och riktlinjer för hur du fastställer dessa för ett specifikt test.

![](assets/samplesize.png)

Bilden nedan visar de fyra möjliga resultaten av ett A/B-test:

![](assets/outcomes.png)

Det är önskvärt att inte få några falska positiva eller falska negativ. Detta kan dock aldrig garanteras genom ett statistiskt test. Det är alltid möjligt att observerade trender inte är representativa för de underliggande konverteringssatserna. I ett test för att se om det var mer sannolikt att huvuden eller klave på ett mynt, även med ett rättvist mynt, skulle man kunna få tio huvuden på tio av slumpen. Den statistiska signifikansen och kraften hjälper oss att kvantifiera de falskt positiva och falska negativa frekvenserna och göra det möjligt för oss att hålla dem på rimliga nivåer för ett givet test.

### Statistisk signifikans {#section_8230FB9C6D1241D8B1786B72B379C3CD}

Betydelsenivån för ett test avgör hur sannolikt det är att testet rapporterar en betydande skillnad i konverteringsgraden mellan två olika erbjudanden när det i själva verket inte finns någon verklig skillnad. Detta kallas falskt positivt eller ett Type I-fel. Signaturnivån är ett tröskelvärde som anges av användaren och är en kompromiss mellan toleransen för falska positiva värden och antalet besökare som måste ingå i testet.

I ett A/B-test antas inledningsvis att båda erbjudandena har samma konverteringsgrad. Sannolikheten för det observerade resultatet beräknas sedan utifrån detta antagande. Om denna sannolikhet (p-värdet) är mindre än ett fördefinierat tröskelvärde (signifikansnivån), drar [!DNL Target] slutsatsen att det ursprungliga antagandet - att båda erbjudandena har samma konverteringsgrad - är felaktigt och därför är konverteringsgraden för A och B statistiskt annorlunda vid den givna signifikansnivån.

En vanlig signifikansnivå vid A/B-testning är 5%, vilket motsvarar en konfidensnivå på 95% (konfidensnivå = 100% - signifikansnivå). En konfidensnivå på 95 % innebär att varje gång du gör ett test finns det en 5-procentig risk för att upptäcka en statistiskt signifikant ökning, även om det inte finns någon skillnad mellan erbjudandena.

Typiska tolkningar av konfidensnivån sammanfattas i tabellen nedan:

| Konfidensnivå | Tolkning |
|--- |--- |
| &lt; 90=&quot;&quot;> | Inga bevis för att det finns någon skillnad mellan konverteringsgraden |
| 90-95 % | Svag bevisning för att det finns en skillnad mellan konverteringsgraden |
| 95-99 % | Måttliga bevis för att det finns en skillnad mellan konverteringsgraden |
| 99-99,9 % | Stabila bevis för att det finns en skillnad mellan konverteringsgraden |
| +99.9 % | Mycket starka bevis för att det finns en skillnad mellan konverteringsgraden |

Det rekommenderas att alltid använda en konfidensnivå på 95% eller högre.

Det är önskvärt att använda högsta möjliga konfidensnivå så att testet ger ett fåtal falskt positiva resultat. En högre konfidensnivå kräver dock ett större antal besökare, vilket ökar den tid som krävs för att göra testet. Dessutom leder en ökning av konfidensnivån till en minskning av den statistiska styrkan.

### Statistisk effekt {#section_1169C27F8E4643719D38FB9D6EBEB535}

Den statistiska effekten av ett A/B-test är sannolikheten att upptäcka en verklig skillnad i konverteringsgrad av en viss storlek. På grund av den slumpmässiga (stokastiska) typen av konverteringshändelser är det möjligt att en statistiskt signifikant skillnad inte observeras - bara av en slump - även om det finns en verklig skillnad i konverteringsgrad mellan de två erbjudandena. Detta kallas ett falskt negativ eller ett Type II-fel.

Statistisk effekt ignoreras ofta eftersom det inte krävs att fastställa statistisk effekt, till skillnad från statistisk signifikans, för att göra ett A/B-test. Genom att bortse från den statistiska styrkan finns det dock en stor risk för att faktiska skillnader mellan konverteringsgraden för olika erbjudanden inte kan identifieras vid testet eftersom urvalsstorleken är för liten. Detta leder till att testerna domineras av falskt positiva resultat.

Det är önskvärt att ha en hög statistisk styrka så att testet har en stor chans att identifiera en verklig skillnad i konverteringsgraden och ger färre falska negativ. Det krävs dock ett större antal besökare för att öka den statistiska förmågan att upptäcka en viss lyft, vilket ökar den tid som krävs för att utföra testet.

Ett vanligen använt värde för statistisk effekt är 80 %, vilket innebär att det finns en 80-procentig risk för att testet upptäcker en skillnad som motsvarar den minsta tillförlitliga lyften som kan detekteras. Testet har en lägre sannolikhet att upptäcka mindre hissar och en större sannolikhet att upptäcka större hissar.

### Minsta tillförlitliga lyft {#section_6101367EE9634C298410BBC2148E33A9}

De flesta organisationer vill mäta minsta möjliga skillnad i konverteringsgrad, eftersom även en liten ökning är värd att implementera. Om du vill att A/B-testet ska ha stor sannolikhet för att upptäcka en mycket liten hiss, är antalet besökare som måste ingå i testet oöverkomligt stort. Skälet till detta är att om skillnaden i konverteringsgrad är liten måste båda konverteringsgraden beräknas med stor noggrannhet för att identifiera skillnaden, vilket kräver ett stort antal besökare. Därför bör minsta tillförlitliga påkänningsbar lyft fastställas utifrån affärskraven med hänsyn till avvägningen mellan detektering av små hissar och körning av testet under längre tidsperioder.

Anta till exempel att två erbjudanden (A och B) har en konverteringsgrad på 10 % respektive 15 %. Om dessa erbjudanden visas för 100 besökare var finns det en 95-procentig chans att observera konverteringsgraden i intervallet 4 % till 16 % för erbjudandet A och 8 % till 22 % för erbjudandet B på grund av konverteringens statiska karaktär. Dessa intervall kallas konfidensintervall i statistiken. De representerar förtroendet för exaktheten i de uppskattade konverteringssatserna. Ju större urvalsstorlek (fler besökare) desto mer säker kan du vara på att uppskattningarna av konverteringsgraden är korrekta.

I figuren nedan visas dessa sannolikhetsfördelningar.

![](assets/probability_distributions.png)

På grund av den stora överlappningen mellan de två intervallen kan testet inte avgöra om konverteringsgraden är annorlunda. Därför kan detta test med 100 besökare inte skilja mellan de två erbjudandena. Men om vi exponerar erbjudandena för 5 000 besökare var finns det en 95-procentig risk för att den observerade konverteringsgraden kommer att sjunka mellan 9 % och 11 % respektive 14 % till 16 %.

![](assets/probability_distributions2.png)

I det här fallet är det mycket osannolikt att testet kommer att resultera i en felaktig slutsats, så testet med 5 000 besökare kan skilja mellan de två erbjudandena. Testet med 5 000 besökare har ett konfidensintervall på cirka +/-1 %. Det innebär att testet kan identifiera skillnader på cirka 1 %. Därför skulle ännu fler besökare behövas om den sanna konverteringsgraden för erbjudandena till exempel var 10 % och 10,5 % istället för 10 % och 15 %.

### Baslinjekonverteringsgrad {#section_39380C9CA3C649B6BE6E1F8A06178B05}

Baslinjekonverteringsgraden är konverteringsgraden för kontrollerbjudandet (erbjudande A). Ofta har ni en bra uppfattning om hur stor konverteringsgraden är för erbjudandet baserat på tidigare erfarenheter. Om så inte är fallet, till exempel på grund av att det är en ny typ av erbjudande eller kreativ, kan testet köras under en dag eller så för att få en ungefärlig uppskattning av den baslinjekonverteringsgrad som kan användas vid beräkningen av provstorleken.

### Antal besökare {#section_19009F165505429E95291E6976E498DD}

Det kan vara svårt att balansera kostnaden för att köra ett test under en längre tid med risken för falska positiva och falska negativa resultat. Det är tydligt att du inte vill fatta fel beslut, men att förlamas av för strikta eller stelbenta teststandarder är inte heller önskvärt.

Som en allmän riktlinje rekommenderas 95% konfidensnivå och 80% statistisk effekt.

Beräkningsverktyget för provstorlek (länk ovan) ber dig att bestämma den statistiska signifikansen (rekommendation: 95 %) och den statistiska styrkan (rekommendation: 80 %). Efter att baslinjekonverteringsgraden och dagstrafiken har angetts för alla erbjudanden visar kalkylbladet antalet besökare som krävs för att identifiera en lyft på 1 %, 2 %, 5 %, 10 %, 15 % och 20 % med en sannolikhet som motsvarar den angivna kraften i testet. I kalkylbladet kan användaren även ange en anpassad minimiuppsättning som kan identifieras på ett tillförlitligt sätt. Dessutom visar kalkylbladet antalet veckor som krävs för testet baserat på den trafiknivå som användaren angett. Det antal veckor som krävs avrundas uppåt till närmaste hela vecka för att undvika veckodagseffekter som påverkar resultaten.

Det finns en kompromiss mellan den minsta hiss som på ett tillförlitligt sätt kan identifieras av testet och det antal besökare som krävs. Figuren nedan, som gäller för en baslinjekonverteringsgrad (kontrollkonverteringsgrad) på 5 %, visar en kraftig minskning av avkastningen för att öka antalet besökare. Det minsta lyft som kan identifieras på ett tillförlitligt sätt förbättras avsevärt när de första besökarna läggs till i testet, men det tar allt fler besökare att förbättra testet. Figuren hjälper till att hitta en lämplig kompromiss mellan den tid som krävs för att köra testet (som bestäms av antalet besökare som krävs och platstrafiken) och den minsta lyft som kan identifieras tillförlitligt av testet.

![](assets/samplesizecontrol.png)

I det här exemplet kan du bestämma att det räcker att identifiera en lyft på 5 % (motsvarande en konverteringsgrad för det alternativa erbjudandet på (100 %+5 %)*5 % = 5,25 %) i 80 av 100 tester, så du behöver en provstorlek på 100 000 besökare för varje erbjudande. Om sajten har 20 000 besökare per dag och du testar två erbjudanden bör testet tillåtas köras i 2*100 000/20 000 = 10 dagar innan det går att avgöra om det alternativa erbjudandet statistiskt sett är betydligt bättre än kontrollerbjudandet.

Vi rekommenderar att den nödvändiga tiden alltid avrundas uppåt till närmaste hela vecka, så att veckodagens effekter undviks. I det här exemplet skulle testet därför köras i två veckor innan resultaten utvärderas.

### Intäkter per besök Mått {#section_C704C0861C9B4641AB02E911648D2DC2}

När du använder Intäkter per besök (RPV) som mätvärde läggs ytterligare en varianskälla till, eftersom RPV är produkten av intäkt per order och konverteringsgrad (RPV = Intäkter / #besökare = (Intäkt per order * #order) / # besökare = Intäkt per order * (#besökare * CTR) / #besökare = Intäkt per order * CTR), var och en med sin egen varians. Variansen i konverteringsgraden kan uppskattas direkt med hjälp av en matematisk modell, men variationen i intäkt per order är specifik för aktiviteten. Använd därför kunskap om denna avvikelse från tidigare aktiviteter eller kör A/B-testet under några dagar för att uppskatta intäktsavvikelsen. Avvikelsen beräknas utifrån värdena för Sum of Sales, Sum of Sales Squared och Number of Visitors som finns i CSV-nedladdningsfilen. När detta är fastställt använder du kalkylbladet för att beräkna den tid som krävs för att slutföra testet.

Beräkningsverktyget för exempelstorlek (länk ovan) kan hjälpa dig att konfigurera RPV-måttet. När du öppnar kalkylatorn visas en flik med namnet [!UICONTROL RPV Metric]. Du behöver följande information när du använder RPV-versionen av kalkylatorn:

* Antal besökare till kontrollerbjudandet
* Total intäkt för kontrollerbjudandet

   Kontrollera att filtret för extrem ordning är markerat.

* Summan av kvadratintäkter för kontrollerbjudandet

   Kontrollera att filtret för extrem ordning är markerat.

Generellt krävs 20-30 % längre för att få samma grad av statistisk konfidensnivå för samma nivå av uppmätt lyft när RPV används som mätvärde. Detta beror på att RPV har den extra variationen av olika orderstorlekar per konvertering. Detta bör beaktas när ni väljer mellan rak konverteringsgrad och RPV som det mätvärde som ligger till grund för ert slutliga affärsbeslut.

## Korrigering för att jämföra flera erbjudanden {#section_1474113764224D0B85472D8B023CCA15}

Varje gång du jämför två alternativ kan du få en falsk positiv effekt (observera en statistiskt signifikant skillnad även när det inte finns någon skillnad i konverteringsgrad) som är lika med signifikansnivån. Om det till exempel finns fem erbjudanden, A/B/C/D/E, och A är kontrollerbjudandet, görs fyra jämförelser (kontroll till B, kontroll till C, kontroll till D och kontroll till E), och sannolikheten för en falsk positiv är 18,5 % även om konfidensnivån är 95 % eftersom Pr(minst en falsk positiv) = 1 - Pr(ingen falsk positiv positiv) = 1 - 0,95 = 18,5 %. I detta sammanhang definieras falskt positivt som antingen den kontroll som rapporteras som bättre än det alternativ eller det alternativ som rapporteras som bättre än kontrollen när det faktiskt inte finns någon skillnad mellan dem.

## Slutsats {#section_AEA2427B90AE4E9395C7FF4F9C5CA066}

Genom att använda en [!UICONTROL Auto-Allocate]-aktivitet identifierar [!DNL Target] en vinnare bland två eller fler upplevelser och omfördelar automatiskt mer trafik till vinnaren för att öka antalet konverteringar medan testet fortsätter att köras och lära sig. [!UICONTROL Auto-Allocate] gör det enkelt att uppnå konverteringsmålen samtidigt som gissningsarbetet tas bort.

Genom att använda den exempelstorlekskalkylator (länk ovan) som introduceras i den här artikeln och låta testet köras under den tid som den föreslår, kan du se till att du alltid utför A/B-tester av hög kvalitet som följer de falska positiva och falska negativa frekvenserna som du har bestämt är lämpliga för det specifika testet. På så sätt kan du vara säker på att dina provningar är konsekventa och att du på ett tillförlitligt sätt kan upptäcka den hiss du är ute efter.
