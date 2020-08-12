---
keywords: reports;auto-target;auto target;AT
description: Information om hur du tolkar sammanfattningsrapporten för det automatiska målet.
title: Sammanfattningsrapport för automatiskt mål
feature: null
subtopic: Multivariate Test
topic: Standard
uuid: a30fa886-e8df-408f-bbc9-11a917a592d8
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---


# Sammanfattningsrapport för automatiskt mål{#auto-target-summary-report}

Information om hur du tolkar Auto-Target-sammanfattningsrapporter.

Så här visar du sammanfattningsrapporter för det automatiska målet:

1. Klicka på den önskade aktiviteten Automatisk målning på [!UICONTROL Activities] sidan.

   Om du har många aktiviteter kan du filtrera listan genom att välja alternativ i listrutorna Typ, Status, Egenskap, Rapporteringskälla, Experience Composer, Mätningstyp och Aktivitetskälla.

1. Klicka på [!UICONTROL Reports] fliken.

## Tabellvy

Följande bild visar hur en typisk sammanfattningsrapport ser ut i &quot;tabellvy&quot; när du använder Automatiskt mål:

![Rapport över tabellvy för automatisk målning](/help/c-reports/assets/at-table-view.png)

Några tips och saker att tänka på när du tolkar dina Auto-Target-rapporter:

* De olika raderna i tabellen hjälper dig att förstå aktivitetsprestanda.

   * De två översta raderna i tabellen på rapportsidan visar resultaten av ett A/B-test mellan de besökare som tilldelats kontrollen (dvs. slumpmässigt hanterade upplevelser) och de besökare som tilldelats personaliseringsalgoritmen. Den här informationen kan användas för att mäta hur personaliseringsalgoritmen utfördes jämfört med den slumpmässigt använda kontrollen.
   * De återstående raderna visar resultat på erfarenhetsnivå. För varje upplevelse finns det en jämförelse mellan det genomsnittliga svaret från besökare som visades den upplevelsen som en slumpmässigt hanterad kontroll och det genomsnittliga svaret från besökare som visades upplevelsen med personaliseringsalgoritmen.

* Den gröna bockikonen bredvid varje upplevelse i rapporten anger att en anpassad maskininlärningsmodell har skapats för den upplevelsen. Klockikonen anger att det inte finns tillräckligt med trafik för att skapa modellen.

   * Eftersom modellen är byggd per upplevelse är det möjligt att se en modell för vissa upplevelser med en grön bock och andra med en klockikon.
   * I det här fallet skickas ytterligare trafik till upplevelser med obyggda modeller för att öka hastigheten på de aktiviteter som har modeller byggda för alla upplevelser.
   * Det måste finnas minst två upplevelser med byggda modeller (grön bock) för att personaliseringen ska kunna börja.

* Att jämföra konverteringsgraden för upplevelsen A med upplevelsen B är inte den rätta jämförelsen i Auto-Target. Frågan är om upplevelsen A fungerar bättre när det används på ett intelligent sätt jämfört med ett slumpmässigt sätt (med andra ord kontra kontrollen). Marknadsförarna bör också vara försiktiga med att tolka lyft från enskilda upplevelser, eftersom personaliseringsalgoritmen försöker optimera för framgångsmätningen över hela aktiviteten, inte över varje enskild upplevelse.
* Erfarenheter med störst lyft kan anses ha den största skillnaden inom befolkningen. Det är algoritmen som har hittat ett segment som gillar den speciella upplevelsen mest.
* De olika kolumnerna i tabellen visar antalet besök, konverteringsgraden, den genomsnittliga lyften och konfidensnivån samt förtroendet. Mer information finns i [Jämka lyft, Lyft gränser och Konfidensintervall](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md).

## Diagramvy

Följande bild visar hur en typisk sammanfattningsrapport ser ut i &quot;diagramvyn&quot; när du använder Automatiskt mål:

![Rapport över diagramvyn för automatisk målning](/help/c-reports/assets/at-graph-view.png)

Som framgår nedan kan du använda de två listrutorna för att välja önskad statistik, beräkningsmetod och mycket annat. Mer information finns i Översikt över [](/help/c-reports/c-report-settings/report-settings.md) Rapportinställningar:

![Rapport över diagramvyn för automatisk målning](/help/c-reports/assets/at-graph-view-2.png)

## Automatiska segment

Klicka på ikonen Automatiska segment. Den här rapporten visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.

![Ikon för automatiserade segment](/help/c-reports/assets/icon-automated-sements.png)

Mer information finns i [rapporten](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)Automatiska segment.

## Viktiga attribut

Klicka på ikonen Viktiga attribut. Den här rapporten visar hur olika attribut är viktigare (eller mindre) i olika aktiviteter för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.

![Ikon för viktiga attribut](/help/c-reports/assets/icon-important-attributes.png)

Mer information finns i [rapporten](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)Viktiga attribut.
