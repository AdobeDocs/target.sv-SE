---
keywords: automatiskt mål;mål;trafikallokering;vanliga frågor;frågor;felsökning;felsökning
description: Lär dig hur [!UICONTROL Auto-Target] aktivitet i [!DNL Target] levererar den mest skräddarsydda upplevelsen till varje besökare baserat på kundprofiler och beteendet hos liknande besökare.
title: Vad är en [!UICONTROL Auto-Target] Aktivitet?
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
source-git-commit: 3e567236b30db453e2cd1bbb7c92c58ae4528ff4
workflow-type: tm+mt
source-wordcount: '1850'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) [!UICONTROL Auto-Target] översikt

[!UICONTROL Auto-Target] verksamhet i [!DNL Adobe Target] använda avancerad maskininlärning för att välja bland flera högpresterande marknadsföringsdefinierade upplevelser för att personalisera innehåll och driva konverteringar. [!UICONTROL Auto-Target] levererar den mest skräddarsydda upplevelsen till varje besökare baserat på den enskilda kundprofilen och beteendet hos tidigare besökare med liknande profiler.

>[!NOTE]
>
>* [!UICONTROL Auto-Target] finns som en del av [!DNL Target Premium] lösning. Den här funktionen är inte tillgänglig i [!DNL Target Standard] utan [!DNL Target Premium] licens. Mer information om de avancerade funktionerna i den här licensen finns i [Mål Premium](/help/main/c-intro/intro.md).
>
>* [!UICONTROL Analytics for Target] (A4T) har stöd för [!UICONTROL Auto-Target] verksamhet. Mer information finns i [A4T-stöd för Automatisk allokering och Automatiskt mål-aktiviteter](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).


## Goda erfarenheter i verkligheten med Auto-Target {#success}

En stor klädhandlare använde nyligen en [!UICONTROL Auto-Target] med tio produktkategoribaserade upplevelser (plus slumpmässig kontroll) för att leverera rätt innehåll till varje besökare. &quot;[!UICONTROL Add to Cart]&quot; valdes som primärt optimeringsmått. De riktade upplevelserna hade en genomsnittlig ökning på 29,09 %. När du har skapat [!UICONTROL Auto-Target] aktiviteterna var satta till 90 % personaliserade upplevelser.

På bara tio dagar uppnåddes mer än 1 700 000 dollar i lyft.

Fortsätt läsa för att lära dig hur du använder [!UICONTROL Auto-Target] för att öka era intäkter.

## Översikt {#section_972257739A2648AFA7E7556B693079C9}

while [skapa en A/B-aktivitet med det guidade arbetsflödet i tre steg](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)kan du välja att tilldela trafik med [!UICONTROL Auto-Target For Personalized Experiences] alternativ:

![Automatisk målgruppsanpassning för personaliserade upplevelser](/help/main/c-activities/assets/auto-target-ui-new.png)

The [!UICONTROL Auto-Target] Med A/B-aktivitetsflödet kan ni utnyttja maskininlärning för att personalisera baserat på en uppsättning marknadsföringsdefinierade upplevelser med ett enda klick. [!UICONTROL Auto-Target] har utformats för att ge maximal optimering, jämfört med traditionell A/B-testning eller [!UICONTROL Auto Allocate]genom att avgöra vilken upplevelse som ska visas för varje besökare. Till skillnad från en A/B-verksamhet där målet är att hitta en enda vinnare, [!UICONTROL Auto-Target] avgör automatiskt den bästa upplevelsen för en viss besökare (baserat på hans eller hennes profil och annan sammanhangsbaserad information) för att leverera en mycket personaliserad upplevelse.

Lika med [!UICONTROL Automated Personalization], [!UICONTROL Auto-Target] använder [Slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), en ledande metod för datavetenskap som ger besökarna den bästa upplevelsen. För [!UICONTROL Auto-Target] kan anpassa sig till förändringar i besökares beteende, kan köras permanent för att ge lyft. Detta kallas ibland för &quot;alltid på&quot;-läge.

Till skillnad från en A/B-aktivitet där upplevelseallokeringen för en viss besökare är fast, [!UICONTROL Auto-Target] optimerar det angivna verksamhetsmålet för varje besök. Gilla in [!UICONTROL Auto Personalization], [!UICONTROL Auto-Target]Som standard reserverar en del av aktivitetens trafik som kontrollgrupp för att mäta lyft. Besökarna i kontrollgruppen får en slumpmässig erfarenhet av aktiviteten.

## Överväganden

Det finns ett antal viktiga saker att tänka på när du använder [!UICONTROL Auto-Target]:

* Du kan inte växla en specifik aktivitet från [!UICONTROL Auto-Target] till [!UICONTROL Automated Personalization]och vice versa.
* Du kan inte växla från [!UICONTROL Manual] trafiktilldelning (traditionell) [!UICONTROL A/B Test]) till [!UICONTROL Auto-Target]och vice versa när en aktivitet har sparats som utkast.
* En modell är byggd för att identifiera den personaliserade strategins prestanda jämfört med slumpvis betjänad trafik jämfört med att skicka all trafik till den övergripande vinnande upplevelsen. Den här modellen hanterar endast träffar och konverteringar i standardmiljön.

   Trafik från en andra uppsättning modeller byggs för varje modellgrupp (AP) eller upplevelse (AT). För var och en av dessa modeller beaktas träffar och konverteringar i alla miljöer.

   Förfrågningar hanteras med samma modell, oavsett miljö, men trafikens mångfald bör komma från standardmiljön för att säkerställa att den identifierade övergripande vinnande upplevelsen överensstämmer med verkliga beteenden.

* Använd minst två upplevelser.

## Terminologi {#section_A309B7E0B258467789A5CACDC1D923F3}

Följande termer är användbara vid diskussion [!UICONTROL Auto-Target]:

| Villkor | Definition |
|---|---|
| [Flerarmad bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | En flerarmad bandit-strategi för optimering balanserar undersökande inlärning och utnyttjande av det inlärningen. |
| [Slumpmässig skog](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Random Forest är en ledande maskininlärningsstrategi. I datavetenskapen är det en unik klassificering, eller regressionsmetod, som fungerar genom att skapa många beslutsträd baserade på besöks- och besöksattribut. Inom [!DNL Target]används Slumpmässig skog för att avgöra vilken erfarenhet som förväntas ha störst sannolikhet för konvertering (eller högsta intäkt per besök) för varje enskild besökare. |
| [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | Målet för Thompson Sampling är att fastställa vilken upplevelse som är bäst totalt sett (icke-personaliserad), samtidigt som man minimerar&quot;kostnaden&quot; för att hitta den upplevelsen. Thompson-urvalet väljer alltid en vinnare, även om det inte finns någon statistisk skillnad mellan två upplevelser. |

## Hur [!UICONTROL Auto-Target] Works {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Läs mer om underliggande data och algoritmer [!UICONTROL Auto-Target] och Automated Personalization via länkarna nedan:

| Villkor | Detaljer |
|--- |--- |
| [Slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Målets huvudsakliga personaliseringsalgoritm används i båda [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] är Slumpmässig skog. Ensemble-metoder som Slumpmässig skog använder flera inlärningsalgoritmer för att få bättre prediktiva prestanda än vad som kan uppnås med någon av de ingående inlärningsalgoritmerna. Algoritmen Slumpmässig skog i [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] verksamhet är en klassificering, eller regressionsmetod, som fungerar genom att en mängd beslutsträd byggs upp under utbildningens gång. |
| [Överför data för målets algoritmer för personalisering](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Det finns flera sätt att mata in data för [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] modeller. |
| [Datainsamling för målets personaliseringsalgoritmer](/help/main/c-activities/t-automated-personalization/ap-data.md) | Målets personaliseringsalgoritmer samlar automatiskt in olika data. |

## Bestämma trafikallokering {#section_AB3656F71D2D4C67A55A24B38092958F}

Beroende på vad din aktivitet har för mål kan du välja en annan trafikfördelning mellan kontroll och personaliserade upplevelser. Det bästa sättet är att fastställa det här målet innan du gör din aktivitet offentlig.

The [!UICONTROL Custom Allocation] I den nedrullningsbara listan kan du välja mellan följande alternativ:

* Utvärdera personaliseringsalgoritm
* Maximera personaliseringstrafiken
* Anpassad allokering

![Listruta för allokeringsmål](/help/main/c-activities/assets/split-new.png)

| Aktivitetsmål | Föreslagen trafikallokering | Överlåtelser |
|--- |--- |--- |
| **Utvärdera personaliseringsalgoritm (50/50)**: Om målet är att testa algoritmen ska du använda en 50/50-procentig delning av besökare mellan kontrollen och målalgoritmen. Denna delning ger den mest korrekta uppskattningen av hissen. Föreslagna för användning med&quot;slumpmässiga upplevelser&quot; som er kontroll. | 50 % kontroll/50 % personlig upplevelsedelning | <ul><li>Maximerar lyften mellan kontroll och personalisering</li><li>relativt färre besökare har en personaliserad upplevelse</li></ul> |
| **Maximera personaliseringstrafiken (90/10)**: Om ditt mål är att skapa en&quot;alltid på&quot;-aktivitet ska 10 % av besökarna ha kontrollen för att se till att det finns tillräckligt med data för att algoritmerna ska kunna fortsätta lära sig över tid. Observera att i utbyte mot personalisering av en större andel av trafiken har ni mindre precision i det exakta lyftet. Oavsett vilket mål du har är detta den rekommenderade trafikdelningen när du använder en specifik upplevelse som kontroll. | Det bästa sättet är att använda en 10-30 % kontroll/70-90 % personaliserad upplevelsedelning | <ul><li>Maximerar antalet besökare som har en personaliserad upplevelse</li><li>Maximerar lyft</li><li>Mindre noggrannhet vad hissen är för aktiviteten</li></ul> |
| **Anpassad allokering** | Dela procentandelen manuellt efter behov. | <ul><li>Du kanske inte uppnår det önskade resultatet. Om du är osäker kan du följa förslagen för något av de föregående alternativen</li></ul> |

Justera [!UICONTROL Control] i procent klickar du på ikonerna i [!UICONTROL Allocation] kolumn. Du kan inte minska kontrollgruppen till mindre än 10 %.

![Ändra automatiskt måltrafikallokering](/help/main/c-activities/assets/auto-target-control.png)

Du kan [välj en specifik upplevelse som ska användas som kontroll](/help/main/c-activities/t-automated-personalization/experience-as-control.md) Du kan också använda alternativet Slumpmässig upplevelse.

## När ska du välja [!UICONTROL Auto-Target] över [!UICONTROL Automated Personalization]? {#section_BBC4871C87944DD7A8B925811A30C633}

Det finns flera scenarier där du kanske föredrar att använda [!UICONTROL Auto-Target] över [!UICONTROL Automated Personalization]:

* Om ni vill definiera hela upplevelsen i stället för enskilda erbjudanden som automatiskt kombineras för att skapa en upplevelse.
* Om du vill använda hela uppsättningen [!UICONTROL Visual Experience Composer] (VEC)-funktioner som inte stöds av [!UICONTROL Auto Personalization]: den anpassade kodredigeraren, flera olika upplevelsemålgrupper med mera.
* Om du vill göra strukturella ändringar på sidan i olika upplevelser. Om du till exempel vill ordna om element på hemsidan [!UICONTROL Auto-Target] är lämpligare att använda än [!UICONTROL Automated Personalization].

## Vad gör [!UICONTROL Auto-Target] har gemensamma [!UICONTROL Automated Personalization]? {#section_2A601F482F9A44E38D4B694668711319}

### Algoritmen optimerar för ett positivt resultat vid varje besök.

* Algoritmen förutser besökarens benägenhet för konvertering (eller beräknade intäkter från konvertering) för att ge bästa möjliga upplevelse.
* En besökare är berättigad till en ny upplevelse vid slutet av en befintlig session (såvida inte besökaren är i kontrollgruppen, i vilket fall den upplevelse som besökaren tilldelas vid det första besöket förblir densamma för efterföljande besök).
* Under en session ändras inte förutsägbarheten, vilket ger en bättre visuell enhetlighet.

### Algoritmen anpassas till förändringar i besökarens beteende.

* Multiarm bandit säkerställer att modellen alltid &quot;spenderar&quot; en liten fraktionstrafik som kan fortsätta att lära sig under aktivitetens livstid och för att förhindra överutnyttjande av tidigare inlärda trender.
* De underliggande modellerna byggs om var 24:e timme med hjälp av de senaste besökarbeteendedata för att säkerställa att [!DNL Target] utnyttjar alltid de föränderliga besökarinställningarna.
* Om algoritmen inte kan avgöra vilka vinnande upplevelser individen har, växlar den automatiskt till att visa den övergripande prestandaoptimerade upplevelsen samtidigt som den fortsätter att leta efter personaliserade vinnare. Den bästa upplevelsen med [Thompson sampling](https://en.wikipedia.org/wiki/Thompson_sampling).

### Algoritmen optimerar kontinuerligt för ett enda målmått.

* Detta mätresultat kan vara konverteringsbaserat eller inkomstbaserat (mer specifikt) [!UICONTROL Revenue per Visit]).

### [!DNL Target] samlar automatiskt in information om besökare för att skapa personaliseringsmodeller.

* Mer information om parametrarna som används i [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization], se [Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md).

### [!DNL Target] använder automatiskt alla [!DNL Adobe Experience Cloud] delade målgrupper för att bygga personaliseringsmodeller.

* Du behöver inte göra något specifikt för att lägga till målgrupper i modellen. Mer information om hur du använder [!DNL Experience Cloud Audiences] med [!DNL Target], se [Experience Cloud målgrupper](/help/main/c-integrating-target-with-mac/mmp.md)

### Marknadsförarna kan överföra offlinedata, benägenhetspoäng eller andra anpassade data för att skapa personaliseringsmodeller.

* Läs mer om [överföra data för [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## Hur [!UICONTROL Auto-Target] skiljer sig från [!UICONTROL Automated Personalization]? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### [!UICONTROL Auto-Target] ofta kräver mindre trafik än [!UICONTROL Automated Personalization] för en personaliserad modell att bygga.

Även om mängden trafik *per upplevelse* krävs för [!UICONTROL Auto-Target] eller [!UICONTROL Auto Personalization] är samma modeller som bygger, men det finns oftast fler upplevelser i en [!UICONTROL Automated Personalization] aktivitet än en [!UICONTROL Auto-Target] aktivitet.

Om du till exempel har en [!UICONTROL Auto Personalization] aktivitet där du har skapat två erbjudanden per plats med två platser, det skulle finnas fyra (2 = 4) totala upplevelser i aktiviteten (utan undantag). Använda [!UICONTROL Auto-Target]kan ni ange upplevelse 1 som inkluderar erbjudande 1 på plats 1 och erbjudande 2 på plats 2, och upplevelse 2 som inkluderar erbjudande 1 på plats 1 och erbjudande 2 på plats 2. För [!UICONTROL Auto-Target] gör att ni kan välja att göra flera ändringar i en upplevelse, så att ni kan minska det totala antalet upplevelser i er aktivitet.

För [!UICONTROL Auto-Target]kan enkla tumregler användas för att förstå trafikkraven:

* **När [!UICONTROL Conversion] är dina framgångsmått:** 1 000 besök och minst 50 konverteringar per dag och upplevelse. Dessutom måste aktiviteten ha minst 7 000 besök och 350 konverteringar.
* **När [!UICONTROL Revenue per Visit] är dina framgångsmått:** 1 000 besök och minst 50 konverteringar per dag och upplevelse. Dessutom måste aktiviteten ha minst 1 000 konverteringar per upplevelse. RPV kräver vanligtvis mer data för att bygga modeller på grund av den högre datavariationen som vanligtvis finns i besöksintäkterna jämfört med konverteringsgraden.

### [!UICONTROL Auto-Target] har fullständig konfigurationsfunktionalitet.

* För [!UICONTROL Auto-Target] är inbäddad i A/B-aktivitetsarbetsflödet, [!UICONTROL Auto-Target] fördelarna med en mer mogen och fullfjädrad [!UICONTROL Visual Experience Composer] (VEC). Du kan också använda [QA-länkar](/help/main/c-activities/c-activity-qa/activity-qa.md) med [!UICONTROL Auto-Target].

### [!UICONTROL Auto-Target] har ett omfattande ramverk för onlinetestning.

* Multiarm bandit ingår i ett större ramverk för onlinetestning som tillåter [!DNL Adobe] datavetare och forskare för att förstå fördelarna med deras kontinuerliga förbättringar i verkliga förhållanden.
* I framtiden kommer den här testbädden att tillåta oss att öppna [!DNL Adobe] maskininlärningsplattform för datatillgängliga kunder så att de kan ta med sina egna modeller för att förstärka [!DNL Target] modeller.

## Rapportering och [!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

Mer information finns i [Rapportering och automatisk målgruppsanpassning](/help/main/c-activities/auto-target/reporting-and-auto-target.md).

## Utbildningsvideo: Förstå aktiviteter som mål automatiskt ![Märket Översikt](/help/main/assets/overview.png)

I den här videon förklaras hur du konfigurerar en [!UICONTROL Auto-Target] A/B-aktivitet.

När du är klar med kursen bör du kunna:

* Definiera [!UICONTROL Auto-Target] testning
* Jämför och kontrast [!UICONTROL Auto-Target] till [!UICONTROL Automated Personalization]
* Skapa [!UICONTROL Auto-Target] verksamhet

>[!VIDEO](https://video.tv.adobe.com/v/18558)
