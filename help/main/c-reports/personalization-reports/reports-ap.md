---
keywords: Målgruppsanpassning;AP-rapporter;automatiserade personaliseringsrapporter;aktivitetsnivårapport;erbjudandenivårapport;erbjudandedetaljrapport;faq
description: Lär dig hur du tolkar sammanfattningsrapporten för Automated Personalization i Adobe Target. Du kan växla till rapporterna Automatiserade segment och Viktiga attribut från den här rapporten.
title: Hur använder jag Automated Personalization Sammanfattningsrapporter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 0%

---

# Automated Personalization Sammanfattningsrapporter

Specialiserade sammanfattningsrapporter är tillgängliga för användare av [!UICONTROL Automated Personalization] aktiviteter i [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Automated Personalization] är tillgänglig som en del av lösningen [!DNL Target Premium]. Den ingår inte i [!DNL Target Standard] utan en [Target Premium-licens](/help/main/c-intro/intro.md#premium).

1. Klicka på **[!UICONTROL Activities]**, klicka på önskad [!UICONTROL Automated Personalization]-aktivitet i listan och klicka sedan på fliken **[!UICONTROL Reports]**.

   Om du har många aktiviteter klickar du på ikonen Filter ( ![Filterikon](/help/main/assets/icons/Filter.svg) ) för att filtrera listan genom att välja alternativ i listrutorna [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] och [!UICONTROL Activity Source] .

1. (Valfritt) Klicka på ikonen **[!UICONTROL Download]** ( ![&#x200B; ikonen Hämta &#x200B;](/help/main/assets/icons/Download.svg) ) för att hämta sammanfattningsvyn (till exempel en jämförelse av Kontroll- och Riktad trafik) uppdelad efter alla tillgängliga framgångsmått.

[!UICONTROL Automated Personalization] innehåller följande rapporter:

* Aktivitetsnivå
* Erbjudandenivå
* Automatiska segment
* Viktiga attribut

## Aktivitetsnivårapport {#section_6F72FC5C790B4492B3DCECBFFA971337}

Rapporten [!UICONTROL Activity Level] jämför den sammanställda prestandan för användning av en [!UICONTROL Automated Personalization]-algoritm med slumpmässigt hanterat innehåll (kontroll).

Standardreglerna för resultattolkning för A/B-tester gäller fortfarande, inklusive lyft, förtroende, trender, varaktighet och så vidare. Mer information om hur du tolkar resultat finns i [Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Erbjudandenivårapport {#section_CAA6409879E349C6906E2BE8156D87A1}

I rapporten [!UICONTROL Offer Level] för funktionen Slumpmässig skog jämförs prestandan för varje algoritmtillämpat erbjudande med samma slumpmässiga erbjudande (Kontroll). Erbjudandena bör därför inte jämföras med varandra i denna vy.

Klicka på upplevelsealgoritmen (Slumpmässig skog eller kontroll) för att visa [!UICONTROL Offer Level]-rapporten.

>[!NOTE]
>
>En klockikon anger att algoritmmodellen fortfarande byggs. En bockmarkeringsikon anger att basalgoritmen har upprättats.

Erbjudanden kan visas i [rapporteringsgrupper](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md) och dessa rapporteringsgrupper kan komprimeras och expanderas. Klicka på **[!UICONTROL Control]** eller **[!UICONTROL Targeted]** i tabellen för att visa sammanställd information efter rapporteringsgrupper, i stället för efter erbjudanden.

## Automatiska segment

Klicka på ikonen [!UICONTROL Automated Segments]. Den här rapporten visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.

Mer information finns i [Rapporten om automatiserade segment](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Viktiga attribut

Klicka på ikonen [!UICONTROL Important Attributes]. Den här rapporten visar hur olika attribut är viktigare (eller mindre) i olika aktiviteter för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.

Mer information finns i [Rapport om viktiga attribut](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Vanliga frågor

### Varför finns det skillnader i data mellan aktivitetsnivå- och erbjudandenivårapporterna?

**[!UICONTROL Activity Level]rapport**: Besök som registrerats i rapporten [!UICONTROL Activity Level] fångar antalet besök i kontrollupplevelsen/kontrollupplevelserna jämfört med riktad trafik. Målstyrd trafik omfattar en blandning av prospekteringstrafik och personaliserad trafik.

**Erbjudandenivårapport**: Impressioner som spelats in i rapporten [!UICONTROL Offer Level] visar antalet visningar för varje erbjudande. I en aktivitet med mer än en plats är därför det totala antalet besök som registrerats i rapporten [!UICONTROL Offer Level] för alla rapporteringsgrupper lika med det antal besök som registrerats för Kontroll- eller riktad trafik i rapporten [!UICONTROL Activity Level] gånger det totala antalet platser i aktiviteten. Impressioner av standardinnehåll som förekommer på platser där standardinnehåll var ett tillgängligt alternativ registreras i erbjudandegruppen&quot;Standardinnehåll&quot;. Impressioner av erbjudanden som inte tilldelats en rapporteringsgrupp registreras i erbjudandegruppen&quot;Ej grupperad&quot;.

>[!NOTE]
>
>Antalet inspelade visningar för rapporten [!UICONTROL Offer Level] kanske inte är en exakt heltalsmultipel av antalet besök som registreras i rapporten [!UICONTROL Activity Level]. Detta beror på mindre avvikelser i insamlingen av datatrafik via Internet (den typiska diskrepansnivån är under 5 %). Därför kommer antalet visningar inte att vara en exakt multipel när antalet platser som är tillgängliga i aktiviteten har ändrats efter att aktiviteten aktiverades.
