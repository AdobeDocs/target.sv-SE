---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: Lär dig hur du använder Traffic Estimator som talar om för dig om du har tillräckligt med trafik för Adobe [!DNL Target] Multivariera testaktivitet för att lyckas.
title: Hur mycket trafik behövs för en multivariat testverksamhet?
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Uppskatta den trafik som krävs för ett lyckat test

Eftersom ett multivariata test jämför flera upplevelser är det viktigt att veta hur mycket trafik som krävs för att få meningsfulla resultat. Trafikuppskattningen använder statistik om er sida och antalet upplevelser som testas för att uppskatta mängden trafik och hur länge testet ska pågå.

Trafikberäkningsverktyget beräknar den provstorlek som krävs för att säkerställa följande:

* 95 % säkerhet

   Detta innebär att risken att rapportera falskt positivt om det inte finns något verkligt lyft är 5 % (100 % - konfidensnivå).
* 80 % statistisk styrka

   Detta innebär att det är 80 % troligt att testet identifierar en verklig lyft på 25 % eller mer.
* Minst 25 % tillförlitligt detekterbar lyft

   Target beräknar mängden trafik som krävs för att ha en 80-procentig chans att upptäcka en verklig ökning på 25 % eller mer.

Testet använder Bonferroni-korrigeringen för att korrigera för flera jämförelser. Den här metoden är känd för att vara konservativ, vilket balanseras genom att en relativt stor, tillförlitlig lyft som kan detekteras används.

Trafikberäkningsverktyget ger även feedback som talar om för dig om du har tillräckligt med trafik för det test du har utformat för att lyckas.

1. I Experience Composer klickar du på **[!UICONTROL Traffic]** ikon.

   Trafikberäkningsverktyget öppnas. Du kan klicka på **[!UICONTROL Traffic]** om du vill dölja trafikberäkningsverktyget igen.

   ![](assets/estimatorempty.png)

1. Ange typisk konverteringsgrad, uppskattade besökare per dag och testvaraktighet.

   * [!UICONTROL Number of Content Combinations]: Beräknas automatiskt baserat på antalet upplevelser som skapas som en del av din aktivitet efter eventuella undantag.
   * [!UICONTROL Typical Conversion Rate]: Konverteringsgraden uttrycks i procent utifrån din uppskattning eller tidigare data från analyssystemet
   * [!UICONTROL Estimated Visitors Per Day]: Det här är antalet besökare som sannolikt kommer att visa den här sidan baserat på målinriktningskriterierna. Detta kan baseras på era analysdata.
   * [!UICONTROL Test Duration]: Antalet dagar som du vill att aktiviteten ska köras.

   Trafikuppskattningen använder dessa statistik för att avgöra vilka justeringar som krävs för att köra ett lyckat test.

   I närheten av överkanten av trafikberäkningsverktyget beräknas de värden du anger och resultatet visas.

   ![](assets/estimatorinsufficient.png)

   När du ändrar siffrorna ändras uppskattningen. Om du till exempel testar ett stort antal upplevelser och din konverteringsgrad och dina visningar är för låga, visar Traffic Estimator hur länge testet måste köras för att lyckas. Eller, om trafiken är låg, kan Traffic Estimator föreslå ett lägre antal upplevelser så att du kan köra testet det önskade antalet dagar.

   Om du inte har tillräckligt med trafik kan du göra något eller båda av följande:

   * Minska antalet kombinationer av erbjudanden och antalet platser.
   * Öka testets varaktighet.

   Justera siffrorna tills Traffic Estimator säger att du har tillräckligt med trafik och utforma sedan testet därefter.

   ![](assets/estimatorok.png)
