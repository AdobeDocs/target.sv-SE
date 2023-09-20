---
keywords: automatiserad trafikallokering;målinriktning;vinnare;statistisk garanti;självförtroende;bestämma vinnare;lyft;självförtroende;standard;standardupplevelse;autoallokera;autoallokera
description: Lär dig hur du tolkar resultatet av en [!UICONTROL Auto-Allocate] A/B-verksamhet i Adobe [!DNL Target] genom att undersöka viktiga indikatorer, bland annat lyft och förtroende.
title: Hur tolkar jag [!UICONTROL Auto-Allocate] Rapporter?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: e9976135c46f6658030b07fce384364f0c9ff0ed
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---

# Tolka autofördelningsrapporter

Tolka resultatet av en [!UICONTROL Auto-Allocate] A/B-aktivitet i [!UICONTROL Adobe Target] genom att undersöka viktiga indikatorer, bland annat lyft och förtroende.

Många marknadsförare gör misstag genom att i förväg deklarera en vinnande upplevelse innan resultatet visar på den tydliga vinnaren. [!DNL Target] gör det enklare för dig att avgöra vinnaren.

Allmän information om hur du deklarerar en vinnare finns i [Tio vanliga A/B-testfall och hur man undviker dem](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identifiera den vinnande upplevelsen {#section_24007470CF5B4D30A06610CE8DD23CE3}

När du använder [!UICONTROL Auto-Allocate] funktion, [!DNL Target] visar ett emblem högst upp på aktivitetens sida som anger &quot;Ingen vinnare ännu&quot; tills aktiviteten når det minsta antalet konverteringar med tillräcklig säkerhet.

![Inget emblem för vinnare](/help/main/c-activities/automated-traffic-allocation/assets/no-winner.png)

När en klar vinnare deklareras, [!DNL Target] visar &quot;Winner: Experience *X*.&quot;

![vinnarbild](assets/winner.png)

>[!NOTE]
>
>Automatisk fördelning av aktiviteter är utformade för att hitta den bästa upplevelsen bland alla alternativ och inte bara för att göra parvisa jämförelser med kontroll.

## Statistiska garantier för automatisk fördelning {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

Efter en A/B-aktivitet [!UICONTROL Auto-Allocate] garanterar att den fastställda vinnaren har en faktisk falskt positiv nivå på 5 %. Detta innebär att bara 5 % av tiden är den bestämda vinnaren egentligen inte den bästa upplevelsen bland alla upplevelser i aktiviteten. För [A/A-test](/help/main/c-activities/t-test-ab/aa-testing.md) (med identiska upplevelser), [!DNL Target] avslutar ett test mindre än 5 % av tiden. Det förväntade beteendet för ett A/A-test (med identiska upplevelser) är att det körs oavbrutet, så vinnarmärket ska aldrig visas.

[!DNL Target] använder inte p-value-baserad säkerhet för [!UICONTROL Auto-Allocate].

The [!UICONTROL Confidence] kolumn i en [!UICONTROL Auto-Allocate] (se bilden nedan) visar sannolikheten för att en upplevelse blir vinnare inom 1 % felmarginal. Algoritmen använder en minsta mätbar effekt på 1 % mellan den bästa och den näst bästa konverteringsgraden. Algoritmen använder [Bernstein Inequality](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) för att beräkna denna sannolikhet.

Normala A/B-tester beräknar tillförlitlighet baserat på p-värden. [!UICONTROL Auto-Allocate] använder inte p-värden. P-värden &quot;löst&quot; beräknar sannolikheten för att en viss upplevelse skiljer sig från kontrollen. Dessa p-värden kan bara användas för att avgöra om en upplevelse kan skilja sig från kontrollen. Dessa värden kan inte användas för att avgöra om en upplevelse skiljer sig från en annan upplevelse (inte kontroll).

>[!IMPORTANT]
>
>[!DNL Target] visar en vinnare efter ett fördefinierat minsta antal konverteringar, men det slutliga beslutet att välja vinnaren ska alltid vara baserat på resultatet av [!DNL Adobe Target] Beräkna samplingsstorlek. [!DNL Target] tar inte hänsyn till en områdes grundläggande konverteringsgrad och andra viktiga aspekter som matas in i beräknaren för att fastställa aktivitetens varaktighet. Detta resulterar i [!DNL Target] kan visa en vinnare tidigare än vad som krävs baserat på ett minsta antal konverteringar. Mer information finns i [Beräkna samplingsstorlek](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Förstå Lyft- och förtroenderapportering i [!UICONTROL Auto-Allocate] verksamhet {#lift-confidence}

I [!UICONTROL Auto-Allocate] aktiviteter definieras den första upplevelsen (som standard med namnet Experience A) alltid som en&quot;kontroll&quot;-upplevelse på [!UICONTROL Reports] -fliken. Denna erfarenhet behandlas inte som en riktig statistisk kontroll i den modellering som används för att fastställa upplevelsernas resultat, men den behandlas som en referens eller baslinje för vissa siffror i rapporten.

Det numeriska&quot;Lyft&quot;-värdet och 95 %-gränserna för varje upplevelse beräknas alltid med referens till den definierade&quot;Kontroll&quot;-upplevelsen. Den definierade kontrollupplevelsen kan inte ha en lyft i förhållande till sig själv, så ett tomt &quot;—&quot;-värde rapporteras för den här upplevelsen. Till skillnad från A/B-tester, [!UICONTROL Auto-Allocate] om en upplevelse fungerar sämre än den definierade kontrollen rapporteras inget negativt Lyft-värde, utan &quot;—&quot; visas.

Visad [!UICONTROL Confidence Interval] staplar representerar det 95-procentiga konfidensintervallet runt den genomsnittliga uppskattningen av en upplevelses konverteringsgrad. Dessa fält är också färgkodade med hänsyn till den definierade &quot;Kontroll&quot;-upplevelsen. &quot;Kontrollfältet&quot; är alltid grått. De delar av konfidensintervallen som ligger under &quot;Kontroll&quot; - upplevelsens konfidensintervall är röda och de delar av konfidensintervallen som ligger över &quot;Kontroll&quot; - upplevelsen är färgade i grönt.

En vinnare hittas när den ledande upplevelsen är 95 % [!UICONTROL Confidence Interval] överlappar inte andra upplevelser. Den vinnande upplevelsen får en grön stjärna till vänster om upplevelsenamnet och i banderollen&quot;Vinnare&quot;. När ingen stjärna är synlig står det &quot;Ingen vinnare än&quot; på banderollen och ingen vinnare har hittats ännu.

Ett&quot;konfidensnummer&quot; rapporteras också bredvid den nuvarande ledande eller vinnande upplevelsen. Denna siffra rapporteras endast tills den ledande upplevelsen [!UICONTROL Confidence] når minst 60 %. Om det finns två upplevelser i [!UICONTROL Auto-Allocate] -aktivitet, det här talet representerar konfidensnivån för att upplevelsen fungerar bättre än den andra. Om det finns fler än två upplevelser i [!UICONTROL Auto-Allocate] -aktivitet, det här talet representerar den konfidensnivå som upplevelsen fungerar bättre än den definierade &quot;Kontroll&quot;-upplevelsen. Om&quot;Kontroll&quot;-upplevelsen vinner rapporteras ingen siffra för&quot;förtroende&quot;.

## Vanliga frågor {#section_C8E068512A93458D8C006760B1C0B6A2}

Här följer svar på vanliga frågor:

### Det har gått några dagar framåt. Varför visar alla konfidensvärden fortfarande 0 %?

En av följande orsaker beskriver varför 0 % visas i rapportens [!UICONTROL Confidence] kolumn för alla aktiviteter:

* Manuella A/B-tester och [!UICONTROL Auto-Allocate] använd olika statistik för att visa [!UICONTROL Confidence] värden.

  Manuella A/B-tester använder p-värden baserade på [Welch&#39;s t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test). Ett P-värde är sannolikheten att hitta den observerade (eller mer extrema) skillnaden mellan en upplevelse och kontrollen, eftersom det i verkligheten inte finns någon sådan skillnad. Dessa P-värden kan bara användas för att avgöra om observerade data är konsekventa med en viss upplevelse och om kontrollen är densamma. Dessa värden kan inte användas för att avgöra om en upplevelse skiljer sig från en annan upplevelse (inte kontroll).

  [!UICONTROL Auto-Allocate] visar sannolikheten för att en viss upplevelse ska bli en riktig vinnare för alla upplevelser i aktiviteten. Det är bara en vinnande upplevelse (som sannolikt är vinnaren) som har ett värde som inte är noll. Alla andra är mest benägna att vara förlorare och visa 0 %.

* [!UICONTROL Auto-Allocate] börjar känna självförtroende först efter att den vinnande upplevelsen fått 60 % självförtroende. Dessa konfidensnivåer uppträder vanligtvis på ungefär hälften så lång tid som ett normalt A/B-test skulle ta att slutföra (även om denna tidsram inte garanteras). Om du vill avgöra hur länge ett normalt A/B-test skulle köras använder du [!DNL Adobe Target] [Beräkna samplingsstorlek](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6): konverteringsgraden för plugin-programmet i &quot;Baseline conversion rate&quot;, &quot;5%&quot; för &quot;Lift&quot; och 95% för &quot;Confidence&quot;. Normalt börjar förtroendet visa sig efter att varje upplevelse har fyllt 50 % av det antal samplingar som krävs per upplevelse. Då får du en uppfattning om när självförtroende börjar uppstå.

* Om rapporten visar 0 procent över hela linjen är det sannolikt för tidigt i verksamheten.

### Finns brickorna &quot;Ingen vinnare&quot;, &quot;vinnare&quot; och &quot;stjärna&quot; för [!UICONTROL Auto-Allocate] aktiviteter som använder [!UICONTROL Analytics as the reporting source] (A4T)?

Märken &quot;Ingen vinnare ännu&quot; och &quot;vinnare&quot; finns för närvarande inte i [!UICONTROL A4T] panel i [!DNL Analysis Workspace]. Dessa emblem är inte heller tillgängliga om samma rapport visas i [!DNL Target]. En &quot;stjärna&quot;-bricka som visas i en [!DNL Target] rapport för [!UICONTROL Auto-Allocate] -aktivitet som använder A4T ska ignoreras.

Mer information om detta och andra begränsningar och anteckningar finns i [Automatisk allokering](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) in *A4T-stöd för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet*.


