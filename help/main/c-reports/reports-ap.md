---
keywords: Målgruppsanpassning;AP-rapporter;automatiserade personaliseringsrapporter;aktivitetsnivårapport;erbjudandenivårapport;erbjudandedetaljrapport;faq
description: Lär dig hur du tolkar sammanfattningsrapporten för Automated Personalization i Adobe Target. Du kan växla till rapporterna Automatiserade segment och Viktiga attribut från den här rapporten.
title: Hur använder jag Automated Personalization Sammanfattningsrapporter?
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Automated Personalization Sammanfattningsrapporter

Specialiserade sammanfattningsrapporter är tillgängliga för användare av [!UICONTROL Automated Personalization] verksamhet i [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Automated Personalization] finns som en del av [!DNL Target Premium] lösning. Den ingår inte i [!DNL Target Standard] utan [Target Premium-licens](/help/main/c-intro/intro.md#premium).

1. Klicka **[!UICONTROL Activities]** klickar du på [!UICONTROL Automated Personalization] från listan och klicka sedan på **[!UICONTROL Reports]** -fliken.

   Om du har många aktiviteter kan du filtrera listan genom att välja [!UICONTROL Automated Personalization] från [!UICONTROL Type] nedrullningsbar lista.

1. (Valfritt) Klicka på **[!UICONTROL Download]** om du vill ladda ned sammanfattningsvyn (till exempel en jämförelse av Kontroll och riktad trafik) uppdelad efter alla tillgängliga framgångsmått.

[!UICONTROL Automated Personalization] innehåller följande rapporter:

* Aktivitetsnivå
* Erbjudandenivå
* Automatiska segment
* Viktiga attribut

## Aktivitetsnivårapport {#section_6F72FC5C790B4492B3DCECBFFA971337}

The [!UICONTROL Activity Level] rapporten jämför den sammanställda prestandan för att använda en [!UICONTROL Automated Personalization] -algoritm för slumpmässigt hanterat innehåll (kontroll).

![Aktivitetsnivårapport](/help/main/c-reports/assets/box_plot_ap.png)

Standardreglerna för resultattolkning för A/B-tester gäller fortfarande, inklusive lyft, förtroende, trender, varaktighet och så vidare. Mer information om hur du tolkar resultat finns i [Om konverteringsgraden](/help/main/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844).

## Erbjudandenivårapport {#section_CAA6409879E349C6906E2BE8156D87A1}

The [!UICONTROL Offer Level] rapporten för Random Forest Experience jämför resultatet för varje algoritmtillämpat erbjudande med samma slumpmässiga erbjudande (Control). Erbjudandena bör därför inte jämföras med varandra i denna vy.

Klicka på upplevelsealgoritmen (Slumpmässig skog eller kontroll) för att visa [!UICONTROL Offer Level] rapport.

![](assets/ap_OfferLevelRpt.png)

Erbjudandena kan visas i rapportgrupper och dessa kan komprimeras och utökas. Välj [!UICONTROL Reporting Group] i listrutan för att visa sammanställd information per rapporteringsgrupp, i stället för efter erbjudanden.

>[!NOTE]
>
>Klockikonen indikerar att algoritmmodellen fortfarande byggs. Kryssmarkeringsikonen anger att basalgoritmen har upprättats.

## Automatiska segment

Klicka på [!UICONTROL Automated Segments] ikon. Den här rapporten visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.

![Ikon för automatiserade segment](/help/main/c-reports/assets/icon-automated-sements-ap.png)

Mer information finns i [Rapport över automatiserade segment](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Viktiga attribut

Klicka på [!UICONTROL Important Attributes] ikon. Den här rapporten visar hur olika attribut är viktigare (eller mindre) i olika aktiviteter för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.

![Ikon för viktiga attribut](/help/main/c-reports/assets/icon-important-attributes-ap.png)

Mer information finns i [Viktiga attributrapporter](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Vanliga frågor

### Varför finns det skillnader i data mellan aktivitetsnivå- och erbjudandenivårapporterna?

**[!UICONTROL Activity Level]rapport**: Besök som registrerats på [!UICONTROL Activity Level] rapportera antalet besök till kontrollupplevelserna jämfört med riktad trafik. Målstyrd trafik omfattar en blandning av prospekteringstrafik och personaliserad trafik.

**Erbjudandenivårapport**: Impression som spelats in på [!UICONTROL Offer Level] rapporten visar antalet visningar för varje erbjudande. I en verksamhet med mer än en plats är det totala antalet besök som registrerats i [!UICONTROL Offer Level] rapporten för alla rapporteringsgrupper är lika med den multipel av antalet besök som registrerats för Kontroll- eller Riktad trafik i [!UICONTROL Activity Level] gånger det totala antalet platser i aktiviteten. Impressioner av standardinnehåll som förekommer på platser där standardinnehåll var ett tillgängligt alternativ registreras i erbjudandegruppen&quot;Standardinnehåll&quot;. Impressioner av erbjudanden som inte tilldelats en rapporteringsgrupp registreras i erbjudandegruppen&quot;Ej grupperad&quot;.

>[!NOTE]
>
>Antal visningar som registrerats på [!UICONTROL Offer Level] rapporten kanske inte är en exakt heltalsmultipel av antalet besök som registreras i [!UICONTROL Activity Level] rapport. Detta beror på mindre avvikelser i insamlingen av datatrafik via Internet (den typiska diskrepansnivån är under 5 %). Därför kommer antalet visningar inte att vara en exakt multipel när antalet platser som är tillgängliga i aktiviteten har ändrats efter att aktiviteten aktiverades.