---
keywords: Mål;rapporter;rapportinställningar;flera mått;mått;visade mått;dolda mått
description: Lär dig hur du väljer flera mätvärden som ska visas i en rapport med Adobe Target.
title: Hur visar jag flera mätvärden i en rapport?
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# Visa flera mätvärden i en rapport

Du kan välja flera mätvärden att visa i en [!DNL Adobe Target]-rapport.

Tänk på följande när du arbetar med flera mätvärden i rapporter:

* Det går endast att visa flera mätvärden för aktiviteterna [A/B Test](/help/main/c-activities/t-test-ab/test-ab.md), [Automatisk fördelning](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Automatisk målning](/help/main/c-activities/auto-target/auto-target-to-optimize.md) och [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md) (XT).
* Du kan inte lägga till fler än 20 mätvärden i en rapport för en aktivitet som använder [Analytics för Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Du kan lägga till så många mätvärden som du har i din aktivitet i rapporter för aktiviteter som *inte* använder A4T.
* Du kan inte använda alternativet [Hämta](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) för att hämta rapporter till CSV om du har valt flera mätvärden. Du måste bara välja ett enskilt mått för att aktivera alternativet [!UICONTROL Download].
* Du kan inte visa flera mått för aktiviteter som skapats före [!DNL Target]-versionen från juli 2015 (30 juli 2015).

**Så här väljer du flera mätvärden som ska visas i rapporten:**

1. Om du vill visa en rapport klickar du på **[!UICONTROL Activities]**, på önskad aktivitet i listan och sedan på fliken **[!UICONTROL Reports]**.
1. Klicka på listrutan **[!UICONTROL Report Metric]** för att visa listorna [!UICONTROL Shown Metrics] och [!UICONTROL Hidden Metrics].

   Du kan använda rutan [!UICONTROL Search] för att snabbt hitta tillgängliga mätvärden som ska läggas till i listan [!UICONTROL Shown Metrics].

   Observera att du kan välja flera mätvärden både för [!UICONTROL Table View] och [!UICONTROL Graph View] i rapporten.

1. Håll muspekaren över önskade mätvärden i listan [!UICONTROL Hidden Metrics] och klicka sedan på **[!UICONTROL Select]** för att flytta dem till listan [!UICONTROL Shown Metrics].

   eller

   Dra och släpp önskade mätvärden från listan [!UICONTROL Hidden Metrics] till listan [!UICONTROL Shown Metrics].

   Det måste finnas minst ett mått i listan [!UICONTROL Shown Metrics].

   Du kan ordna om mätvärdena genom att dra och släppa dem i önskad ordning i listan [!UICONTROL Shown Metrics]. Den valda ordningen återspeglas i [!UICONTROL Table View] och [!UICONTROL Graph View]. Om du vill ta bort ett mått från listan [!UICONTROL Shown Metrics] håller du muspekaren över mätvärdet och klickar sedan på ikonen **X** .

1. Klicka på **[!UICONTROL Save]** när du är klar.
1. (Villkorligt) Håll muspekaren över kolumnrubriken för ett mätresultat när du visar rapporten i [!UICONTROL Table View] om du vill visa en blå pil. Klicka på pilen för att expandera tabellen så att [!UICONTROL Lift] och [!UICONTROL Confidence] för det måttet visas.

   Du kan bara expandera ett mått/en kolumn i taget. Klicka på pilen igen för att komprimera kolumnerna.

1. (Villkorligt) När du visar rapporten i [!UICONTROL Graph View] kan du välja enskilda mått som ska visas i listrutan.
