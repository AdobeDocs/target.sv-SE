---
keywords: a4t;A4T;Analytics as reporting source for Target;analytics for target
description: Lär dig hur du skapar [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter i  [!DNL Target]  som använder  [!DNL Analytics]  som rapportkälla (A4T).
title: Stöder A4T [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: ddced04c730519dae74e70a60bed26462825ad23
workflow-type: tm+mt
source-wordcount: '1276'
ht-degree: 0%

---

# A4T-stöd för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] aktiviteter

Integrationen [!DNL Adobe Target]-till-[!DNL Adobe Analytics], som kallas [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), stöder [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter.

Med A4T-integreringen kan du:

* Använd funktionen [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) för beväpnade bandit för att driva trafik till vinnande upplevelser.
* Använd algoritmen [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) för maskininlärning för att välja den bästa upplevelsen för varje besökare. [!UICONTROL Auto-Target] väljer den bästa upplevelsen baserat på varje användares profil, beteende och kontext, samtidigt som ett [!DNL Adobe Analytics] målmått och de omfattande rapporterings- och analysfunktionerna i [!DNL Adobe Analytics] används.

Kontrollera att du har [implementerat A4T för användning med A/B Test- och Experience Targeting-aktiviteter](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Om du använder `analyticsLogging = client_side` måste du också skicka värdet `sessionId` till [!DNL Analytics]. Mer information finns i [Analytics for Target-rapportering (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html?lang=sv-SE){target=_blank} i *Adobe Target Developer Guide*.

Så här kommer du igång:

1. När du [skapar en [!UICONTROL A/B Test] activity](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) klickar du på kontrollen **[!UICONTROL Targeting]** på sidan **[!UICONTROL Traffic Allocation]** och väljer sedan önskad metod för trafikallokering i den högra rutan.

   ![Inställningar för trafikallokeringsmetod](/help/main/c-activities/assets/auto-target.png)

   Följande metoder för trafiktilldelning är tillgängliga:

   * **[!UICONTROL Manual (Default)]**: Ange hur många procent deltagare som ska se varje upplevelse. Ni kan dela upp procentsatserna jämnt mellan alla upplevelser eller ange högre eller lägre procenttal för varje upplevelse. Det totala antalet upplevelser måste vara 100 %.

   * **[!UICONTROL Auto-Allocate to best experience]**: De flesta aktivitetsdeltagare dirigeras automatiskt till upplevelser med högre prestanda. Vissa besökare tilldelas alla upplevelser för att kunna utforska upplevelser och för att identifiera förändringar i prestandatender. Mer information finns i [[!UICONTROL Auto-Allocate] - översikt](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Auto-Target for personalized experiences]**: [!DNL Target] använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser och sedan leverera den mest anpassade upplevelsen till besökare baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare. Mer information finns i [Översikt över Automatisk målning](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   Mer information och stegvisa instruktioner finns i [Skapa en automatisk allokering av aktivitet](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) och [Skapa en Automatisk målaktivitet](/help/main/c-activities/auto-target/create-auto-target.md).

1. Välj **[!UICONTROL Adobe Analytics]** för **[!UICONTROL Reporting Source]** på sidan **[!UICONTROL Goals & Settings]**, markera företaget och rapportera det programpaket som motsvarar det optimeringsmål du vill ha.

   ![Rapporterar Source-avsnitt på sidan Mål och inställningar](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Ange spårningsservern och sandlådan.

1. Välj ett [!UICONTROL Primary Goal]-mått.

   * Om du vill använda [!DNL Adobe Target] för att ange optimeringsmålet väljer du **[!UICONTROL Conversion]** .
   * Välj **[!UICONTROL Use an Analytics metric]** och välj sedan ett mått från [!DNL Analytics] som ska användas som optimeringsmål. Du kan använda ett [!DNL Analytics]-konverteringsmått som inte finns i kartongen eller en anpassad [!DNL Analytics]-händelse.

   Mer information finns i [Målmått som stöds](#supported) nedan.

1. Spara och aktivera aktiviteten.

   [!UICONTROL Auto-Allocate] använder det valda måttet för att optimera aktiviteten och för besökarna till upplevelsen som maximerar målmåttet.

   eller

   [!UICONTROL Auto-Target] använder dina valda mätvärden för att optimera aktiviteten och för besökarna till en personaliserad, bästa upplevelse.

1. Använd fliken **[!UICONTROL Reports]** om du vill visa aktivitetens rapportering efter ditt val av [!DNL Adobe Analytics]-mått. Klicka på **[!UICONTROL View in Analytics]** om du vill segmentera dina rapportdata mer och mer.

## Målmått som stöds {#supported}

Med [!UICONTROL A4T] för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] kan du välja någon av följande måtttyper som primärt målmått för optimering:

* [!DNL Adobe Target] konverteringsmått
* [!DNL Adobe Analytics] konverteringsmått
* [!DNL Adobe Analytics] anpassade händelser

>[!NOTE]
>
>När du har valt [!UICONTROL Use an Analytics Metric] väljer du [!UICONTROL Maximize Unique Visitor Conversion Rate] om du vill visa tillgängliga [!DNL Adobe Analytics] konverteringsmått och [!UICONTROL Maximize Metric Value per Visitor] om du vill utforska anpassade [!DNL Adobe Analytics]-händelser.

Med [!DNL Target] kan du välja mätvärden baserat på binomiala händelser eller mätvärden baserade på kontinuerliga händelser när du använder [!UICONTROL A4T] för [!UICONTROL Auto-Allocate] - och [!UICONTROL Auto-Target]-aktiviteter.

* **Mått baserade på binomiala händelser**: En binomial händelse inträffar eller inträffar inte. Binomiala händelser omfattar ett klick, en konvertering, en ordning och så vidare. Dessa typer av händelser kallas ibland även för Bernoulli, binära eller diskreta händelser.

* **Mätvärden baserade på kontinuerliga händelser**. Kontinuerliga mätvärden är intäkter, antal beställda produkter, sessionstid, antal sidvisningar under sessionen osv. Dessa typer av händelser kallas ibland icke-binomiala eller icke-Bernoulli-mått.

>[!IMPORTANT]
>
>Från och med version [!DNL Adobe Target Standard/Premium] 22.15.1 (8 mars och 9 mars 2023) fortsätter [!DNL Target] att stödja befintliga aktiviteter med de värden som nu inte stöds (visas i följande tabeller). Efter 9 september 2023 kommer dock dessa mått inte längre att stödjas i befintliga aktiviteter och alla aktiviteter som använder mätvärden som inte stöds kommer att upphöra för att tvinga den befintliga aktivitetsövergången till det nya beteendet.

### Påverkan på [!UICONTROL Auto-Allocate] aktiviteter

| Måttnamn | Stöds inte längre i: |
| --- | --- |
| [!UICONTROL averagepagedepth] | Konverteringsgrad, maximera måttvärde |
| [!UICONTROL averagetimespentonsite] | Konverteringsgrad, maximera måttvärde |
| [!UICONTROL bouncerate] | Konverteringsgrad, maximera måttvärde |
| [!UICONTROL bounces] | Konverteringsgrad, maximera måttvärde |
| [!UICONTROL entries] | Konverteringsgrad, maximera måttvärde |
| [!UICONTROL exits] | Konverteringsgrad, maximera måttvärde |
| [!UICONTROL pageviews] | Maximera måttvärde |
| [!UICONTROL reloads] | Maximera måttvärde |
| [!UICONTROL visitors] | Konverteringsgrad, maximera måttvärde |
| [!UICONTROL visits] | Maximera måttvärde |

### Påverkan på [!UICONTROL Auto-Target] aktiviteter

| Måttnamn | Stöds inte längre i: |
| --- | --- |
| [!UICONTROL cartremovals] | Maximera måttvärde |
| [!UICONTROL pageviews] | Maximera måttvärde |
| [!UICONTROL visitors] | Konverteringsgrad, maximera måttvärde |
| [!UICONTROL visits] | Maximera måttvärde |

## Begränsningar och anteckningar

Vissa begränsningar och anteckningar gäller för både [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter. Andra begränsningar och anteckningar gäller för en aktivitetstyp eller en annan.

### Automatisk allokering och Automatisk målning {#both}

* När du använder [!DNL Adobe Analytics] som rapportkälla för [!UICONTROL Auto-Allocate] eller [!UICONTROL Auto-Target] bör du alltid visa rapporter i [!DNL Analytics].
* Rapporteringskällan kan inte ändras från [!DNL Analytics] till [!DNL Target] eller vice versa efter att en aktivitet har aktiverats.
* Även om beräknade mätvärden inte stöds som primära målmätvärden är det ofta möjligt att uppnå det avsedda resultatet genom att i stället välja en anpassad händelse som primärt målmått. Om du till exempel vill optimera för ett mått som&quot;formulärifyllningar per besökare&quot; väljer du en anpassad händelse som motsvarar&quot;formulärifyllningar&quot; som det primära målmåttet. [!DNL Target] normaliserar automatiskt konverteringsmåtten per besök för att ta hänsyn till ojämn trafikfördelning, så det är inte nödvändigt att använda ett beräknat mätvärde för att utföra normalisering.

### Automatisk allokering {#aa}

* **Utbildningsfrekvens**: [!UICONTROL Auto-Allocate] modeller fortsätter att träna varje timme som vanligt.
* **Attributmodeller**: [!DNL Target] använder [!DNL Adobe Analytics] standardattribueringsmodellen för [!UICONTROL &#x200B; Auto-Allocate] aktiviteter som använder A4T.
* **Konfians**: Den konfidensformel som används av [!UICONTROL Auto-Allocate]-aktiviteter skiljer sig från den formel som visas som standard på panelen [!DNL Adobe Analytics] [!UICONTROL A4T] . [Som beskrivs här](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) använder [!UICONTROL Auto-Allocate] mer försiktiga konfidensintervall än vanliga [!UICONTROL A/B Test]-aktiviteter. Dessa konservativa konfidensnivåer kompenserar för upprepade utvärderingar (peeks) vid data. Därför visar standardrapporten i [!DNL Adobe Analytics] snävare konfidensintervall jämfört med de intervall som används av algoritmen [!UICONTROL Auto-Allocate]. Ni kan dock avgöra vilken upplevelse som prioriteras av algoritmerna utifrån vilken upplevelse som har fler unika besökare som skickas till den.
* **Vinnarstatus**: För närvarande är emblemen [&quot;Ingen vinnare än&quot; och&quot;vinnare&quot; &#x200B;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) inte tillgängliga på panelen [!UICONTROL A4T] i [!DNL Analysis Workspace]. Dessa emblem är inte heller tillgängliga om samma rapport visas i [!DNL Target]. Ett stjärntecken som visas i en [!DNL Target]-rapport för en [!UICONTROL Auto-Allocate]-aktivitet som använder A4T ska ignoreras. Det här emblemet innehåller regelbundna konfidensberäkningar, inte de som används av [!UICONTROL Auto-Allocate].

### Automatiskt mål {#at}

* [!UICONTROL Auto-Target] modeller fortsätter att träna var 24:e timme som vanligt. Konverteringshändelsedata som kommer från [!DNL Analytics] fördröjs med ytterligare sex till 24 timmar. Den här fördröjningen innebär fördelning av trafik med [!DNL Target] spårar de senaste händelser som registrerats i [!DNL Analytics]. Den här fördröjningen har störst effekt de första 48 timmarna efter att en aktivitet initialt har aktiverats. Aktivitetens prestanda speglar [!DNL Analytics]-konverteringsbeteendet närmare efter fem dagar.

  Använd [!UICONTROL Auto-Allocate] i stället för [!UICONTROL Auto-Target] för korttidsaktiviteter där den största trafiken inträffar inom de första fem dagarna i aktivitetens livstid.

* När du använder [!DNL Analytics] som datakälla för en [!UICONTROL Auto-Target]-aktivitet avslutas sessionerna efter sex timmar. Konverteringar som inträffar efter sex timmar räknas inte.

Mer information finns i [Attribution models and lookback windows](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=sv-SE) i *Analytics Tools Guide*.

## Självstudiekurser

Även om det finns omfattande analysfunktioner i [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace] krävs några ändringar av standardpanelen [!UICONTROL Analytics for Target] för att [!UICONTROL Auto-Allocate]- och [!UICONTROL Auto-Target]-aktiviteter ska kunna tolkas korrekt. Dessa ändringar krävs på grund av skillnader mellan experimentella aktiviteter (manuell A/B och [!UICONTROL Auto-Allocate]) och personaliseringsaktiviteter ([!UICONTROL Auto-Target]).

### Konfigurera A4T-rapporter i [!DNL Analysis Workspace] för [!UICONTROL Auto-Allocate]-aktiviteter

I den här självstudiekursen får du hjälp med de rekommenderade ändringarna för analys av [!UICONTROL Auto-Allocate]-aktiviteter i [!DNL Analysis Workspace].

Mer information finns i [Konfigurera A4T-rapporter i Analysis Workspace för automatisk allokering av aktiviteter](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=sv-SE){target=_blank} i *Adobe Target självstudier*.

### Konfigurera A4T-rapporter i [!DNL Analysis Workspace] för [!UICONTROL Auto-Target]-aktiviteter

I den här självstudiekursen får du hjälp med de rekommenderade ändringarna för analys av [!UICONTROL Auto-Target]-aktiviteter i [!DNL Analysis Workspace].

Mer information finns i [Konfigurera A4T-rapporter i Analysis Workspace för Automatiskt mål-aktiviteter](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=sv-SE){target=_blank} i *Adobe Target-självstudiekurser*.


