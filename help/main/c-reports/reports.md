---
keywords: rapporter;blockera IP-adress;blockera besökare från IP-adress;hämtningsrapporter;csv;rapportering
description: Lär dig hur du använder rapportfunktionerna i Adobe [!DNL Target] för att undersöka hur dina aktiviteter fungerar. Fatta bättre beslut baserat på era data för att öka avkastningen.
title: Hur visar jag rapporter?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 0%

---

# Rapporter

Rapporterna innehåller information om förloppet och resultaten av dina [!DNL Adobe Target] aktiviteter som hjälper er att fatta beslut baserat på era data. Rapportdata kan hjälpa er att avgöra när ni ska avsluta en aktivitet, visa er vilken upplevelse av erbjudandet som är vinnaren och ge er insikter eller inlärningar ni behöver för att avgöra nästa åtgärd.

## Visa en rapport {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Klicka **[!UICONTROL Activities]** klickar du sedan på önskad aktivitet i listan.

   Om du har många aktiviteter kan du filtrera listan genom att välja alternativ på menyn [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type]och [!UICONTROL Activity Source] nedrullningsbara listor.

   Du kan till exempel välja [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] från [!UICONTROL Type] nedrullningsbar lista och [!UICONTROL Live] från [!UICONTROL Status] nedrullningsbar lista om du bara vill visa A/B-tester och aktiviteter för Experience Targeting som är i ett aktivt läge.

   Följande bild visar [!UICONTROL Type] nedrullningsbar lista med två valda typer: [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting]. Observera att de tre typerna av A/B-tester (manuella, [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)och [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) är markerat som standard. Du kan avmarkera en eller flera typer efter behov.

   ![Filtrera rapporter efter typ](/help/main/c-reports/assets/report_filters-new.png)

1. Klicka på **[!UICONTROL Reports]** -fliken.

   Varje rapport innehåller en förklaring som hjälper dig att förstå rapporten.

   ![Rapportförklaring](/help/main/c-reports/assets/report_menu_bar-new.png)

   Förklaringen innehåller följande information:

   * Aktivitetsstatus, inklusive datumintervallet när aktiviteten kördes.
   * The [projicerad vinnande upplevelse](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) (om tillgängligt).

   >[!NOTE]
   >
   >Upplevelseresultat visas efter att minst en deltagare har sett upplevelsen.

1. (Valfritt) [Konfigurera rapporten](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA), efter behov.
1. (Valfritt) [Ladda ned rapporten i CSV-format](/help/main/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) för analys i Excel och andra verktyg.

   Följande alternativ är tillgängliga:

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. (Valfritt) Klicka på **[!UICONTROL Table View]** och **[!UICONTROL Graph View]** ikoner för att växla mellan olika rapporteringsformat.

   ![Ikoner för tabell- och diagramvyn](/help/main/c-reports/assets/table-and-graph-icons.png)

   Beroende på vilken typ av rapport du har valt kan det finnas andra vyer och rapporter:

   | Typ av rapportering | Visa |
   | --- | --- |
   | [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Klicka på **[!UICONTROL Automated Segments]** eller **[!UICONTROL Important Attributes]** ikoner.<ul><li>The [Rapport över automatiserade segment](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.</li><li>The [Viktiga attributrapporter](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) visar hur olika attribut i olika aktiviteter är viktigare (eller mindre) för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.</li></ul> |
   | [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Förutom [Automated Personalization Sammanfattningsrapporter](/help/main/c-reports/reports-ap.md)kan du klicka på **[!UICONTROL Automated Segments]** eller **[!UICONTROL Important Attributes]** ikoner.<ul><li>The [Rapport över automatiserade segment](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.</li><li>The [Viktiga attributrapporter](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) visar hur olika attribut är viktigare (eller mindre) för hur modellen bestämmer sig för att personalisera i olika aktiviteter. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.</li></ul> |
   | [Multivariata tester](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Förutom [Experience Performance-rapport](/help/main/c-reports/experience-performance-report.md)kan du klicka på [Platsbidrag](/help/main/c-reports/location-contribution-report.md) om du vill växla rapporten för att visa bidrag per plats. |

## Ytterligare rapporteringsinformation för specifika aktivitetstyper {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Utöver den allmänna rapporteringsinformationen i detta avsnitt och dess underavsnitt finns ytterligare information som är specifik för enskilda aktivitetstyper på annan plats i denna handbok:

| Typ av aktivitet | Detaljer |
|--- |--- |
| [A/B-test](/help/main/c-activities/t-test-ab/test-ab.md) | Att förstå lyft och förtroende samt de statistiska metoder som används för [!DNL Target], se [Planera ett A/B-test](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Tolka autofördelningsrapporter](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Tolka resultatet av en [!UICONTROL Auto-Allocate] A/B-verksamhet genom att undersöka viktiga indikatorer, bland annat lyft och förtroende för [!DNL Target] Gränssnitt. |
| [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Information om [!UICONTROL Summary] Rapportera om AT-verksamhet. Mer information finns i [Sammanfattningsrapport för automatiskt mål](/help/main/c-reports/auto-target-summary-report.md).<br>Information om de två [!UICONTROL Personalization Insights] Rapporter om AT- och AP-verksamhet: [!UICONTROL Automated Segments] rapportera och [!UICONTROL Important Attributes] rapport. Mer information finns i [Insikter om personalisering - rapporter](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Information om de två [!UICONTROL Automated Personalization Summary] rapporter för AP-aktiviteter: [!UICONTROL Activity Level] rapportera och [!UICONTROL Offer Level] rapport. Mer information finns i [Automated Personalization - sammanfattningsrapporter](/help/main/c-reports/reports-ap.md).<br>Information om de två [!UICONTROL Personalization Insights] Rapporter om AT- och AP-verksamhet: [!UICONTROL Automated Segments] rapportera och [!UICONTROL Important Attributes] rapport. Mer information finns i [Insikter om personalisering - rapporter](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Multivariata tester](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Information om de två rapporterna för MVT-aktiviteter: [!UICONTROL Experience Performance] rapportera och [!UICONTROL Location Contribution] rapport. Mer information finns i [Rapport om prestanda för upplevelser](/help/main/c-reports/experience-performance-report.md) (MVT) och  [Platsbidragsrapport](/help/main/c-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics som rapportkälla för Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Information om hur du använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Target]. A4T ger dig tillgång till [!DNL Analytics] rapporter för [!DNL Target] verksamhet. Mer information finns i [Analyser för målrapportering (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |

## Blockera rapporteringsdata från angivna IP-adresser

Du kan blockera besökare från angivna IP-adresser från att räknas i rapporter. Detta är till exempel användbart om du vill blockera rapporteringsdata från era interna besökare.

[Kontakta kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) för att konfigurera IP-filter. Den här filtreringen gäller inte när du använder [Analyser för Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) som rapportkälla.
