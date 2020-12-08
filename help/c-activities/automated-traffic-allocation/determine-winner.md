---
keywords: automated traffic allocation;targeting;winner;statistical guarantee;confidence;determine winner;lift;confidence;default;default experience
description: Bestäm en vinnare i en automatisk fördelning av A/B-aktivitet genom att visa indikatorer i Adobe Target användargränssnitt.
title: Identifiera en vinnare
feature: auto-allocate
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 0%

---


# Tolka autofördelningsrapporter {#determine-a-winner}

Tolka resultaten av en automatisk fördelning av A/B-aktivitet genom att undersöka viktiga indikatorer, inklusive lyft och förtroende, i målgränssnittet.

Många marknadsförare gör misstag genom att i förväg deklarera en vinnande upplevelse innan resultatet visar på den tydliga vinnaren. Vi har nu gjort det enklare för dig att avgöra vinnaren.

>[!NOTE]
>
>Allmän information om hur du deklarerar en vinnare finns i [Tio vanliga A/B-testfall och hur du undviker dem](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identifiera den vinnande upplevelsen {#section_24007470CF5B4D30A06610CE8DD23CE3}

När du använder [!UICONTROL Auto-Allocate] funktionen [!DNL Target] visas ett emblem längst upp på aktivitetssidan som anger &quot;Ingen vinnare än&quot; tills aktiviteten når det minsta antalet konverteringar med tillräcklig säkerhet.

![Inget emblem för vinnare](/help/c-activities/automated-traffic-allocation/assets/no-winner.png)

När en klar vinnare deklareras visas [!DNL Target] &quot;Vinnare: Experience X.&quot;

![](assets/winner.png)

>[!NOTE]
>
>Automatisk fördelning av aktiviteter är utformade för att hitta den bästa upplevelsen bland alla alternativ och inte bara för att göra parvisa jämförelser med kontroll.

## Statistiska garantier för automatisk fördelning {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

Efter en A/B-aktivitet garanterar Auto-Allocate att den fastställda vinnaren har en faktisk falskt positiv nivå på 5 %. Detta innebär att bara 5 % av tiden är den bestämda vinnaren egentligen inte den bästa upplevelsen bland alla upplevelser i aktiviteten. För ett A/A-test (med identiska upplevelser) sluter vi ett test som är mindre än 5 % av tiden. Det förväntade beteendet för ett A/A-test (med identiska upplevelser) är att det körs oavbrutet, så vinnarmärket ska aldrig visas.

Vi använder inte p-value-baserad säkerhet för Automatisk allokering.

Kolumnen Konfidentiellt i en Automatisk allokering-aktivitet (se nedan) visar sannolikheten för att en upplevelse blir vinnare inom en felmarginal på 1 % (d.v.s. algoritmen använder en minsta detekterbar effekt på 1 % mellan den bästa och den näst bästa konverteringsgraden). Observera att algoritmen använder [Bernstein Innequality](https://en.wikipedia.org/wiki/Bernstein_inequalities_(probability_theory)) för att beräkna den här sannolikheten.

Normala A/B-tester beräknar tillförlitlighet baserat på p-värden. Autoallokera använder inte p-värden. P-värden &quot;löst&quot; beräknar sannolikheten för att en viss upplevelse skiljer sig från kontrollen. Dessa p-värden kan bara användas för att avgöra om en upplevelse kan skilja sig från kontrollen. Dessa värden kan inte användas för att avgöra om en upplevelse skiljer sig från en annan upplevelse (inte kontroll).

>[!IMPORTANT]
>
>Target visar en vinnare efter ett fördefinierat minsta antal konverteringar. Men det slutliga beslutet att välja vinnare bör alltid vara baserat på resultatet av Adobe Target [beräkningsverktyg](https://docs.adobe.com/content/target-microsite/testcalculator.html)för provstorlek. Målet tar inte hänsyn till en områdes grundläggande konverteringsgrad och andra viktiga aspekter som matas in i beräknaren för att fastställa aktivitetens varaktighet. Det innebär att Target kan visa en vinnare som är tidigare än vad som krävs på grundval av ett minsta antal konverteringar. Mer information finns i Beräkna [provstorlek](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Förstå Lyft- och förtroenderapportering i Automatisk allokering av aktiviteter {#lift-confidence}

I Automatisk allokering definieras alltid den första upplevelsen (som standard med namnet Experience A) som en kontrollupplevelse på fliken Rapporter. Denna erfarenhet behandlas inte som en riktig statistisk kontroll i den modellering som används för att fastställa upplevelsernas resultat, men den behandlas som en referens eller baslinje för vissa siffror i rapporten.

Det numeriska&quot;Lyft&quot;-värdet och 95 %-gränserna för varje upplevelse beräknas alltid med referens till den definierade&quot;Kontroll&quot;-upplevelsen. Den definierade kontrollupplevelsen kan inte ha en lyft i förhållande till sig själv, så ett tomt &quot;—&quot;-värde rapporteras för den här upplevelsen. Till skillnad från vid A/B-tester rapporteras inte ett negativt Lyft-värde i autofördelningstester om en upplevelse fungerar sämre än den definierade kontrollen. i stället visas &quot;—&quot;.

Fälten för konfidensintervall representerar det 95-procentiga konfidensintervallet runt den genomsnittliga uppskattningen av en upplevelses konverteringsgrad. De är också färgkodade i förhållande till den definierade &quot;Kontroll&quot;-upplevelsen. Kontrollfältet är alltid grått. De delar av konfidensintervallen som ligger under &quot;Kontrollupplevelsens&quot; konfidensintervall är röda och de delar av konfidensintervallen som ligger över &quot;Kontrollupplevelsen&quot; är gröna.

En vinnare blir resultatet när den ledande upplevelsens 95-procentiga konfidensintervall inte överlappar några andra upplevelser. Den vinnande upplevelsen får en grön stjärna till vänster om upplevelsenamnet och i banderollen&quot;Vinnare&quot;. När ingen stjärna är synlig står det &quot;Ingen vinnare än&quot; på banderollen och ingen vinnare har hittats ännu.

Ett&quot;konfidensnummer&quot; rapporteras också bredvid den nuvarande ledande eller vinnande upplevelsen. Denna siffra rapporteras endast tills den ledande upplevelsens förtroende når minst 60 %. Om det finns exakt två upplevelser i Auto-Allocate-experimentet representerar den här siffran konfidensnivån att upplevelsen fungerar bättre än den andra. Om det finns fler än två upplevelser i Auto-Allocate-experimentet representerar den här siffran konfidensnivån att upplevelsen fungerar bättre än den definierade Control-upplevelsen. Om&quot;Kontroll&quot;-upplevelsen vinner rapporteras ingen siffra för&quot;förtroende&quot;.

## Vanliga frågor {#section_C8E068512A93458D8C006760B1C0B6A2}

**Det har gått några dagar framåt. Varför visar alla konfidensvärden fortfarande 0 %?**

Någon av följande orsaker beskriver varför 0 % visas i rapportens [!UICONTROL Confidence] kolumn för alla aktiviteter:

* Manuella A/B-tester och automatisk fördelning använder olika statistik för att visa konfidensvärden.

   Manuella A/B-tester använder p-värden som baseras på [studentens t-test](https://en.wikipedia.org/wiki/Student%27s_t-test). Ett P-värde är sannolikheten att hitta den observerade (eller mer extrema) skillnaden mellan en upplevelse och kontrollen, eftersom det i verkligheten inte finns någon sådan skillnad. Dessa P-värden kan bara användas för att avgöra om observerade data är konsekventa med en viss upplevelse och om kontrollen är densamma. Dessa värden kan inte användas för att avgöra om en upplevelse skiljer sig från en annan upplevelse (inte kontroll).

   Autoallokering visar sannolikheten för att en viss upplevelse ska bli en riktig vinnare för alla upplevelser i aktiviteten. Detta innebär att endast en vinnande upplevelse (som troligtvis kommer att vara vinnaren) kommer att ha ett värde som inte är noll. Alla andra är mest benägna att vara förlorare och kommer att visa 0 %.

* Automatisk allokering börjar visa självförtroende först efter att den vinnande upplevelsen fått 60 % självförtroende. Dessa konfidensnivåer uppträder vanligtvis på ungefär hälften så lång tid som ett normalt A/B-test skulle ta att slutföra (även om detta inte garanteras). Om du vill avgöra hur länge ett normalt A/B-test skulle köras använder du en [exempelstorleksräknare](https://docs.adobe.com/content/target-microsite/testcalculator.html): plug-controls konverteringsgrad i &quot;Baseline conversion rate&quot;, &quot;5%&quot; för &quot;Lift&quot; och 95% för &quot;Confidence&quot;. Normalt börjar förtroendet visa sig efter att varje upplevelse har fyllt 50 % av det antal samplingar som krävs per upplevelse. Då får du en uppfattning om när självförtroende kommer att börja uppstå.
* Om rapporten visar 0 procent över hela linjen är det sannolikt för tidigt i verksamheten.

