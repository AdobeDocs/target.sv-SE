---
keywords: automatiserad personalisering;ap;målgrupper;ensemble;random forest;multi-väpnad bandit;thompson sampling;ml;maskininlärning
description: Lär dig hur du använder [!UICONTROL Automated Personalization] (AP) aktiviteter i  [!DNL Adobe Target] som använder avancerad maskininlärning för att matcha olika erbjudandevariationer för varje besökare.
title: Vad är en [!UICONTROL Automated Personalization]-aktivitet (AP)?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 0%

---

# [!UICONTROL Automated Personalization] (AP)

[!UICONTROL Automated Personalization] (AP)-aktiviteter i [!DNL Adobe Target] kombinerar erbjudanden eller meddelanden och använder avancerad maskininlärning för att matcha olika erbjudandevariationer för varje besökare baserat på deras individuella kundprofil för att anpassa innehåll och öka antalet.

>[!NOTE]
>
>[!UICONTROL Automated Personalization] är tillgänglig som en del av lösningen [!DNL Target Premium]. Den här funktionen är inte tillgänglig i [!DNL Target Standard] utan en [!DNL Target Premium]-licens. Mer information om de avancerade funktioner som den här licensen innehåller finns i [Target Premium](/help/main/c-intro/intro.md#premium).

På liknande sätt som för [!UICONTROL Auto-Target] använder [!UICONTROL Automated Personalization] en [slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), en enemble-metod för datavetenskap, som huvudpersonaliseringsalgoritm för att fastställa den bästa upplevelsen för att visa en besökare. [!UICONTROL Automated Personalization] kan vara värdefullt i testfasen. Det är också användbart att låta maskininlärning avgöra vilket innehåll som är mest effektivt när man riktar in sig på olika besökare. Med tiden lär sig algoritmen att förutsäga det mest effektiva innehållet och visar det innehåll som troligast uppnår dina mål.

Mer information om hur [!UICONTROL Automated Personalization] skiljer sig från [!UICONTROL Auto-Target] finns i [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB).

Marknadsförarna implementerar en fil på sin webbplats, vilket gör att de kan peka och klicka på valfritt innehåll och sedan visuellt skapa och välja ytterligare innehållsalternativ för det området med [!UICONTROL Visual Experience Composer] (VEC). Sedan bestämmer algoritmen automatiskt vilken del av innehållet som ska levereras till varje enskild besökare baserat på alla beteendedata som systemet har om besökaren, vilket ger en personaliserad upplevelse. Eftersom [!UICONTROL Automated Personalization] kan anpassa sig till förändringar i besökares beteende kan det köras utan ett angivet slutdatum för att ge en pågående lyft och personalisering. Det här läget kallas ibland för&quot;alltid på&quot;. Marknadsföraren behöver inte köra ett test, analysera resultaten och sedan leverera en vinnare innan optimeringen genomförs, vilket är en standardordning för åtgärder för att implementera resultatet av en standard A/B-aktivitet.

Följande termer är användbara när du diskuterar [!UICONTROL Automated Personalization]:

| Villkor | Definition |
|---|---|
| Flerarmad bandit | En flerarmad bandit-strategi för optimering balanserar undersökande inlärning och utnyttjande av det inlärningen. |
| Slumpmässig skog | En ledande maskininlärningsstrategi. I datavetenskapliga termer är det en unik klassificerings- eller regressionsmetod som fungerar genom att skapa många beslutsträd baserade på besöks- och besöksattribut. |
| Thompson Sampling | Målet för Thompson Sampling är att fastställa vilken upplevelse som är bäst totalt sett (icke-personaliserad), samtidigt som man minimerar&quot;kostnaden&quot; för att hitta den upplevelsen. Thompson-urvalet väljer alltid en vinnare, även om det inte finns någon statistisk skillnad mellan två upplevelser. Mer information finns i [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling). |

Tänk på följande information när du använder [!UICONTROL Automated Personalization]:

## [!UICONTROL Automated Personalization] använder en slumpmässig skogsalgoritm för att anpassa

Random Forest är en ledande maskininlärningsstrategi. I datavetenskapliga termer är det en unik klassificerings- eller regressionsmetod som fungerar genom att skapa många beslutsträd baserade på besöks- och besöksattribut. Inom [!DNL Target] används Slumpmässig skog för att avgöra vilken erfarenhet som förväntas ha störst sannolikhet för konvertering (eller högsta intäkt per besök) för varje enskild besökare. Besökare som använder Chrome är till exempel guldkunder och som kommer åt din webbplats på tisdagar kan vara mer benägna att konvertera med Experience A. Besökare från New York kan vara mer benägna att konvertera med Experience B. Mer information om Slumpmässig skog i [!DNL Target] finns i [Slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## Personaliseringsmodellen optimerar för varje besök

* Algoritmen förutser besökarens sannolikhet för konvertering (eller beräknade intäkter från konvertering) för att ge bästa möjliga upplevelse.
* En besökare är berättigad till en ny upplevelse vid slutet av en befintlig session, såvida inte besökaren är i kontrollgruppen. Om besökaren befinner sig i kontrollgruppen är upplevelsen som besökaren ser vid det första besöket densamma som vid efterföljande besök.
* Den presenterade upplevelsen ändras inte inom en session för att bevara den visuella enhetligheten.

## Anpassningsmodellen anpassas till förändringar i besökarnas beteende

* Multiarm bandit säkerställer att modellen alltid &quot;spenderar&quot; en liten del av trafiken för att fortsätta lära sig genom hela aktivitetens livstid och för att förhindra överutnyttjande av tidigare inlärda trender.
* De underliggande modellerna återskapas var 24:e timme med hjälp av de senaste besökarbeteendedata för att säkerställa att [!DNL Target] alltid använder ändrade besökarinställningar.
* Om algoritmen inte kan avgöra vilka upplevelser som vinner för enskilda besökare, växlar den automatiskt till att visa den övergripande prestandaoptimerade upplevelsen, samtidigt som den fortsätter att leta efter personaliserade vinnare. Den bästa upplevelsen hittas med [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling).

## Modellen optimerar kontinuerligt ett enskilt målmått

* Det här måttet kan vara konverteringsbaserat eller intäktsbaserat (närmare bestämt [!UICONTROL Revenue per Visitor]).

## [!DNL Target] samlar automatiskt in information om besökare för att skapa personaliseringsmodeller

* Mer information om attributen som används i [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] finns i [Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md).

## [!DNL Target] använder automatiskt alla [!DNL Adobe Experience Cloud] delade målgrupper för att skapa personaliseringsmodeller

* Ni behöver inte göra något specifikt för att lägga till målgrupper i modellen. Mer information om hur du använder [!DNL Experience Cloud Audiences] med [!DNL Target] finns i [Experience Cloud-målgrupper](/help/main/c-integrating-target-with-mac/mmp.md).

## Marknadsförarna kan överföra offlinedata, benägenhetspoäng eller andra anpassade data för att skapa personaliseringsmodeller

Offlinedata, som CRM-information eller kundrespons, kan vara oerhört värdefulla när du bygger personaliseringsmodeller. Det finns flera sätt att ange data i personaliseringsalgoritmerna [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target].

* [mbox-parametrar](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [Profilparametrar](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [API:er på serversidan för profiluppdatering](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}

Mer information om de data som samlas in automatiskt och används av [!UICONTROL Automated Personalization] och [!UICONTROL Auto-Target] personaliseringsalgoritmer finns i [Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Utbildningsvideo: Aktivitetstyper

I den här videon förklaras de aktivitetstyper som är tillgängliga i [!DNL Target]. [!UICONTROL Automated Personalization] diskuteras från 17:55.

* Beskriv de typer av aktiviteter som ingår i [!DNL Adobe Target]
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)
