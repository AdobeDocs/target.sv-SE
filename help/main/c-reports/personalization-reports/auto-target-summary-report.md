---
keywords: rapporter;auto target;auto target;AT;report
description: Lär dig hur du tolkar sammanfattningsrapporten för automatisk målanpassning i Adobe Target. Du kan växla till rapporterna Automatiserade segment och Viktiga attribut från den här rapporten.
title: Hur använder jag den automatiska målsammanfattningsrapporten?
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: 90be7394b4493a99dd07ebcd74dc4945526a0933
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Sammanfattningsrapport för automatiskt mål

Information om hur du tolkar [!UICONTROL Auto-Target Summary] rapporter i [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Auto-Target] finns som en del av [!DNL Target Premium] lösning. Den ingår inte i [!DNL Target Standard] utan [Target Premium-licens](/help/main/c-intro/intro.md#premium).

Visa [!UICONTROL Auto-Target Summary] rapporter:

1. Från [!UICONTROL Activities] klickar du på önskad sida [!UICONTROL Auto-Target] aktivitet.

   Om du har många aktiviteter kan du filtrera listan genom att välja alternativ på menyn [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Property], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type]och [!UICONTROL Activity Source] nedrullningsbara listor.

1. Klicka på [!UICONTROL Reports] och klicka sedan på önskad ikon:

   * Tabellvy
   * Diagramvy
   * Automatiska segment
   * Viktiga attribut

## Tabellvy

Följande bild visar hur en vanlig sammanfattningsrapport ser ut i [!UICONTROL Table View] när du visar [!UICONTROL Auto-Target] aktivitetsrapport:

![Rapport över tabellvy för automatisk målning](/help/main/c-reports/assets/at-table-view.png)

Några tips och överväganden när du tolkar [!UICONTROL Auto-Target] rapporter:

* De olika raderna i tabellen hjälper dig att förstå aktivitetsprestanda.

   * De två översta raderna i tabellen på rapportsidan visar resultaten av ett A/B-test mellan de besökare som tilldelats kontrollen (dvs. slumpmässigt hanterade upplevelser) och de besökare som tilldelats personaliseringsalgoritmen. Den här informationen kan användas för att mäta hur personaliseringsalgoritmen utfördes jämfört med den slumpmässigt använda kontrollen.
   * De återstående raderna visar resultat på erfarenhetsnivå. För varje upplevelse finns det en jämförelse mellan det genomsnittliga svaret från besökare som visades den upplevelsen som en slumpmässigt hanterad kontroll och det genomsnittliga svaret från besökare som visades upplevelsen med personaliseringsalgoritmen.

* Den gröna bockikonen bredvid varje upplevelse i rapporten anger att en anpassad maskininlärningsmodell har skapats för den upplevelsen. Klockikonen anger att det inte finns tillräckligt med trafik för att skapa modellen.

   * Eftersom modellen är byggd per upplevelse är det möjligt att se en modell för vissa upplevelser med en grön bock och andra med en klockikon.
   * I det här fallet skickas ytterligare trafik till upplevelser med obyggda modeller för att öka hastigheten på de aktiviteter som har modeller byggda för alla upplevelser.
   * Det måste finnas minst två upplevelser med byggda modeller (grön bock) för att personaliseringen ska kunna börja.

* Att jämföra konverteringsgraden för upplevelsen A med upplevelsen B är inte den rätta jämförelsen i [!UICONTROL Auto-Target]. Frågan är om upplevelsen A fungerar bättre när det används på ett intelligent sätt jämfört med ett slumpmässigt sätt (med andra ord kontra kontrollen). Marknadsförarna bör också vara försiktiga med att tolka lyft från enskilda upplevelser, eftersom personaliseringsalgoritmen försöker optimera för framgångsmätningen över hela aktiviteten, inte över varje enskild upplevelse.
* Erfarenheter med störst lyft kan anses ha den största skillnaden inom befolkningen. Det är algoritmen som har hittat ett segment som gillar den speciella upplevelsen mest.
* De olika kolumnerna i tabellen visar antalet besök, konverteringsgraden, den genomsnittliga lyften och konfidensnivån samt förtroendet. Mer information finns i [Statistiska beräkningar i A/B-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Diagramvy

Följande bild visar hur en vanlig sammanfattningsrapport ser ut i [!UICONTROL Graph View] när du visar [!UICONTROL Auto-Target] aktivitetsrapport:

![Rapport över diagramvyn för automatisk målning](/help/main/c-reports/assets/at-graph-view.png)

Som framgår nedan kan du använda de två listrutorna för att välja önskad statistik, beräkningsmetod och mycket annat. Se [Översikt över rapportinställningar](/help/main/c-reports/c-report-settings/report-settings.md) för mer information:

![Rapport över diagramvyn för automatisk målning](/help/main/c-reports/assets/at-graph-view-2.png)

## Automatiska segment

Klicka på [!UICONTROL Automated Segments] ikon. Den här rapporten visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.

![Ikon för automatiserade segment](/help/main/c-reports/assets/icon-automated-sements.png)

Mer information finns i [Rapport över automatiserade segment](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Viktiga attribut

Klicka på [!UICONTROL Important Attributes] ikon. Den här rapporten visar hur olika attribut är viktigare (eller mindre) i olika aktiviteter för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.

![Ikon för viktiga attribut](/help/main/c-reports/assets/icon-important-attributes.png)

Mer information finns i [Viktiga attributrapporter](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).
