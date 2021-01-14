---
keywords: reports;block ip address;block visitor from ip address;download reports;csv;reporting
description: Rapporterna innehåller information om hur Adobe Target fungerar
title: Rapporter
feature: Reports
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 0%

---


# Rapporter{#reports}

Rapporterna innehåller information om förloppet och resultaten av dina [!DNL Adobe Target]-aktiviteter som hjälper dig att fatta beslut baserat på dina data. Rapportdata kan hjälpa er att avgöra när ni ska avsluta en aktivitet, visa er vilken upplevelse av erbjudandet som är vinnaren och ge er insikter eller inlärningar ni behöver för att avgöra nästa åtgärd.

## Visa en rapport {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Klicka på **[!UICONTROL Activities]** och sedan på önskad aktivitet i listan.

   Om du har många aktiviteter kan du filtrera listan genom att välja alternativ i listrutorna [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] och [!UICONTROL Activity Source].

   Du kan t.ex. välja [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] i listrutan [!UICONTROL Type] och [!UICONTROL Live] i listrutan [!UICONTROL Status] om du bara vill visa A/B-tester och aktiviteter för Experience Targeting som är i ett aktivt läge.

   Följande bild visar listrutan [!UICONTROL Type] med två valda typer: [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting]. Observera att de tre typerna av A/B-tester (Manuellt, [Automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) och [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md)) är markerade som standard. Du kan avmarkera en eller flera typer efter behov.

   ![Filtrera rapporter efter typ](/help/c-reports/assets/report_filters-new.png)

1. Klicka på fliken **[!UICONTROL Reports]**.

   Varje rapport innehåller en förklaring som hjälper dig att förstå rapporten.

   ![Rapportförklaring](/help/c-reports/assets/report_menu_bar-new.png)

   Förklaringen innehåller följande information:

   * Aktivitetsstatus, inklusive datumintervallet när aktiviteten kördes.
   * [Prognostiserad vinnande upplevelse](/help/c-activities/automated-traffic-allocation/determine-winner.md) (om tillgänglig).

   >[!NOTE]
   >
   >Upplevelseresultat visas efter att minst en deltagare har sett upplevelsen.

1. (Valfritt) [Konfigurera rapporten](/help/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) efter behov.
1. (Valfritt) [Hämta rapporten i CSV-format](/help/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) för analys i Excel och andra verktyg.

   Följande alternativ är tillgängliga:

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. (Valfritt) Klicka på ikonerna **[!UICONTROL Table View]** och **[!UICONTROL Graph View]** för att växla mellan rapporteringsformaten.

   ![Ikoner för tabell- och diagramvyn](/help/c-reports/assets/table-and-graph-icons.png)

   Beroende på vilken typ av rapport du har valt kan det finnas andra vyer och rapporter:

   | Typ av rapportering | Visa |
   | --- | --- |
   | [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md) | Klicka på ikonerna **[!UICONTROL Automated Segments]** eller **[!UICONTROL Important Attributes]**.<ul><li>[Rapporten om automatiserade segment](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.</li><li>[Viktiga attributrapporter](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) visar hur olika attribut i olika aktiviteter är viktigare (eller mindre) för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.</li></ul> |
   | [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Förutom [Sammanfattningsrapporter för Automated Personalization](/help/c-reports/reports-ap.md) kan du klicka på ikonerna **[!UICONTROL Automated Segments]** eller **[!UICONTROL Important Attributes]**.<ul><li>[Rapporten om automatiserade segment](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.</li><li>I [rapporten Viktiga attribut](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) visas hur olika attribut i olika aktiviteter är viktigare (eller mindre) för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.</li></ul> |
   | [Multivariata tester](/help/c-activities/c-multivariate-testing/multivariate-testing.md)  (MVT) | Förutom [Experience Performance-rapporten](/help/c-reports/experience-performance-report.md) kan du klicka på ikonen [Location Contribution](/help/c-reports/location-contribution-report.md) för att växla rapporten så att den visar bidrag per plats. |

## Ytterligare rapporteringsinformation för specifika aktivitetstyper {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Utöver den allmänna rapporteringsinformationen i detta avsnitt och dess underavsnitt finns ytterligare information som är specifik för enskilda aktivitetstyper på annan plats i denna handbok:

| Typ av aktivitet | Detaljer |
|--- |--- |
| [A/B-test](/help/c-activities/t-test-ab/test-ab.md) | För att förstå lyft och förtroende samt de statistiska metoder som används i [!DNL Target], se [Planera ett A/B-test](/help/c-activities/t-test-ab/sample-size-determination.md). |
| [Tolka autofördelningsrapporter](/help/c-activities/automated-traffic-allocation/determine-winner.md) | Tolka resultaten av en [!UICONTROL Auto-Allocate] A/B-aktivitet genom att undersöka viktiga indikatorer, inklusive lyft och förtroende, i [!DNL Target]-gränssnittet. |
| [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md)  (AT) | Information om [!UICONTROL Summary]-rapporten för AT-aktiviteter. Mer information finns i [Sammanfattningsrapport för Automatiskt mål](/help/c-reports/auto-target-summary-report.md).<br>Information om de två  [!UICONTROL Personalization Insights] rapporterna för AT- och AP-aktiviteter:  [!UICONTROL Automated Segments] rapportera och  [!UICONTROL Important Attributes] rapportera. Mer information finns i [Insights Reports](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md) för personalisering. |
| [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Information om de två [!UICONTROL Automated Personalization Summary]-rapporterna för AP-aktiviteter: [!UICONTROL Activity Level]-rapport och [!UICONTROL Offer Level]-rapport. Mer information finns i [Sammanfattningsrapporter för Automated Personalization](/help/c-reports/reports-ap.md).<br>Information om de två  [!UICONTROL Personalization Insights] rapporterna för AT- och AP-aktiviteter:  [!UICONTROL Automated Segments] rapportera och  [!UICONTROL Important Attributes] rapportera. Mer information finns i [Insights Reports](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md) för personalisering. |
| [Multivariata tester](/help/c-activities/c-multivariate-testing/multivariate-testing.md)  (MVT) | Information om de två rapporterna för MVT-aktiviteter: [!UICONTROL Experience Performance]-rapport och [!UICONTROL Location Contribution]-rapport. Mer information finns i [Experience Performance Report](/help/c-reports/experience-performance-report.md) (MVT) och [Location Contribution Report](/help/c-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics som rapportkälla för Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Information om hur du använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Target]. A4T ger dig åtkomst till [!DNL Analytics]-rapporter för dina [!DNL Target]-aktiviteter. Mer information finns i [Analytics for Target (A4T) Reporting](/help/c-reports/analytics-for-target-a4t-reporting.md). |

## Blockera rapporteringsdata från angivna IP-adresser

Du kan blockera besökare från angivna IP-adresser från att räknas i rapporter. Detta är till exempel användbart om du vill blockera rapporteringsdata från era interna besökare.

[Kontakta Client ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) Carson för att konfigurera IP-filter. Den här filtreringen gäller inte när du använder [Analytics för Target](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) som rapportkälla.
