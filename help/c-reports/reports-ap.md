---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: Specialiserade rapporter är tillgängliga för användare av Automated Personalization-aktiviteter i Adobe Target.
title: Automated Personalization Sammanfattningsrapporter
feature: reports
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Automated Personalization Sammanfattningsrapporter{#automated-personalization-summary-reports}

Specialiserade rapporter är tillgängliga för användare av aktiviteter [!UICONTROL Automated Personalization] i [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Automated Personalization] finns som en del av [!DNL Target Premium] lösningen. Det ingår inte [!DNL Target Standard] utan en [Target Premium-licens](/help/c-intro/intro.md#premium).

1. Klicka **[!UICONTROL Activities]** på önskad [!UICONTROL Automated Personalization] aktivitet i listan och klicka sedan på **[!UICONTROL Reports]** fliken.

   Om du har många aktiviteter kan du filtrera listan genom att välja [!UICONTROL Automated Personalization] i [!UICONTROL Type] listrutan.

1. (Valfritt) Klicka på [!UICONTROL Download] ikonen för att hämta sammanfattningsvyn (till exempel för att jämföra trafik med styrning och mål) uppdelat efter alla tillgängliga framgångsmått.

[!UICONTROL Automated Personalization] innehåller följande rapporter:

## Aktivitetsnivårapport {#section_6F72FC5C790B4492B3DCECBFFA971337}

I rapporten jämförs den sammanlagda prestandan för att använda en [!UICONTROL Activity Level] [!UICONTROL Automated Personalization] algoritm med slumpmässigt hanterat innehåll (kontroll).

![Aktivitetsnivårapport](/help/c-reports/assets/box_plot_ap.png)

Standardreglerna för resultattolkning för A/B-tester gäller fortfarande, inklusive lyft, förtroende, trender, varaktighet och så vidare. Mer information om hur du tolkar resultat finns i [Om konverteringsgraden](/help/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844).

## Erbjudandenivårapport {#section_CAA6409879E349C6906E2BE8156D87A1}

I rapporten [!UICONTROL Offer Level] för Random Forest Experience jämförs resultatet för varje algoritmtillämpat erbjudande med samma slumpmässiga erbjudande (Control). Erbjudandena bör därför inte jämföras med varandra i denna vy.

Klicka på upplevelsealgoritmen (Slumpmässig skog eller kontroll) för att visa [!UICONTROL Offer Level] rapporten.

![](assets/ap_OfferLevelRpt.png)

Erbjudandena kan visas i rapportgrupper och dessa kan komprimeras och utökas. Välj [!UICONTROL Reporting Group] i listrutan om du vill visa sammanställd information efter rapporteringsgrupper, i stället för efter erbjudanden.

>[!NOTE]
>
>Klockikonen indikerar att algoritmmodellen fortfarande byggs. Kryssmarkeringsikonen anger att basalgoritmen har upprättats.

## Automatiska segment

Klicka på [!UICONTROL Automated Segments] ikonen. Den här rapporten visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.

![Ikon för automatiserade segment](/help/c-reports/assets/icon-automated-sements-ap.png)

Mer information finns i [rapporten](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)Automatiska segment.

## Viktiga attribut

Klicka på [!UICONTROL Important Attributes] ikonen. Den här rapporten visar hur olika attribut är viktigare (eller mindre) i olika aktiviteter för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.

![Ikon för viktiga attribut](/help/c-reports/assets/icon-important-attributes-ap.png)

Mer information finns i [rapporten](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)Viktiga attribut.