---
keywords: a4t;A4T;Analyser som rapportkälla för Target
description: Kan jag använda A4T med Automatiskt mål och Automatisk allokering?
title: A4T-stöd för Automatisk allokering och Automatiskt mål-aktiviteter
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4f0f1df1bcb6baad0e20c4dc1ae7e12751080d91
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 0%

---


# A4T-stöd för Automatisk allokering och Automatiskt mål-aktiviteter

Integreringen [!DNL Adobe Target]-to-[!DNL Adobe Analytics], som kallas [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) stöder aktiviteterna [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target].

Med A4T-integreringen kan du:

* Använd [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md):s multiväpnade bandit-funktion för att driva trafik till vinnande upplevelser.
* Använd [Automatisk målalgoritm](/help/c-activities/auto-target/auto-target-to-optimize.md) för maskininlärning för att välja en bästa upplevelse för varje besökare baserat på profil, beteende och kontext, samtidigt som du använder ett [!DNL Adobe Analytics]-målmått och [!DNL Adobe Analytics] omfattande rapporterings- och analysfunktioner.

Kontrollera att du har [implementerat A4T för användning med A/B Test- och Experience Targeting-aktiviteter](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Om du använder `analyticsLogging = client_side` måste du också skicka `sessionId`-värdet till [!DNL Analytics]. Mer information finns i [Analytics for Target-rapportering (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) i *Adobe Target SDKs*-guiden.

Så här kommer du igång:

1. När du skapar en A/B-testaktivitet väljer du ett av följande alternativ på sidan **[!UICONTROL Targeting]** som **[!UICONTROL Traffic Allocation Method]**:

   * [!UICONTROL Auto-allocate to best experience]
   * [!UICONTROL Auto-target for personalized experiences]

   ![Alternativ för trafikallokeringsmetoder: Manuell, Automatisk fördelning och Automatisk målning](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Mer information och stegvisa instruktioner finns i [Skapa en automatisk allokeringsaktivitet](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) och [Skapa en Automatisk målaktivitet](/help/c-activities/auto-target/create-auto-target.md).

1. Välj **[!UICONTROL Adobe Analytics]** för **[!UICONTROL Reporting Source]** på **[!UICONTROL Goals & Settings]**-sidan och välj den rapportsvit som motsvarar det optimeringsmål du vill ha.

1. Välj ett primärt målmått.

   * Välj **[!UICONTROL Conversion]** om du vill använda [!DNL Adobe Target] för att ange optimeringsmålet.
   * Välj **[!UICONTROL Use an Analytics metric]** och välj sedan ett mått från [!DNL Analytics] som ska användas som optimeringsmål. Du kan använda ett [!DNL Analytics]-konverteringsmått eller en [!DNL Analytics] anpassad händelse.

1. Spara och aktivera aktiviteten.

   [!UICONTROL Auto-Allocate] kommer att använda de valda mätvärdena för att optimera aktiviteten och locka besökarna till upplevelsen som maximerar målmätningen.

   eller

   [!UICONTROL Auto-Target] kommer att använda de valda mätvärdena för att optimera aktiviteten och leda besökarna till en personaliserad, bästa upplevelse.

1. Använd fliken **[!UICONTROL Reports]** om du vill visa aktivitetens rapportering genom att välja [!DNL Adobe Analytics] mått. Klicka på **[!UICONTROL View in Analytics]** för att segmentera dina rapporteringsdata ytterligare.

## Målmått som stöds

[!UICONTROL A4T] för  [!UICONTROL Auto-Allocate] och  [!UICONTROL Auto-Target] låter dig välja någon av följande måtttyper som det primära målmåttet för optimering:

* [!DNL Adobe Target] konverteringsmått
* [!DNL Adobe Analytics] konverteringsmått
* [!DNL Adobe Analytics] anpassade händelser

[!UICONTROL A4T] för  [!UICONTROL Auto-Allocate] och  [!UICONTROL Auto-Target] kräver att du väljer ett mätvärde som baseras på en binomial-händelse, det vill säga en händelse som antingen inträffar eller inte inträffar, till exempel ett klick, en konvertering, en ordning osv. Dessa typer av händelser kallas ibland även för Bernoulli, binära eller diskreta händelser.

[!UICONTROL A4T] for  [!UICONTROL Auto-Allocate] and  [!UICONTROL Auto-Target] does not support optimization for continuous metrics such as revenue, number of products ordered, session duration, number of page views in session, osv. Dessa metattyper som inte stöds kallas ibland icke-binomiala eller icke-Bernoulli-mått.

Följande måtttyper stöds inte som primära målmått:

* [!DNL Adobe Target] interaktions- och intäktsmått
* [!DNL Adobe Analytics] interaktions- och intäktsmått

   Det kan vara möjligt att välja ett [!DNL Analytics] engagemang- eller intäktsmått som primärt målmått eftersom [!DNL Target] inte kan identifiera och exkludera alla engagemang- och intäktsmått från [!DNL Analytics]. Var försiktig när du bara väljer binomial konverteringsstatistik eller anpassade händelser från [!DNL Analytics].

* [!DNL Adobe Analytics] beräknade värden

## Begränsningar och anteckningar

Vissa begränsningar och anteckningar gäller för både [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter. Andra begränsningar och anteckningar gäller för en aktivitetstyp eller en annan.

### Automatisk fördelning och Automatisk målgruppsanpassning

* Rapporteringskällan kan inte ändras från [!DNL Analytics] till [!DNL Target] eller vice versa efter att en aktivitet har aktiverats.
* Även om beräknade mätvärden inte stöds som primära målmätvärden är det ofta möjligt att uppnå det avsedda resultatet genom att i stället välja en anpassad händelse som primärt målmått. Om du till exempel vill optimera för ett mått som&quot;formulärifyllningar per besökare&quot; väljer du en anpassad händelse som motsvarar&quot;formulärifyllningar&quot; som det primära målmåttet. [!DNL Target] normaliserar automatiskt konverteringsmåtten per besök för att ta hänsyn till ojämn trafikfördelning, så det är inte nödvändigt att använda ett beräknat mätvärde för att utföra normaliseringen.
* [!DNL Target] använder attribueringsmodellen &quot;Same Touch&quot; i  [!UICONTROL Auto-Allocate] funktionen: Analyser för Target (A4T).

### Automatisk allokering

* [!UICONTROL Auto-Allocate] modellerna fortsätter att träna varannan timme som vanligt.

### Automatiskt mål

* [!UICONTROL Auto-Target] modellerna fortsätter att träna var 24:e timme som vanligt. Konverteringshändelsedata som kommer från [!DNL Analytics] fördröjs med ytterligare sex till 24 timmar. Fördröjningen innebär att trafikfördelningen med [!DNL Target] spårar de senaste händelser som spelats in i [!DNL Analytics]. Den största effekten under de första 48 timmarna efter att en aktivitet initialt har aktiverats. Aktivitetens prestanda speglar [!DNL Analytics] konverteringsbeteende närmare efter fem dagar. Du bör överväga att använda [!UICONTROL Auto-Allocate] i stället för [!UICONTROL Auto-Target] för korttidsaktiviteter där den största trafiken förekommer inom de första fem dagarna i aktivitetens livstid.
* När du använder [!DNL Analytics] som datakälla för en [!UICONTROL Auto-Target]-aktivitet anses sessionerna vara avslutade efter sex timmar. Konverteringar som inträffar efter sex timmar räknas inte.

Mer information finns i [Attribution models and lookback windows](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) i *Analytics Tools Guide*.
