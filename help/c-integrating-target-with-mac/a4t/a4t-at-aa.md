---
keywords: a4t;A4T;Analyser som rapportkälla för Target
description: Lär dig hur du skapar aktiviteter för automatisk fördelning och automatisk målanpassning i Adobe Target som använder Analytics som rapportkälla (A4T).
title: Har A4T stöd för automatisk fördelning och automatisk målanpassning?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bd226d255ece635272e6c3f372c6936a9acd5faf
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 0%

---


# A4T-stöd för Automatisk allokering och Automatiskt mål-aktiviteter

Integreringen [!DNL Adobe Target]-to-[!DNL Adobe Analytics], som kallas [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) stöder aktiviteterna [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target].

Med A4T-integreringen kan du:

* Använd [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md):s flerarmade bandit-funktion för att driva trafik till vinnande upplevelser.
* Använd [Automatisk målalgoritm](/help/c-activities/auto-target/auto-target-to-optimize.md) för maskininlärning för att välja den bästa upplevelsen för varje besökare. Auto-Target väljer den bästa upplevelsen baserat på användarnas profiler, beteenden och kontext samtidigt som ett [!DNL Adobe Analytics]-målmått och [!DNL Adobe Analytics]-omfattande rapporterings- och analysfunktioner används.

Kontrollera att du har [implementerat A4T för användning med A/B Test- och Experience Targeting-aktiviteter](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Om du använder `analyticsLogging = client_side` måste du också skicka `sessionId`-värdet till [!DNL Analytics]. Mer information finns i [Analytics for Target-rapportering (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) i *Adobe Target SDKs*-guiden.

Så här kommer du igång:

1. När du skapar en A/B-testaktivitet väljer du ett av följande alternativ på sidan **[!UICONTROL Targeting]** som **[!UICONTROL Traffic Allocation Method]**:

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experiences]

   ![Alternativ för trafikallokeringsmetoder: Manuell, Automatisk fördelning och Automatisk målning](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Mer information och stegvisa instruktioner finns i [Skapa en automatisk allokeringsaktivitet](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) och [Skapa en Automatisk målaktivitet](/help/c-activities/auto-target/create-auto-target.md).

1. Välj **[!UICONTROL Adobe Analytics]** för **[!UICONTROL Reporting Source]** på **[!UICONTROL Goals & Settings]**-sidan och välj den rapportsvit som motsvarar det optimeringsmål du vill ha.

   ![Avsnittet Rapporteringskälla på sidan Mål och inställningar](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Välj ett primärt målmått.

   * Om du vill använda [!DNL Adobe Target] för att ange optimeringsmålet väljer du **[!UICONTROL Conversion]** .
   * Välj **[!UICONTROL Use an Analytics metric]** och välj sedan ett mått från [!DNL Analytics] som ska användas som optimeringsmål. Du kan använda ett [!DNL Analytics]-konverteringsmått eller en [!DNL Analytics] anpassad händelse.

   Mer information finns i [Målmått](#supported) nedan.

1. Spara och aktivera aktiviteten.

   [!UICONTROL Auto-Allocate] använder det valda måttet för att optimera aktiviteten och för besökarna till upplevelsen som maximerar målmåttet.

   eller

   [!UICONTROL Auto-Target] använder de mätvärden du väljer för att optimera aktiviteten och locka besökarna till en personaliserad, bästa upplevelse.

1. Använd fliken **[!UICONTROL Reports]** om du vill visa aktivitetens rapportering genom att välja [!DNL Adobe Analytics] mått. Klicka på **[!UICONTROL View in Analytics]** för att segmentera dina rapporteringsdata ytterligare.

## Målmått {#supported} som stöds

[!UICONTROL A4T] för  [!UICONTROL Auto-Allocate] och  [!UICONTROL Auto-Target] låter dig välja någon av följande måtttyper som det primära målmåttet för optimering:

* [!DNL Adobe Target] konverteringsmått
* [!DNL Adobe Analytics] konverteringsmått
* [!DNL Adobe Analytics] anpassade händelser

[!UICONTROL A4T] för  [!UICONTROL Auto-Allocate] och  [!UICONTROL Auto-Target] kräver att du väljer ett mått som baseras på en binomial-händelse. En binomialhändelse inträffar eller inträffar inte. Binomiala händelser omfattar ett klick, en konvertering, en ordning och så vidare. Dessa typer av händelser kallas ibland även för Bernoulli, binära eller diskreta händelser.

[!UICONTROL A4T] för  [!UICONTROL Auto-Allocate] och  [!UICONTROL Auto-Target] stöder inte optimering för kontinuerliga mätvärden. Kontinuerliga mätvärden är intäkter, antal beställda produkter, sessionstid, antal sidvisningar under sessionen osv. Dessa metattyper som inte stöds kallas ibland icke-binomiala eller icke-Bernoulli-mått.

Följande måtttyper stöds inte som primära målmått:

* [!DNL Adobe Target] interaktions- och intäktsmått
* [!DNL Adobe Analytics] interaktions- och intäktsmått

   Det går att välja ett [!DNL Analytics]-mått för engagemang eller intäkt som primärt målmått eftersom [!DNL Target] inte kan identifiera och exkludera alla mått för engagemang och intäkt från [!DNL Analytics]. Välj endast binomialkonverteringsmått eller anpassade händelser från [!DNL Analytics].

* [!DNL Adobe Analytics] beräknade värden

## Begränsningar och anteckningar

Vissa begränsningar och anteckningar gäller för både [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter. Andra begränsningar och anteckningar gäller för en aktivitetstyp eller en annan.

### Automatisk fördelning och Automatisk målgruppsanpassning

* Rapporteringskällan kan inte ändras från [!DNL Analytics] till [!DNL Target] eller omvänt efter att en aktivitet har aktiverats.
* Även om beräknade mätvärden inte stöds som primära målmätvärden är det ofta möjligt att uppnå det avsedda resultatet genom att i stället välja en anpassad händelse som primärt målmått. Om du till exempel vill optimera för ett mått som&quot;formulärifyllningar per besökare&quot; väljer du en anpassad händelse som motsvarar&quot;formulärifyllningar&quot; som det primära målmåttet. [!DNL Target] normaliserar automatiskt konverteringsmåtten per besök för att ta hänsyn till ojämn trafikfördelning, så det är inte nödvändigt att använda ett beräknat mätvärde för att utföra normaliseringen.
* [!DNL Target] använder attribueringsmodellen &quot;Same Touch&quot; i  [!UICONTROL Auto-Allocate] funktionen: Analyser för Target (A4T).

### Automatisk allokering

* [!UICONTROL Auto-Allocate] modellerna fortsätter att träna varannan timme som vanligt.

### Automatiskt mål

* [!UICONTROL Auto-Target] modellerna fortsätter att träna var 24:e timme som vanligt. Konverteringshändelsedata som kommer från [!DNL Analytics] fördröjs med ytterligare sex till 24 timmar. Fördröjningen innebär att trafiken distribueras med [!DNL Target] för att spåra de senaste händelser som spelats in i [!DNL Analytics]. Den här fördröjningen har störst effekt de första 48 timmarna efter att en aktivitet initialt har aktiverats. Aktivitetens prestanda speglar [!DNL Analytics] konverteringsbeteende närmare efter fem dagar. Överväg att använda [!UICONTROL Auto-Allocate] i stället för [!UICONTROL Auto-Target] för korttidsaktiviteter där den största trafiken förekommer inom de första fem dagarna av aktivitetens livstid.
* När du använder [!DNL Analytics] som datakälla för en [!UICONTROL Auto-Target]-aktivitet avslutas sessionerna efter sex timmar. Konverteringar som inträffar efter sex timmar räknas inte.

Mer information finns i [Attribution models and lookback windows](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) i *Analytics Tools Guide*.

## Självstudiekurs: Ställa in A4T-rapporter i Analysis Workspace för Auto-Target-aktiviteter {#tutorial}

Även om det finns omfattande analysfunktioner i [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace] krävs några ändringar i standardpanelen [!UICONTROL Analytics for Target] för att automålsaktiviteter ska kunna tolkas korrekt. Dessa ändringar krävs på grund av skillnader mellan experimentella aktiviteter (manuell A/B och [!UICONTROL Auto-Allocate]) och personaliseringsaktiviteter ([!UICONTROL Auto-Target]).

I den här självstudiekursen får du hjälp med de rekommenderade ändringarna för analys av [!UICONTROL Auto-Target]-aktiviteter i [!UICONTROL Workspace].

Mer information finns i [Konfigurera A4T-rapporter i Analysis Workspace för Automatiskt mål-aktiviteter](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) i *Adobe Target Tutorials*.