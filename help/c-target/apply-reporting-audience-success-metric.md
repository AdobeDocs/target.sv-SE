---
keywords: Targeting;audience;reporting;success metric
description: Välj ett framgångsmått i Adobe Target som kvalificerar användaren för den rapporterande målgruppen.
title: Använd en rapportpublik för att mäta framgångar i Adobe Target
feature: success metrics
uuid: cc485785-84cc-4a60-acf8-788b842b243f
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---


# Tillämpa en rapportmålgrupp på ett framgångsmått{#apply-a-reporting-audience-to-a-success-metric}

Välj ett framgångsmått som kvalificerar användaren för den rapporterande målgruppen.

I [!UICONTROL Applied At] listrutan kan du för alla aktiviteter tillämpa en målgrupp på ett framgångsmått så att du kan visa rapportnummer när mätvärdena har nåtts och för efterföljande åtgärder.

![](assets/success_metric.png)

Anta till exempel att du har skapat en aktivitet för alla besökare som kommer in från din hemsida och når konverteringssidan, men du vill också detaljgranska mer för besökare som har lagt till mer än 50 USD i kundvagnen innan du konverterar.

Listrutan Används kan innehålla tre kategorier: besökare, endast besökare som når ett visst steg i aktiviteten eller endast besökare som når konverteringen. Eller, för att uttrycka det på ett annat sätt, kan du ange att en besökare måste ha nått en mbox på startsidan för aktiviteten, en mbox som definierar en punkt i mitten av aktiviteten eller konverteringsrutan i slutet av aktiviteten.

[Resultatstatistik](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) är bara tillgängliga om du har konfigurerat dem för din aktivitet. Om du inte har definierat framgångsmått visas bara två alternativ i listrutan: Kampanjinträde och konvertering.

Tänk på följande information när du använder en rapportpublik för ett framgångsmått:

* För åtgärder före åtgärden med det tillämpade framgångsmåttet tillämpar Target inte en segmenterad målgrupp.
* För åtgärder efter det använda framgångsmåttet använder Target en segmenterad målgrupp.

Om du vill visa segmenteringen i rapporter väljer du önskad målgrupp i listrutan Målgrupp i aktivitetens rapport.

![](assets/reporting_audience_dropdown.png)

