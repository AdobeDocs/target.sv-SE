---
keywords: rapporter;blockera IP-adress;blockera besökare från IP-adress;hämtningsrapporter;csv;rapportering
description: Lär dig hur du använder rapportfunktionerna i Adobe [!DNL Target] för att undersöka hur dina aktiviteter fungerar. Fatta bättre beslut baserat på era data för att öka avkastningen.
title: Hur visar jag rapporter?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: a7a03cba466fbe7abfc8eb1f80292e1a2de7fe2d
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 0%

---

# Rapporter

Rapporterna innehåller information om förloppet och resultaten av dina [!DNL Adobe Target]-aktiviteter som hjälper dig att fatta beslut baserat på dina data. Rapportdata kan hjälpa er att avgöra när ni ska avsluta en aktivitet, visa er vilken upplevelse av erbjudandet som är vinnaren och ge er insikter eller inlärningar ni behöver för att avgöra nästa åtgärd.

## Visa en rapport {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Klicka på **[!UICONTROL Activities]** och sedan på önskad aktivitet i listan.

   Om du har många aktiviteter kan du filtrera listan genom att välja alternativ i listrutorna [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] och [!UICONTROL Activity Source].

   Du kan t.ex. välja [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] i listrutan [!UICONTROL Type] och [!UICONTROL Live] i listrutan [!UICONTROL Status] om du bara vill visa A/B-tester och aktiviteter för mål för upplevelse som är i ett aktivt läge.

   Följande bild visar listrutan [!UICONTROL Type] med två valda typer: [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting]. Observera att de tre typerna av A/B-tester (Manuellt, [Automatisk fördelning](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) och [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) är markerade som standard. Du kan avmarkera en eller flera typer efter behov.

   ![Filtrera rapporter efter typ](/help/main/c-reports/assets/report_filters-new.png)

1. Klicka på fliken **[!UICONTROL Reports]**.

   Varje rapport innehåller en förklaring som hjälper dig att förstå rapporten.

   ![Rapportförklaring](/help/main/c-reports/assets/report_menu_bar-new.png)

   Förklaringen innehåller följande information:

   * Aktivitetsstatus, inklusive datumintervallet när aktiviteten kördes.
   * Den [projicerade vinnande upplevelsen](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) (om tillgänglig).

   >[!NOTE]
   >
   >Upplevelseresultat visas efter att minst en deltagare har sett upplevelsen.

1. (Valfritt) [Konfigurera rapporten](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) efter behov.
1. (Valfritt) [Hämta rapporten i CSV-format](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) för analys i Excel och andra verktyg.

   Följande alternativ är tillgängliga:

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. (Valfritt) Klicka på ikonerna **[!UICONTROL Table View]** och **[!UICONTROL Graph View]** för att växla mellan rapporteringsformat.

   ![Ikoner för tabell- och diagramvyn](/help/main/c-reports/assets/table-and-graph-icons.png)

   Beroende på vilken typ av rapport du har valt kan det finnas andra vyer och rapporter:

   | Typ av rapportering | Visa |
   | --- | --- |
   | [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Klicka på ikonerna **[!UICONTROL Automated Segments]** eller **[!UICONTROL Important Attributes]**.<ul><li>Rapporten [Automatiska segment](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.</li><li>Rapporten [Viktiga attribut](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) visar hur olika attribut i olika aktiviteter är viktigare (eller mindre) för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.</li></ul> |
   | [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Förutom [sammanfattningsrapporterna för Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md) kan du klicka på ikonerna **[!UICONTROL Automated Segments]** eller **[!UICONTROL Important Attributes]** .<ul><li>Rapporten [Automatiska segment](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.</li><li>[Viktiga attribut-rapporten](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) visar hur olika attribut i olika aktiviteter är viktigare (eller mindre) för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.</li></ul> |
   | [Multivariata tester](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Förutom [Experience Performance-rapporten](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) kan du klicka på ikonen [Location Contribution](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) för att växla rapporten så att den visar bidrag per plats. |

## Ytterligare rapporteringsinformation för specifika aktivitetstyper {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Utöver den allmänna rapporteringsinformationen i detta avsnitt och dess underavsnitt finns ytterligare information som är specifik för enskilda aktivitetstyper på annan plats i denna handbok:

| Typ av aktivitet | Information |
|--- |--- |
| [A/B-test](/help/main/c-activities/t-test-ab/test-ab.md) | Mer information om lyft och förtroende samt om de statistiska metoder som används i [!DNL Target] finns i [Planera ett A/B-test](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Tolka automatiskt fördelade rapporter](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Tolka resultatet av en [!UICONTROL Auto-Allocate] A/B-aktivitet genom att undersöka viktiga indikatorer, inklusive lyft och förtroende, i [!DNL Target]-gränssnittet. |
| [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Information om rapporten [!UICONTROL Summary] för AT-aktiviteter. Mer information finns i [Sammanfattningsrapport för automatiskt mål](/help/main/c-reports/personalization-reports/auto-target-summary-report.md).<br>Information om de två [!UICONTROL Personalization Insights] rapporterna för AT- och AP-aktiviteter: [!UICONTROL Automated Segments]-rapport och [!UICONTROL Important Attributes]-rapport. Mer information finns i [Personalization Insights Reports](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Information om de två [!UICONTROL Automated Personalization Summary]-rapporterna för AP-aktiviteter: [!UICONTROL Activity Level]-rapport och [!UICONTROL Offer Level]-rapport. Mer information finns i [Sammanfattningsrapporter för Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).<br>Information om de två [!UICONTROL Personalization Insights] rapporterna för AT- och AP-aktiviteter: [!UICONTROL Automated Segments]-rapport och [!UICONTROL Important Attributes]-rapport. Mer information finns i [Personalization Insights Reports](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Multivariata tester](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Information om de två rapporterna för MVT-aktiviteter: [!UICONTROL Experience Performance]-rapport och [!UICONTROL Location Contribution]-rapport. Mer information finns i [Experience Performance Report](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) och [Location Contribution Report](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics som Reporting Source för Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Information om hur du använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Target]. A4T ger dig åtkomst till [!DNL Analytics] rapporter för dina [!DNL Target]-aktiviteter. Mer information finns i [Analys för målrapportering (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |
| [[!DNL Target] rapporterar i [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) | Information om integrationen mellan [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} och [!DNL Target] som ger kraftfull analys och tidsbesparande verktyg för optimeringsprogrammet. |

## Blockera rapporteringsdata från angivna IP-adresser

Du kan blockera besökare från angivna IP-adresser från att räknas i rapporter. Detta är till exempel användbart om du vill blockera rapporteringsdata från era interna besökare.

[Kontakta kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) om du vill konfigurera IP-filter. Den här filtreringen gäller inte när [Analytics för Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) används som rapportkälla.
