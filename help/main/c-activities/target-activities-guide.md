---
keywords: aktivitetsguide;aktiviteter;aktivitet;aktivitetstyper;aktivitetsåtgärder
description: Hämta ett interaktivt PDF som beskriver de olika aktivitetstyperna i  [!DNL Adobe Target].
title: Vilka aktivitetstyper är tillgängliga i  [!DNL Target]?
feature: Activities
exl-id: fa62592d-230a-4388-94bb-d9bc3bdfe973
source-git-commit: 1e23c1170475869e2798e23551d63575031502b4
workflow-type: tm+mt
source-wordcount: '1413'
ht-degree: 0%

---

# [!DNL Target] aktivitetstyper

Hämta ett interaktivt PDF som beskriver de olika aktivitetstyperna i [!DNL Adobe Target].

>[!NOTE]
>
>Om du vill få en så bra upplevelse som möjligt och dela med andra hämtar du den interaktiva [Adobe Target Activity Guide PDF](/help/main/assets/activities_guide_82817.pdf).
>
>Den här artikeln innehåller ingen information om [[!UICONTROL Recommendations] aktiviteter](/help/main/c-recommendations/recommendations.md). Du kan dock inkludera rekommendationer inuti [!UICONTROL A/B Test]-, [!UICONTROL Auto-Allocate]-, [!UICONTROL Auto-Target]- och [!UICONTROL Experience Targeting] (XT)-aktiviteter. Mer information finns i [Recommendations som erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md). Den här funktionen kräver att du har en [Target Premium-licens](/help/main/c-intro/intro.md#premium).

## Vad gör den? {#section_4ECAACC68723402EB3649033190E1BBC}

| Typ av aktivitet | Information |
|--- |--- |
| Manuell [!UICONTROL A/B Test]<P>![ikon](/help/main/c-activities/assets/icon_ab.png) | Jämför två eller flera upplevelser för att se vilken upplevelse som förbättrar konverteringarna bäst under en förspecificerad testperiod.<P>Mer information finns i [A/B-test](/help/main/c-activities/t-test-ab/test-ab.md). |
| [!UICONTROL Auto-Allocate]<P>![Ikon för automatisk tilldelning](/help/main/c-activities/assets/icon_auto_allocate.png) | Identifierar en vinnare bland två eller fler upplevelser och dirigerar sedan om trafiken till den vinnande upplevelsen, vilket ökar konverteringsgraden när testet körs och lär sig.<P>Mer information finns i [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| [!UICONTROL Auto-Target]<P>![Ikon AT](/help/main/c-activities/assets/icon_auto_target.png) | Använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser och sedan leverera den mest skräddarsydda upplevelsen till besökare baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare.<P>Mer information finns i [Automatiskt mål för personaliserade upplevelser](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |
| [!UICONTROL Automated Personalization] (AP)<P>![Ikon-AP](/help/main/c-activities/assets/icon_ap.png) | Använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att kombinera specifika erbjudanden eller meddelanden och sedan matcha olika erbjudandevariationer för besökarna utifrån deras individuella kundprofiler.<P>Mer information finns i [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md). |
| [!UICONTROL Multivariate Test] (MVT)<P>![Ikon MVT](/help/main/c-activities/assets/icon_mvt.png) | Jämför kombinationer av erbjudanden mellan element på en sida för att se vilken kombination av erbjudanden som fungerar bäst för en viss målgrupp. Identifierar även vilket element på sidan som bäst förbättrar konverteringarna under en fördefinierad testperiod.<P>Mer information finns i [Multivariata test](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md). |
| Experience Targeting (XT)<P>![Ikon XT](/help/main/c-activities/assets/icon_xt.png) | Levererar innehåll till en viss målgrupp baserat på en uppsättning marknadsföringsdefinierade regler och kriterier.<P>Mer information finns i [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md). |

## Varför använder du den här typen av aktivitet? {#section_46A70DD7CE3448749E635DDF5EAFC131}

| Typ av aktivitet | Orsak |
|--- |--- |
| Manuell [!UICONTROL A/B Test] | Ett mycket kontrollerat experiment med trafikmätningar, uppdelat efter procenttal i stället för efter en regel, som gör att ni kan analysera testdata, få insikt om er målgrupp och avgöra vilken upplevelse som fungerar bäst. |
| [!UICONTROL Auto-Allocate] | Ett sätt att identifiera en vinnande upplevelse och justera trafiktilldelningen för att leverera den vinnande upplevelsen till besökarna så snabbt som möjligt, vilket ger snabbare och större konverteringsrisk. |
| [!UICONTROL Auto-Target] | Ett sätt att identifiera vinnarna bland flera olika upplevelser och sedan leverera den mest lämpliga upplevelsen till specifika besökare. Målinriktningen anpassas över tiden när besökarnas intressen ändras, eftersom algoritmen förutser besökarens benägenhet för konvertering för en viss upplevelse vid en viss tidpunkt. |
| [!UICONTROL Automated Personalization] (AP) | Ett sätt att personalisera en uppsättning erbjudanden (skapade eller fördefinierade, i element på en sida eller på flera sidor) och leverera kombinationer som fungerar bäst för att locka till sig specifika besökare. |
| [!UICONTROL Multivariate Testing] (MVT) | Ett sätt att visa flera erbjudanden i flera olika element och sedan testa de unika upplevelser som skapas samtidigt mot ett specifikt mål, vilket hjälper till att avgöra vilken elementvariation som är mest framgångsrik. En MVT-aktivitet kan också visa vilka element som har störst positiv eller negativ inverkan på besökarens interaktion. |
| [!UICONTROL Experience Targeting] (XT) | Ett sätt att rikta specifikt innehåll mot en viss målgrupp baserat på en uppsättning definierade allokeringsregler. |

## Vilken typ av marknadsförare ska använda för aktiviteten? {#section_A843D663D3E543FFB1A594266B560395}

| Typ av aktivitet | Marknadsföraren |
|--- |--- |
| Manuell [!UICONTROL A/B Test] | Är känd i statistik.<P>Har tid att vänta tills testperiodens slut för att analysera resultaten. |
| [!UICONTROL Auto-Allocate] | Har en kort tidsram.<P>Måste identifiera den bästa upplevelsen och leverera snabbt.<P>Vill kunna&quot;söka&quot; i resultaten när testet körs. |
| [!UICONTROL Auto-Target] | Har flera valbara upplevelser.<P>vill matcha upplevelser med specifika besökare vid rätt tidpunkt baserat på deras dynamiska och föränderliga profiler. |
| [!UICONTROL Automated Personalization] (AP) | Har ett eller flera erbjudanden.<P>vill skapa kombinationer av erbjudanden som ger optimala personaliserade upplevelser för specifika besökare i olika unika profiler och beteenden. |
| [!UICONTROL Multivariate Testing] (MVT) | Är känd i statistik.<P>Har ett eller flera erbjudanden.<P>Vill analysera konverteringstrender som relaterar till interaktioner för sidelement. |
| [!UICONTROL Experience Targeting] (XT) | Måste leverera en specifik upplevelse eller innehållsdel till en viss målgrupp. |

## Statistisk information {#section_22CF2D07DB054505AB5EC702B99A5BB0}

| Typ av aktivitet | Information |
|--- |--- |
| Manuell [!UICONTROL A/B Test] | Testet jämför varje utmanarupplevelse med en kontrollupplevelse och rankar sedan resultatet för alla upplevelser, vilket identifierar både en vinnande upplevelse och en förlorad upplevelse jämfört med kontrollen. |
| [!UICONTROL Auto-Allocate] | Testet ger en statistisk garanti på en riktig vinnare direkt och dirigerar sedan mer trafik till målgrupper som har större sannolikhet för konvertering med den vinnande upplevelsen. |
| [!UICONTROL Auto-Target] | Optimeringsmekanismen identifierar den relevanta publiken för varje upplevelse genom att visa ökningar och minskningar av lyft över tiden och innan den avgör vilken upplevelse som ska levereras till vilken besökare. Optimeringsmekanismen bygger på konverteringar, segment, parametrar och profilskript. Därifrån väljer mekanismen automatiskt vilken algoritm som ska användas för att generera en högre lyft och konverteringsgrad. |
| [!UICONTROL Automated Personalization] (AP) | Optimeringsmekanismen justerar ständigt vilka upplevelser som levereras till besökare baserat på nya besökares beteende och tidigare beteenden hos liknande besökare, och ett erbjudandes resultat mäts mot samtidiga kontrollgrupper. |
| [!UICONTROL Multivariate Testing] (MVT) | Testet hjälper till att identifiera den relativa påverkan som specifika element har på konverteringen. |
| [!UICONTROL Experience Targeting] (XT) | Metoden definierar regler som riktar sig antingen till en viss upplevelse eller ett visst innehållsavsnitt till en viss målgrupp. Kunderna kan göra uppdateringar på erfarenhetsnivå. |

## Fördelar och överväganden {#section_56C46ABEF7B945DDA0C1E6D714377123}

| Typ av aktivitet | Fördelar | Överväganden |
|--- |--- |--- |
| Manuell [!UICONTROL A/B Test] | A/B-vilan hjälper er att få en fullständig förståelse för hur varje upplevelse fungerar, bortom vilken upplevelse som fungerar bäst. | Om du i en [!UICONTROL A/B Test] tittar på testresultaten innan provstorleken har nåtts riskerar du att förlita dig på felaktiga resultat (du kan inte &quot;tjuvkika&quot; tidigare!).<P>Till skillnad från [!UICONTROL Auto-Allocate] förblir trafikdistributionen fast i ett A/B-test även när du känner igen att vissa upplevelser är bättre än andra.<P>Mer information om de effektivaste strategierna för [!UICONTROL A/B Test]-aktiviteter finns i [Hur länge ska du köra ett A/B-test](/help/main/c-activities/t-test-ab/sample-size-determination.md) och [Tio vanliga A/B-testfel och hur du undviker dem](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md). |
| [!UICONTROL Auto-Allocate] | [!UICONTROL Auto-Allocate] minskar kostnaden för ett vanligt A/B-test eftersom det har en högre total konverteringsgrad än ett manuellt A/B-test. Konverteringsgraden är högre eftersom [!UICONTROL Auto-Allocate] skjuter ut mer trafik till den mest presterande upplevelsen, vilket innebär att du kan dra nytta av den vinnande upplevelsen tidigare än i slutet av testperioden (du kan titta!). | [!UICONTROL Auto-Allocate] identifierar vinnaren men skiljer sig inte åt mellan förlorarna. Om du måste veta hur varje upplevelse fungerar är A/B-testning att föredra.<P>Funktionen [!UICONTROL Auto-Allocate] fungerar bara med en avancerad måttinställning, som är Öka antal och Behåll användare i aktivitet. Om du inte vill räkna antalet upprepade konverteringar bör du använda A/B-testning i stället. |
| [!UICONTROL Auto-Target] | Med [!UICONTROL Auto-Target] används maskininlärning på alla typer av upplevelser, inklusive flersidiga upplevelser. Med en [!UICONTROL Auto-Target]-aktivitet kan du även få värdet [!UICONTROL Automated Personalization] när du använder det välbekanta A/B-testarbetsflödet. | Om du med [!UICONTROL Auto-Target] vill ändra innehållet i dina erbjudanden ofta eller ofta behöver algoritmen tillräckligt med tid efter varje ändring för att kunna utnyttja vad den lär sig och leverera det innehållet till rätt besökare. |
| [!UICONTROL Automated Personalization] (AP) | Med [!UICONTROL Automated Personalization] kan du samla alla dina erbjudanden på ett och samma ställe, och algoritmen avgör den bästa kombinationen av erbjudanden. Ni behöver inte specificera eller bygga enskilda upplevelser. [!UICONTROL Automated Personalization] använder samma maskininlärningsalgoritmer som [!UICONTROL Auto-Target]. | När ni kombinerar flera olika erbjudanden sker en explosion i kombination, vilket leder till ett behov av en betydande mängd trafik. Algoritmen [!UICONTROL Automated Personalization] representerar många faktorer och kräver därför flest trafik.<P>[!UICONTROL Automated Personalization] kan inte använda rapporter i [Analytics för Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). |
| [!UICONTROL Multivariate Testing] (MVT) | Med [!UICONTROL Multivariate Testing] kan du testa flera element samtidigt. | En [!UICONTROL Multivariate Test] är tidskrävande, och på grund av de många variabler som spelas upp är det inte nödvändigtvis en vinnande upplevelse med tillförsikt.<P>Det är ofta en utmaning att nå den mängd trafik som krävs för att slutföra testet. Eftersom alla [!UICONTROL Multivariate Test]-experiment är helt faktoriella kan för många element på en gång snabbt lägga till upp till många möjliga kombinationer som måste testas.<P>Även en webbplats med ganska hög trafik kan ha problem med att slutföra ett test med mer än 25 kombinationer på en rimlig tid. |
| [!UICONTROL Experience Targeting] (XT) | Med [!UICONTROL Experience Targeting] kan du snabbt agera utifrån insikter som härleds från aktivitetsresultaten.<P>Om du till exempel har kört ett A/B-test där utmanaren inte utförde kontrollen, men resultatet visar att ett visst segment av besökare konverterades fyra gånger mer med utmanaren än de gjorde med kontrollen, kan du använda [!UICONTROL Experience Targeting] för att dirigera utmanarupplevelsen till just det segmentet. | [!UICONTROL Experience Targeting] tillåter inte att du styr den procentuella delningen av en upplevelse över flera målgrupper. |
