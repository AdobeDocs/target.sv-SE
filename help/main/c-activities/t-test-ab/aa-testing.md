---
keywords: a/b;a/a;aa;
description: Lär dig vad ett A/A-test är, varför du kanske vill göra ett A/A-test, hur länge du ska köra testet och hur du ska tolka resultaten.
title: Vad är A/A-testning?
feature: A/B Tests
exl-id: 7489f4f5-3655-45f9-a743-651ba1c23c53
source-git-commit: 4f0ebdd06287a438e519d9bccb677ab1a9093396
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 0%

---

# A/A-tester

Innan du utför ett A/A-test på din plats med [!DNL Adobe Target], det är viktigt att förstå vad ett A/A-test är, varför du kanske vill utföra ett A/A-test, hur länge du ska köra testet och hur resultatet ska tolkas.

## Vad är A/A-tester?

Innan vi förklarar A/A-tester är det bra att granska A/B-tester så att vi sedan kan diskutera skillnaderna.

I ett standard-A/B-test fördelas trafiken på två eller flera olika upplevelser. En upplevelse är vanligtvis&quot;kontrollen&quot; och variationer av upplevelsen testas mot kontrollen för att se vilken upplevelse som ger störst lyft i ett givet mätresultat.

A/A-tester innebär dock att trafik tilldelas till två identiska upplevelser, vanligtvis med en 50/50-uppdelad trafikallokering. Med ett standard-A/B-test vill du vanligtvis upptäcka en ökning av konverteringen. Detta skiljer sig från ett A/A-test där ditt mål vanligtvis är att fastställa att det finns *no* skillnaden i lyft mellan de identiska upplevelserna.

## Varför vill ni testa två identiska upplevelser och vad innebär detta?

Vissa organisationer utför A/A-tester när de implementerar ett nytt testverktyg, som [!DNL Target], för att avgöra om:

* Aktiviteten konfigurerades korrekt
* Koden implementerades korrekt
* Rapporteringen är korrekt

Även om få organisationer kör A/A-tester är det god praxis att köra dem som&quot;sanitetsexperiment&quot; för att bygga upp förtroende efter att verktyget har implementerats eller innan A/B-tester utförs som kan påverka konvertering och intäkter.

## Varför skulle ni vilja lyfta för en upplevelse när upplevelserna är identiska?

Det finns många orsaker till varför du kan se en ny upplevelse framför en annan (identisk) upplevelse:

### A/A-testet övervakades kontinuerligt

Ett vanligt problem med att köra alla typer av tester, inklusive A/A-tester, är att titta på resultaten kontinuerligt och i förtid stoppa ett test när du ser statistisk signifikans och deklarera en vinnande upplevelse. Analytikerna gör ofta det som kallas&quot;datasökning&quot;. Vid sökning efter data måste man titta på testdata tidigt och ofta, samtidigt som man försöker avgöra vilken upplevelse som fungerar bättre. Risken är att stoppa testet i förtid, vilket kan göra resultaten ogiltiga.

I ett A/A-test kan dataperspektiv ofta få analytiker att se en lyft i en upplevelse, när det i själva verket inte ska vara någon skillnad, eftersom de två upplevelserna är identiska. A/A-tester är faktiskt *garanterad* att visa &quot;statistisk signifikans&quot; (dvs. en konfidensnivå över ett visst tröskelvärde, såsom 95 %) vid något tillfälle under testet.

För att undvika detta, och på samma sätt som med ett vanligt A/B-test, bör du därför i förväg bestämma vilken provstorlek som ska användas, baserat på den minsta effektstorleken (den minsta lyft under vilken en effekt inte är viktig för ditt företag), den effekt och de signifikansnivåer som du anser godtagbara.

I ett A/A-test är målet då att *not* se ett statistiskt signifikant resultat efter att ditt test har nått den önskade provstorleken.

The [!UICONTROL Adobe Target Sample Size Calculator] är ett viktigt verktyg som du kan använda för att avgöra vilken provstorlek du ska rikta dig mot och hur länge du ska köra testet.

* [Adobe Target Size Calculator](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

I följande artiklar finns dessutom information om hur länge du ska köra en aktivitet och andra användbara tips och tricks:

* [Hur länge ska du köra ett A/B-test?](/help/main/c-activities/t-test-ab/sample-size-determination.md)
* [Tio vanliga A/B-fallfall och hur man undviker dem](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### Statistisk signifikans påverkar testresultaten

Betydelsenivån för ett test avgör hur sannolikt det är att testet rapporterar en betydande skillnad i konverteringsgraden mellan två olika erbjudanden när det i själva verket inte finns någon verklig skillnad. Detta kallas falskt positivt eller ett Type I-fel. Signaturnivån är ett tröskelvärde som anges av användaren och det finns en kompromiss mellan toleransen för falska positiva värden och antalet besökare som måste ingå i testet när man väljer rätt signifikansnivå.

En vanlig signifikansnivå vid A/A- och A/B-testning är 5%, vilket motsvarar en konfidensnivå på 95% (konfidensnivå = 100% - signifikansnivå). En konfidensnivå på 95 % innebär att det varje gång du utför ett test finns en 5-procentig risk för att upptäcka en statistiskt signifikant ökning, även om det inte finns någon skillnad mellan upplevelserna.

Anta att du vill uppnå en 95-procentig konfidensnivå med A/A-testet. Med en konfidensnivå på 95% kan 1 av 20 A/A-tester visa statistiskt signifikant ökning av konverteringarna. Med en konfidensnivå på 90 % kan 1 av 10 tester visa ökning av antalet konverteringar när identiska upplevelser testas.

## Bästa praxis

Om du bestämmer dig för att ett A/A-test är nödvändigt i din organisation, ska du vara medveten om att identiska upplevelser tillfälligt kan visa en skillnad från kontrollen. Detta kan vara normalt, beroende på den tid som testet tillåts köras. Skillnaden bör krympa med tanke på mer tid och besökare.

Bästa praxis är att använda regelbundna A/B-testmetoder: bestämma provstorleken i förväg baserat på en minsta relevant effektstorlek, önskad effekt och signifikans med hjälp av [Adobe Target Size Calculator](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

Låt sedan besökarna lägga ned tillräckligt med tid innan ni kommer fram till några slutsatser, och kom ihåg att beroende på testets signifikansnivå finns det en chans att en upplevelse visar skillnad och till och med förklaras vinnare.
