---
keywords: slumpskog;beslutsträd;ap;Automated Personalization
description: Lär dig hur  [!DNL Adobe Target]  använder algoritmen Slumpmässig skog i både [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] aktiviteter.
title: Hur använder  [!DNL Target] algoritmen Slumpmässig skog?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
exl-id: 07a89525-4071-4434-ac96-c59a4f4422ad
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '1413'
ht-degree: 0%

---

# Slumpmässig skogsalgoritm

Den huvudsakliga personaliseringsalgoritmen som används i både (AP) och [!DNL Auto-Target]-aktiviteter är Slumpmässig skog. Ensemble-metoder, till exempel Slumpskog, använder flera olika inlärningsalgoritmer för att få bättre prediktiva prestanda än vad som kan uppnås med någon av de ingående inlärningsalgoritmerna. Algoritmen Slumpmässig skog i [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] är en klassificerings- eller regressionsmetod som fungerar genom att skapa en mängd beslutsträd när den tränas.

När man tänker på statistik kan man komma ihåg en enda regressionsmodell som används för att förutsäga ett resultat. Den senaste datavetenskapliga forskningen tyder på att&quot;unika metoder&quot;, där flera modeller skapas från samma datauppsättning och sedan kombineras på ett intelligent sätt, ger bättre resultat än vad man kan förutsäga enbart utifrån en modell.

Algoritmen Slumpmässig skog är den viktigaste underliggande personaliseringsalgoritmen som används i [!UICONTROL Automated Personalization]- och [!UICONTROL Auto-Target]-aktiviteter. Random Forest kombinerar hundratals beslutsträd för att uppnå en bättre förutsägelse än ett enskilt träd.

## Vad är ett beslutsträd? {#section_7F5865D8064447F4856FED426243FDAC}

Målet för ett beslutsträd är att dela upp alla tillgängliga besöksdata som ett system kan lära sig av och sedan gruppera dessa data, där besöken inom varje grupp är så lika många som möjligt med avseende på målmåttet. Inom olika grupper är besöken dock så olika som möjligt när det gäller målmåttet (till exempel konverteringsgraden). Beslutsträdet undersöker de olika variabler som det har i kursen för att fastställa hur data ska delas upp i en MECE-väg (Mutually Exclusive Collectively Exhaustive) i dessa grupper (eller &quot;löv&quot;) för att maximera detta mål.

I ett enkelt exempel antar vi två indatavariabler:

* Kön (med två möjliga värden: man eller kvinna)
* Postnummer (med fem möjliga värden i den lilla datauppsättningen: 1111, 2222, 3333, 4444 eller 5555)

Om målmåttet är konvertering avgör trädet först vilken av de två variablerna som förklarar den största variationen i besöksdatas konverteringsgrad.

Säg att postnummer är mest prediktivt. Den här variabeln utgör då den första &quot;grenen&quot; i trädet. Beslutsträdet skulle sedan avgöra hur besöksdata skulle delas upp, t.ex. konverteringsgraden för posterna inom varje delning var så lik som möjligt, och konverteringsgraden mellan delningarna var så olika som möjligt. I det här exemplet antas 1111, 2222, 33333 vara en delning och 44444 och 55555 är en andra delning.

Den här åtgärden resulterar i det första lagret i beslutsträdet:

![decsion_tree_1 image](assets/decsion_tree_1.png)

Beslutsträdet ställer frågan&quot;What is the most preditive variable?&quot; I det här exemplet finns det bara två variabler, så svaret här är tydligt genus. Trädet försöker nu slutföra en liknande övning för att dela data *inom varje gren*. Först ska vi titta på grenarna 1111, 2222 och 33333. I dessa postnummer, om det finns en skillnad i konvertering mellan män och kvinnor, finns det två löv (män och kvinnor), och den här grenen skulle vara fullständig. I de andra grenarna, 44444 och 5555, antar vi att det inte finns någon statistisk skillnad mellan hur kvinnor och män konverterar. I det här fallet blir den första grenen den sista delningen.

Exemplet skulle resultera i trädet nedan:

![decsion_tree_2 image](assets/decsion_tree_2.png)

## Hur används beslutsträd av Random Forest? {#section_536C105EF9F540C096D60450CAC6F627}

Beslutsträd kan vara ett kraftfullt statistiskt verktyg. De har dock vissa nackdelar. Kritiskt sett kan de&quot;överanpassa&quot; data så att ett enskilt träd inte förutser framtida data som inte har använts för att skapa det inledande trädet. Utmaningen kallas [avvikelse-handel](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff) inom statistisk inlärning. Slumpmässiga skogar hjälper till att övervinna denna överanpassning. På den högsta nivån är en slumpmässig skog en samling beslutsträd som byggts något annorlunda på samma datauppsättning som&quot;rösträtt&quot; tillsammans för att ge en bättre modell än ett enskilt träd. Träden byggs genom att man slumpmässigt väljer ut en deluppsättning av besöksposter med ersättning (så kallad baging) och slumpmässigt väljer en deluppsättning av attributen, så att skogen består av något olika beslutsträd. Med den här metoden introduceras små variationer i de träd som skapas i den slumpmässiga skogen. Genom att lägga till den här kontrollerade variansmängden förbättras algoritmens prediktiva precision.

## Hur använder personaliseringsalgoritmerna [!DNL Target] en slumpmässig skog? {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

### Hur modeller byggs

I följande diagram sammanfattas hur modeller skapas för [!UICONTROL Auto-Target]- och [!UICONTROL Automated Personalization]-aktiviteter:

![random_forest_flow-bild](assets/random_forest_flow.png){width="650" zoomable="yes"}

1. Target samlar in data om besökare och levererar upplevelser eller erbjudanden slumpmässigt
1. När [!DNL Target] har nått en kritisk datamängd utför [!DNL Target] funktionskonstruktion
1. [!DNL Target] bygger slumpmässiga skogsmodeller för varje upplevelse eller erbjudande
1. [!DNL Target] kontrollerar om modellen uppfyller ett tröskelvärde för kvalitetspoäng
1. [!DNL Target] flyttar modellen till produktion för att anpassa framtida trafik

[!DNL Target] använder data som samlas in automatiskt, och anpassade data som tillhandahålls av dig, för att skapa sina personaliseringsalgoritmer. Dessa modeller förutser den bästa upplevelsen eller det bästa erbjudandet att visa för besökarna. I allmänhet skapas en modell per upplevelse (om det är en [!UICONTROL Auto-Target]-aktivitet) eller per erbjudande (om det är en [!UICONTROL Automated Personalization]-aktivitet). [!DNL Target] visar sedan upplevelsen eller erbjudandet som ger det högsta förväntade framgångsmåttet (till exempel konverteringsgrad). Dessa modeller måste utbildas i slumpmässigt utvalda besök innan de kan användas för förutsägelse. När en aktivitet börjar visas därför även de besökare som är i den personaliserade gruppen slumpmässigt olika upplevelser eller erbjudanden tills personaliseringsalgoritmerna är klara.

Varje modell måste valideras för att vara säker på att den är bra på att förutsäga besökarnas beteende innan den används i din aktivitet. Modellerna valideras utifrån deras område under kurvan (AUC). På grund av behovet av validering beror den exakta tidpunkten då en modell börjar leverera personaliserade upplevelser på detaljerna i data. I praktiken, och för trafikplaneringssyften, tar det vanligtvis mer än det minsta antalet konverteringar innan varje modell är giltig.

När en modell blir giltig för en upplevelse eller ett erbjudande ändras klockikonen till vänster om upplevelsen/erbjudandets namn till en grön kryssruta. När det finns giltiga modeller för minst två upplevelser eller erbjudanden börjar vissa besök bli personaliserade.

### Omvandling av funktioner

Innan data går igenom personaliseringsalgoritmen genomgår den en funktionsomformning, som man kan tänka sig som att de data som samlas in i utbildningsmaterialet förbereds för användning av personaliseringsmodellerna.

Funktionsomformningarna beror på attributtypen. Det finns främst två typer av attribut (eller&quot;funktioner&quot; som de ibland beskrivs av datavetare):

* **Kategoriscal:** Kategoriserade funktioner kan inte räknas men kan sorteras i olika grupper. De kan vara funktioner som land, kön eller postnummer.
* **Numeriska:** Numeriska funktioner kan mätas eller räknas, t.ex. ålder, inkomster osv.

För kategoriserade funktioner behålls en uppsättning med alla möjliga funktioner och sannolikhetsomformningen används för att minska datastorleken. För numeriska funktioner säkerställer omskalning att funktionerna är jämförbara över hela gränssnittet.

### Balancing learning kontra personalizing with the multi-väpnad bandit

När [!DNL Target] har personaliseringsmodeller som har skapats för att personalisera din trafik finns det en tydlig kompromiss som du kan se för framtida besökare i din aktivitet. Ska ni personalisera all trafik baserat på den aktuella modellen eller ska ni fortsätta att lära er av nya besökare genom att slumpmässigt leverera slumpmässiga erbjudanden? Ni vill se till att personaliseringsalgoritmen alltid lär er om nya trender hos era besökare, samtidigt som ni personaliserar merparten av trafiken.

Flerarmsbanken är så [!DNL Target] hjälper dig att uppnå det här målet. Multiarm bandit säkerställer att modellen alltid &quot;spenderar&quot; en liten fraktionstrafik som kan fortsätta att lära sig under aktivitetens livstid och för att förhindra överutnyttjande av tidigare inlärda trender.

I datavetenskapen är problemet med beväpnade bandit ett klassiskt exempel på problemet med prospektering kontra exploatering där en samling enarmade banditer, var och en med okänd sannolikhet för belöning, ges. Nyckelidén är att utveckla en strategi, vilket ger armen den största sannolikheten att lyckas så att den totala belöningen maximeras. Flerarmad bandit används i systemet för onlinebedömning efter att onlinemodellerna har byggts. Denna process hjälper till med onlineinlärning vid utforskandet. Den aktuella flerarmade algoritmen är en epsilon (Δ) girig algoritm. I den här algoritmen, med sannolikhet 1- ‡, väljs den bästa armen. Och med sannolikheten Δväljs alla andra armar slumpmässigt.
