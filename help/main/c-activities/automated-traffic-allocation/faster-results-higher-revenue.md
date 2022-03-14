---
keywords: automatiserad trafikallokering;mål;autoallokering;automatisk tilldelning
description: Lär dig hur en autoallokeringsaktivitet i Adobe [!DNL Target] identifierar en vinnare bland två eller fler upplevelser och omfördelar automatiskt mer trafik till vinnaren.
title: Kan autofördela aktiviteter få snabbare resultat och högre intäkter?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 0%

---

# Automatisk allokering kan ge snabbare testresultat och högre intäkter än ett manuellt test

Med en manuell A/B-aktivitet kan du förlora konverteringar eftersom du inte kan leverera den vinnande upplevelsen till hela målgruppen förrän aktiviteten är klar. Er trafikdistribution är fast även efter att ni har insett att vissa upplevelser är bättre än andra, och aktiviteten måste gå hela kursen innan ni kan agera på en vinnare.

## Automatisk fördelning av trafik

Om du vill ha ett alternativ för att betjäna den vinnande upplevelsen oftare och tidigare i aktiviteten samtidigt som du tar bort eller minskar installations- och beräkningskostnaderna för att välja provstorlekar, konfidensnivåer och andra statistiska begrepp, [!UICONTROL Auto-Allocate] är det bästa alternativet.

## Hur fungerar Automatisk fördelning?

[!UICONTROL Auto-Allocate] använder principen om en flerarmad bandit. Om termen inte är känd är en enarmad bandit en kollokal term för en kortplatsmaskin (tänk: Las Vegas). Visualisera automatisk fördelning av trafik som att ha flera kortplatsmaskiner, i det här fallet testvariationer, och först dra alla handtag lika. Med tiden kan en eller flera maskiner, eller testvariationer, betala ut mer än andra. När det här händer skulle en spelare naturligtvis börja dra i handtagen av dem som vinner oftare. I trafikallokeringsvillkor [!DNL Adobe Target] ger fler besökare den upplevelse eller de upplevelser som vinner mer.

Se följande bild på en tvåveckorsaktivitet i A/B. Med [!UICONTROL Auto-Allocate], som en vinnande upplevelse, [!UICONTROL Target] flyttar ut mer av trafiken till vinnaren tidigt under testet.

![Automatisk fördelning av illustration](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Hur ger Automatisk fördelning mig snabbare resultat?

Uppsidan är ganska tydlig: fler besökare ser de variationer som fungerar bäst. Och som en enda variant kommer ännu fler besökare att dirigeras om till den vinnande upplevelsen medan testet fortfarande var igång. Detta är särskilt användbart om A/B-aktiviteten som körs inträffar under en tid som huvudverksamheten omfattar t.ex. en semester, produktlansering eller ett evenemang på världsmarknaden.

## Hur kan autofördelning ge mig högre intäkter?

[!UICONTROL Auto-Allocate] hittar vinnaren snabbare än en manuell A/B-delning och gör det även möjligt att utnyttja den vinnaren som omedelbart fångar upp upp intäkter som skulle ha gått förlorade i en traditionell eller manuell strategi. För [!UICONTROL Auto-Allocate] dirigerar mer trafik till upplevelsen med den högsta konverteringsgraden, vilket kan öka dina intäkter medan aktiviteten körs och lär sig.

I följande exempel [!UICONTROL Auto-Allocate] ökade intäkterna under testet genom att öka trafiken (40 %) till Experience D, som hade den högsta konverteringsgraden.

![Autoallokering ger en större intäktsillustration](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## I vilka fall ska jag stå fast vid manuell trafiktilldelning?

När du behöver rangordna hur varje upplevelse som utförs i förhållande till de andra, är ett manuellt A/B-test mest lämpligt. [!UICONTROL Auto-Allocate] hittar och utnyttjar topppresterande men garanterar inte differentiering mellan de lägre presterande upplevelserna. Ni bör använda manuell trafiktilldelning för att få fullständig kontroll över hur mycket besökstrafiken ser varje testvariant och för att anpassa de statistiska trösklar som är relevanta för ert företag.

## Kom igång

Klart att starta din första [!UICONTROL Auto-Allocate] aktivitet? [Läs mer här](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).
