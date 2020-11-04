---
keywords: traffic estimator;automated personalization;ap
description: Traffic Estimator ger dig feedback som visar om du har tillräckligt med trafik för att din Adobe Target-aktivitet ska lyckas.
title: Uppskatta den trafik som krävs för att lyckas
feature: ap
topic: Standard
uuid: 9961ebaa-8761-431d-9605-852025ca580f
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Uppskatta den trafik som krävs för att lyckas{#estimate-the-traffic-required-for-success}

Här [!UICONTROL Traffic Estimator] får du information om du har tillräckligt med trafik för att din [!DNL Adobe Target] aktivitet ska lyckas.

Eftersom en [!UICONTROL Automated Personalization] aktivitet använder flera kombinationer av erbjudanden är det viktigt att veta hur mycket trafik som krävs för att ge meningsfulla resultat. I programmet [!UICONTROL Traffic Estimator] används statistik om er sida och antalet upplevelser som testas för att uppskatta mängden trafik och hur lång tid som krävs för att aktiviteten ska bli framgångsrik.

Det [!UICONTROL Traffic Estimator] avgör om det finns tillräckligt med trafik för att generera personaliserade modeller genom att jämföra sidornas uppskattade tryck och typiska konverteringsgrad. Det bästa är om du väljer en lyckad aktivitet med rätt samplingsstorlek, så att det anpassade innehållet är klart inom 50 % av aktivitetens varaktighet eller 14 dagar, beroende på vilket värde som är lägst. Detta ger tillräckligt med tid för att få personaliserat innehåll och lära sig vilket innehåll som ska levereras.

Kom ihåg att [!DNL Target] leverera upplevelser slumpmässigt tills personaliseringsalgoritmerna byggs. Kryssmarkeringsikonen bredvid varje erbjudande visar när modellen för det erbjudandet är klar och [!DNL Target] kan börja leverera personaliserat innehåll. Eftersom lift (lift) förväntas först när modellerna är klara kan du med den visuella indikeringen ställa in rätt förväntningar. Använd [!UICONTROL Traffic Estimator] i [!UICONTROL Visual Experience Composer] (VEC) för att få riktlinjer för när modellerna ska vara klara.

## Använda Traffic Estimator

1. From the [!UICONTROL Visual Experience Composer], click **[!UICONTROL Traffic]**.

   ![Trafikikon](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   De [!UICONTROL Traffic Estimator] öppnas. Du kan klicka **[!UICONTROL Traffic]** igen för att dölja [!UICONTROL Traffic Estimator].

   ![](assets/ap_est.png)

1. Ange typisk konverteringsgrad (eller den konverteringsgrad du förväntar dig av den här aktiviteten), beräknade aktivitetsavtryck per dag och testets varaktighet.

   * **Antal erbjudanden**: Beräknas automatiskt baserat på antalet upplevelser som skapas som en del av din aktivitet efter eventuella undantag.
   * **Normal konverteringsgrad**: Konverteringsgraden uttrycks som en procentandel, baserat på din uppskattning eller tidigare data från analyssystemet.
   * **Beräknade besök per dag**: Detta är antalet besök per dag från besökare som kan visa aktiviteten, baserat på målinriktningskriterierna. Detta kan baseras på era analysdata. Observera att det här numret ska vara besök, inte unika besökare.
   * **Testvaraktighet**: Antalet dagar som du vill att aktiviteten ska köras.

   Den [!UICONTROL Traffic Estimato]eller använder statistiken för att avgöra vilka justeringar som krävs för att köra ett lyckat test.

   I närheten av överkanten av [!UICONTROL Traffic Estimator]bilden beräknas de värden du anger och resultatet visas.

   ![](assets/ap_est_no.png)

   När du ändrar siffrorna ändras uppskattningen. Om du t.ex. testar ett stort antal kombinationer och konverteringsgraden och antalet visningar är för låga visas hur länge testet måste köras för att det ska lyckas. [!UICONTROL Traffic Estimator] Eller, om trafiken är låg, [!UICONTROL Traffic Estimator] så kan det bero på ett lägre antal erbjudandekombinationer så att du kan köra testet på det önskade antalet dagar.

   Om du inte har tillräckligt med trafik kan du göra något av följande:

   * Överväg att använda en [Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md) -aktivitet i stället för [!UICONTROL Automated Personalization] att skapa upplevelser med flera olika erbjudandeändringar i en upplevelsevariant.
   * Minska antalet erbjudandekombinationer inom er [!UICONTROL Automated Personalization] verksamhet.
   * Öka aktivitetens varaktighet.

   Justera siffrorna tills [!UICONTROL Traffic Estimator] du får tillräckligt med trafik och utforma sedan testet därefter.

   ![](assets/ap_est_yes.png)

   Om trafiken är tillräcklig visas en grön kontroll med [!UICONTROL Traffic] ikonen . Om ikonen inte är tillräcklig visas en röd varningsetikett.

## Vanliga frågor om trafikberäkningsverktyget

Tänk på följande vanliga frågor och svar när du arbetar med [!UICONTROL Traffic Estimator]:

### Varför bygger ni [!DNL Target] inte personaliserade modeller när min AP-aktivitet har tillräckligt med trafik?

Under vissa omständigheter kan trafiken vara tillräckligt stor för att en personaliserad modell ska kunna byggas, men trafiken kan informera om [!DNL Target] att det inte finns någon meningsfull skillnad mellan den personaliserade modellen och slumpmässigt. Även om modellen är inbyggd [!DNL Target] och testad kommer den inte att distribueras eftersom modellen inte är betydligt bättre än slumpmässig.

En möjlig orsak till att modellen inte är bättre än slumpmässigt kan vara att erbjudandena inte skiljer sig nämnvärt från varandra. Om så är fallet kan du prova att göra erbjudandena mer visuellt annorlunda om meddelandet är liknande, eller så kan du försöka ändra själva meddelandet.
