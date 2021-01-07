---
keywords: a/b;a/a;aa;
description: Innan du utför ett A/A-test på din webbplats med Adobe Target är det viktigt att du förstår vad ett A/A-test är, varför du kanske vill utföra ett A/A-test, hur länge du ska köra testet och hur resultatet ska tolkas.
title: A/A-tester
feature: A/B Tests
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 0%

---


# A/A-tester

Innan du utför ett A/A-test på platsen med [!DNL Adobe Target] är det viktigt att förstå vad A/A-testet är, varför du kanske vill utföra ett A/A-test, hur länge du ska köra testet och hur resultatet ska tolkas.

## Vad är A/A-tester?

Innan vi förklarar A/A-tester är det bra att granska A/B-tester så att vi sedan kan diskutera skillnaderna.

I ett standard-A/B-test fördelas trafiken på två eller flera olika upplevelser. En upplevelse är vanligtvis&quot;kontrollen&quot; och variationer av upplevelsen testas mot kontrollen för att se vilken upplevelse som ger störst lyft i ett givet mätresultat.

A/A-tester innebär dock att trafik tilldelas till två identiska upplevelser, vanligtvis med en 50/50-uppdelad trafikallokering. Med ett standard-A/B-test vill du vanligtvis upptäcka en ökning av konverteringen. Detta skiljer sig från ett A/A-test där ditt mål vanligtvis är att fastställa att det finns *ingen* skillnad i lyft mellan de identiska upplevelserna.

## Varför vill ni testa två identiska upplevelser och vad innebär detta?

Vissa organisationer utför A/A-tester när de implementerar ett nytt testverktyg, som [!DNL Target], för att avgöra om:

* Aktiviteten konfigurerades korrekt
* Koden implementerades korrekt
* Rapporteringen är korrekt

Även om få organisationer kör A/A-tester är det i själva verket bra rutin att köra dem som&quot;friska&quot; experiment för att bygga upp förtroende efter att verktyget implementerats eller innan A/B-tester utförs som kan påverka konvertering och intäkter.

## Varför skulle ni vilja lyfta för en upplevelse när upplevelserna är identiska?

Det finns många orsaker till varför du kan se en ökning i en upplevelse jämfört med en annan (identisk) upplevelse:

### A/A-testet kunde inte köras tillräckligt länge

Ett vanligt problem med att köra alla typer av tester, inklusive ett A/A-test, är att i förväg stoppa ett test och deklarera en vinnande upplevelse. Analytikerna gör ofta det som kallas&quot;datasökning&quot;. Vid sökning efter data måste man titta på testdata tidigt och ofta, samtidigt som man försöker avgöra vilken upplevelse som fungerar bättre. Risken är att stoppa testet i förtid, vilket kan göra resultaten ogiltiga.

I ett A/A-test kan datapisökning ofta få analytiker att se en lyft i en upplevelse, när de antar att det inte ska vara någon skillnad, eftersom de två upplevelserna är identiska. Under en viss tid och med tillräckligt många besök bör lyfningsskillnaden krympa.

Som med ett vanligt A/B-test bör du därför i förväg bestämma vilken provstorlek som ska användas, baserat på den minsta effektstorlek, effekt och signifikansnivå som du anser vara acceptabel. I ett A/A-test är målet då att *inte* se ett statistiskt signifikant resultat efter att testet har nått den önskade provstorleken.

[!UICONTROL Adobe Target Sample Size Calculator] är ett viktigt verktyg som hjälper dig att avgöra vilken provstorlek du ska rikta dig mot och hur länge du ska köra testet.

* [Adobe Target Size Calculator](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

I följande artiklar finns dessutom information om hur länge du ska köra en aktivitet samt andra användbara tips och tricks:

* [Hur länge ska du köra ett A/B-test?](/help/c-activities/t-test-ab/sample-size-determination.md)
* [Tio vanliga A/B-fallfall och hur man undviker dem](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### Statistisk signifikans påverkar testresultaten

Betydelsenivån för ett test avgör hur sannolikt det är att testet rapporterar en betydande skillnad i konverteringsgraden mellan två olika erbjudanden när det i själva verket inte finns någon verklig skillnad. Detta kallas falskt positivt eller ett Type I-fel. Signaturnivån är ett tröskelvärde som anges av användaren och det finns en kompromiss mellan toleransen för falska positiva värden och antalet besökare som måste ingå i testet när man väljer rätt signifikansnivå.

En vanlig signifikansnivå vid A/A- och A/B-testning är 5%, vilket motsvarar en konfidensnivå på 95% (konfidensnivå = 100% - signifikansnivå). En konfidensnivå på 95 % innebär att det varje gång du utför ett test finns en 5-procentig risk för att upptäcka en statistiskt signifikant ökning, även om det inte finns någon skillnad mellan upplevelserna.

Anta att du vill uppnå en 95-procentig konfidensnivå med A/A-testet. Med en konfidensnivå på 95% kan 1 av 20 A/A-tester visa statistiskt signifikant ökning av konverteringarna. Med en konfidensnivå på 90 % kan 1 av 10 tester visa ökad konverteringsgrad när identiska upplevelser testas.

## Bästa praxis

Om du bestämmer dig för att ett A/A-test är nödvändigt i din organisation, ska du vara medveten om att identiska upplevelser tillfälligt kan visa en skillnad från kontrollen. Detta kan vara normalt, beroende på den tid som testet tillåts köras. Skillnaden bör krympa med tanke på mer tid och besökare.

Det bästa sättet är att använda regelbundna A/B-testmetoder: bestämma provstorleken i förväg baserat på en minsta effektstorlek, önskad effekt och signifikans med [Adobe Target Size Calculator](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

Låt sedan besökarna lägga ned tillräckligt med tid innan ni kommer fram till några slutsatser, och kom ihåg att beroende på testets signifikansnivå finns det en chans att en upplevelse visar skillnad och till och med förklaras vinnare.
