---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Du kan konfigurera en aktivitet i Target Standard/Premium så att Adobe Analytics används som rapportkälla (A4T).
title: Skapa en aktivitet som använder A4T som rapportkälla
feature: a4t general
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '1348'
ht-degree: 0%

---


# Skapa en aktivitet som använder Analytics som rapportkälla

Du kan konfigurera en aktivitet i [!DNL Target] som ska användas [!DNL Adobe Analytics] som rapportkälla (A4T).

Innan du ställer in en aktivitet som använder [!DNL Analytics] som rapportkälla måste du fastställa målet för aktiviteten, till exempel att förbättra intäkterna per besökare eller öka antalet klick i kundvagnen. Välj ett slutligt framgångsmått för aktiviteten. Även om du kan välja ytterligare mått när som helst i [!DNL Analytics]måste du ändå ange ett visst mått som testet ska påverka.

## Skapa aktiviteten

Att skapa en [!DNL Target] aktivitet som använder [!DNL Analytics] som rapportkälla liknar att skapa en vanlig [!DNL Target] aktivitet, med några viktiga skillnader. Du kan till exempel inte välja ett segment för rapportering när du skapar aktiviteten eftersom alla segment som är tillgängliga i [!DNL Analytics] kan användas när du visar en rapport.

1. Klicka på **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >Ett aktivitetsnamn får inte innehålla tecknet % om [!DNL Analytics] används som rapportkälla.

1. Välj aktivitetstyp och börja konfigurera aktiviteten.
1. När du kommer till den **[!UICONTROL Settings]** del av aktivitetsskapandet som du skapar väljer du **[!UICONTROL Adobe Analytics]** och anger ditt företag.
1. Välj en rapportsvit.

   Du kan välja vilken rapportserie som helst som är tillgänglig för dig i [!DNL Analytics]. Rapportsviten definierar var insamlade data ska vara tillgängliga. Virtuella rapportsviter ingår inte i rapportsvitlistan.

   Du kan stöta på två möjliga fel när du väljer rapportsviten:

   * Du får ett fel om att det inte finns några rapportsviter tillgängliga, men att ditt konto är korrekt konfigurerat.

      Du kanske måste kolla ditt [!DNL Analytics] företag. Om ditt [!DNL Adobe Experience Cloud] konto är knutet till mer än ett [!DNL Analytics] företag loggar du ut [!DNL Target]och loggar in [!DNL Analytics] under rätt företag. Återgå sedan till [!DNL Target]så läses rapportsviterna in.

   * Du ser inte den rapportserie som du förväntar dig.

      Endast rapportsviter som har etablerats för att ansluta till [!DNL Target] är tillgängliga för urval. Om du inte ser de rapportsviter du förväntar dig kan du först logga ut och sedan logga in igen för att [!DNL Adobe Experience Cloud] försöka igen.
   Om rapportsviten/-sviterna fortfarande saknas i listan, [kontakta kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Ange spårningsservern.

   Se [Använda en analysspårningsserver](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Definiera upplevelsen.
1. Ange aktivitetsmålet.

   Du måste välja ett framgångsmått som ska användas som mål för varje aktivitet. Aktivitetens mål är den konverteringsaktivitet som signalerar en lyckad aktivitet. Det är god praxis att aldrig göra ett test utan att ha något mål att förbättra på något specifikt sätt. Du kan välja valfritt [!DNL Analytics] mätresultat i [!DNL Analytics] mätväljaren.

   >[!NOTE]
   >
   >Du kan skicka ett anpassat målbaserat mått till [!DNL Analytics] i stället för att bara förlita dig på [!DNL Analytics] data. Du kan till exempel övervaka när du klickar på en sida, som vanligtvis inte spåras av [!DNL Analytics]. Det här anpassade måttet skickas [!DNL Analytics] automatiskt från [!DNL Target] servern och visas som&quot;[!DNL Target] konverteringsmåttet&quot; i mätväljaren i [!DNL Analytics]. Konverteringsmåttet [!DNL Target] är tomt om du väljer att använda [!DNL Analytics] mått.

   Att du anger ett mål innebär inte att du inte kan använda ett annat mått när du utvärderar testresultat. Målet är dock en påminnelse om det som du vill förbättra med aktiviteten.

   Besökaren är kvar i aktiviteten när de har nått målet. Besökaren fortsätter att se aktivitetsinnehåll men räknas inte som en ny aktivitetspost.

   >[!NOTE]
   >
   >När du skapar en aktivitet efter att du har konfigurerat [!DNL Analytics] den som rapportkälla finns det inget alternativ för att konfigurera målgrupper för rapportering. [!DNL Analytics] segment är tillgängliga i rapporten för [!DNL Target] aktiviteter.

1. Klicka på **[!UICONTROL Save]**.

## Analyser för Target-stöd (A4T) för aktiviteterna Automatisk allokering och Automatiskt mål {#a4t-aa}

Vi har uppgraderat integreringen mellan Adobe Target och Adobe Analytics, så kallad [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md). Automatisk allokering och Automatisk målfunktion har nu stöd för Analytics for Target.

Med den här integreringen kan du:

* Använd [Automatisk fördelning](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)av multiväpnade bandit-funktioner för att driva trafik till vinnande upplevelser
* Använd [Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md):s unika maskininlärningsalgoritm för att välja den bästa upplevelsen för varje besökare utifrån deras profil, beteende och kontext, samtidigt som ni använder [!DNL Adobe Analytics] målmätvärden och [!DNL Adobe Analytics]de omfattande rapporterings- och analysfunktionerna.

Kontrollera att du har [implementerat A4T för användning med A/B Test- och Experience Targeting-aktiviteter](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Om du använder `analyticsLogging = client_side`måste du också skicka `sessionId` värdet till [!DNL Analytics]. Mer information finns i [Analytics for Target-rapportering](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) (A4T) i guiden för *Adobe Target SDK* .

Så här kommer du igång:

1. När du skapar en A/B-testaktivitet väljer du något av följande alternativ på **[!UICONTROL Targeting]** sidan **[!UICONTROL Traffic Allocation Method]**:

   * Autoallokera till bästa upplevelse
   * Automatisk målgruppsanpassning för personaliserade upplevelser

1. Välj **[!UICONTROL Adobe Analytics]** för din **[!UICONTROL Reporting Source]** **[!UICONTROL Goals & Settings]** sida och välj den rapportserie som motsvarar det optimeringsmål du vill ha.

1. Välj ett primärt målmått.

   * Välj **[!UICONTROL Conversion]** att använda [!DNL Adobe Target] för att ange optimeringsmålet.
   * Välj **[!UICONTROL Use an Analytics metric]** och välj sedan ett mätvärde [!DNL Analytics] som ska användas som optimeringsmål. Du kan använda ett värde för out-of-box- [!DNL Analytics] konvertering eller en [!DNL Analytics] anpassad händelse.

1. Spara och aktivera aktiviteten.

   [!UICONTROL Auto-Allocate] kommer att använda de valda mätvärdena för att optimera aktiviteten och locka besökarna till upplevelsen som maximerar målmätningen.

   eller

   [!UICONTROL Auto-Target] kommer att använda de valda mätvärdena för att optimera aktiviteten och leda besökarna till en personaliserad, bästa upplevelse.

1. Använd fliken **[!UICONTROL Reports]** för att visa aktivitetens rapportering efter ditt val av [!DNL Adobe Analytics] mätvärden. Klicka **[!UICONTROL View in Analytics]** för att segmentera dina rapportdata ytterligare.

### Målmått som stöds

[!UICONTROL A4T] för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] låter dig välja någon av följande måtttyper som det primära målmåttet för optimering:

* [!DNL Adobe Target] konverteringsmått
* [!DNL Adobe Analytics] konverteringsmått
* [!DNL Adobe Analytics] anpassade händelser

[!UICONTROL A4T] for [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] kräver att du väljer ett mätvärde som baseras på en binomial-händelse, det vill säga en händelse som antingen inträffar eller inte inträffar, till exempel ett klick, en konvertering, en ordning osv. (Dessa typer av händelser kallas ibland även för Bernoulli, binära eller diskreta händelser.)

[!UICONTROL A4T] för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] stöder inte optimering för kontinuerliga mätvärden som intäkter, antal beställda produkter, sessionslängd, antal sidvisningar under sessionen osv. (Dessa mätvärden som inte stöds kallas ibland icke-binomiala eller icke-Bernoulli-mätvärden.)

Följande måtttyper stöds inte som primära målmått:

* [!DNL Adobe Target] interaktions- och intäktsmått
* [!DNL Adobe Analytics] interaktions- och intäktsmått

   Det kan vara möjligt att välja ett [!DNL Analytics] engagemangs- eller intäktsmått som det primära målmåttet, eftersom [!DNL Target] det inte går att identifiera och exkludera alla engagemangs- och intäktsmått från [!DNL Analytics]. Var försiktig när du bara väljer binomial konverteringsstatistik eller anpassade händelser från [!DNL Analytics].

* [!DNL Adobe Analytics] beräknade värden

### Begränsningar och anteckningar

Vissa begränsningar och anteckningar gäller för både Automatisk allokering och Automatisk målning. Andra begränsningar och anteckningar gäller för en aktivitetstyp eller en annan.

#### Automatisk fördelning och Automatisk målgruppsanpassning

* Rapporteringskällan kan inte ändras från [!DNL Analytics] till [!DNL Target] eller vice versa efter att en aktivitet har aktiverats.
* Även om beräknade mätvärden inte stöds som primära målmätvärden är det ofta möjligt att uppnå det avsedda resultatet genom att i stället välja en anpassad händelse som primärt målmått. Om du till exempel vill optimera för ett mått som&quot;formulärifyllningar per besökare&quot; väljer du en anpassad händelse som motsvarar&quot;formulärifyllningar&quot; som det primära målmåttet. [!DNL Target] normaliserar automatiskt konverteringsmåtten per besök för att ta hänsyn till ojämn trafikfördelning, så det är inte nödvändigt att använda ett beräknat mätvärde för att utföra normaliseringen.
* [!DNL Target] använder attribueringsmodellen&quot;Same Touch&quot; i A4T-implementeringen [!UICONTROL Auto-Allocate] .

#### Automatisk allokering

* [!UICONTROL Auto-Allocate] modellerna fortsätter att träna varannan timme som vanligt.

#### Automatiskt mål

* [!UICONTROL Auto-Target] modellerna fortsätter att träna var 24:e timme som vanligt. Konverteringshändelsedata som kommer från [!DNL Analytics] fördröjs dock med ytterligare 6 till 24 timmar. Förseningen innebär att trafiken distribueras genom [!DNL Target] att de senaste händelser som registreras i [!DNL Analytics]spåras. Detta kommer att få störst effekt inom de första 48 timmarna efter det att en aktivitet först har aktiverats. Aktivitetens prestanda kommer att mer noggrant spegla [!DNL Analytics] konverteringsbeteendet efter fem dagar. Du bör överväga att använda [!UICONTROL Auto-Allocate] istället [!UICONTROL Auto-Target] för korttidsaktiviteter där den största trafiken sker inom de första fem dagarna av aktivitetens livstid.
* När du använder [!DNL Analytics] som datakälla för en [!UICONTROL Auto-Target] aktivitet anses sessionerna vara avslutade efter sex timmar. Konverteringar som inträffar efter sex timmar räknas inte.

Mer information finns i [Attribution models and lookback windows](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/models.html) i *Analytics Tools Guide*.
