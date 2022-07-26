---
keywords: automatiserad personalisering;ap;målgrupper;ensemble;random forest;multi-väpnad bandit;thompson sampling;ml;maskininlärning
description: Lär dig hur du använder Automated Personalization-aktiviteter (AP) i Adobe [!DNL Target] som använder avancerad maskininlärning för att matcha olika erbjudandevarianter för varje besökare.
title: Vad är en Automated Personalization-aktivitet (AP)?
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Automated Personalization (AP)

[!UICONTROL Automated Personalization] (AP) aktiviteter i [!DNL Adobe Target] kombinera erbjudanden eller meddelanden och använder avancerad maskininlärning för att matcha olika erbjudandevariationer för varje enskild besökare baserat på deras individuella kundprofil, för att personalisera innehåll och driva på lyft.

>[!NOTE]
>
>[!UICONTROL Automated Personalization] finns som en del av [!DNL Target Premium] lösning. Den ingår inte i [!DNL Target Standard] utan [!DNL Target Premium] licens. Om du har en [!DNL Target Premium] licens, [!DNL Target Premium] kortet ersätter [!DNL Target Standard] i [!DNL Adobe Experience Cloud].

Lika med [!UICONTROL Auto-Target], [!UICONTROL Automated Personalization] använder en slumpmässig skogsalgoritm, en ledande enemble-metod för datavetenskap, som sin huvudsakliga personaliseringsalgoritm för att fastställa den bästa upplevelsen för att visa en besökare. [!UICONTROL Automated Personalization] kan vara värdefullt i testfasen. Det är också användbart att låta maskininlärning avgöra vilket innehåll som är mest effektivt när man riktar in sig på olika besökare. Med tiden lär sig algoritmen att förutsäga det mest effektiva innehållet och visar det innehåll som troligast uppnår dina mål.

Om du vill ha mer information om hur [!UICONTROL Automated Personalization] skiljer sig från [!UICONTROL Auto-Target], se [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

Marknadsförarna implementerar en fil på sin webbplats, vilket gör att de kan peka och klicka på valfritt innehåll och sedan visuellt skapa och välja ytterligare innehållsalternativ för det området med hjälp av VEC ([!UICONTROL Visual Experience Composer]). Sedan bestämmer algoritmen automatiskt vilken del av innehållet som ska levereras till varje enskild besökare baserat på alla beteendedata som systemet har om besökaren, vilket ger en personaliserad upplevelse. För [!UICONTROL Automated Personalization] kan anpassa sig till förändringar i besökarnas beteende, kan köras utan ett fast slutdatum för att ge kontinuerlig lyft och personalisering. Detta kallas ibland för &quot;alltid på&quot;-läge. Marknadsföraren behöver inte köra ett test, analysera resultaten och sedan leverera en vinnare innan optimeringen genomförs, vilket är en standardordning för åtgärder för att implementera resultatet av en standard A/B-aktivitet.

Följande termer är användbara vid diskussion [!UICONTROL Automated Personalization]:

| Villkor | Definition |
|---|---|
| Flerarmad bandit | En flerarmad bandit-strategi för optimering balanserar undersökande inlärning och utnyttjande av det inlärningen. |
| Slumpmässig skog | Random Forest är en ledande maskininlärningsstrategi. I datavetenskapen är det en unik klassificering- eller regressionsmetod som fungerar genom att skapa ett stort antal beslutsträd baserade på besöks- och besöksattribut. Inom Target används Slumpmässig skog för att fastställa vilken erfarenhet som förväntas ha störst sannolikhet för konvertering (eller högsta intäkt per besök) för varje enskild besökare. Mer information om Slumpmässig skog i Target finns i [Slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md). |
| Thompson Sampling | Målet för Thompson Sampling är att fastställa vilken upplevelse som är bäst totalt sett (icke-personaliserad), samtidigt som man minimerar&quot;kostnaden&quot; för att hitta den upplevelsen. Thompson-urvalet väljer alltid en vinnare, även om det inte finns någon statistisk skillnad mellan två upplevelser. Mer information finns i [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling). |

Tänk på följande när du använder [!UICONTROL Automated Personalization]:

**[!UICONTROL Automated Personalization]använder en slumpmässig skogsalgoritm för att personalisera.**

Random Forest är en ledande maskininlärningsstrategi. I datavetenskapen är det en unik klassificering- eller regressionsmetod som fungerar genom att skapa ett stort antal beslutsträd baserade på besöks- och besöksattribut. Inom Target används Slumpmässig skog för att fastställa vilken erfarenhet som förväntas ha störst sannolikhet för konvertering (eller högsta intäkt per besök) för varje enskild besökare. Besökare som använder Chrome är till exempel guldkunder och som har tillgång till din webbplats på tisdagar kan vara mer benägna att konvertera med Experience A, medan besökare från New York kan vara mer benägna att konvertera med Experience B. Mer information om Slumpmässig skog i Target finns i [Slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

**Personaliseringsmodellen optimerar för varje besök.**

* Algoritmen förutser besökarens sannolikhet för konvertering (eller beräknade intäkter från konvertering) för att ge bästa möjliga upplevelse.
* En besökare är berättigad till en ny upplevelse vid slutet av en befintlig session (såvida han eller hon inte är i kontrollgruppen, i vilket fall den upplevelse som besökaren ser vid det första besöket är samma upplevelse som han eller hon kommer att se vid efterföljande besök).
* I en session ändras inte upplevelsen för att bibehålla den visuella enhetligheten.

**Anpassningsmodellen anpassas till förändringar i besökarnas beteende.**

* Multiarm bandit säkerställer att modellen alltid &quot;spenderar&quot; en liten del av trafiken för att fortsätta lära sig genom hela aktivitetens livstid och för att förhindra att tidigare inlärda trender utnyttjas i alltför stor utsträckning.
* De underliggande modellerna byggs om var 24:e timme med hjälp av de senaste besökarbeteendedata för att säkerställa att Target alltid utnyttjar förändrade besökarinställningar.
* Om algoritmen inte kan avgöra vilka upplevelser som vinner för enskilda besökare, växlar den automatiskt till att visa den övergripande prestandaoptimerade upplevelsen, samtidigt som den fortsätter att leta efter personaliserade vinnare. Den bästa upplevelsen med [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling).

**Modellen optimerar kontinuerligt ett enskilt målmått.**

* Detta mätresultat kan vara konverteringsbaserat eller inkomstbaserat (mer specifikt, [!UICONTROL Revenue per Visitor]).

**Target samlar automatiskt in information om besökare för att skapa personaliseringsmodeller.**

* Mer information om attributen som används i [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization], se [Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md).

**Målet använder automatiskt alla [!DNL Adobe Experience Cloud] delade målgrupper för att bygga personaliseringsmodeller.**

* Ni behöver inte göra något specifikt för att lägga till målgrupper i modellen. Mer information om hur du använder [!DNL Experience Cloud Audiences] med [!DNL Target], se [Experience Cloud målgrupper](/help/main/c-integrating-target-with-mac/mmp.md).

**Marknadsförarna kan överföra offlinedata, benägenhetspoäng eller andra anpassade data för att bygga personaliseringsmodeller.**

Offlinedata, som CRM-information eller kundbortfallspoäng, kan vara oerhört värdefulla när du skapar personaliseringsmodeller. Det finns flera sätt att mata in data i [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] personaliseringsalgoritmer.

* [mbox-parametrar](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}
* [Profilparametrar](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}
* [API:er på serversidan för profiluppdatering](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/)

För information om data som samlas in och används av [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] personaliseringsalgoritmer, se [Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md).

## ![Märket Översikt](/help/main/assets/overview.png) Utbildningsvideo: Typ av aktivitet

I den här videon förklaras aktivitetstyperna som finns i [!DNL Target Standard/Premium]. [!UICONTROL Automated Personalization] behandlas från 17:55.

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)
