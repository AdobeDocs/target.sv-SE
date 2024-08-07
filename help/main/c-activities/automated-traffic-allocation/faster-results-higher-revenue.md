---
keywords: automatiserad trafikallokering;mål;autoallokering;automatisk tilldelning
description: Lär dig hur en [!UICONTROL Auto Allocate]-aktivitet i [!DNL Adobe Target] identifierar en vinnare bland två eller fler upplevelser och automatiskt omfördelar mer trafik till vinnaren.
title: Kan [!UICONTROL Auto-Allocate] aktiviteter få snabbare resultat och högre intäkter?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
source-git-commit: e9976135c46f6658030b07fce384364f0c9ff0ed
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# [!UICONTROL Auto-Allocate] ger dig snabbare testresultat och högre intäkter än ett manuellt test

Med en manuell A/B-aktivitet kan du förlora konverteringar eftersom du inte kan leverera den vinnande upplevelsen till hela målgruppen förrän aktiviteten är klar. Er trafikdistribution är fast även efter att ni har insett att vissa upplevelser är bättre än andra, och aktiviteten måste gå hela kursen innan ni kan agera på en vinnare.

## Automatisk fördelning av trafik

Om du vill ha ett alternativ för att leverera den vinnande upplevelsen oftare och tidigare i aktiviteten samtidigt som du tar bort eller minskar installations- och beräkningskostnaderna för att välja provstorlekar, konfidensnivåer och andra statistiska begrepp, är [!UICONTROL Auto-Allocate] det bästa alternativet.

## Hur fungerar [!UICONTROL Auto-Allocate]?

[!UICONTROL Auto-Allocate] använder principen för den flerarmade banken. Om termen inte är bekant är en enarmad bandit en kollokal term för en kortplatsmaskin (tänk: Las Vegas). Visualisera automatisk fördelning av trafik som att ha flera kortplatsmaskiner, i det här fallet testvariationer, och först dra alla handtag lika. Med tiden kan en eller flera maskiner, eller testvariationer, betala ut mer än andra. När det här inträffar skulle en spelare naturligtvis börja ta hand om de som vinner oftare. I villkoren för trafikallokering ger [!DNL Target] fler besökare en upplevelse eller upplevelser som vinner mer.

Se följande bild på en tvåveckorsaktivitet i A/B. Med [!UICONTROL Auto-Allocate] dirigeras mer av trafiken från [!UICONTROL Target] till vinnaren tidigt i testet när en vinnande upplevelse uppstår.

![Autoallokera illustration](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Hur ger [!UICONTROL Auto-Allocate] snabbare resultat?

Uppsidan är tydlig: fler besökare ser de variationer som fungerar bäst. Och som en enda variant kommer ännu fler besökare att dirigeras om till den vinnande upplevelsen medan testet fortfarande var igång. Den här metoden är särskilt användbar om A/B-aktiviteten som körs inträffar under ett viktigt tillfälle, t.ex. en semester, produktlansering eller ett världsomspännande nyhetsevenemang.

## Hur kan [!UICONTROL Auto-Allocate] ge högre intäkter?

[!UICONTROL Auto-Allocate] hittar vinnaren snabbare än en manuell A/B-delning och gör det även möjligt att utnyttja den vinnaren som omedelbart fångar upp upp intäkter som skulle ha gått förlorade i en traditionell eller manuell strategi. Eftersom [!UICONTROL Auto-Allocate] dirigerar mer trafik till upplevelsen med den högsta konverteringsgraden kan det öka dina intäkter medan aktiviteten körs och lär sig.

I följande exempel ökade [!UICONTROL Auto-Allocate] intäkterna under testet genom att öka trafiken (40 %) till Experience D, som hade den högsta konverteringsgraden.

![Automatisk allokering ger en större intäktsillustration](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## I vilka fall ska jag stå fast vid manuell trafiktilldelning?

När du måste rangordna hur varje upplevelse som utförs i förhållande till de andra, är ett manuellt A/B-test det lämpligaste. [!UICONTROL Auto-Allocate] hittar och utnyttjar topppresterande men garanterar inte en differentiering mellan de lågpresterande upplevelserna. Använd manuell trafikallokering för att få fullständig kontroll över hur mycket av besökstrafiken som ser varje testvariant och för anpassning av de statistiska trösklar som är relevanta för ert företag.

## Kom igång

Vill du starta din första [!UICONTROL Auto-Allocate]-aktivitet? [Lär dig mer här](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).
