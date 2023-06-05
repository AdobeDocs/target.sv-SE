---
keywords: Målgrupp;målgrupp;rapportering;framgångsmått
description: Lär dig hur du väljer ett framgångsmått i [!DNL Adobe Target] som kvalificerar användaren för den rapporterande målgruppen.
title: Kan jag använda en rapportmålgrupp i ett framgångsmått?
feature: Success Metrics
exl-id: 6b2f6669-6178-4da4-850d-8b1ce796a50d
source-git-commit: bcbb6dec9d6add07c109b07bf125c1356ad2a8b9
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

---

# Tillämpa en rapportmålgrupp på ett framgångsmått

Välj ett framgångsmått som kvalificerar användaren för den rapporterande målgruppen i [!DNL Adobe Target].

För alla verksamheter gäller att [!UICONTROL Applied At] Med den nedrullningsbara listan kan du ange en målgrupp för ett framgångsmått så att du kan visa rapportnummer när mätvärdena har nåtts och för efterföljande åtgärder.

![success_metric, bild](assets/success_metric.png)

Anta till exempel att du har skapat en aktivitet för alla besökare som kommer in från din hemsida och når konverteringssidan, men du vill också detaljgranska mer för besökare som har lagt till mer än 50 USD i kundvagnen innan du konverterar.

The [!UICONTROL Applied At] nedrullningsbar lista kan innehålla tre kategorier:

* Alla besökare till aktiviteten
* Endast besökare som når ett visst steg i aktiviteten
* Endast besökare som når konvertering

Eller, för att uttrycka det på ett annat sätt, kan du ange att en besökare måste ha nått en mbox på startsidan för aktiviteten, en mbox som definierar en punkt i mitten av aktiviteten eller konverteringsrutan i slutet av aktiviteten.

>[!NOTE]
>
>[Framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) är bara tillgängliga om du har konfigurerat dem för din aktivitet. Om du inte har definierat framgångsmått visas bara två alternativ i listrutan: [!UICONTROL Campaign Entry] och [!UICONTROL Conversion].


## Överväganden

Tänk på följande information när du använder en rapportpublik för ett framgångsmått:

* Endast framgångsmått från och med den som målgruppen tillämpas på visar rapportdata som segmenterats av målgruppen
* Framgångsmått som föregår de som målgruppen tillämpas på segmenteras inte av målgruppen och visar alla besöksdata
* Måtten betraktas utifrån deras ordning i aktivitetsdefinitionen, med [!UICONTROL Primary Goal] som den sista.

## Visa segmentering i rapportering

Om du vill visa segmenteringen i rapporter väljer du önskad målgrupp på menyn [!UICONTROL Audience] nedrullningsbar lista i aktivitetens rapport.

![reporting_publik_dropdown image](assets/reporting_audience_dropdown.png)

## Exempel

Överväg en aktivitet som har Success Metric1, Success Metric2, Success Metric3 och det primära målet.

Anta att du har rapporterat Audience1 inställt på Entry och rapporterat Audience2 inställt på Success Metric2. Målgrupperna kommer att filtrera rapporteringsdata enligt följande:

|  | Besökare | Resultatmått1 | Resultatmått 2 | Resultatmått3 | Primärt mål |
| --- | --- | --- | --- | --- | --- |
| Audience1 | Används | Används | Används | Används | Används |
| Audience2 | Ej tillämpat | Ej tillämpat | Används | Används | Används |
