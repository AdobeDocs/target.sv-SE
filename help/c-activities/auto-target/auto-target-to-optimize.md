---
keywords: auto-target;targeting;traffic allocation;frequently aske questions;faq;troubleshooting;trouble shooting
description: Auto-Target i Adobe Target använder avancerad maskininlärning för att välja bland flera högpresterande marknadsföringsdefinierade upplevelser för att personalisera innehåll och driva konverteringar. Auto-Target levererar den mest skräddarsydda upplevelsen till varje besökare baserat på hans eller hennes individuella kundprofil och beteendet hos tidigare besökare med liknande profiler.
title: Översikt över Automatiskt mål
feature: auto-target
topic: Standard
uuid: fce769d2-9e7f-4064-add7-76e1fc394b4f
translation-type: tm+mt
source-git-commit: 777b5a84fed7455274183d2b9fe7f20096087064
workflow-type: tm+mt
source-wordcount: '1933'
ht-degree: 0%

---


# ![Översikt över PREMIUM](/help/assets/premium.png) Auto-Target

[!UICONTROL Auto-Target] använder avancerad maskininlärning för att välja bland flera högpresterande marknadsföringsdefinierade upplevelser för att personalisera innehåll och driva konverteringar. Auto-Target levererar den mest skräddarsydda upplevelsen till varje besökare baserat på hans eller hennes individuella kundprofil och beteendet hos tidigare besökare med liknande profiler.

>[!NOTE]
>
>[!UICONTROL Auto-Target] finns som en del av [!DNL Target Premium] lösningen. Den här funktionen är inte tillgänglig i [!DNL Target Standard] utan [!DNL Target Premium] licens. Mer information om de avancerade funktionerna i den här licensen finns i [Target Premium](/help/c-intro/intro.md).

## Goda erfarenheter i verkligheten med Auto-Target {#success}

En stor klädhandlare använde nyligen en aktivitet med tio produktkategoribaserade upplevelser (plus slumpmässig kontroll) för att leverera rätt innehåll till varje besökare. [!UICONTROL Auto-Target] &quot;[!UICONTROL Add to Cart]&quot; valdes som primärt optimeringsmått. De riktade upplevelserna hade en genomsnittlig ökning på 29,09 %. Efter att ha skapat [!UICONTROL Auto-Target] modellerna var aktiviteten satt till 90 % personaliserade upplevelser.

På bara tio dagar uppnåddes mer än 1 700 000 dollar i lyft.

Fortsätt läsa för att lära dig hur ni kan använda [!UICONTROL Auto-Target] för att öka lyft och intäkter för er organisation.

## Översikt {#section_972257739A2648AFA7E7556B693079C9}

När du [skapar en A/B-aktivitet med det guidade arbetsflödet](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)i tre steg kan du välja att fördela trafik med [!UICONTROL Auto-Target For Personalized Experiences] alternativet:

![Automatisk målgruppsanpassning för personaliserade upplevelser](/help/c-activities/assets/auto-target-ui-new.png)

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
| Slumpmässig skog | Random Forest är en ledande maskininlärningsstrategi. I datavetenskap är det en ensemble klassificering, eller regressionsmetod, som fungerar genom att ett stort antal beslutsträd byggs utifrån besöks- och besöksattribut. Inom Target används Slumpmässig skog för att fastställa vilken erfarenhet som förväntas ha störst sannolikhet för konvertering (eller högsta intäkt per besök) för varje enskild besökare. Mer information om Slumpmässig skog i Target finns i [Slumpmässig skogsalgoritm](/help/c-activities/t-automated-personalization/algo-random-forest.md). |
| Thompson Sampling | Målet för Thompson Sampling är att fastställa vilken upplevelse som är bäst totalt sett (icke-personaliserad), samtidigt som man minimerar&quot;kostnaden&quot; för att hitta den upplevelsen. Thompson-urvalet väljer alltid en vinnare, även om det inte finns någon statistisk skillnad mellan två upplevelser. Mer information finns i [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling). |

## Så här [!UICONTROL Auto-Target] fungerar {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Läs mer om underliggande data och algoritmer [!UICONTROL Auto-Target] och Automated Personalization på länkarna nedan:

| Villkor | Detaljer |
|--- |--- |
| [Slumpmässig skogsalgoritm](/help/c-activities/t-automated-personalization/algo-random-forest.md) | Målets huvudsakliga personaliseringsalgoritm som används i både [!UICONTROL Auto-Target] och Automated Personalization är Slumpmässig skog. Ensemble-metoder som Slumpmässig skog använder flera inlärningsalgoritmer för att få bättre prediktiva prestanda än vad som kan uppnås med någon av de ingående inlärningsalgoritmerna. Algoritmen Random Forest i det automatiserade personaliseringssystemet är en klassificering, eller regressionsmetod, som fungerar genom att en mängd beslutsträd byggs ut under utbildningstiden. |
| [Överför data för målets algoritmer för personalisering](/help/c-activities/t-automated-personalization/algo-random-forest.md) | Det finns flera sätt att mata in data för [!UICONTROL Auto-Target] och Automated Personalization-modeller. |
| [Datainsamling för målets personaliseringsalgoritmer](/help/c-activities/t-automated-personalization/ap-data.md) | Målets personaliseringsalgoritmer samlar automatiskt in en mängd olika data. |

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

![Ändra automatiskt måltrafikallokering](/help/c-activities/assets/auto-target-control.png)

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

**Target samlar automatiskt in information om besökare för att skapa personaliseringsmodeller.**

* Mer information om parametrarna som används i [!UICONTROL Auto-Target] och Automated Personalization finns i [Automated Personalization Data Collection](/help/c-activities/t-automated-personalization/ap-data.md).

**Target använder automatiskt alla delade målgrupper från Experience Cloud för att skapa personaliseringsmodeller.**

* Du behöver inte göra något specifikt för att lägga till målgrupper i modellen. Mer information om hur du använder målgrupper med Experience Cloud finns i [Experience Cloud](/help/c-integrating-target-with-mac/mmp.md)

**Marknadsförarna kan överföra offlinedata, benägenhetspoäng eller andra anpassade data för att skapa personaliseringsmodeller.**

* Läs mer om hur du [överför data för Auto-Target och Automated Personalization](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## Hur skiljer sig [!UICONTROL Auto-Target] det från Automated Personalization? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**[!UICONTROL Auto-Target]ofta kräver mindre trafik än Automated Personalization för att bygga en personaliserad modell.**

Även om mängden trafik *per upplevelse* som krävs för att bygga [!UICONTROL Auto-Target] eller [!UICONTROL Auto Personalization] modeller är densamma, finns det vanligtvis fler upplevelser i en Automated Personalization-aktivitet än i en [!UICONTROL Auto-Target] aktivitet. Om du till exempel har en [!UICONTROL Auto Personalization] aktivitet där du har skapat två erbjudanden per plats med två platser, skulle det finnas fyra (2 = 4) totala upplevelser i aktiviteten (utan undantag). Med [!UICONTROL Auto-Target]hjälp av kan ni ange upplevelse 1 som inkluderar erbjudande 1 på plats 1 och erbjudande 2 på plats 2, och upplevelse 2 som inkluderar erbjudande 1 på plats 1 och erbjudande 2 på plats 2. Eftersom [!UICONTROL Auto-Target] ni kan välja att göra flera ändringar i en upplevelse kan ni minska antalet totala upplevelser i er aktivitet.

Exempelvis [!UICONTROL Auto-Target]kan enkla reglage användas för att förstå trafikkraven:

* **När konverteringen är din framgångsfaktor:** 1 000 besök och minst 50 konverteringar per dag och upplevelse. Dessutom måste aktiviteten ha minst 7 000 besök och 350 konverteringar.
* **När intäkt per besök är ditt framgångsmått:** 1 000 besök och minst 50 konverteringar per dag och upplevelse. Dessutom måste aktiviteten ha minst 1 000 konverteringar per upplevelse. RPV kräver vanligtvis mer data för att bygga modeller på grund av den högre datavariationen som vanligtvis finns i besöksintäkterna jämfört med konverteringsgraden.

**[!UICONTROL Auto-Target]har fullständig konfigurationsfunktionalitet.**

* Eftersom [!UICONTROL Auto-Target] är inbäddad i A/B-aktivitetsarbetsflödet har det [!UICONTROL Auto-Target] bättre och mer kompletta visuella Experience Composer (VEC). Du kan också utnyttja [QA-länkar](/help/c-activities/c-activity-qa/activity-qa.md) med [!UICONTROL Auto-Target].

**[!UICONTROL Auto-Target]har ett omfattande ramverk för onlinetestning.**

* Flerarmsbanken ingår i ett större ramverk för onlinetestning, som gör det möjligt för våra datavetare och forskare att förstå fördelarna med sina kontinuerliga förbättringar i verkliga förhållanden.
* I framtiden kommer den här testbädden att göra det möjligt för oss att öppna vår maskininlärningsplattform för våra dataskunniga kunder så att de kan ta in sina egna modeller för att förstärka Target-modellerna.

## Rapportering och [!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

Mer information finns i [Automatisk målsammanfattning](/help/c-reports/auto-target-summary-report.md) i [rapportavsnittet](/help/c-reports/reports.md) .

## Utbildningsvideo: Om märket ![Översikt över aktiviteter automatiskt som mål](/help/assets/overview.png)

I den här videon förklaras hur du konfigurerar en [!UICONTROL Auto-Target] A/B-aktivitet.

När du är klar med kursen bör du kunna:

* Definiera [!UICONTROL Auto-Target] testning
* Jämför och kontrast [!UICONTROL Auto-Target] med Automated Personalization
* Skapa [!UICONTROL Auto-Target] aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/18558)