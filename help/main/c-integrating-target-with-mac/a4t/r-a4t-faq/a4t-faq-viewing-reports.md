---
keywords: frågor och svar;vanliga frågor;analyser för mål;a4T;rapport;rapporter;visa rapporter;rapportera;inventeringsmetod;visningar;besökare;besök;standardmått;aktivitetskonverteringar;ospecificerad
description: Hitta svar på frågor som ofta ställs om att visa rapporter när Analytics for [!DNL Target] (A4T) används. Med A4T kan du använda Analytics-rapportering för  [!DNL Target] aktiviteter.
title: Hitta svar på frågor om att visa rapporter med A4T?
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: c747a8a0ed480130f254818e21b98addca16ca41
workflow-type: tm+mt
source-wordcount: '2539'
ht-degree: 1%

---

# Visa rapporter - A4T FAQ

Det här avsnittet innehåller svar på frågor som ofta ställs om att visa rapporter när [!DNL Adobe Analytics] används som rapportkälla för [!DNL Adobe Target] (A4T).

## Kan jag visa mina [!DNL Target] aktivitetsdata i [!DNL Analysis Workspace]? {#workspace}

+++Svar
Du kan använda [!DNL Analysis Workspace] för att analysera dina [!DNL Target]-aktiviteter och -upplevelser. Med [Analytics for Target panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=sv-SE) kan du se hur mycket du kan uppnå och lita på att det finns så många som tre framgångsmått. Du kan också fördjupa dig i tabeller och visualiseringar.

Om du vill ha mer information och exempel öppnar du [Självstudiekursen &#x200B;](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) Analytics &amp; Target: Best Practices for Analysis, som finns i [!UICONTROL Adobe Experience League].

+++

## Var kan segment användas i [!DNL Analysis Workspace]? {#segmentation}

+++Svar
Segment används oftast högst upp på en panel i segmentets släppzon. Segmentet tillämpas på alla tabeller och visualiseringar i panelen. Den här tekniken är mest användbar för att se hur testet påverkar en delmängd av människor (till exempel, hur utfördes det här testet för människor i Storbritannien)?

Ett segment kan också läggas i lager direkt i friformstabellen, men observera att du måste täcka över hela tabellen för att kunna bevara lyftnings- och tillförlitlighetsberäkningarna i A4T-panelen. Kolumnnivåsegment stöds för närvarande inte på panelen.

+++

## Vilken Attribution IQ-modell används i [!DNL Analysis Workspace]?

+++Svar
När du använder [!DNL Target] aktivitetsavtryck och konverteringar i [!DNL Analysis Workspace] är Attribution IQ-modellen Same Touch standardmodellen som används för mätvärdena för att säkerställa korrekt räkning. Den här modellen fungerar bra i 99 % av fallen. Du kan dock åsidosätta standardtilldelningen i Attribution IQ.

+++

## Varför returneras orelaterade upplevelser när jag använder ett träffsegment för en viss [!DNL Target]-aktivitet? {#activity-segmentation}

+++Svar
Variabeln [!DNL Target] som skickas till [!DNL Analytics] har en 90-dagars standardförfalloperiod. (Obs! Den här förfalloperioden kan justeras av kundtjänst om det behövs.) När besökare navigerar på webbplatsen genom det här förfallofönstret är de en del av många [!DNL Target] aktiviteter, som alla samlas in i dimensionen.

När du segmenterar för att en aktivitet ska finnas i en träff får du alla upplevelser som ingår i den aktiviteten *plus* alla andra upplevelser som kvarstår i den träffen.

+++

## Varför kan jag inte komma åt [!UICONTROL Goal Metrics] när jag konfigurerar [!UICONTROL Advanced Settings]?

+++Svar
För aktiviteter som använder [!DNL Analytics] som rapportkälla (A4T) använder målmåttet inställningarna [!UICONTROL Increment Count & Keep User in Activity] och [!UICONTROL On Every Impression]. Dessa inställningar är *inte* konfigurerbara.

Mer information finns i&quot;När jag konfigurerar mina målmått, varför kan jag inte komma åt alternativen för Avancerade inställningar?&quot; i [Måttdefinitioner - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## Bör jag använda besökare, besök eller aktivitetsuttryck som min normaliserande mätning (dvs. beräkningsmetod)? {#metrics}

+++Svar
Det finns flera alternativ för normalisering av mätvärden i A4T-rapportering. Detta mätresultat, som också kallas beräkningsmetoden, blir nämnare för beräkningen av lyft. Det påverkar också hur data aggregeras innan konfidensberäkningen tillämpas.

* ***Unika besökare*** ökar en gång när en användare först kvalificerar sig för en aktivitet.
* Ökningen ***Besök*** för varje session när en användare (Unik besökare) anger en aktivitet, även om aktiviteten inte visas vid efterföljande besök.
* Ökning för ***aktivitetsavtryck*** varje gång aktivitetsinnehållet hanteras. (Mäts av [!DNL Target]).

När en besökare visar en sida som innehåller en aktivitet, ställs en variabel in för besökaren som innehåller aktivitetens namn. Se de detaljerade scenarierna nedan för hur varje beräkningsmetod jämförs.

Tänk på följande:

* Ovanstående mått utlöses när en användare kvalificerar sig för en aktivitet och innehållet returneras från [!DNL Target]. Det behöver inte innebära att användaren såg erbjudandet. Om en aktivitetsupplevelse är under förskjutningen och användaren inte rullar nedåt på sidan, så betjänades erbjudandet av [!DNL Target] men inte av användaren.
* [!UICONTROL Activity Impressions] (mätt med [!DNL Target]) och [!UICONTROL Instances] (mätt med [!DNL Analytics]) är lika, om det inte finns flera mbox-anrop på samma sida i samma aktivitet. Detta gör att flera [!UICONTROL Activity Impressions] räknas, men bara en [!UICONTROL Instance].

Mer information finns i [Konfigurera A4T-rapporter i Analysis Workspace för Automatiskt mål-aktiviteter](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=sv-SE) i *Adobe Target-självstudiekurser*.

+++

## Varför är &quot;aktivitetsavtryck&quot; och &quot;aktivitetskonverteringar&quot; högre i [!DNL Analysis Workspace] än [!UICONTROL Reports & Analytics]? {#sametouch}

+++Svar
[!DNL Reports & Analytics] tillämpar en attribueringsmodell med samma tryckning på aktivitetsavtryck och aktivitetskonverteringar, medan [!DNL Analysis Workspace] visar rådatamätningar, som kan visas som inflaterade på grund av att dimensionen [!DNL Target] är beständig.

Om du vill utvärdera exakta [!UICONTROL Activity Impressions]- och [!UICONTROL Activity Conversions]-mått i [!DNL Analysis Workspace] kontrollerar du att båda mätvärdena har [!UICONTROL Same Touch] attribueringsmodeller. Du kan använda modeller genom att klicka på kugghjulet för kolumninställningar, aktivera [!UICONTROL Non-default attribution models] och sedan välja [!UICONTROL Same Touch]. Läs mer om attribuering i [Översikt över attribut-IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html?lang=sv-SE) i *Analysverktygshandboken*.

+++

## Vad betyder&quot;aktivitetskonverteringar&quot; om marknadsföraren väljer ett [!DNL Analytics]-mått under aktivitetsinställningarna? {#section_F3EBACF85AF846E9B366A549AAB64356}

+++Svar
&quot;Aktivitetskonverteringar&quot; är tomma om ett [!DNL Analytics]-mått har valts som konverteringsmått för aktiviteten.

+++

## Varför visas&quot;ospecificerad&quot; i [!DNL Analytics]-rapporterna? Vad betyder det? {#unspecified}

+++Svar
I andra rapporter betyder&quot;ospecificerad&quot; att data inte uppfyller en klassificeringsregel, men i A4T ska detta aldrig ske. Om du ser&quot;ospecificerad&quot; har klassificeringstjänsten inte körts ännu. Det tar i allmänhet mellan 24 och 72 timmar innan aktivitetsdata visas i rapporterna. Även om aktiviteterna inte visas i den här rapporten förrän vid den tidpunkten hämtas alla besöksdata som är kopplade till dessa aktiviteter och visas när klassificeringen är klar.

Efter klassificeringsperioden visas data i dessa rapporter ungefär en timme efter det att de samlats in från webbplatsen. Alla mätvärden, segment och värden i rapporterna kommer från den rapportsserie du valde när du konfigurerade aktiviteten.

Om klassificeringen gjordes för den aktiviteten, och du fortfarande ser en ospecificerad rad i rapporten, kontrollerar du att rapporten inte använder ett icke-[!DNL Target]-mått för att visa data. Om rapporten inte använder ett [!DNL Target]-specifikt mått innehåller raden Ospecificerad händelser för anrop som inte är associerade med [!DNL Target]. Den raden kommer inte att innehålla någon [!DNL Target]-associerad information (till exempel besökare/besök/visningar).

+++

## Varför skickas [!DNL Target] mätvärden till [!DNL Analytics] även efter att aktiviteten har inaktiverats? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

+++Svar
Variabeln [!DNL Target] som skickas till [!DNL Analytics] har en 90-dagars standardförfalloperiod. Den här förfalloperioden kan justeras av kundtjänst om det behövs. Den här inställningen är global för alla aktiviteter, så den bör inte justeras för ett fall.

[!DNL Target] variabler kan skickas till [!DNL Analytics] efter förfalloperioden eftersom förfallotiden är 90 dagar, men bara om användaren aldrig ser någon annan A4T-aktiverad [!DNL Target]-aktivitet. Om en användare kommer tillbaka till webbplatsen dag 45 och ser en annan aktivitet, har hela A4T eVar-värdet återställts till 90 dagar. Det innebär att den första kampanjen från dag 1 nu kan vara beständig i upp till 45 + 90 = 135 dagar. Om användaren kommer tillbaka kan du komma till den punkt där du ser mätvärden som skickats till [!DNL Analytics] i din rapportering från mycket äldre aktiviteter. När användare tar bort cookies och inte återvänder till webbplatsen, försvinner siffrorna i aktiviteten, men du kan fortfarande se dem.

Det innebär att aktiviteter fortsätter att få sidvisningar, besök och så vidare i upp till 90 dagar efter att aktiviteten avslutas för besökare som blev en del av aktiviteten medan den var aktiv. Om du däremot tittar på måttet [!UICONTROL Activity Impressions] bör du inte se några visningar efter att aktiviteten har avslutats.

Detta är normalt och förväntat beteende. A4T-variabeln fungerar på samma sätt som andra eVar-variabler. Värdet associeras med användaren tills det når förfallotidsperioden (90 dagar). Om en aktivitet bara är aktiv i två veckor är därför värdet fortfarande associerat med användaren under minst de kommande 90 dagarna.

Bästa praxis är att endast visa rapporter för den aktiviteten för den tidsperiod som aktiviteten var aktiv. Datumen bör anges korrekt som standard när du visar aktiviteten i [!DNL Analytics], så om du inte manuellt har förlängt datumet bör det inte vara något problem ur rapportsynpunkt.

Låt oss anta att variabeln A4T upphör att gälla efter 90 dagar och att testet är aktivt från 1 januari till 15 januari.

Den 1 januari kommer användaren till webbplatsen och ser aktiviteten XYZ en gång och har sedan fem sidvisningar. Under de kommande två veckorna kommer användaren aldrig tillbaka till webbplatsen. Data skulle se ut så här för den här användaren:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

Användaren återgår den 1 februari, visar ytterligare fem sidor och stöter inte på fler målaktiviteter och den ursprungliga aktiviteten är inte längre aktiv. Även om aktiviteten inte längre är aktiv följer den fortfarande användaren via eVar persistence. Data ser nu ut så här:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

Användaren kommer tillbaka den 1 mars och ser en ny aktivitet, ABC. Användaren visar också fem sidor. Eftersom aktiviteten XYZ fortfarande följer användaren genom persistence, och den här användaren sedan har ABC inställt, visas två radartiklar i rapporten:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

Användaren kommer sedan tillbaka den 1 april, besöker ytterligare fem sidor och gör ett köp. 90-dagars förfallotid för det första eVar-värdet återställs den 1 april, så du ser det i rapporter. Och alla Target-aktiviteter som användaren ser får kredit för konverteringen, men det totala antalet konverteringar tas bort:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare | Beställningar |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| Totalt | 2 | 20 | 3 | 1 | 1 |

Eftersom båda upplevelserna sågs före konverteringen får de båda&quot;kredit&quot; för ordern. Men det var bara en order som gjordes i systemet, och det är det som syns. För [!DNL Target]-rapportering, eftersom du inte placerar en [!DNL Target]-aktivitet mot en annan aktivitet för att se vilken som är mest framgångsrik, spelar det ingen roll att alla aktiviteter som användaren såg fick kredit. Du jämför resultaten av två objekt i den enskilda aktiviteten. Det är inte möjligt för en användare att se olika upplevelser i samma aktivitet, så du behöver inte bekymra dig om korskontaminering av orderkrediter.

Mer information finns i [Konverteringsvariabler (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html?lang=sv-SE)) i *Administratörshandboken för analyser*.

+++

## Varför ser jag fler intryck när min aktivitet har inaktiverats? {#deactivated}

+++Svar
En källa till visningar för en A4T-aktivitets rapport efter avaktivering kan vara trafik i QA-läge. Målet loggar normalt inte händelser för en inaktiverad aktivitet, men det finns inget sätt att veta att det kommer att synas i QA-läge i Analytics. När Target-aktivitetsrapporten hämtas från Analytics visas dessa intryck. Detta fungerar som avsett eftersom kunderna behöver ett sätt att kontrollera A4T-rapporter även om aktiviteten inte är aktiv i QA-läge.

+++

## Varför beräknar [!DNL Analytics] och [!UICONTROL Analytics for Adobe Target] (A4T) siffror för måttet [!UICONTROL Unique Visitors] olika? {#section_0C3B648AB54041F9A2AA839D51791883}

+++Svar
När du kör ett A/B-test, som använder [Welchs t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} (konfidensmåttet) för att välja en testvinnare, är en av antagandena att det finns en fast tidshorisont. Testet är inte statistiskt giltigt om du inte tittar på den fasta provstorleken.

Måttet [!UICONTROL Unique Visitors] är inte samma i [!DNL Analytics] och [!DNL Target] bara när du tittar på en period som är kortare än det faktiska testet. Om du inte har uppnått din provstorlek är testet inte lika tillförlitligt. Mer information finns i [Så här kör du ett A/B-test](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) på [Evan Millers webbplats](https://www.evanmiller.org/index.html).

Måttet [!UICONTROL Unique Visitors] visar antalet personer som har exponerats för testet och som har besökt platsen under den angivna tidsperioden. Dessa personer är en del av testet och bör räknas. Om du bara vill se antalet personer som exponerades under en vecka, kan du skapa ett segment med besökare som hade ett aktivitetsintryck och använda det på rapporten.

Du kan förkorta den tid som variabeln [!DNL Target] kvarstår ned till en session, men det är problematiskt för tester där konverteringshändelsen inte är så trolig att den inträffar inom samma session.

+++

## Varför räknas samma besökare ibland i flera upplevelser i [!DNL Analytics]? {#section_1397E972D31C4207A142E4D2D6D794A2}

+++Svar
I följande lista förklaras varför samma besökare kunde räknas i flera upplevelser i [!DNL Analytics]:

* Profilen [!DNL Target] har upphört att gälla men cookien [!DNL Analytics] finns fortfarande kvar. I den här situationen utvärderar [!DNL Target] om användaren, men [!DNL Analytics] anser att besökaren är samma person.
* Om besökaren använder `mbox3rdPartyId` kan [!DNL Target] ge besökaren en annan upplevelse för att matcha med ID:t från tredje part när den anonyma besökaren slås samman med profilen för ID:t från tredje part. Mer information finns i [Synkronisering av realtidsprofiler för mbox3rdPartyID](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] kanske spårar olika enheter som samma besökare på ett annat sätt än [!DNL Target] spårar dessa enheter: konfigurationen av tredje parts-ID i [!DNL Target] skiljer sig från den i Analytics.

+++

## Stöder A4T virtuella rapportsviter? {#virtual}

+++Svar
Även om virtuella rapportsviter inte ingår i listan [!UICONTROL Report Suite] har alla A4T-data som delas med en rapportsvit som är länkad till en virtuell rapportsvit i [!DNL Analytics] åtkomst till dessa data. Observera att alla målgrupper som skapats från en virtuell rapportserie inte kan delas tillbaka till [!DNL Target].

+++

## Kan jag ändra procentandelen trafiktilldelning i en aktivitet som använder A4T efter att aktiviteten har aktiverats?

+++Svar
Om du ändrar procentandelen för trafikallokering i en aktivitet efter aktivering kan det orsaka inkonsekvent rapportering i [!DNL Analytics] eftersom ändringen bara påverkar nya besökare. Återkommande besökare påverkas inte.

Det bästa är att du stoppar den befintliga aktiviteten och sedan skapar en ny aktivitet i stället för att ändra procentandelen efter aktiveringen. Rapporteringen för den nya aktiviteten börjar med nya besökare och data från återkommande besökare orsakar inte inkonsekvent rapportering.

+++

## Hur räknas besök i [!DNL Analytics] och konverteringskrediter som allokeras i en [!UICONTROL Auto-Target]-aktivitet som använder A4T?

+++Svar
När en besökare kvalificerar sig för, visar innehåll eller konverterar i en A4T-aktivitet skickar [!DNL Target] händelsedata till [!DNL Analytics]. Med dessa händelsedata kan [!DNL Analytics] attribuera konverteringshändelser och andra klickströmshändelser som inträffar på sidan till relevanta [!DNL Target]-aktiviteter och -upplevelser.

Här följer några saker du bör tänka på när du visar [!DNL Analytics] rapporter:

* Som en god praxis bör ditt rapporteringsfönster börja från aktivitetens startdatum.
* Om en konvertering sker utanför rapportens fönster visas inte konverteringen i [!DNL Analytics].
* När besökarna befinner sig i den&quot;riktade&quot; delen av trafiken för [!UICONTROL Auto-Target]-aktiviteter kan de se olika upplevelser från en session till nästa. Om deras profil eller kontext till exempel har ändrats och [!DNL Target]s maskininlärningsalgoritmer avgör att det är mer sannolikt att de konverteras på en ny upplevelse. När besökarna rör sig från upplevelse till upplevelse ökar besöksantalet för varje upplevelse som ses. Detta skiljer sig från vanliga A/B-testningsaktiviteter där upplevelserna är kladdiga för besökarna vid olika besök.
* Om en besökare ser flera upplevelser på flera besök, tillskrivs all konvertering alltid den senaste upplevelsen som besökaren såg. Som vi nämnt ökas besöksantalet för varje upplevelse som besökaren såg. Detta kan på ett konstlat sätt påverka konverteringsgraden per upplevelse när du visar upplevelser under dimensionen [!UICONTROL Targeted] i [!DNL Adobe Analytics]-rapporter.

+++

## Hur spårar jag aktivitetsavtryck i [!DNL Analysis Workspace] när jag använder [!UICONTROL Analytics for Target] (A4T)? {#activity-impressions}

+++Svar

Så här visar du aktivitetsavtryck i [!DNL Analysis Workspace]:

1. Klicka på [!DNL Target] i användargränssnittet för **[!UICONTROL View in Analytics]**.
1. Lägg till kolumnen **[!UICONTROL Activity Impressions]** i rapporten [[!DNL Analytics Workspace]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=sv-SE){target=_blank}.
1. Klicka på ikonen **[!UICONTROL Activity Impressions]** i kolumnen [!UICONTROL Gear].
1. Klicka på **[!UICONTROL Use non-default attribution model]**.
1. Välj **[!UICONTROL Same Touch Model]** > **[!UICONTROL Apply]**.

+++
