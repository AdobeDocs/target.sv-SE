---
keywords: frågor och svar;vanliga frågor;analyser för mål;a4T;rapport;rapporter;visa rapporter;rapportera;inventeringsmetod;visningar;besökare;besök;standardmått;aktivitetskonverteringar;ospecificerad
description: Det här avsnittet innehåller svar på frågor som ofta ställs om att visa rapporter när Analytics används som rapportkälla för Target (A4T).
title: Visa rapporter - A4T FAQ
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '2332'
ht-degree: 1%

---


# Visa rapporter - A4T FAQ

Det här avsnittet innehåller svar på frågor som ofta ställs om att visa rapporter när du använder [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T).

## Kan jag visa mina Target-aktivitetsdata i Analysis Workspace? {#workspace}

Du kan använda [!DNL Analysis Workspace] för att analysera dina [!DNL Target] aktiviteter och upplevelser. Med [Analytics for Target panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) kan du se hur mycket du kan lita på och förbättra resultatet för så många som tre framgångsmått. Du kan också fördjupa dig i tabeller och visualiseringar.

Mer information och exempel finns i [Analytics &amp; Target: Självstudiekursen&quot;Best Practices for Analysis&quot;](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)&quot; från Adobe Experience League.

## Var kan segment användas i Analysis Workspace? {#segmentation}

Segment används oftast på den övre delen av en panel i segmentets släppzon. Segmentet tillämpas på alla tabeller och visualiseringar i panelen. Den här tekniken är mest användbar för att se hur testet påverkar en delmängd av människor (till exempel, hur utfördes det här testet för människor i Storbritannien)?

## Varför returneras orelaterade upplevelser när jag väljer ett träffsegment för en viss Target-aktivitet? {#activity-segmentation}

Variabeln [!DNL Target] som skickas till [!DNL Analytics] har en standardförfalloperiod på 90 dagar. (Obs! denna förfalloperiod kan justeras av kundtjänst om det behövs). När besökare navigerar på webbplatsen genom det här förfallofönstret är de en del av många [!DNL Target]-aktiviteter, som alla samlas in i dimensionen.

När du segmenterar för att en aktivitet ska vara närvarande i en träff får du därför alla upplevelser som är en del av aktiviteten *plus* alla andra upplevelser som är bestående i den träffen.

## Varför har jag inte åtkomst till Avancerade inställningar när jag konfigurerar mina måltider?

För aktiviteter som använder [!DNL Analytics] som rapportkälla (A4T) använder målmåttet alltid inställningarna [!UICONTROL Increment Count & Keep User in Activity] och [!UICONTROL On Every Impression]. Detta är *inte* konfigurerbart.

Mer information finns i&quot;När jag konfigurerar min målkod, varför kan jag inte komma åt alternativen för Avancerade inställningar?&quot; i [Måttdefinitioner - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## Bör jag använda besökare, besök eller aktivitetsuttryck som min normaliserande mätning (dvs. beräkningsmetod)? {#metrics}

Det finns flera alternativ för normalisering av mätvärden i A4T-rapportering. Detta mätresultat, som också kallas beräkningsmetoden, blir nämnare för beräkningen av lyft. Det påverkar också hur data aggregeras innan konfidensberäkningen tillämpas.

* ***Unik*** besöksregistrering en gång när en användare först kvalificerar sig för en aktivitet.
* ***När en användare (Unik besökare) har loggat in i en aktivitet*** visas besökaren för varje session, även om aktiviteten inte visas vid efterföljande besök.
* ***Aktivitetsintryck*** varje gång aktivitetsinnehållet betjänas. (mätt med [!DNL Target]).

När en besökare visar en sida som innehåller en aktivitet, ställs en variabel in för besökaren som innehåller aktivitetens namn. Se de detaljerade scenarierna nedan för hur varje beräkningsmetod jämförs.

Tänk på följande:

* Alla mätvärden ovan utlöses när en användare kvalificerar sig för en aktivitet och innehållet returneras från [!DNL [!DNL Target]]. Det behöver inte innebära att användaren såg erbjudandet. Om en aktivitetsupplevelse är under förskjutningen och användaren inte rullar nedåt på sidan, så har erbjudandet levererats av [!DNL Target] men inte av användaren.
* [!UICONTROL Activity Impressions] (mätt med  [!DNL Target]) och  [!UICONTROL Instances] (mätt med  [!DNL Analytics]) är lika, såvida det inte finns flera anrop till samma sida i samma aktivitet. Detta gör att flera [!UICONTROL Activity Impressions] räknas, men bara en [!UICONTROL Instance].

## Varför är&quot;aktivitetsintryck&quot; och&quot;aktivitetskonverteringar&quot; högre i Analysis Workspace än i Rapporter och analyser? {#sametouch}

[!DNL Reports & Analytics] tillämpar en attribueringsmodell med samma tryckning på &quot;aktivitetsavtryck&quot; och &quot;aktivitetskonverteringar&quot; medan  [!DNL Analysis Workspace] visar rådatamätningar, som kan se inflaterade ut på grund av  [!DNL Target] dimensionens beständighet.

Om du vill utvärdera exakta [!UICONTROL Activity Impressions]- och [!UICONTROL Activity Conversions]-mått i [!DNL Analysis Workspace] kontrollerar du att båda måtten har [!UICONTROL Same Touch]-attribueringsmodeller. Du kan använda modeller genom att klicka på kolumninställningskugget, aktivera [!UICONTROL Non-default attribution models] och sedan välja [!UICONTROL Same Touch]. Läs mer om attribuering i [Attributes IQ overview](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) i *Analytics Tools Guide*.

## Vad betyder&quot;aktivitetskonverteringar&quot; om marknadsföraren väljer ett analysmått under aktivitetsinställningarna? {#section_F3EBACF85AF846E9B366A549AAB64356}

&quot;Aktivitetskonverteringar&quot; är tomma om ett [!DNL Analytics]-mått har valts som konverteringsmått för aktiviteten.

## Varför ser jag&quot;ospecificerad&quot; i Analytics-rapporterna? Vad betyder det? {#unspecified}

I andra rapporter betyder&quot;ospecificerad&quot; att data inte uppfyller en klassificeringsregel, men i A4T ska detta aldrig ske. Om du ser&quot;ospecificerad&quot; har klassificeringstjänsten inte körts ännu. Det tar i allmänhet mellan 24 och 72 timmar innan aktivitetsdata visas i rapporterna. Även om aktiviteterna inte visas i den här rapporten förrän den tidpunkten hämtas alla besöksdata som är kopplade till dessa aktiviteter och visas när klassificeringen är klar.

Efter klassificeringsperioden visas data i dessa rapporter ungefär en timme efter det att de samlats in från webbplatsen. Alla mätvärden, segment och värden i rapporterna kommer från den rapportsserie du valde när du konfigurerade aktiviteten.

Om klassificeringen gjordes för den aktiviteten, och du fortfarande ser en ospecificerad rad i rapporten, kontrollerar du att rapporten inte använder ett icke-[!DNL Target]-mått för att visa data. Om inte rapporten använder ett [!DNL Target]-specifikt mått kommer raden &quot;Ospecificerad&quot; att innehålla händelser för anrop som inte är associerade med [!DNL Target]. Den raden kommer inte att innehålla någon [!DNL Target]-associerad information (t.ex. besökare/besök/visningar).

## Varför skickas Target-mått till Analytics även efter att aktiviteten har inaktiverats? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

Variabeln [!DNL Target] som skickas till [!DNL Analytics] har en standardförfalloperiod på 90 dagar. Den här förfalloperioden kan justeras av kundtjänst om det behövs. Den här inställningen är global för alla aktiviteter, så den bör inte justeras för ett fall.

Du kan se [!DNL Target]-variabler som skickas till [!DNL Analytics] efter förfalloperioden eftersom förfallotiden är 90 dagar, men bara om användaren aldrig ser någon annan A4T-aktiverad [!DNL Target]-aktivitet. Om en användare kommer tillbaka till webbplatsen dag 45 och ser en annan aktivitet, har A4T-eVar värde återställts till 90 dagar. Det innebär att den första kampanjen från dag 1 nu kan vara beständig i upp till 45 + 90 = 135 dagar. Om användaren kommer tillbaka kan du komma till den punkt där du ser mätvärden som skickats till [!DNL Analytics] i din rapportering från mycket äldre aktiviteter. När användare tar bort cookies och inte återvänder till webbplatsen kommer siffrorna i den aktiviteten att tas bort, men du kommer fortfarande att se dem.

Det innebär att aktiviteter fortsätter att få sidvisningar, besök och så vidare i upp till 90 dagar efter att aktiviteten avslutas för besökare som blev en del av aktiviteten medan den var aktiv. Om du däremot tittar på [!UICONTROL Activity Impressions]-måttet ska du inte se några intryck efter att aktiviteten har avslutats.

Detta är normalt och förväntat beteende. A4T-variabeln fungerar på samma sätt som andra eVar. Värdet associeras med användaren tills det når förfallotidsperioden (90 dagar). Om en aktivitet bara är aktiv i två veckor kommer därför värdet fortfarande att associeras med användaren under minst de kommande 90 dagarna.

Bästa praxis är att endast visa rapporter för den aktiviteten för den tidsperiod som aktiviteten var aktiv. Datumen bör anges korrekt som standard när du visar aktiviteten i [!DNL Analytics], så om du inte manuellt har förlängt datumet bör detta inte vara något problem ur rapportsynpunkt.

Låt oss till exempel anta att variabeln A4T upphör att gälla efter 90 dagar och vårt test är aktivt från 1 januari till 15 januari.

Den 1 januari kommer användaren till webbplatsen och ser aktiviteten XYZ en gång och har sedan fem sidvisningar. Under de kommande två veckorna kommer användaren aldrig tillbaka till webbplatsen. Data skulle se ut så här för den här användaren:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare |
|--- |--- |--- |--- |--- |
| XYZ | 3 | 5 | 3 | 3 |

Användaren återgår den 1 februari, visar ytterligare fem sidor och stöter inte på fler Target-aktiviteter och den ursprungliga aktiviteten är inte längre aktiv. Även om aktiviteten inte längre är aktiv följer den fortfarande användaren via eVar persistence. Data ser nu ut så här:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare |
|--- |--- |--- |--- |--- |
| XYZ | 3 | 10 | 2 | 1 |

Användaren kommer tillbaka den 1 mars och ser en ny aktivitet, ABC. Användaren visar också fem sidor. Eftersom aktiviteten XYZ fortfarande följer användaren genom persistence, och den här användaren sedan har ABC inställt, visas två radartiklar i rapporten:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare |
|--- |--- |--- |--- |--- |
| XYZ | 3 | 15 | 3 | 3 |
| ABC | 3 | 5 | 3 | 1 |

Användaren kommer sedan tillbaka den 1 april, besöker ytterligare fem sidor och gör ett köp. Det första eVar 90-dagars förfallodatum återställs den 1 april, så vi kommer att se det i rapporter. Och alla Target-aktiviteter som användaren ser får kredit för konverteringen, men det totala antalet konverteringar tas bort:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare | Beställningar |
|--- |--- |--- |--- |--- |--- |
| XYZ | 3 | 20 | 4 | 1 | 3 |
| ABC | 3 | 10 | 2 | 3 | 3 |
| Totalt | 2 | 20 | 3 | 3 | 3 |

Eftersom båda upplevelserna sågs före konverteringen får de båda&quot;kredit&quot; för ordern. Men det var bara en order som gjordes i systemet, och det är det som syns. För [!DNL Target]-rapportering, eftersom du inte placerar en [!DNL Target]-aktivitet mot en annan aktivitet för att se vilken som är mest framgångsrik, spelar det ingen roll att alla aktiviteter som användaren såg fick kredit. Ni jämför resultaten av två objekt i en enda aktivitet, och det är inte möjligt för en användare att se olika upplevelser i samma aktivitet så att ni inte behöver bekymra er om korskontaminering av orderkrediter.

Mer information finns i [Konverteringsvariabler (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) i *administratörshandboken för analyser*.

## Varför beräknas siffror för de unika besökarvärdena olika i Analytics och Analytics for Target (A4T)? {#section_0C3B648AB54041F9A2AA839D51791883}

När du kör ett A/B-test, där Students t-test (konfidensmåttet) används för att välja en testvinnare, är en av antagandena att det finns en fast tidshorisont. Testet är inte statistiskt giltigt om du inte tittar på den fasta provstorleken.

Måttet [!UICONTROL Unique Visitors] skiljer sig bara åt i [!DNL Analytics] och [!DNL Target] när du tittar på en tidsrymd som är kortare än det faktiska testet. Om du inte har uppnått din provstorlek är testet inte lika tillförlitligt. Mer information finns i [Så här kör du ett A/B-test](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) på [Evan Millers webbplats](https://www.evanmiller.org/index.html).

Måttet [!UICONTROL Unique Visitors] visar antalet personer som har exponerats för testet och som har besökt platsen under den angivna tidsperioden. Dessa personer är fortfarande en del av testet och bör räknas. Om du bara vill se antalet personer som exponerades under en vecka, kan du skapa ett segment med besökare som hade ett aktivitetsintryck och använda det på rapporten.

Du kan korta ned den tid som variabeln [!DNL Target] kvarstår ned till en session; Men det är vanligtvis problematiskt för tester där konverteringshändelsen inte inträffar lika lätt under samma session.

## Varför räknas samma besökare ibland i flera olika upplevelser i Analytics? {#section_1397E972D31C4207A142E4D2D6D794A2}

I följande lista förklaras varför samma besökare kunde räknas med i flera upplevelser i [!DNL Analytics]:

* Profilen [!DNL Target] har upphört att gälla men cookien [!DNL Analytics] finns fortfarande kvar. I den här situationen utvärderar [!DNL Target] användaren på nytt, men [!DNL Analytics] anser att besökaren är samma person.
* Om besökaren använder `mbox3rdPartyId` kan [!DNL Target], när den anonyma besökaren slås samman med sin ID-profil från tredje part, ge besökaren en annan upplevelse för att matcha med ID:t från tredje part. Mer information finns i [Profilsynkronisering i realtid för mbox3rdPartyID](/help/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] kan spåra olika enheter som samma besökare på ett annat sätt än att  [!DNL Target] spåra dessa enheter: Inställningarna av ID:t från tredje part i  [!DNL Target] skiljer sig från dem i Analytics.

## Stöder A4T virtuella rapportsviter?

Virtuella rapportsviter är *inte* inkluderade i [!UICONTROL Report Suite]-listan och målgrupper från virtuella rapportsviter stöds inte i A4T-rapportering.

## Kan jag ändra procentandelen trafiktilldelning i en aktivitet som använder A4T efter att aktiviteten har aktiverats?

Om du ändrar procentandelen för trafikallokering i en aktivitet efter aktivering kan det leda till inkonsekvent rapportering i [!DNL Analytics] eftersom förändringen bara påverkar nya besökare. Återkommande besökare påverkas inte.

Det bästa är att du stoppar den befintliga aktiviteten och sedan skapar en ny aktivitet i stället för att ändra procentandelen efter aktiveringen. Rapportering för den nya aktiviteten börjar med nya besökare och data från återkommande besökare orsakar inte inkonsekvent rapportering.

## Hur räknas besök i Analytics och konverteringskrediter som allokeras i en Auto-Target-aktivitet som använder A4T?

När en besökare kvalificerar sig för, visar innehåll eller konverterar i en A4T-aktivitet skickar [!DNL Target] händelsedata till [!DNL Analytics], vilket gör att [!DNL Analytics] kan attribuera konverteringshändelser och andra klickströmshändelser som inträffar på sidan till relevanta [!DNL Target]-aktiviteter och -upplevelser.

Här följer några saker du bör tänka på när du tittar på [!DNL Analytics]-rapporter:

* Som en god praxis bör ditt rapporteringsfönster börja från aktivitetens startdatum.
* Om en konvertering sker utanför rapportens fönster visas inte konverteringen i [!DNL Analytics].
* När besökarna befinner sig i den&quot;riktade&quot; delen av trafiken för [!UICONTROL Auto-Target]-aktiviteter kan de se olika upplevelser från en session till nästa. Om deras profil eller kontext till exempel har ändrats och [!DNL Target] maskininlärningsalgoritmer avgör att de är mer benägna att konvertera på en ny upplevelse. När besökarna rör sig från upplevelse till upplevelse ökar besöksantalet för varje upplevelse som ses. Detta skiljer sig från vanliga A/B-testningsaktiviteter där upplevelserna är kladdiga för besökarna vid olika besök.
* Om en besökare ser flera upplevelser på flera besök, tillskrivs all konvertering alltid den senaste upplevelsen som besökaren såg. Som vi nämnt ökas besöksantalet för varje upplevelse som besökaren såg. Detta kan på ett konstlat sätt påverka konverteringsgraden per upplevelse när du visar upplevelser enligt dimensionen [!UICONTROL Targeted] i [!DNL Adobe Analytics]-rapporter.
