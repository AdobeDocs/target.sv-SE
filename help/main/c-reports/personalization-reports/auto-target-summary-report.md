---
keywords: rapporter;auto target;auto target;AT;report
description: Lär dig hur du tolkar sammanfattningsrapporten för automatisk målanpassning i Adobe Target. Du kan växla till rapporterna Automatiserade segment och Viktiga attribut från den här rapporten.
title: Hur använder jag den automatiska målsammanfattningsrapporten?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---

# [!UICONTROL Auto-Target Summary report]

Information om hur du tolkar [!UICONTROL Auto-Target Summary]-rapporter i [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Auto-Target] är tillgänglig som en del av lösningen [!DNL Target Premium]. Den ingår inte i [!DNL Target Standard] utan en [Target Premium-licens](/help/main/c-intro/intro.md#premium).

Så här visar du [!UICONTROL Auto-Target Summary]-rapporter:

1. Klicka på önskad [!UICONTROL Activities]-aktivitet på sidan [!UICONTROL Auto-Target].

   Om du har många aktiviteter klickar du på ikonen Filter ( ![Filterikon](/help/main/assets/icons/Filter.svg) ) för att filtrera listan genom att välja alternativ i listrutorna [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] och [!UICONTROL Activity Source] .

1. Klicka på fliken **[!UICONTROL Reports]** och sedan på önskad ikon:

   * **[!UICONTROL Table View]** ( ![Tabellvyikon](/help/main/assets/icons/Table.svg) )
   * **[!UICONTROL Graph View]** ( ![Diagramvyikon](/help/main/assets/icons/GraphTrend.svg) )
   * **[!UICONTROL Automated Segments]** ( ![Rapporten Automatiska segment &#x200B;](/help/main/assets/icons/AutomatedSegment.svg) )
   * [!UICONTROL Important Attributes]** ( ![ikon för viktiga attribut](/help/main/assets/icons/ViewList.svg) )

## Tabellvy

Några tips och överväganden när du tolkar dina [!UICONTROL Auto-Target]-rapporter:

* De olika raderna i tabellen hjälper dig att förstå aktivitetsprestanda.

   * De två översta raderna i tabellen på rapportsidan visar resultaten av ett A/B-test mellan de besökare som tilldelats kontrollen (det vill säga slumpmässigt hanterade upplevelser) och de besökare som tilldelats personaliseringsalgoritmen. Den här informationen kan användas för att mäta hur personaliseringsalgoritmen utfördes jämfört med den slumpmässigt hanterade kontrollen.
   * De återstående raderna visar resultat på erfarenhetsnivå. För varje upplevelse finns det en jämförelse mellan det genomsnittliga svaret från besökare som visades den upplevelsen som en slumpmässigt hanterad kontroll och det genomsnittliga svaret från besökare som visades upplevelsen med personaliseringsalgoritmen.

* Den gröna bockikonen bredvid varje upplevelse i rapporten anger att en anpassad maskininlärningsmodell har skapats för den upplevelsen. Klockikonen anger att det inte finns tillräckligt med trafik för att skapa modellen.

   * Eftersom modellen är byggd per upplevelse är det möjligt att se en modell för vissa upplevelser med en grön bock och andra med en klockikon.
   * I det här fallet skickas ytterligare trafik till upplevelser med obyggda modeller för att öka hastigheten på de aktiviteter som har modeller byggda för alla upplevelser.
   * Det måste finnas minst två upplevelser med byggda modeller (grön bock) för att personaliseringen ska kunna börja.

* Att jämföra konverteringsgraden för upplevelsen A med upplevelsen B är inte rätt jämförelse i [!UICONTROL Auto-Target]. Frågan är om upplevelsen A fungerar bättre när det används på ett intelligent sätt jämfört med ett slumpmässigt sätt (med andra ord kontra kontrollen). Marknadsförarna bör också vara försiktiga med att tolka lyft från enskilda upplevelser, eftersom personaliseringsalgoritmen försöker optimera för framgångsmätningen över hela aktiviteten, inte över varje enskild upplevelse.
* Erfarenheter med störst lyft kan anses ha den största skillnaden inom befolkningen. Det innebär att algoritmen har hittat ett segment som gillar den speciella upplevelsen mest.
* De olika kolumnerna i tabellen visar antalet besök, konverteringsgraden, den genomsnittliga lyften och konfidensnivån samt förtroendet. Mer information finns i [Statistiska beräkningar i A/B-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Diagramvy

Använd de två nedrullningsbara listrutorna för att välja önskad statistik, beräkningsmetod med mera. Mer information finns i [Översikt över rapportinställningar](/help/main/c-reports/c-report-settings/report-settings.md):

## Automatiska segment

Den här rapporten visar hur olika besökare svarar annorlunda på erbjudanden/upplevelser i din AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av personaliseringsmodellerna i [!DNL Target] svarade på erbjudandena/upplevelserna i aktiviteten.

Mer information finns i rapporten [Automatiska segment](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Viktiga attribut

Den här rapporten visar hur olika attribut är viktigare (eller mindre) i olika aktiviteter för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.

Mer information finns i rapporten [Viktiga attribut](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).
