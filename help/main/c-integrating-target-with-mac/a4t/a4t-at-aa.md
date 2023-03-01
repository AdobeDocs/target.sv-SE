---
keywords: a4t;A4T;Analyser som rapportkälla för Target
description: Lär dig hur du skapar aktiviteter för automatisk fördelning och automatisk målanpassning i Adobe [!DNL Target] som använder Analytics som rapportkälla (A4T).
title: Har A4T stöd för automatisk fördelning och automatisk målanpassning?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 3ac61272ee1ccd72a8670966f181e7798cbe9f76
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 0%

---

# A4T-stöd för Automatisk allokering och Automatiskt mål-aktiviteter

The [!DNL Adobe Target]-till-[!DNL Adobe Analytics] integrering, kallas [Analyser för Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) har stöd för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet.

Med A4T-integreringen kan du:

* Använd [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)s multiväpnade bandit-kapacitet som driver trafik till vinnande upplevelser.
* Använd [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md)En unik maskininlärningsalgoritm som ger varje besökare den bästa upplevelsen. AutoTarget väljer den bästa upplevelsen baserat på användarnas profiler, beteenden och kontext när ett [!DNL Adobe Analytics] målmått och [!DNL Adobe Analytics]&quot; omfattande rapporterings- och analysfunktioner.

Se till att du har [implementerat A4T för användning med A/B Test- och Experience Targeting-aktiviteter](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Om du använder `analyticsLogging = client_side`måste du också skicka `sessionId` värde till [!DNL Analytics]. Mer information finns i [Analyser för målrapportering (A4T)](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} i *Adobe Target SDKs* guide.

Så här kommer du igång:

1. När du skapar en A/B-testaktivitet, på **[!UICONTROL Targeting]** väljer du något av följande alternativ som **[!UICONTROL Traffic Allocation Method]**:

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experiences]

   ![Alternativ för trafikallokeringsmetoder: Manuell, Automatisk fördelning och Automatisk målning](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Mer information och stegvisa instruktioner finns i [Skapa en automatiskt fördelad aktivitet](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) och [Skapa en Automatisk målaktivitet](/help/main/c-activities/auto-target/create-auto-target.md).

1. Välj **[!UICONTROL Adobe Analytics]** för **[!UICONTROL Reporting Source]** på **[!UICONTROL Goals & Settings]** och välj den rapportsvit som motsvarar det optimeringsmål du vill ha.

   ![Avsnittet Rapporteringskälla på sidan Mål och inställningar](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Välj ett primärt målmått.

   * Används [!DNL Adobe Target] om du vill ange optimeringsmålet väljer du **[!UICONTROL Conversion]** .
   * Välj **[!UICONTROL Use an Analytics metric]** och välj sedan ett mätvärde från [!DNL Analytics] som ska användas som optimeringsmål. Du kan använda en färdig fil [!DNL Analytics] konverteringsmått eller [!DNL Analytics] anpassad händelse.

   Se [Målmått som stöds](#supported) nedan om du vill ha mer information.

1. Spara och aktivera aktiviteten.

   [!UICONTROL Auto-Allocate] använder det valda måttet för att optimera aktiviteten och för besökarna till upplevelsen som maximerar målmåttet.

   eller

   [!UICONTROL Auto-Target] använder de mätvärden du väljer för att optimera aktiviteten och locka besökarna till en personaliserad, bästa upplevelse.

1. Använd **[!UICONTROL Reports]** för att visa aktivitetens rapportering efter ditt val av [!DNL Adobe Analytics] mätvärden. Klicka **[!UICONTROL View in Analytics]** att fördjupa och segmentera rapportdata ytterligare.

## Målmått som stöds {#supported}

[!UICONTROL A4T] for [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] gör att du kan välja någon av följande måtttyper som det primära målmåttet för optimering:

* [!DNL Adobe Target] konverteringsmått
* [!DNL Adobe Analytics] konverteringsmått
* [!DNL Adobe Analytics] anpassade händelser

[!UICONTROL A4T] for [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] kräver att du väljer ett mätvärde som baseras på en binomial-händelse. En binomialhändelse inträffar eller inträffar inte. Binomiala händelser omfattar ett klick, en konvertering, en ordning och så vidare. Dessa typer av händelser kallas ibland även för Bernoulli, binära eller diskreta händelser.

[!UICONTROL A4T] for [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] stöder inte optimering för kontinuerliga mätvärden. Kontinuerliga mätvärden är intäkter, antal beställda produkter, sessionstid, antal sidvisningar under sessionen osv. Dessa metattyper som inte stöds kallas ibland icke-binomiala eller icke-Bernoulli-mått.

Följande måtttyper stöds inte som primära målmått:

* [!DNL Adobe Target] interaktions- och intäktsmått
* [!DNL Adobe Analytics] interaktions- och intäktsmått

   Du kan välja en [!DNL Analytics] engagemangs- eller intäktsmått som det primära målmåttet eftersom [!DNL Target] kan inte identifiera och utesluta alla interaktions- och intäktsmått från [!DNL Analytics]. Välj endast binomikonverteringsmått eller anpassade händelser från [!DNL Analytics].

* [!DNL Adobe Analytics] beräknade värden

## Begränsningar och anteckningar

Vissa begränsningar och anteckningar gäller för båda [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet. Andra begränsningar och anteckningar gäller för en aktivitetstyp eller en annan.

### Automatisk fördelning och Automatisk målgruppsanpassning {#both}

* När du använder [!DNL Adobe Analytics] som rapportkälla för [!UICONTROL Auto-Allocate] eller [!UICONTROL Auto-Target]bör du alltid visa rapporter i [!DNL Analytics].
* Rapporteringskällan kan inte ändras från [!DNL Analytics] till [!DNL Target] eller omvänt efter att en aktivitet har aktiverats.
* Även om beräknade mätvärden inte stöds som primära målmätvärden är det ofta möjligt att uppnå det avsedda resultatet genom att i stället välja en anpassad händelse som primärt målmått. Om du till exempel vill optimera för ett mått som&quot;formulärifyllningar per besökare&quot; väljer du en anpassad händelse som motsvarar&quot;formulärifyllningar&quot; som det primära målmåttet. [!DNL Target] normaliserar automatiskt konverteringsmåtten per besök för att ta hänsyn till ojämn trafikfördelning, så det är inte nödvändigt att använda ett beräknat mätvärde för att utföra normaliseringen.
* När du använder [!DNL Adobe Analytics] som rapportkälla för [!UICONTROL Auto-Allocate] eller [!UICONTROL Auto-Target] aktiviteter, du bör alltid visa rapporter i [!DNL Analytics].
* Rapporteringskällan kan inte ändras från [!DNL Analytics] till [!DNL Target] eller vice versa efter att en aktivitet har aktiverats.
* Även om beräknade mätvärden inte stöds som primära målmätvärden är det ofta möjligt att uppnå det avsedda resultatet genom att i stället välja en anpassad händelse som primärt målmått. Om du till exempel vill optimera för ett mått som&quot;formulärifyllningar per besökare&quot; väljer du en anpassad händelse som motsvarar&quot;formulärifyllningar&quot; som det primära målmåttet. [!DNL Target] normaliserar automatiskt konverteringsstatistik per besökare för [!UICONTROL Auto-Allocate] -aktiviteter, så det är inte nödvändigt att använda ett beräknat mått för att utföra normalisering.

### Automatisk allokering {#aa}

* **Utbildningsfrekvens**: [!UICONTROL Auto-Allocate] fortsätter modellerna att träna varje timme som vanligt.
* **Attributionsmodeller**: [!DNL Target] använder [!DNL Adobe Analytics] standardattribueringsmodell för[!UICONTROL  Auto-Allocate] aktiviteter som använder A4T.
* **Förtroende**: Konfidensformeln som används av [!UICONTROL Auto-Allocate] aktiviteterna skiljer sig från formeln som visas som standard i [!DNL Adobe Analytics] [!UICONTROL A4T] -panelen. [Enligt beskrivning](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Auto-Allocate] använder mer försiktiga konfidensintervall än med regelbundna [!UICONTROL A/B Test] verksamhet. Dessa konservativa konfidensnivåer kompenserar för upprepade utvärderingar (peeks) vid data. Därför är standardrapporten i [!DNL Adobe Analytics] visar snävare konfidensintervall jämfört med dem som används av [!UICONTROL Auto-Allocate] algoritm. Ni kan dock avgöra vilken upplevelse som prioriteras av algoritmerna utifrån vilken upplevelse som har fler unika besökare som skickas till den.
* **Vinnarstatus**: För närvarande är [&quot;Ingen vinnare ännu&quot; och &quot;vinnare&quot;-märken](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) är inte tillgängliga i [!UICONTROL A4T] panel i [!DNL Analysis Workspace]. Dessa emblem är inte heller tillgängliga om samma rapport visas i [!DNL Target]. En &quot;stjärna&quot;-bricka som visas i en [!DNL Target] rapport för [!UICONTROL Auto-Allocate] -aktivitet som använder A4T ska ignoreras. Den här ikonen visar vanliga konfidensberäkningar och inte de som används av [!UICONTROL Auto-Allocate].

### Automatiskt mål {#at}

* [!UICONTROL Auto-Target] modellerna fortsätter att träna var 24:e timme som vanligt. Konverteringshändelsedata kommer dock från [!DNL Analytics] fördröjs med ytterligare 6 till 24 timmar. Förseningen innebär fördelning av trafik med [!DNL Target] följer de senaste händelser som spelats in i [!DNL Analytics]. Den här fördröjningen har störst effekt de första 48 timmarna efter att en aktivitet initialt har aktiverats. Aktivitetens prestanda kommer att spegla bättre [!DNL Analytics] konverteringsbeteende efter fem dagar. Överväg att använda [!UICONTROL Auto-Allocate] i stället för [!UICONTROL Auto-Target] för korttidsaktiviteter där den största trafiken förekommer inom de fem första dagarna av verksamhetens livstid.
* När du använder [!DNL Analytics] som datakälla för en [!UICONTROL Auto-Target] aktivitet, sessionerna avslutas efter sex timmar. Konverteringar som inträffar efter sex timmar räknas inte.

Mer information finns i [Attributmodeller och uppslagsfönster](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) i *Handbok för analysverktyg*.

## Självstudiekurs: Konfigurera A4T-rapporter i Analysis Workspace för Automatiskt mål-aktiviteter {#tutorial}

Även om det finns omfattande analysfunktioner i [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], några ändringar av standardinställningen [!UICONTROL Analytics for Target] -panelen krävs för att tolka Automatiskt mål-aktiviteter på rätt sätt. Dessa ändringar är nödvändiga på grund av skillnader mellan experimentella aktiviteter (manuell A/B och [!UICONTROL Auto-Allocate]) och personalisering ([!UICONTROL Auto-Target]).

I den här självstudiekursen får du hjälp med de rekommenderade ändringarna för analys [!UICONTROL Auto-Target] verksamhet i [!UICONTROL Workspace].

Mer information finns i [Konfigurera A4T-rapporter i Analysis Workspace för Automatiskt mål-aktiviteter](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*.
