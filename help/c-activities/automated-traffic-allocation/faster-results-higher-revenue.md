---
keywords: automated traffic allocation;targeting;auto-allocate;auto allocate
description: Aktiviteten Automatisk allokering i Adobe Target identifierar en vinnare bland två eller fler upplevelser och omfördelar automatiskt mer trafik till vinnaren för att öka antalet konverteringar medan testet fortsätter att köras och lära sig.
title: Automatisk allokering kan ge snabbare testresultat och högre intäkter än ett manuellt test
feature: Auto-Allocate
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 0%

---


# Automatisk allokering kan ge snabbare testresultat och högre intäkter än ett manuellt test

Med en manuell A/B-aktivitet kan du förlora konverteringar eftersom du inte kan leverera den vinnande upplevelsen till hela målgruppen förrän aktiviteten är klar. Er trafikdistribution är fast även efter att ni har insett att vissa upplevelser är bättre än andra, och aktiviteten måste gå hela kursen innan ni kan agera på en vinnare.

## Automatisk fördelning av trafik

Om du vill ha ett alternativ för att leverera den vinnande upplevelsen oftare och tidigare i aktiviteten samtidigt som du tar bort eller minskar installations- och beräkningskostnaderna för att välja provstorlekar, konfidensnivåer och andra statistiska koncept, är [!UICONTROL Auto-Allocate] det bästa alternativet.

## Hur fungerar Automatisk fördelning?

[!UICONTROL Auto-Allocate] använder principen om en flerarmad bandit. Om termen inte är känd är en enarmad bandit en kollokal term för en kortplatsmaskin (tänk: Las Vegas). Visualisera automatisk fördelning av trafik som att ha flera kortplatsmaskiner, i det här fallet testvariationer, och först dra alla handtag lika. Med tiden kan en eller flera maskiner, eller testvariationer, betala ut mer än andra. När det här händer skulle en spelare naturligtvis börja dra i handtagen av dem som vinner oftare. När det gäller trafikallokering kommer [!DNL Adobe Target] att ge fler besökare den upplevelse eller de upplevelser som vinner mer.

Se följande bild på en tvåveckorsaktivitet i A/B. Med [!UICONTROL Auto-Allocate] dirigerar [!UICONTROL Target] allt mer trafik till vinnaren tidigt under testet.

![Automatisk fördelning av illustration](/help/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Hur ger Automatisk fördelning mig snabbare resultat?

Uppsidan är ganska tydlig: fler besökare ser de variationer som fungerar bäst. Och som en enda variant kommer ännu fler besökare att dirigeras om till den vinnande upplevelsen medan testet fortfarande var igång. Detta är särskilt användbart om A/B-aktiviteten som körs inträffar under en tid som huvudverksamheten omfattar t.ex. en semester, produktlansering eller ett evenemang på världsmarknaden.

## Hur kan autofördelning ge mig högre intäkter?

[!UICONTROL Auto-Allocate] hittar vinnaren snabbare än en manuell A/B-delning och gör det även möjligt att utnyttja den vinnaren som omedelbart fångar upp upp intäkter som skulle ha gått förlorade i en traditionell eller manuell strategi. Eftersom [!UICONTROL Auto-Allocate] dirigerar mer trafik till upplevelsen med den högsta konverteringsgraden, kan intäkterna öka medan aktiviteten körs och lär sig.

I följande exempel ökade [!UICONTROL Auto-Allocate] intäkterna under testet genom att öka trafiken (40 %) till Experience D, som hade den högsta konverteringsgraden.

![Autoallokering ger en större intäktsillustration](/help/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## I vilka fall ska jag stå fast vid manuell trafiktilldelning?

När du behöver rangordna hur varje upplevelse som utförs i förhållande till de andra, är ett manuellt A/B-test mest lämpligt. [!UICONTROL Auto-Allocate] hittar och utnyttjar topppresterande men garanterar inte differentiering mellan de lägre presterande upplevelserna. Ni bör använda manuell trafiktilldelning för att få fullständig kontroll över hur mycket besökstrafiken ser varje testvariant och för att anpassa de statistiska trösklar som är relevanta för ert företag.

## Kom igång

Vill du starta din första [!UICONTROL Auto-Allocate]-aktivitet? [Läs mer här](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

