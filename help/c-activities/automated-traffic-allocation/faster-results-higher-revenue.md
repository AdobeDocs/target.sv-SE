---
keywords: automated traffic allocation;targeting;auto-allocate
description: Med Automatisk tilldelning identifieras en vinnare bland två eller fler upplevelser och fler kunder tilldelas automatiskt mer trafik till vinnaren för att öka antalet konverteringar medan testet fortsätter att köras och lära sig mer.
title: Automatisk allokering kan ge snabbare testresultat och högre intäkter än ett manuellt test
feature: auto-allocate
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---


# Automatisk allokering kan ge snabbare testresultat och högre intäkter än ett manuellt test

Med en manuell A/B-aktivitet kan du förlora konverteringar eftersom du inte kan leverera den vinnande upplevelsen till hela målgruppen förrän aktiviteten är klar. Er trafikdistribution är fast även efter att ni har insett att vissa upplevelser är bättre än andra, och aktiviteten måste gå hela kursen innan ni kan agera på en vinnare.

## Automatisk fördelning av trafik

Om du vill att det ska gå att betjäna den vinnande upplevelsen oftare och tidigare i aktiviteten samtidigt som du tar bort eller minskar kostnaderna för konfiguration och beräkning av plockstorlekar, konfidensnivåer och andra statistiska koncept, [!UICONTROL Auto-Allocate] är det bästa alternativet.

## Hur fungerar Automatisk fördelning?

[!UICONTROL Auto-Allocate] använder principen om en flerarmad bandit. Om termen inte är känd är en enarmad bandit en kollokal term för en kortplatsmaskin (tänk: Las Vegas). Visualisera automatisk fördelning av trafik som att ha flera kortplatsmaskiner, i det här fallet testvariationer, och först dra alla handtag lika. Med tiden kan en eller flera maskiner, eller testvariationer, betala ut mer än andra. När det här händer skulle en spelare naturligtvis börja dra i handtagen av dem som vinner oftare. När det gäller trafikallokering kommer fler besökare att få tillgång till upplevelser eller upplevelser som vinner mer. [!DNL Adobe Target]

Se följande bild på en tvåveckorsaktivitet i A/B. När [!UICONTROL Auto-Allocate]en vinnande upplevelse dyker upp dirigerar [!UICONTROL Target] mer av trafiken till vinnaren tidigt på testet.

![Automatisk fördelning av illustration](/help/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Hur ger Automatisk fördelning mig snabbare resultat?

Uppsidan är ganska tydlig: fler besökare ser de variationer som fungerar bäst. Och som en enda variant kommer ännu fler besökare att dirigeras om till den vinnande upplevelsen medan testet fortfarande var igång. Detta är särskilt användbart om A/B-aktiviteten som körs inträffar under en tid som huvudverksamheten omfattar t.ex. en semester, produktlansering eller ett evenemang på världsmarknaden.

## Hur kan autofördelning ge mig högre intäkter?

[!UICONTROL Auto-Allocate] hittar vinnaren snabbare än en manuell A/B-delning och gör det även möjligt att utnyttja den vinnaren som omedelbart fångar upp upp intäkter som skulle ha gått förlorade i en traditionell eller manuell strategi. Eftersom [!UICONTROL Auto-Allocate] dirigerar mer trafik till upplevelsen med den högsta konverteringsgraden kan det öka intäkterna medan aktiviteten körs och lär sig.

I följande exempel ökade [!UICONTROL Auto-Allocate] intäkterna under testet genom att öka trafiken (40 %) till Experience D, som hade den högsta konverteringsgraden.

![Autoallokering ger en större intäktsillustration](/help/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## I vilka fall ska jag stå fast vid manuell trafiktilldelning?

När du behöver rangordna hur varje upplevelse som utförs i förhållande till de andra, är ett manuellt A/B-test mest lämpligt. [!UICONTROL Auto-Allocate] hittar och utnyttjar topppresterande men garanterar inte differentiering mellan de lägre presterande upplevelserna. Ni bör använda manuell trafiktilldelning för att få fullständig kontroll över hur mycket besökstrafiken ser varje testvariant och för att anpassa de statistiska trösklar som är relevanta för ert företag.

## Kom igång

Vill du starta din första [!UICONTROL Auto-Allocate] aktivitet? [Läs mer här](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

