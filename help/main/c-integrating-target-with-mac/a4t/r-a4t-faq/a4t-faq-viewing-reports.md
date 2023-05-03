---
keywords: frågor och svar;vanliga frågor;analyser för mål;a4T;rapport;rapporter;visa rapporter;rapportera;inventeringsmetod;visningar;besökare;besök;standardmått;aktivitetskonverteringar;ospecificerad
description: Hitta svar på frågor som ofta ställs om att visa rapporter när Analytics används för [!DNL Target] (A4T). Med A4T kan ni använda analysrapporter för [!DNL Target] verksamhet.
title: Hitta svar på frågor om att visa rapporter med A4T?
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: 79ae58377c9eea0faca1ade11f2ab53da56b7bc1
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Visa rapporter - A4T FAQ

Det här avsnittet innehåller svar på frågor som ofta ställs om att visa rapporter när du använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T).

## Kan jag se min [!DNL Target] aktivitetsdata i [!DNL Analysis Workspace]? {#workspace}

+++Svar Du kan använda [!DNL Analysis Workspace] för att analysera [!DNL Target] aktiviteter och upplevelser. The [Analyser för målpanelen](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) ger er möjlighet att se lyft och självförtroende för så många som tre framgångsmått. Du kan också fördjupa dig i tabeller och visualiseringar.

Detaljerad information och exempel finns i [Analytics &amp; Target: Självstudiekurs om metodtips för analys](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), tillhandahålls av [!UICONTROL Adobe Experience League].

+++

## Var kan segment användas i [!DNL Analysis Workspace]? {#segmentation}

+++Svarssegment används oftast överst på en panel i segmentets släppzon. Segmentet tillämpas på alla tabeller och visualiseringar i panelen. Den här tekniken är mest användbar för att se hur testet påverkar en delmängd av människor (till exempel, hur utfördes det här testet för människor i Storbritannien)?

Ett segment kan också läggas i lager direkt i friformstabellen, men observera att du måste täcka över hela tabellen för att kunna bevara lyftnings- och tillförlitlighetsberäkningarna i A4T-panelen. Kolumnnivåsegment stöds för närvarande inte på panelen.

+++

## Kan jag använda Attribution IQ&quot;Samma beröring&quot; i [!DNL Analysis Workspace]?

+++Besvara vid användning [!DNL Target] aktivitetsintryck och konverteringar i [!DNL Analysis Workspace]använder du modellen &quot;Same Touch&quot; på mätvärdena för att säkerställa korrekt Attribution IQ. Använda en [icke-standardattribueringsmodell](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html), högerklicka på måttet för att **Ändra kolumninställningar > aktivera Använd icke-standardattribueringsmodell > välj samma Touch-modell**. Om den här modellen inte används överskattas mätvärdena.

Alla aktuella [!DNL Adobe Analytics] paket kan lägga till den här modellen med [!UICONTROL Attribution IQ]. Om du inte har tillgång till [!UICONTROL Attribution IQ], förlita dig på A4T-data i [!UICONTROL Reports & Analytics].

+++

## När jag använder ett träffsegment för ett specifikt [!DNL Target] aktivitet, varför returneras orelaterade upplevelser? {#activity-segmentation}

+++Besvara [!DNL Target] variabel skickad till [!DNL Analytics] har en 90-dagars standardförfalloperiod. (Obs! denna förfalloperiod kan justeras av kundtjänst om det behövs). När besökare navigerar på webbplatsen genom det här förfallofönstret är de en del av många [!DNL Target] verksamhet, som alla samlas in i dimensionen.

När du väljer att en aktivitet ska vara närvarande i en träff får du alla upplevelser som är en del av den aktiviteten *plus* alla andra upplevelser som är bestående av den träffen.

+++

## När jag konfigurerar [!UICONTROL Goal Metrics], varför kan jag inte komma åt [!UICONTROL Advanced Settings]?

+++Besvara aktiviteter som använder [!DNL Analytics] som rapportkälla (A4T) använder målmåttet &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; och &quot;[!UICONTROL On Every Impression]&quot;. Dessa inställningar *not* kan konfigureras.

Mer information finns i&quot;När jag konfigurerar mina målmått, varför kan jag inte komma åt alternativen för Avancerade inställningar?&quot; in [Måttdefinitioner - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## Bör jag använda besökare, besök eller aktivitetsuttryck som min normaliserande mätning (dvs. beräkningsmetod)? {#metrics}

+++Svar Det finns flera alternativ för normalisering av mätvärden i A4T-rapportering. Detta mätresultat, som också kallas beräkningsmetoden, blir nämnare för beräkningen av lyft. Det påverkar också hur data aggregeras innan konfidensberäkningen tillämpas.

* ***Unika besökare*** ökas en gång när en användare först kvalificerar sig för en aktivitet.
* ***Besök*** stegvis ökning för varje session när en användare (Unik besökare) deltar i en aktivitet, även om aktiviteten inte visas vid efterföljande besök.
* ***Aktivitetsintryck*** ökning varje gång aktivitetsinnehållet hanteras. (Mätt med [!DNL Target]).

När en besökare visar en sida som innehåller en aktivitet, ställs en variabel in för besökaren som innehåller aktivitetens namn. Se de detaljerade scenarierna nedan för hur varje beräkningsmetod jämförs.

Tänk på följande:

* Ovanstående mått utlöser när en användare kvalificerar sig för en aktivitet och innehållet returneras från [!DNL Target]. Det behöver inte innebära att användaren såg erbjudandet. Om en aktivitetsupplevelse är under upplösningen och användaren inte rullar nedåt på sidan, så har erbjudandet [!DNL Target] men inte av användaren.
* [!UICONTROL Activity Impressions] (mätt med [!DNL Target]) och [!UICONTROL Instances] (mätt med [!DNL Analytics]) är lika, såvida det inte finns flera mbox-anrop på samma sida i samma aktivitet. Detta orsakar flera [!UICONTROL Activity Impressions] ska räknas, men bara en [!UICONTROL Instance].

Mer information finns i [Konfigurera A4T-rapporter i Analysis Workspace för Automatiskt mål-aktiviteter](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*.

+++

## Varför är &quot;aktivitetsintryck&quot; och &quot;aktivitetskonverteringar&quot; högre i [!DNL Analysis Workspace] än [!UICONTROL Reports & Analytics]? {#sametouch}

+++Svar
[!DNL Reports & Analytics] använder samma attribueringsmodell för &quot;aktivitetsavtryck&quot; och &quot;aktivitetskonverteringar&quot;, medan [!DNL Analysis Workspace] visar de obearbetade måtten, som kan se inflammaterade ut på grund av att [!DNL Target] dimension.

Utvärdera korrekt [!UICONTROL Activity Impressions] och [!UICONTROL Activity Conversions] mätvärden i [!DNL Analysis Workspace], se till att båda mätvärdena har [!UICONTROL Same Touch] använda attribueringsmodeller. Du kan använda modeller genom att klicka på kolumninställningskugget, aktivera [!UICONTROL Non-default attribution models]väljer [!UICONTROL Same Touch]. Läs mer om attribuering i [Översikt över attribut-IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) i *Handbok för analysverktyg*.

+++

## Vad betyder&quot;aktivitetskonverteringar&quot; om marknadsföraren väljer en [!DNL Analytics] mått under aktivitetsinställningarna? {#section_F3EBACF85AF846E9B366A549AAB64356}

+++Besvara &quot;Aktivitetskonverteringar&quot; är tomma om en [!DNL Analytics] Mått valdes som konverteringsmått för aktiviteten.

+++

## Varför ser jag&quot;ospecificerad&quot; i [!DNL Analytics] rapporter? Vad betyder det? {#unspecified}

+++Svar I andra rapporter betyder&quot;ospecificerad&quot; att data inte uppfyller en klassificeringsregel, men i A4T ska detta aldrig ske. Om du ser&quot;ospecificerad&quot; har klassificeringstjänsten inte körts ännu. Det tar i allmänhet mellan 24 och 72 timmar innan aktivitetsdata visas i rapporterna. Även om aktiviteterna inte visas i den här rapporten förrän vid den tidpunkten hämtas alla besöksdata som är kopplade till dessa aktiviteter och visas när klassificeringen är klar.

Efter klassificeringsperioden visas data i dessa rapporter ungefär en timme efter det att de samlats in från webbplatsen. Alla mätvärden, segment och värden i rapporterna kommer från den rapportsserie du valde när du konfigurerade aktiviteten.

Om en klassificering har gjorts för den aktiviteten och du fortfarande ser raden &quot;Ospecificerad&quot; i rapporten, kontrollerar du att rapporten inte använder en[!DNL Target] mått för att visa data. Om inte rapporten använder en [!DNL Target]-specifikt mått, att raden &quot;Ospecificerad&quot; innehåller händelser för anrop som inte är associerade [!DNL Target]. Den raden innehåller inga [!DNL Target]-associerad information (till exempel besökare/besök/visningar).

+++

## Varför [!DNL Target] mått skickade till [!DNL Analytics] även efter att aktiviteten har inaktiverats? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

+++Besvara [!DNL Target] variabel skickad till [!DNL Analytics] har en 90-dagars standardförfalloperiod. Den här förfalloperioden kan justeras av kundtjänst om det behövs. Denna inställning är global för alla verksamheter. Därför bör den inte justeras för ett fall.

Du kanske ser [!DNL Target] variabler skickade till [!DNL Analytics] efter förfalloperioden eftersom förfallotiden är 90 dagar, men bara om användaren aldrig ser någon annan A4T-aktiverad [!DNL Target] aktivitet. Om en användare kommer tillbaka till webbplatsen dag 45 och ser en annan aktivitet, har A4T-eVar värde återställts till 90 dagar. Det innebär att den första kampanjen från dag 1 nu kan vara beständig i upp till 45 + 90 = 135 dagar. Om användaren kommer tillbaka kan du komma till den punkt där mätvärdena skickas till [!DNL Analytics] i rapporter från mycket äldre aktiviteter. När användare tar bort cookies och inte återvänder till webbplatsen, försvinner siffrorna i aktiviteten, men du kan fortfarande se dem.

Det innebär att aktiviteter fortsätter att få sidvisningar, besök och så vidare i upp till 90 dagar efter att aktiviteten avslutas för besökare som blev en del av aktiviteten medan den var aktiv. Om du tittar på [!UICONTROL Activity Impressions] ska du inte se några intryck när aktiviteten är slut.

Detta är normalt och förväntat beteende. A4T-variabeln fungerar på samma sätt som andra eVar. Värdet associeras med användaren tills det når förfallotidsperioden (90 dagar). Om en aktivitet bara är aktiv i två veckor är därför värdet fortfarande associerat med användaren under minst de kommande 90 dagarna.

Bästa praxis är att endast visa rapporter för den aktiviteten för den tidsperiod som aktiviteten var aktiv. Datumen bör anges korrekt som standard när du visar aktiviteten i [!DNL Analytics], så om du inte har förlängt datumet manuellt bör det inte vara något problem ur en rapportsynpunkt.

Låt oss till exempel anta att variabeln A4T upphör att gälla efter 90 dagar och att testet är aktivt från 1 januari till 15 januari.

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

Användaren kommer sedan tillbaka den 1 april, besöker ytterligare fem sidor och gör ett köp. Det första eVar 90-dagars förfallodatum återställs den 1 april, så du ser det i rapporter. Och alla Target-aktiviteter som användaren ser får kredit för konverteringen, men det totala antalet konverteringar tas bort:

| Aktivitetsnamn | Instanser (Impressions) | Sidvyer | Besök | Unika besökare | Beställningar |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| Totalt | 2 | 20 | 3 | 1 | 1 |

Eftersom båda upplevelserna sågs före konverteringen får de båda&quot;kredit&quot; för ordern. Men det var bara en order som gjordes i systemet, och det är det som syns. För [!DNL Target] rapportering, eftersom du inte skickar [!DNL Target] aktivitet mot en annan aktivitet för att se vilken som är mest framgångsrik, det spelar ingen roll att alla aktiviteter som användaren såg fick kredit. Du jämför resultaten av två objekt i den enskilda aktiviteten. Det är inte möjligt för en användare att se olika upplevelser i samma aktivitet, så du behöver inte bekymra dig om korskontaminering av orderkrediter.

Mer information finns i [Konverteringsvariabler (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) i *Administratörshandbok för analyser*.

+++

## Varför ser jag fler intryck när min aktivitet har inaktiverats? {#deactivated}

+++Svar En källa till visningar av en A4T-aktivitets rapport efter avaktiveringen kan vara trafik i QA-läge. Målet loggar normalt inte händelser för en inaktiverad aktivitet, men det finns inget sätt att veta att det kommer att synas i QA-läge i Analytics. När Target-aktivitetsrapporten hämtas från Analytics visas dessa intryck. Detta fungerar som avsett eftersom kunderna behöver ett sätt att kontrollera A4T-rapporter även om aktiviteten inte är aktiv i QA-läge.

+++

## Varför [!DNL Analytics] och [!UICONTROL Analytics for Adobe Target] (A4T) beräkna tal för [!UICONTROL Unique Visitors] mätvärden annorlunda? {#section_0C3B648AB54041F9A2AA839D51791883}

+++Svar När du kör ett A/B-test, som använder [Welch&#39;s t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} (konfidensmåttet) för att välja en vinnare av ett test är en av antagandena att det finns en fast tidshorisont. Testet är inte statistiskt giltigt om du inte tittar på den fasta provstorleken.

The [!UICONTROL Unique Visitors] är olika i [!DNL Analytics] och [!DNL Target] bara när du tittar på en period som är kortare än det faktiska testet. Om du inte har uppnått din provstorlek är testet inte lika tillförlitligt. Se [Så här kör du ett A/B-test](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) på [Evan Millers webbplats](https://www.evanmiller.org/index.html) för mer information.

The [!UICONTROL Unique Visitors] Mätvärdet visar det antal personer som har exponerats för testet och som har besökt platsen under den angivna tidsperioden. Dessa personer är en del av testet och bör räknas. Om du bara vill se antalet personer som exponerades under en vecka, kan du skapa ett segment med besökare som hade ett aktivitetsintryck och använda det på rapporten.

Du kan korta ned tiden [!DNL Target] variabeln kvarstår ned till en session, Detta är dock problematiskt för tester där konverteringshändelsen inte är så trolig att inträffa under samma session.

+++

## Varför räknas samma besökare ibland i olika upplevelser i [!DNL Analytics]? {#section_1397E972D31C4207A142E4D2D6D794A2}

+++Svar I följande lista förklaras varför samma besökare kan räknas med i flera upplevelser i [!DNL Analytics]:

* The [!DNL Target] profilen har gått ut men [!DNL Analytics] cookie är fortfarande där. I denna situation [!DNL Target] omvärderar användaren men [!DNL Analytics] anser att besökaren är samma person.
* Om besökaren använder `mbox3rdPartyId`, när den anonyma besökaren sammanfogas med profilen för tredjeparts-ID, [!DNL Target] skulle kunna ge besökaren en annan upplevelse för att matcha med ett ID från tredje part. Mer information finns i [Profilsynkronisering i realtid för mbox3rdPartyID](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] kan spåra olika enheter som samma besökare på ett annat sätt än [!DNL Target] spårar enheterna: konfiguration av tredje parts-ID i [!DNL Target] skiljer sig från Analytics.

+++

## Stöder A4T virtuella rapportsviter? {#virtual}

+++Svar Även om virtuella rapportsviter inte ingår i [!UICONTROL Report Suite] lista, alla A4T-data som delas med en rapportserie som är länkad till en virtuell rapportserie i [!DNL Analytics] har tillgång till dessa data. Observera att alla målgrupper som skapats från en virtuell rapportserie inte kan delas tillbaka till [!DNL Target].

+++

## Kan jag ändra procentandelen trafiktilldelning i en aktivitet som använder A4T efter att aktiviteten har aktiverats?

+++Svar Om du ändrar procentvärdet för trafikallokering i en aktivitet efter aktivering kan det leda till inkonsekvent rapportering i [!DNL Analytics] eftersom förändringen endast påverkar nya besökare. Återkommande besökare påverkas inte.

Det bästa är att du stoppar den befintliga aktiviteten och sedan skapar en ny aktivitet i stället för att ändra procentandelen efter aktiveringen. Rapporteringen för den nya aktiviteten börjar med nya besökare och data från återkommande besökare orsakar inte inkonsekvent rapportering.

+++

## Hur räknas besök i [!DNL Analytics] och konverteringskrediter som tilldelats i en [!UICONTROL Auto-Target] aktivitet som använder A4T?

+++Svar När en besökare kvalificerar sig för, visar innehåll eller konverterar i en A4T-aktivitet, [!DNL Target] skickar händelsedata till [!DNL Analytics]. Dessa händelsedata tillåter [!DNL Analytics] för att attribuera konverteringshändelser och andra klickströmshändelser på sidan till relevanta [!DNL Target] aktiviteter och upplevelser.

Här är några saker du bör tänka på när du tittar [!DNL Analytics] rapporter:

* Som en god praxis bör ditt rapporteringsfönster börja från aktivitetens startdatum.
* Om en konvertering sker utanför rapportens fönster visas inte konverteringen i [!DNL Analytics].
* I den&quot;riktade&quot; delen av trafiken för [!UICONTROL Auto-Target] aktiviteter kan besökarna se olika upplevelser från en session till nästa. Om deras profil eller kontext till exempel har ändrats och [!DNL Target]Med maskininlärningsalgoritmerna vet vi att de är mer benägna att konvertera till en ny upplevelse. När besökarna rör sig från upplevelse till upplevelse ökar besöksantalet för varje upplevelse som ses. Detta skiljer sig från vanliga A/B-testningsaktiviteter där upplevelserna är kladdiga för besökarna vid olika besök.
* Om en besökare ser flera upplevelser på flera besök, tillskrivs all konvertering alltid den senaste upplevelsen som besökaren såg. Som vi nämnt ökas besöksantalet för varje upplevelse som besökaren såg. Detta kan på ett konstlat sätt påverka konverteringsgraden per upplevelse när du visar upplevelser under &quot;[!UICONTROL Targeted]&quot; dimension in [!DNL Adobe Analytics] rapporter.

+++

## Hur spårar jag aktivitetsintryck i [!DNL Analysis Workspace] när [!UICONTROL Analytics for Target] (A4T)? {#activity-impressions}

+++Svar

Visa aktivitetsuttryck i [!DNL Analysis Workspace]:

1. I [!DNL Target] Gränssnitt, klicka **[!UICONTROL View in Analytics]**.
1. Lägg till **[!UICONTROL Activity Impressions]** kolumn till [[!DNL Analytics Workspace]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html){target=_blank} rapport.
1. På **[!UICONTROL Activity Impressions]** kolumn, klicka på [!UICONTROL Gear] ikon.
1. Klicka på **[!UICONTROL Use non-default attribution model]**.
1. Välj **[!UICONTROL Same Touch Model]** > **[!UICONTROL Apply]**.

+++