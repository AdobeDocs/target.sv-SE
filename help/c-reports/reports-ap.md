---
keywords: Målgruppsanpassning;AP-rapporter;automatiserade personaliseringsrapporter;aktivitetsnivårapport;erbjudandenivårapport;erbjudandedetaljrapport;faq
description: Hur använder jag Automated Personalization Summary-rapporterna?
title: Automated Personalization - sammanfattningsrapporter
feature: Reports
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMAutomatiserade sammanfattningsrapporter för personalisering

Specialiserade sammanfattningsrapporter är tillgängliga för användare av [!UICONTROL Automated Personalization]-aktiviteter i [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Automated Personalization] finns som en del av  [!DNL Target Premium] lösningen. Den ingår inte i [!DNL Target Standard] utan [Target Premium-licens](/help/c-intro/intro.md#premium).

1. Klicka på **[!UICONTROL Activities]**, klicka på önskad [!UICONTROL Automated Personalization]-aktivitet i listan och klicka sedan på fliken **[!UICONTROL Reports]**.

   Om du har många aktiviteter kan du filtrera listan genom att välja [!UICONTROL Automated Personalization] i listrutan [!UICONTROL Type].

1. (Valfritt) Klicka på ikonen **[!UICONTROL Download]** för att hämta sammanfattningsvyn (till exempel för att jämföra trafik med styrning och mål) uppdelad efter alla tillgängliga framgångsmått.

[!UICONTROL Automated Personalization] innehåller följande rapporter:

* Aktivitetsnivå
* Erbjudandenivå
* Automatiska segment
* Viktiga attribut

## Aktivitetsnivårapport {#section_6F72FC5C790B4492B3DCECBFFA971337}

I [!UICONTROL Activity Level]-rapporten jämförs den sammanlagda prestandan för att använda en [!UICONTROL Automated Personalization]-algoritm med slumpmässigt hanterat innehåll (kontroll).

![Aktivitetsnivårapport](/help/c-reports/assets/box_plot_ap.png)

Standardreglerna för resultattolkning för A/B-tester gäller fortfarande, inklusive lyft, förtroende, trender, varaktighet och så vidare. Mer information om hur du tolkar resultat finns i [Om konverteringsgraden](/help/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844).

## Erbjudandenivårapport {#section_CAA6409879E349C6906E2BE8156D87A1}

I [!UICONTROL Offer Level]-rapporten för funktionen Slumpmässig skog jämförs resultatet för varje algoritmtillämpat erbjudande med samma slumpmässiga erbjudande (Control). Erbjudandena bör därför inte jämföras med varandra i denna vy.

Klicka på upplevelsealgoritmen (Slumpmässig skog eller kontroll) för att visa [!UICONTROL Offer Level]-rapporten.

![](assets/ap_OfferLevelRpt.png)

Erbjudandena kan visas i rapportgrupper och dessa kan komprimeras och utökas. Välj [!UICONTROL Reporting Group] i listrutan om du vill visa sammanställd information efter rapporteringsgrupper, i stället för efter erbjudanden.

>[!NOTE]
>
>Klockikonen indikerar att algoritmmodellen fortfarande byggs. Kryssmarkeringsikonen anger att basalgoritmen har upprättats.

## Automatiska segment

Klicka på ikonen [!UICONTROL Automated Segments]. Den här rapporten visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.

![Ikon för automatiserade segment](/help/c-reports/assets/icon-automated-sements-ap.png)

Mer information finns i [Rapporten om automatiserade segment](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Viktiga attribut

Klicka på ikonen [!UICONTROL Important Attributes]. Den här rapporten visar hur olika attribut är viktigare (eller mindre) i olika aktiviteter för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.

![Ikon för viktiga attribut](/help/c-reports/assets/icon-important-attributes-ap.png)

Mer information finns i [Viktiga attribut-rapport](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Vanliga frågor

### Varför finns det skillnader i data mellan aktivitetsnivå- och erbjudandenivårapporterna?

**[!UICONTROL Activity Level]rapport**: Besök som registreras i  [!UICONTROL Activity Level] rapporten visar antalet besök i kontrollupplevelsen eller kontrollupplevelserna jämfört med riktad trafik. Målstyrd trafik omfattar en blandning av prospekteringstrafik och personaliserad trafik.

**Erbjudandenivårapport**: De exponeringar som registreras i  [!UICONTROL Offer Level] rapporten visar antalet visningar för varje erbjudande. I en aktivitet med mer än en plats är det totala antalet besök som registrerats i [!UICONTROL Offer Level]-rapporten för alla rapporteringsgrupper därför lika med det antal besök som registrerats för Kontroll- eller riktad trafik i [!UICONTROL Activity Level]-rapporten gånger det totala antalet platser i aktiviteten. Impressioner av standardinnehåll som förekommer på platser där standardinnehåll var ett tillgängligt alternativ registreras i erbjudandegruppen&quot;Standardinnehåll&quot;. Impressioner av erbjudanden som inte tilldelats en rapporteringsgrupp registreras i erbjudandegruppen&quot;Ej grupperad&quot;.

>[!NOTE]
>
>Antalet visningar som har registrerats i [!UICONTROL Offer Level]-rapporten kanske inte är en exakt heltalsmultipel av antalet besök som har registrerats i [!UICONTROL Activity Level]-rapporten. Detta beror på mindre avvikelser i insamlingen av datatrafik via Internet (den typiska diskrepansnivån är under 5 %). Därför kommer antalet visningar inte att vara en exakt multipel när antalet platser som är tillgängliga i aktiviteten har ändrats efter att aktiviteten aktiverades.
