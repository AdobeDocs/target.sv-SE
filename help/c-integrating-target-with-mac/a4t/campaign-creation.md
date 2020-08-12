---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: Du kan konfigurera en aktivitet i Target Standard/Premium så att Adobe Analytics används som rapportkälla (A4T).
title: Skapa aktivitet
feature: null
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 0%

---


# Skapa aktivitet{#activity-creation}

Du kan konfigurera en aktivitet i [!DNL Target] som ska användas [!DNL Adobe Analytics] som rapportkälla (A4T).

Innan du ställer in en aktivitet som använder [!DNL Analytics] som rapportkälla måste du fastställa målet för aktiviteten, till exempel att förbättra intäkterna per besökare eller öka antalet klick i kundvagnen. Välj ett slutligt framgångsmått för aktiviteten. Även om du kan välja ytterligare mått när som helst i [!DNL Analytics]måste du ändå ange ett visst mått som testet ska påverka.

## Skapa en aktivitet som använder Analytics som rapportkälla

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
   Om rapportsviten/-sviterna fortfarande saknas i listan, [kontakta kundtjänst](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Ange spårningsservern.

   Se [Använda en analysspårningsserver](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

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

## Analyser för målstöd (A4T) för automatisk allokering av aktiviteter {#a4t-aa}

Vi har uppgraderat integreringen mellan Adobe Target och Adobe Analytics, så kallad [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md).

[!UICONTROL Auto-Allocate] nu support [!UICONTROL Analytics for Target]. Tack vare den här integreringen kan ni använda funktionen för autoallokering av flera beväpnade bandit för att driva trafik till vinnande upplevelser, samtidigt som ni använder [!DNL Adobe Analytics] målstatistik och/eller [!DNL Adobe Analytics] rapporterings- och analysfunktioner. Om du redan har [implementerat A4T för användning med A/B Test- och Experience Targeting-aktiviteter](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)är du redo att börja!

Så här kommer du igång:

1. Skapa en A/B-testaktivitet och välj **[!UICONTROL Auto-allocate to best experience]** som **[!UICONTROL Traffic Allocation Method]** på [!UICONTROL Targeting] sidan.
1. Välj **[!UICONTROL Adobe Analytics]** för din **[!UICONTROL Reporting Source]** **[!UICONTROL Goals & Settings]** sida och välj den rapportserie som motsvarar det optimeringsmål du vill ha.
1. Välj ett primärt målmått.

   Välj **[!UICONTROL Conversion]** att använda [!DNL Adobe Target] för att ange optimeringsmålet.

   eller

   Välj **[!UICONTROL Use an Analytics metric]** och välj sedan ett mätvärde [!DNL Analytics] som ska användas som optimeringsmål. Du kan använda ett användbart [!DNL Analytics] konverteringsmått eller en [!DNL Analytics] anpassad händelse.

1. Spara och aktivera aktiviteten.

   [!UICONTROL Auto-Allocate] kommer att använda de valda mätvärdena för att optimera aktiviteten och locka besökarna till upplevelsen som maximerar målmätningen.

1. Använd fliken **[!UICONTROL Reports]** för att visa aktivitetens rapportering efter ditt val av [!DNL Adobe Analytics] mätvärden. Klicka **[!UICONTROL View in Analytics]** för att segmentera dina rapportdata ytterligare.

### Målmått som stöds

A4T for [!UICONTROL Auto-Allocate] gör att du kan välja någon av följande måtttyper som det primära målmåttet för optimering:

* [!DNL Adobe Target] konverteringsmått
* [!DNL Adobe Analytics] konverteringsmått
* [!DNL Adobe Analytics] anpassade händelser

A4T för [!UICONTROL Auto-Allocate] kräver att du väljer ett mätvärde som baseras på en binomial-händelse, det vill säga en händelse som antingen inträffar eller inte inträffar, till exempel ett klick, en konvertering, en ordning osv. (Dessa typer av händelser kallas ibland även för Bernoulli, binära eller diskreta händelser.)

A4T för [!UICONTROL Auto-Allocate] stöder inte optimering för kontinuerliga mätvärden som intäkter, antal beställda produkter, sessionens varaktighet, antal sidvisningar i sessionen osv. (Dessa mätvärden som inte stöds kallas ibland icke-binomiala eller icke-Bernoulli-mätvärden.)

Följande måtttyper stöds inte som primära målmått:

* [!DNL Adobe Target] interaktions- och intäktsmått
* [!DNL Adobe Analytics] interaktions- och intäktsmått

   >[!NOTE]
   >
   >Det kan vara möjligt att välja [!DNL Analytics] interaktions- och intäktsmått som det primära målmåttet eftersom [!DNL Target] inte kan identifiera alla interaktions- och intäktsmått från [!DNL Analytics]. Var försiktig när du bara väljer binomial konverteringsstatistik eller anpassade händelser från [!DNL Analytics].

* Adobe Analytics beräknade värden

### Begränsningar och anteckningar

* Rapporteringskällan kan inte ändras från [!DNL Analytics] till [!DNL Target] eller vice versa när en aktivitet har aktiverats.
* Även om beräknade mätvärden inte stöds som primära målmätvärden är det ofta möjligt att uppnå det avsedda resultatet genom att i stället välja en anpassad händelse som primärt målmått. Om du till exempel vill optimera för ett mått som&quot;formulärifyllningar per besökare&quot; väljer du en anpassad händelse som motsvarar&quot;formulärifyllningar&quot; som det primära målmåttet. [!DNL Target] normaliserar automatiskt konverteringsmåtten per besök för att ta hänsyn till ojämn trafikfördelning, så det är inte nödvändigt att använda ett beräknat mätvärde för att utföra normaliseringen.
* [!DNL Target] använder attribueringsmodellen&quot;Same Touch&quot; i A4T-implementeringen av Automatisk allokering.

Mer information finns i [Attribution overview](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html) i *Analytics Tools Guide*.
