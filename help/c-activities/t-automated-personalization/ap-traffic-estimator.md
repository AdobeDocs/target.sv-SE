---
description: Trafikberäkningsverktyget ger dig feedback som visar om du har tillräckligt med trafik för att din aktivitet ska lyckas.
title: Uppskatta den trafik som krävs för att lyckas
feature: null
topic: Standard
uuid: 9961ebaa-8761-431d-9605-852025ca580f
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Uppskatta den trafik som krävs för att lyckas{#estimate-the-traffic-required-for-success}

Trafikberäkningsverktyget ger dig feedback som visar om du har tillräckligt med trafik för att din aktivitet ska lyckas.

Eftersom en Automated Personalization-aktivitet använder flera kombinationer av erbjudanden är det viktigt att veta hur mycket trafik som krävs för att uppnå meningsfulla resultat. Trafikuppskattningen använder statistik om er sida och antalet upplevelser som testas för att uppskatta mängden trafik och hur lång tid som krävs för att aktiviteten ska lyckas.

Traffic Estimator avgör om det finns tillräckligt med trafik för att generera personaliserade modeller genom att jämföra sidornas uppskattade visningar och typiska konverteringsgrad. Det bästa är om du väljer en lyckad aktivitet med rätt samplingsstorlek, så att det anpassade innehållet är klart inom 50 % av aktivitetens varaktighet eller 14 dagar, beroende på vilket värde som är lägst. Detta ger tillräckligt med tid för att få personaliserat innehåll och lära sig vilket innehåll som ska levereras.

Kom ihåg att Target levererar upplevelser slumpmässigt tills personaliseringsalgoritmerna byggs. Kryssmarkeringsikonen bredvid varje erbjudande visar när modellen för det erbjudandet är klar och Target kan börja leverera personaliserat innehåll. Eftersom lift (lift) förväntas först när modellerna är klara kan du med den visuella indikeringen ställa in rätt förväntningar. Använd trafikuppskattaren i Visual Experience Composer (VEC) för att få riktlinjer för när modellerna ska vara klara.

1. Klicka på i Experience Composer **[!UICONTROL Traffic]**.

   ![Trafikikon](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   Trafikberäkningsverktyget öppnas. Du kan klicka **[!UICONTROL Traffic]** igen för att dölja trafikberäkningsverktyget.

   ![](assets/ap_est.png)

1. Ange typisk konverteringsgrad (eller den konverteringsgrad du förväntar dig av den här aktiviteten), beräknade aktivitetsavtryck per dag och testets varaktighet.

   * Antal innehållskombinationer: Beräknas automatiskt baserat på antalet upplevelser som skapas som en del av din aktivitet efter eventuella undantag.
   * Normal konverteringsgrad: Konverteringsgraden uttrycks som en procentandel, baserat på din uppskattning eller tidigare data från analyssystemet.
   * Beräknade besök per dag: Detta är antalet besök per dag från besökare som kan visa aktiviteten, baserat på målinriktningskriterierna. Detta kan baseras på era analysdata. Observera att det här numret ska vara besök, inte unika besökare.
   * Testvaraktighet: Antalet dagar som du vill att aktiviteten ska köras.

   Trafikuppskattningen använder dessa statistik för att avgöra vilka justeringar som krävs för att köra ett lyckat test.

   I närheten av överkanten av trafikberäkningsverktyget beräknas de värden du anger och resultatet visas.

   ![](assets/ap_est_no.png)

   När du ändrar siffrorna ändras uppskattningen. Om du till exempel testar ett stort antal kombinationer och din konverteringsgrad och dina visningar är för låga, visar Traffic Estimator hur lång tid testet måste ta för att lyckas. Eller, om trafiken är låg, kan Traffic Estimator föreslå ett lägre antal erbjudandekombinationer så att du kan köra testet det önskade antalet dagar.

   Om du inte har tillräckligt med trafik kan du göra något av följande:

   * Överväg att använda Auto-Target i stället för Automated Personalization för att skapa upplevelser med flera olika erbjudandeändringar i en upplevelsevariant.
   * Minska antalet erbjudandekombinationer i er Automated Personalization-aktivitet.
   * Öka aktivitetens varaktighet.

   Justera siffrorna tills Traffic Estimator säger att du har tillräckligt med trafik och utforma sedan testet därefter.

   ![](assets/ap_est_yes.png)

   Om trafiken är tillräcklig visas en grön kontroll med ikonen Trafik. Om ikonen inte är tillräcklig visas en röd varningsetikett.
