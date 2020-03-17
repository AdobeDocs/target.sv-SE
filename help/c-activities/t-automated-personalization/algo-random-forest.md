---
keywords: Targeting
description: Målets huvudsakliga personaliseringsalgoritm som används i både Automated Personalization och Auto-Target är Random Forest. Ensemble-metoder som Slumpmässig skog använder flera inlärningsalgoritmer för att få bättre prediktiva prestanda än vad som kan uppnås med någon av de ingående inlärningsalgoritmerna. Algoritmen Random Forest i Automated Personalization är en klassifikations- eller regressionsmetod som fungerar genom att skapa en mängd beslutsträd när den tränas.
title: Slumpmässig skogsalgoritm
uuid: 35e4ca00-5c53-4fea-b0ef-0fb51c0f8184
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) Slumpmässig skogsalgoritm{#random-forest-algorithm}

Målets huvudsakliga personaliseringsalgoritm som används i både Automated Personalization och Auto-Target är Random Forest. Ensemble-metoder som Slumpmässig skog använder flera inlärningsalgoritmer för att få bättre prediktiva prestanda än vad som kan uppnås med någon av de ingående inlärningsalgoritmerna. Algoritmen Random Forest i Automated Personalization är en klassifikations- eller regressionsmetod som fungerar genom att skapa en mängd beslutsträd när den tränas.

När man tänker på statistik kan man komma ihåg en enda regressionsmodell som används för att förutsäga ett resultat. Den senaste datavetenskapliga forskningen tyder på att&quot;unika metoder&quot;, där flera modeller skapas från samma datauppsättning och sedan kombineras på ett intelligent sätt, ger bättre resultat än vad man kan förutsäga enbart utifrån en modell.

Algoritmen Random Forest är den viktigaste underliggande personaliseringsalgoritmen som används i Automated Personalization och Auto-Target-aktiviteter. Random Forest kombinerar hundratals beslutsträd för att komma fram till en bättre förutsägelse än ett enskilt träd.

## Vad är ett beslutsträd? {#section_7F5865D8064447F4856FED426243FDAC}

Målet för ett beslutsträd är att dela upp alla tillgängliga besöksdata som ett system kan lära sig av och sedan gruppera dessa data, där besöken inom varje grupp är så lika många som möjligt när det gäller målmåttet. Inom olika grupper skiljer sig dock besöken så mycket som möjligt när det gäller målmåttet (t.ex. konverteringsgraden). Beslutsträdet tittar på de olika variabler det har i utbildningsuppsättningen för att avgöra hur data ska delas upp i en MECE-väg (Mutually-Exclusive-Collectively-Exhaustive) i dessa grupper (eller &quot;löv&quot;) för att maximera detta mål.

I ett enkelt exempel antar vi att vi bara har två indatavariabler:

* Kön (med två möjliga värden: man eller kvinna)
* Postnummer (med fem möjliga värden i vår lilla datauppsättning: 11111, 2222, 3333, 4444 eller 5555)

Om vårt målmått är konvertering, skulle trädet först avgöra vilken av våra två variabler som förklarar den största variationen i besöksdatas konverteringsgrad.

Säg att postnummer är mest prediktivt. Den här variabeln utgör då den första &quot;grenen&quot; i trädet. Beslutsträdet skulle sedan avgöra hur besöksdata skulle delas upp, t.ex. konverteringsgraden för posterna inom varje delning var så lik som möjligt, och konverteringsgraden mellan delningarna var så olika som möjligt. I vårt exempel antar vi att 11111, 2222, 33333 är en delning och 4444 och 55555 är en andra delning.

Den här åtgärden skulle resultera i det första skiktet i vårt beslutsträd:

![](assets/decsion_tree_1.png)

Beslutsträdet frågar frågan:&quot;Vilken är den mest förutsägbara variabeln?&quot; I vårt exempel har vi bara två variabler, så svaret här är tydligt genus. Trädet kommer nu att försöka slutföra en liknande övning för att dela data *inom varje gren*. Först ska vi titta på grenarna 1111, 2222 och 33333. I dessa postnummer, om det finns en skillnad i konvertering mellan män och kvinnor, finns det två löv (män och kvinnor), och den här grenen skulle vara fullständig. I den andra grenen, 44444 och 5555, antar vi att det inte finns någon statistisk skillnad mellan hur kvinnor och män konverterar. I det här fallet blir den första grenen den sista delningen.

Vårt exempel skulle resultera i följande träd:

![](assets/decsion_tree_2.png)

## Hur används beslutsträd av Random Forest? {#section_536C105EF9F540C096D60450CAC6F627}

Beslutsträd kan vara ett kraftfullt statistiskt verktyg. De har dock vissa nackdelar. Kritiskt sett kan de&quot;överanpassa&quot; data så att ett enskilt träd inte förutser framtida data som inte har använts för att skapa det inledande trädet. Utmaningen kallas [avvikelsehandel](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff) inom statistisk inlärning. Slumpmässiga skogar hjälper till att övervinna denna överpassningsutmaning. På den högsta nivån är en slumpmässig skog en samling beslutsträd som byggts något annorlunda på samma datauppsättning som&quot;rösträtt&quot; tillsammans för att ge en bättre modell än ett enskilt träd. Träden byggs genom att man slumpmässigt väljer ut en deluppsättning besöksposter med ersättning (så kallad baging) och slumpmässigt väljer en deluppsättning av attributen, så att skogen består av något olika beslutsträd. Med den här metoden introduceras små variationer i de träd som skapas i den slumpmässiga skogen. Genom att lägga till den här kontrollerade variansmängden förbättras algoritmens prediktiva precision.

## Hur använder Target personaliseringsalgoritmer Slumpmässig skog? {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

**Så här bygger du modeller**

I följande diagram sammanfattas hur modeller byggs för Automatisk målanpassning eller Automatiserad personalisering:

![](assets/random_forest_flow.png)

1. Target samlar in data om besökare och levererar upplevelser/erbjudanden slumpmässigt
1. När Target når en kritisk datamassa utför det funktionskonstruktion
1. Target bygger slumpmässiga skogsmodeller för varje upplevelse/erbjudande
1. Målet kontrollerar om modellen uppfyller ett tröskelvärde för kvalitetspoäng
1. Target push the model to production to personalize future trafik

Target använder data som samlas in automatiskt, samt anpassade data som tillhandahålls av er, för att skapa sina personaliseringsalgoritmer. Dessa modeller förutser den bästa upplevelsen eller det bästa erbjudandet att visa för besökarna. I allmänhet skapas en modell per upplevelse (om det är en Automatisk målaktivitet) eller per erbjudande (om det är en automatiserad personaliseringsaktivitet). Sedan väljer Target att visa den upplevelse eller det erbjudande som ger det högsta förväntade framgångsmåttet (t.ex. konverteringsgrad). Dessa modeller måste utbildas i slumpmässigt utvalda besök innan de kan användas för förutsägelse. När en aktivitet börjar visas därför även de besökare som är i den personaliserade gruppen slumpmässigt olika upplevelser eller erbjudanden tills personaliseringsalgoritmerna är klara.

Varje modell måste valideras för att vara säker på att den är bra på att förutsäga besökarnas beteende innan den används i din aktivitet. Modellerna valideras utifrån deras AUC (arean under kurvan). På grund av behovet av validering beror den exakta tidpunkten då en modell kommer att börja leverera personaliserade upplevelser på detaljerna i informationen. I praktiken, och för trafikplaneringssyften, tar det vanligtvis mer än det minsta antalet konverteringar innan varje modell är giltig.

När en modell blir giltig för en upplevelse eller ett erbjudande ändras klockikonen till vänster om upplevelsen/erbjudandets namn till en grön kryssruta. När det finns giltiga modeller för minst två upplevelser/erbjudanden börjar vissa besök bli personaliserade.

**Funktionstransformering **

Innan data går igenom personaliseringsalgoritmen genomgår den en funktionsomformning, som man kan tänka sig som att de data som samlas in i utbildningsmaterialet förbereds för användning av personaliseringsmodellerna.

Funktionsomformningarna beror på attributtypen. Det finns främst två typer av attribut (eller&quot;funktioner&quot; som de ibland beskrivs av datavetare):

* **Kategorisisk:** Kategorifunktioner kan inte räknas men kan sorteras i olika grupper. De kan vara funktioner som land, kön eller postnummer.
* **Numeriskt:** Numeriska egenskaper kan mätas eller räknas, t.ex. ålder, intäkter osv.

För kategoriserade funktioner behålls en uppsättning med alla möjliga funktioner och sannolikhetsomformningen används för att minska datastorleken. För numeriska funktioner säkerställer omskalning att funktionerna är jämförbara över hela gränssnittet.

**Balancing Learning vs. Personalizing with the Multi-Armed Bandit**

Efter att Target har personaliseringsmodeller som har byggts för att personalisera trafiken finns det en tydlig kompromiss som ni kan hantera för framtida besökare i er verksamhet: bör ni personalisera all trafik baserat på den aktuella modellen eller bör ni fortsätta att lära er av nya besökare genom att slumpmässigt leverera slumpmässiga erbjudanden? Ni vill se till att personaliseringsalgoritmen alltid lär er om nya trender hos era besökare, samtidigt som ni personaliserar merparten av trafiken.

Flerarmsbanken är hur Target hjälper er att uppnå detta mål. Multiarm bandit ser till att modellen alltid&quot;spenderar&quot; en liten fraktionstrafik som fortsätter att lära sig under aktivitetens livstid och för att förhindra att tidigare inlärda trender utnyttjas i alltför stor utsträckning.

I datavetenskapen är MAB-problemet ett klassiskt exempel på utforsknings- och exploateringsproblemet där en samling enarmade banditer (med okänd sannolikhet för belöning) tas emot. Nyckelidén är att utveckla en strategi, vilket ger armen den största sannolikheten att lyckas så att den totala belöningen maximeras. Flerarmad bandit används i systemet när det är för onlinebedömning efter att onlinemodellerna har byggts. Detta hjälper till med onlineinlärning vid utforskandet. Den aktuella flerarmade algoritmen är epsilon (Δ) girig algoritm. I den här algoritmen, med sannolikhet 1- ‡, väljs den bästa armen. Och med sannolikheten Δväljs alla andra armar slumpmässigt.
