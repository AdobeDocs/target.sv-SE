---
keywords: Mål;rapporter;rapportinställningar;flera mått;mått;visade mått;dolda mått
description: Välj flera mätvärden som ska visas i en rapport med Adobe Target.
title: Visa flera mått i en rapport
feature: Reports
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---


# Visa flera mätvärden i en rapport{#view-multiple-metrics-in-a-report}

Du kan välja flera mätvärden att visa i en [!DNL Adobe Target]-rapport.

Tänk på följande när du arbetar med flera mätvärden i rapporter:

* Det går endast att visa flera mätvärden för [A/B-tester](/help/c-activities/t-test-ab/test-ab.md), [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Automatisk målning](/help/c-activities/auto-target/auto-target-to-optimize.md) och [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) (XT)-aktiviteter.
* Du kan inte lägga till fler än 20 mätvärden i en rapport för en aktivitet som använder [Analytics för Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Du kan lägga till så många mätvärden som du har i din aktivitet i rapporter för aktiviteter som *inte* använder A4T.
* Du kan inte använda alternativet [Hämta](/help/c-reports/downloading-data-in-csv-file.md) för att hämta rapporter till CSV om du har valt flera mätvärden. Du måste bara välja ett enskilt mått för att aktivera alternativet [!UICONTROL Download].
* Du kan inte visa flera mått för aktiviteter som skapats före versionen från juli 2015 [!DNL Target] (30 juli 2015).

**Så här väljer du flera mätvärden som ska visas i rapporten:**

1. Om du vill visa en rapport klickar du på **[!UICONTROL Activities]**, på önskad aktivitet i listan och sedan på fliken **[!UICONTROL Reports]**.
1. Klicka på listrutan **[!UICONTROL Report Metric]** för att visa listorna [!UICONTROL Shown Metrics] och [!UICONTROL Hidden Metrics].

   ![](assets/multiple_metrics.png)

   Du kan använda rutan [!UICONTROL Search] för att snabbt hitta tillgängliga mätvärden som ska läggas till i [!UICONTROL Shown Metrics]-listan.

   Observera att du kan välja flera mätvärden både i rapportens [!UICONTROL Table View]- och [!UICONTROL Graph View]-lägen.

1. Håll muspekaren över de önskade mätvärdena i [!UICONTROL Hidden Metrics]-listan och klicka sedan på **[!UICONTROL Select]** för att flytta dem till [!UICONTROL Shown Metrics]-listan.

   eller

   Dra och släpp önskade mätvärden från [!UICONTROL Hidden Metrics]-listan till [!UICONTROL Shown Metrics]-listan.

   Det måste finnas minst ett mått i [!UICONTROL Shown Metrics]-listan.

   Du kan ordna om mätvärdena genom att dra och släppa dem i önskad ordning i [!UICONTROL Shown Metrics]-listan. Den valda ordningen återspeglas i [!UICONTROL Table View] och [!UICONTROL Graph View]. Om du vill ta bort ett mått från [!UICONTROL Shown Metrics]-listan håller du muspekaren över mätvärdet och klickar sedan på ikonen **X**.

1. Klicka på **[!UICONTROL Save]** när du är klar.
1. (Villkorligt) Håll muspekaren över kolumnrubriken för ett mätresultat om du vill visa en blå pil när du visar rapporten i [!UICONTROL Table View]. Klicka på pilen för att utöka tabellen så att den visar [!UICONTROL Lift] och [!UICONTROL Confidence] för det måttet.

   ![](assets/multiple_metrics_table.png)

   Du kan bara expandera ett mått/en kolumn i taget. Klicka på pilen igen för att komprimera kolumnerna.

1. (Villkorligt) När du visar rapporten i diagramvyn kan du välja enskilda mått att visa i listrutan:

   ![](assets/multiple_metrics_graph.png)

