---
keywords: faq;frequently asked questions;analytics for target;a4T;report;reports;view reports;reporting;counting methodology;impressions;visitors;visits;default metric;activity conversions;unspecified
description: Det här avsnittet innehåller svar på frågor som ofta ställs om att visa rapporter när Analytics används som rapportkälla för Target (A4T).
title: Visa rapporter - A4T FAQ
feature: a4t troubleshooting
topic: Standard
uuid: d51991f7-cdda-4a59-b64c-7ef1c3f8380d
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1967'
ht-degree: 1%

---


# Visa rapporter - A4T FAQ{#view-reports-a-t-faq}

Det här avsnittet innehåller svar på frågor som ofta ställs om att visa rapporter när du använder [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T).

## Kan jag visa mina Target-aktivitetsdata i Analysis Workspace? {#workspace}

Ni kan använda [!DNL Analysis Workspace] för att analysera era [!DNL Target] aktiviteter och upplevelser. Med [Analytics for Target-panelen](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) kan ni se lyft och självförtroende för så många som tre framgångsmått. Du kan också fördjupa dig i tabeller och visualiseringar.

Om du vill ha detaljerad information och exempel öppnar du [Analytics &amp; Target: Självstudiekursen](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)Best Practices for Analysis från Adobe Experience League.

## Var kan segment användas i Analysis Workspace? {#segmentation}

Segment används oftast på den övre delen av en panel i segmentets släppzon. Segmentet tillämpas på alla tabeller och visualiseringar i panelen. Den här tekniken är mest användbar för att se hur testet påverkar en delmängd av människor (till exempel, hur utfördes det här testet för människor i Storbritannien)?

## Varför returneras orelaterade upplevelser när jag väljer ett träffsegment för en viss Target-aktivitet? {#activity-segmentation}

Den [!DNL Target] variabel som skickas till [!DNL Analytics] har en 90-dagars standardförfalloperiod. (Obs! denna förfalloperiod kan justeras av kundtjänst om det behövs). När besökare navigerar på webbplatsen genom det här förfallofönstret är de en del av många [!DNL Target] aktiviteter, som alla samlas in i dimensionen.

När ni segmenterar för att en aktivitet ska vara närvarande i en träff får ni alltså alla upplevelser som är en del av den aktiviteten *plus* alla andra upplevelser som är bestående i den träffen.

## Bör jag använda besökare, besök eller aktivitetsuttryck som min normaliserande mätning (dvs. beräkningsmetod)? {#metrics}

Det finns flera alternativ för normalisering av mätvärden i A4T-rapportering. Detta mätresultat, som också kallas beräkningsmetoden, blir nämnare för beräkningen av lyft. Det påverkar också hur data aggregeras innan konfidensberäkningen tillämpas.

* ***Unika besökare*** ökar en gång när en användare först kvalificerar sig för en aktivitet.
* ***Besökssteg*** för varje session när en användare (Unik besökare) påbörjar en aktivitet, även om aktiviteten inte visas vid efterföljande besök.
* ***Ökning av aktivitetsavtryck*** varje gång aktivitetsinnehållet betjänas. (Mätt av [!DNL Target]).

När en besökare visar en sida som innehåller en aktivitet, ställs en variabel in för besökaren som innehåller aktivitetens namn. Se de detaljerade scenarierna nedan för hur varje beräkningsmetod jämförs.

Tänk på följande:

* Alla mätvärden ovan utlöses när en användare kvalificerar sig för en aktivitet och innehållet returneras från [!DNL [!DNL Target]]. Det behöver inte innebära att användaren såg erbjudandet. Om en aktivitetsupplevelse är under förskjutningen och användaren inte rullar nedåt på sidan, har erbjudandet levererats av användaren [!DNL Target] men inte av användaren.
* [!UICONTROL Activity Impressions] (mätt med [!DNL Target]) och [!UICONTROL Instances] (mätt med [!DNL Analytics]) är lika, såvida det inte finns flera mbox-anrop på samma sida i samma aktivitet. Detta gör [!UICONTROL Activity Impressions] att flera räknas, men bara en enda [!UICONTROL Instance].

## Varför är&quot;aktivitetsintryck&quot; och&quot;aktivitetskonverteringar&quot; högre i Analysis Workspace än i Rapporter och analyser? {#sametouch}

[!DNL Reports & Analytics] tillämpar en attribueringsmodell med samma tryckning på &quot;aktivitetsavtryck&quot; och &quot;aktivitetskonverteringar&quot; medan [!DNL Analysis Workspace] visar rådatamätningar, som kan visas som inflaterade på grund av [!DNL Target] dimensionens beständighet.

Om du vill utvärdera exakta [!UICONTROL Activity Impressions] värden och [!UICONTROL Activity Conversions] mätvärden i [!DNL Analysis Workspace]ska du se till att båda mätvärdena har [!UICONTROL Same Touch] attribueringsmodeller. Du kan använda modeller genom att klicka på kolumninställningskugget, aktivera [!UICONTROL Non-default attribution models]och sedan välja [!UICONTROL Same Touch]. Läs mer om attribuering i [Attributes IQ overview](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) i *Analytics Tools Guide*.

## Vad betyder&quot;aktivitetskonverteringar&quot; om marknadsföraren väljer ett analysmått under aktivitetsinställningarna? {#section_F3EBACF85AF846E9B366A549AAB64356}

&quot;Aktivitetskonverteringar&quot; är tomma om ett [!DNL Analytics] mått har valts som konverteringsmått för aktiviteten.

## Varför ser jag&quot;ospecificerad&quot; i Analytics-rapporterna? Vad betyder det? {#unspecified}

I andra rapporter betyder&quot;ospecificerad&quot; att data inte uppfyller en klassificeringsregel, men i A4T ska detta aldrig ske. Om du ser&quot;ospecificerad&quot; har klassificeringstjänsten inte körts ännu. Det tar i allmänhet mellan 24 och 72 timmar innan aktivitetsdata visas i rapporterna. Även om aktiviteterna inte visas i den här rapporten förrän den tidpunkten hämtas alla besöksdata som är kopplade till dessa aktiviteter och visas när klassificeringen är klar.

Efter klassificeringsperioden visas data i dessa rapporter ungefär en timme efter det att de samlats in från webbplatsen. Alla mätvärden, segment och värden i rapporterna kommer från den rapportsserie du valde när du konfigurerade aktiviteten.

## Varför skickas Target-mått till Analytics även efter att aktiviteten har inaktiverats? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

Den [!DNL Target] variabel som skickas till [!DNL Analytics] har en 90-dagars standardförfalloperiod. Den här förfalloperioden kan justeras av kundtjänst om det behövs. Den här inställningen är global för alla aktiviteter, så den bör inte justeras för ett fall.

Du kan se [!DNL Target] variabler som skickas till [!DNL Analytics] efter förfalloperioden eftersom förfallotiden är 90 dagar, men bara om användaren aldrig ser någon annan A4T-aktiverad [!DNL Target] aktivitet. Om en användare kommer tillbaka till webbplatsen dag 45 och ser en annan aktivitet, har A4T-eVar värde återställts till 90 dagar. Det innebär att den första kampanjen från dag 1 nu kan vara beständig i upp till 45 + 90 = 135 dagar. Om användaren kommer tillbaka kan du komma till den punkt där du ser mätvärden som skickas till [!DNL Analytics] i din rapportering från mycket äldre aktiviteter. När användare tar bort cookies och inte återvänder till webbplatsen kommer siffrorna i den aktiviteten att tas bort, men du kommer fortfarande att se dem.

Det innebär att aktiviteter fortsätter att få sidvisningar, besök och så vidare i upp till 90 dagar efter att aktiviteten avslutas för besökare som blev en del av aktiviteten medan den var aktiv. Om du tittar på [!UICONTROL Activity Impressions] måtten ska du dock inte se några intryck när aktiviteten är slut.

Detta är normalt och förväntat beteende. A4T-variabeln fungerar på samma sätt som andra eVar. Värdet associeras med användaren tills det når förfallotidsperioden (90 dagar). Om en aktivitet bara är aktiv i två veckor kommer därför värdet fortfarande att associeras med användaren under minst de kommande 90 dagarna.

Bästa praxis är att endast visa rapporter för den aktiviteten för den tidsperiod som aktiviteten var aktiv. Datumen bör anges korrekt som standard när du visar aktiviteten i [!DNL Analytics], så om du inte manuellt har förlängt datumet bör detta inte vara något problem ur rapporteringssynpunkt.

Låt oss till exempel anta att variabeln A4T upphör att gälla efter 90 dagar och vårt test är aktivt från 1 januari till 15 januari.

Den 1 januari kommer användaren till webbplatsen och ser aktiviteten XYZ en gång och har sedan fem sidvisningar. Under de kommande två veckorna kommer användaren aldrig tillbaka till webbplatsen. Data skulle se ut så här för den här användaren:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

Användaren återgår den 1 februari, visar ytterligare fem sidor och stöter inte på fler Target-aktiviteter och den ursprungliga aktiviteten är inte längre aktiv. Även om aktiviteten inte längre är aktiv följer den fortfarande användaren via eVar persistence. Data ser nu ut så här:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

Användaren kommer tillbaka den 1 mars och ser en ny aktivitet, ABC. Användaren visar också fem sidor. Eftersom aktiviteten XYZ fortfarande följer användaren genom persistence, och den här användaren sedan har ABC inställt, visas två radartiklar i rapporten:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

Användaren kommer sedan tillbaka den 1 april, besöker ytterligare fem sidor och gör ett köp. Det första eVar 90-dagars förfallodatum återställs den 1 april, så vi kommer att se det i rapporter. Och alla Target-aktiviteter som användaren ser får kredit för konverteringen, men det totala antalet konverteringar tas bort:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare | Beställningar |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| Totalt | 2 | 20 | 3 | 1 | 1 |

Eftersom båda upplevelserna sågs före konverteringen får de båda&quot;kredit&quot; för ordern. Men det var bara en order som gjordes i systemet, och det är det som syns. För [!DNL Target] rapporter gäller att eftersom du inte placerar en [!DNL Target] aktivitet mot en annan aktivitet för att se vilken som blir mer framgångsrik, spelar det ingen roll att alla aktiviteter som användaren såg fick kredit. Ni jämför resultaten av två objekt i en enda aktivitet, och det är inte möjligt för en användare att se olika upplevelser i samma aktivitet så att ni inte behöver bekymra er om korskontaminering av orderkrediter.

Mer information finns i [Konverteringsvariabler (eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) i *administratörshandboken* för Analytics.

## Varför beräknas siffror för de unika besökarvärdena olika i Analytics och Analytics for Target (A4T)? {#section_0C3B648AB54041F9A2AA839D51791883}

När du kör ett A/B-test, där Students t-test (konfidensmåttet) används för att välja en testvinnare, är en av antagandena att det finns en fast tidshorisont. Testet är inte statistiskt giltigt om du inte tittar på den fasta provstorleken.

Mätvärdena skiljer sig åt i [!UICONTROL Unique Visitors] och [!DNL Analytics] [!DNL Target] bara när du tittar på en tidsperiod som är kortare än det faktiska testet. Om du inte har uppnått din provstorlek är testet inte lika tillförlitligt. Se [How Not to Run an A/B Test](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) on [Evan Millers webbplats](https://www.evanmiller.org/index.html) för mer information.

Mätvärdet visar [!UICONTROL Unique Visitors] antalet personer som har exponerats för testet och som har besökt platsen under den angivna tidsperioden. Dessa personer är fortfarande en del av testet och bör räknas. Om du bara vill se antalet personer som exponerades under en vecka, kan du skapa ett segment med besökare som hade ett aktivitetsintryck och använda det på rapporten.

Du kan korta ned tiden som variabeln [!DNL Target] kvarstår ned till en session; Men det är vanligtvis problematiskt för tester där konverteringshändelsen inte är så trolig att inträffa under samma session.

## Varför räknas samma besökare ibland i flera olika upplevelser i Analytics? {#section_1397E972D31C4207A142E4D2D6D794A2}

I följande lista förklaras varför samma besökare kunde räknas med i flera olika upplevelser i [!DNL Analytics]:

* Profilen har [!DNL Target] gått ut, men [!DNL Analytics] cookien finns fortfarande kvar. I den här situationen utvärderar [!DNL Target] användaren på nytt, men [!DNL Analytics] anser att besökaren är samma person.
* Om besökaren använder `mbox3rdPartyId`kan besökaren, när den anonyma besökaren slås samman med sin ID-profil från tredje part, [!DNL Target] få en annan upplevelse att matcha med ID:t från tredje part. Mer information finns i Synkronisering av [realtidsprofiler för mbox3rdPartyID](../../../c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] kan spåra olika enheter som samma besökare på ett annat sätt än att [!DNL Target] spåra dessa enheter: Inställningarna av ID:t från tredje part i [!DNL Target] skiljer sig från dem i Analytics.

## Stöder A4T virtuella rapportsviter?

Virtuella rapportsviter ingår *inte* i [!UICONTROL Report Suite] listan och målgrupper från virtuella rapportsviter stöds inte i A4T-rapportering.

## Kan jag ändra procentandelen trafiktilldelning i en aktivitet som använder A4T efter att aktiviteten har aktiverats?

Om du ändrar procentandelen för trafikallokering i en aktivitet efter aktivering kan det leda till inkonsekvent rapportering [!DNL Analytics] eftersom förändringen bara påverkar nya besökare. Återkommande besökare påverkas inte.

Det bästa är att du stoppar den befintliga aktiviteten och sedan skapar en ny aktivitet i stället för att ändra procentandelen efter aktiveringen. Rapportering för den nya aktiviteten börjar med nya besökare och data från återkommande besökare orsakar inte inkonsekvent rapportering.
