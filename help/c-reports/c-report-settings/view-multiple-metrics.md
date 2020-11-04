---
keywords: Target;reports;report settings;multiple metrics;metrics;shown metrics;hidden metrics
description: Välj flera mätvärden som ska visas i en rapport med Adobe Target.
title: Visa flera mätvärden i en rapport med Adobe Target
feature: report settings
uuid: f3ea7313-0f98-4b58-88aa-e2438c06e739
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---


# Visa flera mätvärden i en rapport{#view-multiple-metrics-in-a-report}

Du kan välja flera mätvärden att visa i en [!DNL Adobe Target] rapport.

Tänk på följande när du arbetar med flera mätvärden i rapporter:

* Det går endast att visa flera mätvärden för [A/B-tester](/help/c-activities/t-test-ab/test-ab.md), [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md)och [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) -aktiviteter (XT).
* Du kan inte lägga till fler än 20 mätvärden i en rapport för en aktivitet som använder [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Du kan lägga till så många mätvärden som du har i din aktivitet i rapporter för aktiviteter som *inte* använder A4T.
* Du kan inte använda alternativet [](/help/c-reports/downloading-data-in-csv-file.md) Hämta för att hämta rapporter till CSV om du har valt flera mätvärden. Du måste bara välja ett mått för att aktivera [!UICONTROL Download] alternativet.
* Du kan inte visa flera värden för aktiviteter som skapats före juli 2015- [!DNL Target] versionen (30 juli 2015).

**Så här väljer du flera mätvärden som ska visas i rapporten:**

1. Om du vill visa en rapport klickar du **[!UICONTROL Activities]** på önskad aktivitet i listan och sedan på **[!UICONTROL Reports]** fliken.
1. Klicka på den **[!UICONTROL Report Metric]** nedrullningsbara listan för att visa [!UICONTROL Shown Metrics] och [!UICONTROL Hidden Metrics] listorna.

   ![](assets/multiple_metrics.png)

   Du kan använda [!UICONTROL Search] rutan för att snabbt hitta tillgängliga mätvärden att lägga till i [!UICONTROL Shown Metrics] listan.

   Observera att du kan välja flera mätvärden både från rapportens [!UICONTROL Table View] - och [!UICONTROL Graph View] -lägen.

1. Håll muspekaren över önskade mätvärden i [!UICONTROL Hidden Metrics] listan och klicka sedan på dem **[!UICONTROL Select]** för att flytta dem till [!UICONTROL Shown Metrics] listan.

   eller

   Dra och släpp önskade mätvärden från [!UICONTROL Hidden Metrics] listan till [!UICONTROL Shown Metrics] listan.

   Det måste finnas minst ett mått i [!UICONTROL Shown Metrics] listan.

   Du kan ändra måtten genom att dra och släppa dem i önskad ordning i [!UICONTROL Shown Metrics] listan. Den valda ordningen återspeglas i [!UICONTROL Table View] och [!UICONTROL Graph View]. Om du vill ta bort ett mätresultat från [!UICONTROL Shown Metrics] listan håller du muspekaren över mätvärdet och klickar sedan på **X** -ikonen.

1. Klicka **[!UICONTROL Save]** när du är klar.
1. (Villkorligt) Håll muspekaren över kolumnrubriken för ett mätresultat när du visar rapporten i [!UICONTROL Table View]och visa en blå pil. Klicka på pilen för att expandera tabellen så att den visas [!UICONTROL Lift] och [!UICONTROL Confidence] för det måttet.

   ![](assets/multiple_metrics_table.png)

   Du kan bara expandera ett mått/en kolumn i taget. Klicka på pilen igen för att komprimera kolumnerna.

1. (Villkorligt) När du visar rapporten i diagramvyn kan du välja enskilda mått att visa i listrutan:

   ![](assets/multiple_metrics_graph.png)

