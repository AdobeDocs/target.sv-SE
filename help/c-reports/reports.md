---
keywords: reports;block ip address;block visitor from ip address;download reports;csv;reporting
description: Rapporterna innehåller information om hur dina aktiviteter fungerar
title: Rapporter
subtopic: Multivariate Test
topic: Standard
uuid: 8d20f4e7-72fd-4872-a21f-54ce16a2d2ab
translation-type: tm+mt
source-git-commit: 316c1157a4dff346f16862cfd7a04994c6a1bc7d
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 0%

---


# Rapporter{#reports}

Rapporterna innehåller information om förloppet och resultaten av dina aktiviteter som hjälper dig att fatta beslut baserat på dina data. Rapportdata kan hjälpa er att avgöra när ni ska avsluta ett test, visa er vilken upplevelse av erbjudandet som är vinnaren och ge er insikter eller inlärningar ni behöver för att avgöra nästa åtgärd.

>[!NOTE]
>
>Du kan blockera besökare från angivna IP-adresser från att räknas i rapporter. Kontakta Client Care för att konfigurera IP-filter. Den här filtreringen gäller inte när [Analytics for Target](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) används som rapportkälla.

## Rapporteringsinformation för specifika aktivitetstyper {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Utöver den allmänna rapporteringsinformationen i detta avsnitt och dess underavsnitt finns ytterligare information som är specifik för enskilda aktivitetstyper på annan plats i denna handbok:

| Typ av aktivitet | Detaljer |
|--- |--- |
| [A/B-test](/help/c-activities/t-test-ab/test-ab.md) | För att förstå lyft och förtroende samt de statistiska metoder som används i [!DNL Target], se [Planera ett A/B-test](/help/c-activities/t-test-ab/sample-size-determination.md). |
| [Tolka autofördelningsrapporter](/help/c-activities/automated-traffic-allocation/determine-winner.md) | Tolka resultaten av en automatisk fördelning av A/B-aktivitet genom att undersöka viktiga indikatorer, inklusive lyft och förtroende, i målgränssnittet. |
| [Automatiskt mål](/help/c-activities/auto-target-to-optimize.md) (AT) | Information om [!UICONTROL Summary] rapporten för AT-aktiviteter. Mer information finns i [Sammanfattningsrapport](/help/c-reports/auto-target-summary-report.md)för Automatiskt mål.<br>Information om de två [!UICONTROL Personalization Insights] rapporterna för AT- och AP-aktiviteter: [!UICONTROL Automated Segments] rapportera och [!UICONTROL Important Attributes] rapportera. Mer information finns i [Insikter om personalisering](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Automatiserad personalisering](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Information om de två [!UICONTROL Automated Personalization Summary] rapporterna för AP-aktiviteter: [!UICONTROL Activity Level] rapportera och [!UICONTROL Offer Level] rapportera. Mer information finns i [Automatiserade sammanfattningsrapporter](/help/c-reports/reports-ap.md)för personalisering.<br>Information om de två [!UICONTROL Personalization Insights] rapporterna för AT- och AP-aktiviteter: [!UICONTROL Automated Segments] rapportera och [!UICONTROL Important Attributes] rapportera. Mer information finns i [Insikter om personalisering](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Multivariata tester](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Information om de två rapporterna för MVT-aktiviteter: [!UICONTROL Experience Performance] rapportera och [!UICONTROL Location Contribution] rapportera. Mer information finns i [Experience Performance Report](/help/c-reports/experience-performance-report.md) (MVT) och [Location Contribution Report](/help/c-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics som rapportkälla för Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Information om hur du använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Target]. A4T ger dig tillgång till [!DNL Analytics] rapporter för dina [!DNL Target] aktiviteter. Mer information finns i [Analytics for Target (A4T) Reporting](/help/c-reports/analytics-for-target-a4t-reporting.md). |

## Visa en rapport {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Klicka på **[!UICONTROL Activities]** och sedan på önskad aktivitet i listan.

   Om du har många aktiviteter kan du filtrera listan genom att välja alternativ i listrutorna [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer][!UICONTROL Metrics Type]och [!UICONTROL Activity Source] .

   Du kan till exempel välja [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] från [!UICONTROL Type] listrutan och [!UICONTROL Live] från [!UICONTROL Status] listrutan för att endast visa A/B-tester och aktiviteter för Experience Targeting som är i ett aktivt läge.

   I följande bild visas den [!UICONTROL Type] nedrullningsbara listan med två valda typer: A/B Test and Experience Targeting. Observera att de tre typerna av A/B-tester (Manuellt, [Automatisk fördelning](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)och [Automatiskt mål](/help/c-activities/auto-target-to-optimize.md)) är markerade som standard. Du kan avmarkera en eller flera typer efter behov.

   ![Filtrera rapporter efter typ](/help/c-reports/assets/report_filters-new.png)

1. Klicka på **[!UICONTROL Reports]** fliken.

   Varje rapport innehåller en förklaring som hjälper dig att förstå rapporten.

   ![Rapportförklaring](/help/c-reports/assets/report_menu_bar-new.png)

   Förklaringen innehåller följande information:

   * Aktivitetsstatus, inklusive datumintervallet när aktiviteten kördes.
   * Den [projicerade vinnande upplevelsen](/help/c-activities/automated-traffic-allocation/determine-winner.md) (om den är tillgänglig).
   >[!NOTE]
   >
   >Upplevelseresultat visas efter att minst en deltagare har sett upplevelsen.

1. (Valfritt) [Konfigurera rapporten](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)efter behov.
1. (Valfritt) [Hämta rapporten i CSV-format](../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) för analys i Excel och andra verktyg.

   Följande alternativ är tillgängliga:

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. (Valfritt) Klicka på ikonerna **[!UICONTROL Table View]** och **[!UICONTROL Graph View]** ikonerna för att växla mellan olika rapporteringsformat.

   Beroende på vilken typ av rapport du har valt kan det finnas andra vyer och rapporter:

   | Typ av rapportering | Visa |
   | --- | --- |
   | Automatiskt mål | Klicka på **[!UICONTROL Automated Segments]** - eller **[!UICONTROL Important Attributes]** ikonerna.<ul><li>Rapporten om [automatiserade segment](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.</li><li>Rapporten [](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) Viktiga attribut visar hur olika attribut är viktigare (eller mindre) för hur modellen bestämmer sig för att personalisera i olika aktiviteter. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.</li></ul> |
   | Automatiserad personalisering (AP) | Förutom [Automated Personalization Summary Reports](/help/c-reports/reports-ap.md)kan du klicka på **[!UICONTROL Automated Segments]** - eller **[!UICONTROL Important Attributes]** ikonerna.<ul><li>Rapporten om [automatiserade segment](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.</li><li>Rapporten [](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) Viktiga attribut visar hur olika attribut är viktigare (eller mindre) för hur modellen bestämmer sig för att personalisera i olika aktiviteter. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.</li></ul> |
   | Multivariata tester (MVT) | Förutom rapporten [](/help/c-reports/experience-performance-report.md)Experience Performance kan du klicka på ikonen [Location Contribution](/help/c-reports/location-contribution-report.md) för att växla rapporten för att visa bidrag per plats. |
