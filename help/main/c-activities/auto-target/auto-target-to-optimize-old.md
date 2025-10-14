---
keywords: automatiskt mål;mål;trafikallokering;vanliga frågor;frågor;felsökning;felsökning
description: Lär dig hur en [!UICONTROL Auto-Target]-aktivitet i [!DNL Target] ger den mest anpassade upplevelsen för varje besökare baserat på kundprofiler och beteendet hos liknande besökare.
title: Vad är en [!UICONTROL Auto-Target]-aktivitet?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '1864'
ht-degree: 0%

---

# [!UICONTROL Auto-Target] - översikt

[!UICONTROL Auto-Target] aktiviteter i [!DNL Adobe Target] använder avancerad maskininlärning för att välja bland flera högpresterande, marknadsföringsdefinierade upplevelser för att personalisera innehåll och driva konverteringar. [!UICONTROL Auto-Target] levererar den mest anpassade upplevelsen till varje besökare baserat på den enskilda kundprofilen och beteendet hos tidigare besökare med liknande profiler.

>[!NOTE]
>
>* [!UICONTROL Auto-Target] är tillgänglig som en del av lösningen [!DNL Target Premium]. Den här funktionen är inte tillgänglig i [!DNL Target Standard] utan en [!DNL Target Premium]-licens. Mer information om de avancerade funktioner som den här licensen innehåller finns i [Target Premium](/help/main/c-intro/intro.md).
>
>* [!UICONTROL Analytics for Target] (A4T) stöder [!UICONTROL Auto-Target] aktiviteter. Mer information finns i [Stöd för A4T för aktiviteter som automatisk allokering och automatisk målning](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

## Goda erfarenheter i verkligheten med Auto-Target {#success}

En stor klädhandlare använde nyligen en [!UICONTROL Auto-Target]-aktivitet med tio produktkategoribaserade upplevelser (plus slumpmässig kontroll) för att leverera rätt innehåll till varje besökare. [!UICONTROL Add to Cart] har valts som primärt optimeringsmått. De riktade upplevelserna hade en genomsnittlig ökning på 29,09 %. När du har skapat [!UICONTROL Auto-Target]-modellerna ställdes aktiviteten in på 90 % personaliserade upplevelser.

På bara tio dagar uppnåddes mer än 1 700 000 dollar i lyft.

Läs mer om hur du använder [!UICONTROL Auto-Target] för att öka lyft och intäkter för din organisation.

## Ökning {#section_972257739A2648AFA7E7556B693079C9}

När du [skapar en A/B-aktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) med det guidade arbetsflödet i tre steg, väljer du alternativet **[!UICONTROL Auto-Target for personalized experiences]** på sidan **[!UICONTROL Targeting]** (steg 2).

![Automatiskt mål för personaliserade upplevelser &#x200B;](/help/main/c-activities/assets/auto-target-ui-new.png)

Alternativet [!UICONTROL Auto-Target] i A/B-aktivitetsflödet gör att du kan anpassa maskininlärningen utifrån en uppsättning marknadsföringsdefinierade upplevelser med ett klick. [!UICONTROL Auto-Target] är utformat för att leverera maximal optimering, jämfört med traditionell A/B-testning eller [!UICONTROL Auto Allocate], genom att avgöra vilken upplevelse som ska visas för varje besökare. Till skillnad från en A/B-aktivitet där målet är att hitta en enskild vinnare, avgör [!UICONTROL Auto-Target] automatiskt den bästa upplevelsen för en viss besökare. Den bästa upplevelsen bygger på besökarens profil och annan sammanhangsbaserad information för att leverera en mycket personaliserad upplevelse.

På liknande sätt som för [!UICONTROL Automated Personalization] använder [!UICONTROL Auto-Target] en [slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), en metod som är unik för datavetenskapen, för att fastställa den bästa upplevelsen för en besökare. Eftersom [!UICONTROL Auto-Target] kan anpassa sig till förändringar i besökares beteende kan det köras permanent för att ge lyft. Den här metoden kallas ibland för&quot;alltid på&quot;-läge.

Till skillnad från en A/B-aktivitet där upplevelseallokeringen för en viss besökare är fast, optimerar [!UICONTROL Auto-Target] det angivna affärsmålet för varje besök. Som i [!UICONTROL Auto Personalization] reserverar [!UICONTROL Auto-Target] som standard en del av aktivitetens trafik som en kontrollgrupp för att mäta lyft. Besökarna i kontrollgruppen får en slumpmässig erfarenhet av aktiviteten.

## Överväganden

Det finns några viktiga saker att tänka på när du använder [!UICONTROL Auto-Target]:

* Du kan inte växla en specifik aktivitet från [!UICONTROL Auto-Target] till [!UICONTROL Automated Personalization], och tvärtom.
* Du kan inte växla från [!UICONTROL Manual] trafikallokering (traditionell [!UICONTROL A/B Test]) till [!UICONTROL Auto-Target], och tvärtom efter att en aktivitet har sparats som utkast.
* En modell är byggd för att identifiera den personaliserade strategins prestanda jämfört med slumpvis betjänad trafik jämfört med att skicka all trafik till den övergripande vinnande upplevelsen. Den här modellen hanterar endast träffar och konverteringar i standardmiljön.

  Trafik från en andra uppsättning modeller byggs för varje modellgrupp (AP) eller upplevelse (AT). För var och en av dessa modeller beaktas träffar och konverteringar i alla miljöer.

  Förfrågningar hanteras med samma modell, oavsett miljö, men trafikens mångfald bör komma från standardmiljön för att säkerställa att den identifierade övergripande vinnande upplevelsen överensstämmer med verkliga beteenden.

* Använd minst två upplevelser.

## Terminologi {#section_A309B7E0B258467789A5CACDC1D923F3}

Följande termer är användbara när du diskuterar [!UICONTROL Auto-Target]:

| Villkor | Definition |
|---|---|
| [Flerarmad bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | En flerarmad bandit-strategi för optimering balanserar undersökande inlärning och utnyttjande av det inlärningen. |
| [Slumpmässig skog](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Random Forest är en ledande maskininlärningsstrategi. I datavetenskapen är det en unik klassificering, eller regressionsmetod, som fungerar genom att skapa många beslutsträd baserade på besöks- och besöksattribut. Inom [!DNL Target] används Slumpmässig skog för att avgöra vilken erfarenhet som förväntas ha störst sannolikhet för konvertering (eller högsta intäkt per besök) för varje enskild besökare. |
| [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | Målet för Thompson Sampling är att fastställa vilken upplevelse som är bäst totalt sett (icke-personaliserad), samtidigt som man minimerar&quot;kostnaden&quot; för att hitta den upplevelsen. Thompson-urvalet väljer alltid en vinnare, även om det inte finns någon statistisk skillnad mellan två upplevelser. |

## Så här fungerar [!UICONTROL Auto-Target] {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Läs mer om underliggande data och algoritmer för [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] via länkarna nedan:

| Villkor | Information |
|--- |--- |
| [Slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Den huvudpersonaliseringsalgoritm som används av [!DNL Target] i både [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] är Slumpmässig skog. Ensemble-metoder, till exempel Slumpskog, använder flera olika inlärningsalgoritmer för att få bättre prediktiva prestanda än vad som kan uppnås med någon av de ingående inlärningsalgoritmerna. Algoritmen Slumpmässig skog i aktiviteterna [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] är en klassificering, eller regressionsmetod, som används genom att skapa en mängd beslutsträd under utbildningstiden. |
| [Överför data för  [!DNL Target]s Personalization-algoritmer](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Det finns flera sätt att mata in data för [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] modeller. |
| [Datainsamling för Personalization-algoritmer för  [!DNL Target]](/help/main/c-activities/t-automated-personalization/ap-data.md) | Personaliseringsalgoritmerna för [!DNL Target] samlar automatiskt in olika data. |

## Bestämma trafikallokering {#section_AB3656F71D2D4C67A55A24B38092958F}

Beroende på vad din aktivitet har för mål kan du välja en annan trafikfördelning mellan kontroll och personaliserade upplevelser. Det bästa sättet är att fastställa det här målet innan du gör din aktivitet offentlig.

I listrutan [!UICONTROL Custom Allocation] kan du välja mellan följande alternativ:

* [!UICONTROL Evaluate Personalization Algorithm]
* [!UICONTROL Maximize Personalization Traffic]
* [!UICONTROL Custom Allocation]

![Listruta för allokeringsmål](/help/main/c-activities/assets/split-new.png)

| Aktivitetsmål | Föreslagen trafikallokering | Överlåtelser |
|--- |--- |--- |
| **Utvärdera Personalization-algoritm (50/50)**: Om ditt mål är att testa algoritmen använder du en 50/50-procentig delning av besökare mellan kontrollen och målalgoritmen. Denna delning ger den mest korrekta uppskattningen av hissen. Föreslagna för användning med&quot;slumpmässiga upplevelser&quot; som er kontroll. | 50 % kontroll/50 % personlig upplevelsedelning | <ul><li>Maximerar lyften mellan kontroll och personalisering</li><li>relativt färre besökare har en personaliserad upplevelse</li></ul> |
| **Maximera Personalization-trafik (90/10)**: Om målet är att skapa en&quot;alltid på&quot;-aktivitet ska 10 % av besökarna kontrolleras för att se till att det finns tillräckligt med data för att algoritmerna ska kunna fortsätta lära sig över tid. Hantverket här är att i utbyte mot att personalisera en större andel av trafiken har ni mindre precision i det exakta lyftet. Oavsett vilket mål du har är detta den rekommenderade trafikdelningen när du använder en specifik upplevelse som kontroll. | Det bästa sättet är att använda en 10-30 % kontroll/70-90 % personaliserad upplevelsedelning | <ul><li>Maximerar antalet besökare som har en personaliserad upplevelse</li><li>Maximerar lyft</li><li>Mindre noggrannhet vad hissen är för aktiviteten</li></ul> |
| **Anpassad allokering** | Dela procentandelen manuellt efter behov. | <ul><li>Du kanske inte uppnår det önskade resultatet. Om du är osäker kan du följa förslagen för något av de föregående alternativen</li></ul> |

Om du vill justera procentandelen [!UICONTROL Control] klickar du på ikonerna i kolumnen [!UICONTROL Allocation]. Du kan inte minska kontrollgruppen till mindre än 10 %.

![Ändra automatiskt måltrafikallokering](/help/main/c-activities/assets/auto-target-control.png)

Du kan [välja en specifik upplevelse som ska användas som kontroll](/help/main/c-activities/t-automated-personalization/experience-as-control.md) eller använda alternativet Slumpmässig upplevelse.

## När ska du välja [!UICONTROL Auto-Target] över [!UICONTROL Automated Personalization]? {#section_BBC4871C87944DD7A8B925811A30C633}

Det finns flera scenarier där du kanske föredrar att använda [!UICONTROL Auto-Target] framför [!UICONTROL Automated Personalization]:

* Om ni vill definiera hela upplevelsen i stället för enskilda erbjudanden som automatiskt kombineras för att skapa en upplevelse.
* Om du vill använda alla [!UICONTROL Visual Experience Composer] (VEC)-funktioner som inte stöds av [!UICONTROL Auto Personalization]: den anpassade kodredigeraren, flera upplevelsemålgrupper med mera.
* Om du vill göra strukturella ändringar på sidan i olika upplevelser. Om du till exempel vill ordna om element på din hemsida är [!UICONTROL Auto-Target] mer lämpligt att använda än [!UICONTROL Automated Personalization].

## Vad har [!UICONTROL Auto-Target] gemensamt med [!UICONTROL Automated Personalization]? {#section_2A601F482F9A44E38D4B694668711319}

### Algoritmen optimerar för ett positivt resultat vid varje besök.

* Algoritmen förutser besökarens benägenhet för konvertering (eller beräknade intäkter från konvertering) för att ge bästa möjliga upplevelse.
* En besökare är berättigad till en ny upplevelse vid slutet av en befintlig session (såvida inte besökaren är i kontrollgruppen, i vilket fall den upplevelse som besökaren tilldelas vid det första besöket förblir densamma för efterföljande besök).
* Under en session ändras inte förutsägbarheten, vilket ger en bättre visuell enhetlighet.

### Algoritmen anpassas till förändringar i besökarens beteende.

* Multiarm bandit säkerställer att modellen alltid &quot;spenderar&quot; en liten fraktionstrafik som kan fortsätta att lära sig under aktivitetens livstid och för att förhindra överutnyttjande av tidigare inlärda trender.
* De underliggande modellerna återskapas var 24:e timme med hjälp av de senaste besökarbeteendedata för att säkerställa att [!DNL Target] alltid utnyttjar förändrade besökarinställningar.
* Om algoritmen inte kan avgöra vilka vinnande upplevelser individen har, växlar den automatiskt till att visa den övergripande prestandaoptimerade upplevelsen samtidigt som den fortsätter att leta efter personaliserade vinnare. Den bästa upplevelsen hittas med [Thompson-sampling](https://en.wikipedia.org/wiki/Thompson_sampling).

### Algoritmen optimerar kontinuerligt för ett enda målmått.

* Det här måttet kan vara konverteringsbaserat eller intäktsbaserat (mer specifikt [!UICONTROL Revenue per Visit]).

### [!DNL Target] samlar automatiskt in information om besökare för att skapa personaliseringsmodeller.

* Mer information om parametrarna som används i [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] finns i [Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md).

### [!DNL Target] använder automatiskt alla [!DNL Adobe Experience Cloud] delade målgrupper för att skapa personaliseringsmodeller.

* Du behöver inte göra något specifikt för att lägga till målgrupper i modellen. Mer information om hur du använder [!DNL Experience Cloud Audiences] med [!DNL Target] finns i [Experience Cloud-målgrupper](/help/main/c-integrating-target-with-mac/mmp.md).

### Marknadsförarna kan överföra offlinedata, benägenhetspoäng eller andra anpassade data för att skapa personaliseringsmodeller.

* Läs mer om att [överföra data för [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## Hur skiljer sig [!UICONTROL Auto-Target] från [!UICONTROL Automated Personalization]? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### [!UICONTROL Auto-Target] kräver ofta mindre trafik än [!UICONTROL Automated Personalization] för en anpassad modell att bygga.

Även om mängden trafik *per upplevelse* som krävs för att [!UICONTROL Auto-Target] eller [!UICONTROL Auto Personalization] modeller ska kunna skapas är densamma, finns det vanligtvis fler upplevelser i en [!UICONTROL Automated Personalization]-aktivitet än i en [!UICONTROL Auto-Target]-aktivitet.

Om du till exempel har en [!UICONTROL Auto Personalization]-aktivitet där du har skapat två erbjudanden per plats med två platser, så finns det fyra (2 = 4) totala upplevelser i aktiviteten (utan undantag). Med [!UICONTROL Auto-Target] kan du ange upplevelse 1 som inkluderar erbjudande 1 på plats 1 och erbjudande 2 på plats 2, och upplevelse 2 som inkluderar erbjudande 1 på plats 1 och erbjudande 2 på plats 2. Eftersom [!UICONTROL Auto-Target] tillåter att du kan välja att ha flera ändringar i en upplevelse, kan du minska antalet totala upplevelser i din aktivitet.

För [!UICONTROL Auto-Target] kan enkla tumregler användas för att förstå trafikkrav:

* **När [!UICONTROL Conversion] är ditt framgångsmått:** 1 000 besök och minst 50 konverteringar per dag och upplevelse, och aktiviteten måste dessutom ha minst 7 000 besök och 350 konverteringar.
* **När [!UICONTROL Revenue per Visit] är ditt framgångsmått:** 1 000 besök och minst 50 konverteringar per dag och upplevelse, och aktiviteten måste dessutom ha minst 1 000 konverteringar per upplevelse. RPV kräver vanligtvis mer data för att bygga modeller på grund av den högre datavariationen som vanligtvis finns i besöksintäkterna jämfört med konverteringsgraden.

### [!UICONTROL Auto-Target] har fullfjädrade installationsfunktioner.

* Eftersom [!UICONTROL Auto-Target] är inbäddad i A/B-aktivitetsarbetsflödet drar [!UICONTROL Auto-Target] nytta av den mer mogna och fullfjädrade [!UICONTROL Visual Experience Composer] (VEC). Du kan också använda [QA-länkar](/help/main/c-activities/c-activity-qa/activity-qa.md) med [!UICONTROL Auto-Target].

### [!UICONTROL Auto-Target] tillhandahåller ett omfattande ramverk för onlinetestning.

* Flerarmsbanken ingår i ett större ramverk för onlinetestning som gör att [!DNL Adobe] datavetare och forskare kan förstå fördelarna med sina kontinuerliga förbättringar i verkliga förhållanden.
* I framtiden kommer denna testbädd att tillåta oss att öppna [!DNL Adobe] maskininlärningsplattform för datagunda klienter så att de kan ta in sina egna modeller för att förstärka [!DNL Target]-modellerna.

## Rapportering och [!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

Mer information finns i [Rapportering och Automatiskt mål](/help/main/c-activities/auto-target/reporting-and-auto-target.md).

## Utbildningsvideo: Förstå aktiviteter med automål

I den här videon förklaras hur du konfigurerar en [!UICONTROL Auto-Target] A/B-aktivitet.

När du är klar med kursen bör du kunna:

* Definiera [!UICONTROL Auto-Target]-testning
* Jämför och kontrastera [!UICONTROL Auto-Target] med [!UICONTROL Automated Personalization]
* Skapa [!UICONTROL Auto-Target] aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/18558)
