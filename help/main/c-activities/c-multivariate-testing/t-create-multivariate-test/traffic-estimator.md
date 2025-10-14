---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: Lär dig hur du använder Traffic Estimator som talar om för dig om du har tillräckligt med trafik för din  [!DNL Adobe Target] [!UICONTROL Multivariate Test]-aktivitet för att lyckas.
title: Hur mycket trafik krävs för en [!UICONTROL Multivariate Test]-aktivitet (MVT)?
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Uppskatta den trafik som krävs för en lyckad [!UICONTROL Multivariate Test]-aktivitet

Eftersom ett multivariata test jämför flera upplevelser är det viktigt att veta hur mycket trafik som krävs för att få meningsfulla resultat. [!UICONTROL Traffic Estimator] använder statistik om din sida och antalet upplevelser som testas för att uppskatta mängden trafik och hur länge testet ska pågå.

[!UICONTROL Traffic Estimator] beräknar samplingsstorleken som krävs för att säkerställa följande:

* 95 % förtroende. Denna statistik innebär att risken att rapportera falskt positivt om det inte finns någon verklig ökning är 5 % (100 % - konfidensnivå).
* 80 % statistisk styrka. Denna siffra innebär att det är 80 % troligt att provningen identifierar en verklig lyft på 25 % eller mer.
* Minst 25 % tillförlitligt detekterbar lyft. [!DNL Target] beräknar mängden trafik som krävs för att ha en 80-procentig chans att upptäcka en verklig ökning på 25 % eller mer.

Testet använder Bonferroni-korrigeringen för att korrigera för flera jämförelser. Den här metoden är känd för att vara konservativ, vilket balanseras genom att en relativt stor, tillförlitlig lyft som kan detekteras används.

[!UICONTROL Traffic Estimator] ger även feedback som talar om för dig om du har tillräckligt med trafik för testet som ska lyckas.

1. Klicka på ikonen [!UICONTROL Experiences] ( [!UICONTROL Visual Experience Composer]Trafikberäkning[!UICONTROL Multivariate] ) i det övre vänstra hörnet på **[!UICONTROL Traffic]**-sidan ![&#x200B; i &#x200B;](/help/main/assets/icons/Gauge2.svg) i en [!UICONTROL Experiences] -aktivitet.

   [!UICONTROL Traffic Estimator] öppnas.

   ![Användargränssnittet för trafikberäkning](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   Du kan klicka på ikonen igen om du vill dölja [!UICONTROL Traffic Estimator].

   I närheten av överkanten av [!UICONTROL Traffic Estimator] beräknas de värden du angav och resultaten visas.

1. (Villkorligt) Ange typisk konverteringsgrad, uppskattade besökare per dag och testvaraktighet.

   * **[!UICONTROL Number of Content Combinations]**: Beräknas automatiskt baserat på antalet upplevelser som skapas som en del av din aktivitet efter eventuella undantag.
   * **[!UICONTROL Typical Conversion Rate]**: Konverteringsgraden uttrycks i procent utifrån din uppskattning eller tidigare data från analyssystemet.
   * **[!UICONTROL Estimated Visitors Per Day]**: Det här är antalet besökare som sannolikt kommer att visa den här sidan baserat på målinriktningskriterierna. Detta kan baseras på era analysdata.
   * **[!UICONTROL Test Duration]**: Det antal dagar som du vill att aktiviteten ska köras.

   [!UICONTROL Traffic Estimator] använder den här statistiken för att avgöra vilka justeringar som krävs för att köra ett lyckat test.

   När du ändrar siffrorna ändras uppskattningen. Om du till exempel testar många upplevelser och din konverteringsgrad och dina visningar är för låga, visar [!UICONTROL Traffic Estimator] hur länge testet måste köras för att lyckas. Om trafiken är låg kan [!UICONTROL Traffic Estimator] föreslå ett lägre antal upplevelser så att du kan köra testet på det önskade antalet dagar.

   Om du inte har tillräckligt med trafik kan du göra något eller båda av följande:

   * Minska antalet kombinationer av erbjudanden och antalet platser.
   * Öka testets varaktighet.

   Justera siffrorna tills [!UICONTROL Traffic Estimator] indikerar att du har tillräckligt med trafik och utforma sedan testet därefter.
