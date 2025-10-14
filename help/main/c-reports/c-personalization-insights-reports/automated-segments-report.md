---
keywords: Riktning;AP-rapporter;automatiserade personaliseringsrapporter;auto target;auto target;auto target report;auto target report;auto target report;personalization;insights;automatic segments;faq;Vanliga frågor
description: Lär dig hur olika segment som definieras av Adobe [!DNL Target] personaliseringsmodeller svarar på erbjudanden/upplevelser i aktiviteten genom att visa rapporten om automatiserade segment.
title: Vad är rapporten om automatiserade segment?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Reports
exl-id: d21517b7-770b-4618-9899-7ac4948c2a8b
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '2066'
ht-degree: 0%

---

# [!UICONTROL Automated Segments]-rapport

Information om rapporten [!UICONTROL Automated Segments], en av de två specialiserade rapporterna som är tillgängliga för användare av [!UICONTROL Automated Personalization]- (AP) och [!UICONTROL Auto-Target] (AT)-aktiviteter.

>[!NOTE]
>
>Tänk på följande när du använder [!UICONTROL Personalization Insights] rapporter:
>
>* AP- och AT-aktiviteter är tillgängliga som en del av lösningen [!DNL Target Premium]. De ingår inte i [!DNL Target Standard] utan en [!DNL Target Premium]-licens.
>
>* [!UICONTROL Personalization Insights] rapporter är bara tillgängliga för AP- och AT-aktiviteter som använder ett konverteringsoptimeringsmål. Aktiviteter där optimeringsmålet ändrades till konvertering från intäkter efter att aktiviteten redan var aktiv stöds inte heller.
>
>* [!UICONTROL Personalization Insights] rapporter är bara tillgängliga om [!UICONTROL Primary Goal] har valts i listrutan [!UICONTROL Report Metric].
>
>* [!UICONTROL Personalization Insights] rapporter stöds endast i [standardmiljön](/help/main/administrating-target/hosts.md).
>
>* [!UICONTROL Personalization Insights] rapporter genereras bara för aktiviteter som har statusen [!UICONTROL Live] och har aktiverats och tagit emot trafik i minst 15 dagar.

Olika besökare svarar annorlunda på erbjudandena/upplevelserna i er AP/AT-aktivitet. Den här rapporten visar hur olika automatiserade segment som definierats av Target personaliseringsmodeller svarade på erbjudandena/upplevelserna i aktiviteten.

## Åtkomst till rapporten Automated Segments {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Klicka på **[!UICONTROL Activities]** och sedan på önskad aktivitet för [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) i listan.

   Om du har många aktiviteter klickar du på ikonen Filter ( ![Filterikon](/help/main/assets/icons/Filter.svg) ) för att filtrera listan genom att välja alternativ i listrutorna [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] och [!UICONTROL Activity Source] .

1. Klicka på **[!UICONTROL Reports]**.

   Rapporten [Automated Personalization Summary](/help/main/c-reports/personalization-reports/reports-ap.md) eller [Auto-Target Summary](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) visas, som innehåller information om hur dina aktiviteter fungerar, vilket representeras av ikonen för första skärmen. De två extra ikonerna representerar de två [!UICONTROL Personalization Insights]-rapporterna: **[!UICONTROL Automated Segments]** ( ![rapporten Automatiska segment &#x200B;](/help/main/assets/icons/AutomatedSegment.svg) ) och **[!UICONTROL Important Attributes]** ( ![ikonen Viktiga attribut](/help/main/assets/icons/ViewList.svg) ). Automatiskt mål har en extra diagramikon för den grafiska vyn i rapporten [!UICONTROL Summary].

   >[!IMPORTANT]
   >
   >[!UICONTROL Automated Segments]-rapporten är inte tillgänglig förrän minst 15 dagar efter att du har aktiverat aktiviteten. Under den inledande perioden kommer du inte att kunna komma åt den här rapporten eller klicka på ikonen [!UICONTROL Automated Segments]. Efter 15 dagar, under förutsättning att det finns tillräckligt med personaliserad trafik i din aktivitet, är [!UICONTROL Automated Segments]-rapporten tillgänglig.

1. Efter 15 dagar från det att aktiviteten har aktiverats kan du klicka på ikonen **[!UICONTROL Automated Segments]**.

1. Välj önskat datumintervall.

   Till skillnad från rapporten [!UICONTROL Summary] (prestandarapportering) är [!UICONTROL Personalization Insights], inklusive [!UICONTROL Automated Segments], bara tillgängligt för fasta datumintervall: 15 dagar, 30 dagar och 60 dagar. Med dessa fasta datumintervall kan [!UICONTROL Personalization Insights] använda tillräckligt många data för att minska sannolikheten för att du får insikter från ett kort mönster i din aktivitet. De två beslut som du kan fatta för datumintervallet är&quot;Slutdatum&quot; och&quot;Varaktighet&quot;. Du kommer att märka att &quot;Start&quot; är nedtonat. Startdatumet ändras automatiskt baserat på dina val för slutdatumet och varaktigheten.

   Du kommer åt de tillgängliga fasta datumintervallen i listrutan [!UICONTROL Preset Date Range].

1. Granska rapportdata för [!UICONTROL Automated Segments].

1. (Valfritt) Klicka på ikonen **[!UICONTROL Download]** ( ![ikonen Hämta](/help/main/assets/icons/Download.svg) ) för att [hämta rapporten i CSV-format](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) för analys i Excel och andra verktyg.

   >[!NOTE]
   >
   >Personalization Insights-gränssnittsrapporten innehåller urvalsinformation. CSV-nedladdningen för rapporten Automated Segments innehåller ytterligare information. Nedladdningen av rapporten Automated Segments innehåller ytterligare automatiserade segment utöver de främsta segmenten som ingår i användargränssnittet, tillsammans med hur dessa segment fungerade i förhållande till era erbjudanden eller upplevelser.

## Tolka rapporten Automatiserade segment

I följande tabell beskrivs hur du tolkar rapporten och dess element:

| Element | Information |
|--- |--- |
| Vänster sidopanel | Den vänstra panelen listar de 20 största&quot;automatiserade segmenten&quot; som identifieras av Target personaliseringsmodeller för den här aktiviteten. Ett&quot;automatiserat segment&quot; är som en målgrupp, men definieras av Target personaliseringsmodeller i stället för av marknadsföraren. Varje automatiserat segment består av specifika värden (eller värdeintervall) för specifika attribut.<br>Automatiska segment kan överlappa varandra. Automatiska segment kan definieras med ett, två, tre eller fyra attribut. Se exemplen nedan för mer information.<br>Mer information om Target personaliseringsmodeller finns i [Slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md). Mer information om attributen Target personaliseringsmodeller använder för att skapa automatiserade segment finns i [Datainsamling för Target&#39;s Personalization Algorithms](/help/main/c-activities/t-automated-personalization/ap-data.md). |
| Centrera diagram | I mittdiagrammen visas hur aktivitetens innehåll har utförts för det markerade automatiserade segmentet. När du klickar på olika segment på den vänstra panelen uppdateras diagrammen i mitten. |
| Cirkeldiagram | Cirkeldiagrammen högst upp på mittpanelen visar det automatiserade segmentets storlek samt det totala antalet personaliserade besök i aktiviteten (till exempel trafik till den här aktiviteten som betjänades av personaliseringsmodellen). Omfattar inte kontrolltrafik eller trafik som betjänas av den övergripande vinnarmodellen). Segmentets storlek baseras endast på personaliserade besök.<br>![Cirkeldiagram](/help/main/c-reports/assets/pie.png) |
| Stapeldiagram med dubbla axlar | I stapeldiagrammet med dubbla axlar ingår besöks- och konverteringsinformation från erbjudandet eller upplevelsen för det specifika automatiserade segmentet. |
| Rosa fält | Det rosa strecket representerar konverteringsgraden och använder diagrammets nedre axel. Om du vill ha mer information håller du pekaren över fältet |
| Blå stapel | Det blå fältet representerar antalet besök och använder diagrammets övre axel. Om du vill ha mer information håller du pekaren över fältet. |
| Grå prickad linje | Den grå prickade linjen representerar konverteringsgraden för alla personaliserade besök i aktiviteten, för alla erbjudanden/upplevelser och automatiserade segment. |

**Exempel på automatiserat segment**

Detta automatiserade segment definieras utifrån endast ett attribut. Besökarna i det här automatiserade segmentet såg den här AP-aktiviteten på en veckodag utanför de vanliga arbetstiderna eller på en helg.

![Exempel på rapport för automatiserade segment &#x200B;](/help/main/c-reports/assets/automated_segment_example_1.png)

**Exempel på automatiserat segment 2**

Detta automatiska segment definieras baserat på två attribut. Besökare som ingick i det här automatiska segmentet och som såg denna AP-aktivitet hade färre än tre sidvisningar vid sitt aktuella besök och var geografiskt baserade i Latitude 42.57 och 47.29 (ungefär mellan New Hampshire/Oregon och Washington/Maine för ett amerikanskt företag).

![Exempel på rapport för automatiserade segment 2](/help/main/c-reports/assets/automated_segment_example_2.png)

## Vanliga frågor om automatiserade segment {#section_740910A52FA646B4AC9452F98C2F5719}

**Personalization Insights-rapporter är inte tillgängliga än för min aktivitet. Varför är det där?**

Det finns flera orsaker till varför [!UICONTROL Personalization Insights]-rapporterna ännu inte är tillgängliga för din aktivitet:

* 15 dagar har inte gått sedan du aktiverade aktiviteten. Automatiserade segment och viktiga attributrapporter är inte tillgängliga förrän tidigast 15 dagar efter att du har påbörjat aktiviteten. Under den inledande perioden kommer du inte att kunna komma åt dessa rapporter eller klicka på ikonerna Automatiserade segment och Viktiga attribut.
* Din aktivitet har inte haft tillräckligt med trafik under den angivna tidsramen. Efter 15 dagar kommer rapporter om automatiserade segment och viktiga attribut att finnas tillgängliga, förutsatt att det finns tillräckligt med personaliserad trafik i din aktivitet för att skapa personaliseringsmodeller.
* Din aktivitet har ett intäktsoptimeringsmål. För närvarande är [!UICONTROL Personalization Insights] bara tillgängligt för målaktiviteter för konverteringsoptimering. Adobe kommer att lägga till stöd för intäktsoptimeringsmålaktiviteter i en kommande release.

**Vad är ett attribut?**

Ett attribut är information om en besökare eller hans eller hennes specifika besök som används av personaliseringsalgoritmerna för att lära sig att personalisera trafik. Ett attribut kan till exempel vara webbläsartyp, plats, tidpunkt på besöksdagen och så vidare.

Mer information om vilka attribut [!DNL Target] använder i sina anpassningsmodeller finns i [Datainsamling för Target&#39;s Personalization Algorithms](/help/main/c-activities/t-automated-personalization/ap-data.md). Mer information om hur du överför nya attribut till Target för användning i Target-personaliseringsmodeller finns i [Metoder för att hämta data till Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=sv-SE){target=_blank}.

**Vad är ett automatiserat segment?**

Ett&quot;automatiserat segment&quot; är som en målgrupp, men definieras av Target personaliseringsmodeller i stället för av marknadsföraren.

Ett automatiserat segment består av specifika värden (eller värdeintervall) för specifika attribut. Se steg 5 ovan för exempel automatiserade segment. Segment kan överlappa varandra.

Mer information om den slumpmässiga algoritmen för skogspersonalisering, som är grunden för Target personaliseringsmodeller, finns i [Slumpmässig skogsalgoritm](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

**Vad bestämmer ordningen på de automatiserade segmenten?**

Poängen beräknas för varje segment utifrån dess storlek och hur annorlunda det utfördes med innehållet i din aktivitet. Kombinationen av dessa indata avgör ordningen på de automatiserade segmenten så att större segment med större skillnader i hur de svarade på det olika innehållet visas närmare segmentlistans övre del.

**Varför visas bara några av mina erbjudanden/upplevelser i rapporten om automatiserade segment?**

AP- och AT-aktiviteter bygger en modell per erbjudande (i fallet AP) och en modell per upplevelse (i fallet AT). De här aktiviteterna börjar betjäna personaliserad trafik och skapar din [!UICONTROL Personalization Insights] med så lite som två modeller skapade. Om du inte ser alla dina erbjudanden/upplevelser i [!UICONTROL Personalization Insights] har du förmodligen inte skapat några modeller för de specifika erbjudandena/upplevelserna. Du kan kontrollera aktivitetens [!UICONTROL Summary]-rapport och se om det finns en urtikon bredvid erbjudandet/upplevelsen. Den här ikonen anger att modeller ännu inte har byggts för det erbjudandet/upplevelsen.

**Varför får vissa erbjudanden/upplevelser med en lägre konverteringsgrad större trafik jämfört med andra erbjudanden/upplevelser för ett visst automatiserat segment?**

Det finns flera möjliga orsaker till varför du kan se fler besök i ett erbjudande om lägre konverteringsgrad eller en upplevelse inom ett automatiserat segment, bland annat:

* Ett litet antal vyer för vissa eller alla erbjudanden/upplevelser för ett visst automatiserat segment.
* Aktiviteter med låg volym där vissa erbjudanden/upplevelser inte har några modeller byggda, eller där modeller har skapats tidigare för vissa erbjudanden/upplevelser än andra.
* Riktlinjer för ett specifikt erbjudande som begränsar vilka besökare som kan se vilka erbjudanden/upplevelser som finns.

**Är informationen i [!UICONTROL Automated Segments]- och [!UICONTROL Important Attributes]-rapporterna densamma som i CSV-nedladdningen?**

Nej, UI-rapporten innehåller urvalsinformation. CSV-nedladdningen innehåller ytterligare information. Nedladdningen av rapporten Automated Segment Insights innehåller ytterligare automatiserade segment utöver de främsta segmenten som ingår i användargränssnittet, tillsammans med hur dessa segment fungerade i förhållande till era erbjudanden eller upplevelser. Rapporten Viktiga attribut innehåller de 100 viktigaste besökarattributen och deras relativa betydelse, medan användargränssnittet endast innehåller de 10 viktigaste besökarattributen.

**Kan jag se [!UICONTROL Personalization Insights] för ett anpassat datumintervall?**

Personalization Insights-rapportering (både [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes]) är bara tillgänglig för fasta datumintervall: 15 dagar, 30 dagar och 60 dagar. Med dessa fasta datumintervall kan [!UICONTROL Personalization Insights] använda tillräckligt många data för att minska sannolikheten för att du får insikter från ett kort mönster i din aktivitet. Du kan välja de här varaktigheterna för ett slutdatum (där dessa data är tillräckligt många för att aktiviteten ska klara varaktigheten).

**Hur skapas [!UICONTROL Personalization Insights]?**

[!UICONTROL Personalization Insights] har skapats med en patentsökt Adobe-teknik som heter MAGIX (Model Agnostic Global Interpretable Förklarings). Du kan läsa mer om MAGIX i Adobe forskningsgrupps publicerade rapport på webbplatsen [arXiv.org](https://arxiv.org/abs/1706.07160).

**Varför matchar inte den totala besökstrafiken i [!UICONTROL Automated Segments]-rapporten min AP- eller AT-sammanfattning/prestandarapport?**

[!UICONTROL Personalization Insights]-rapporterna innehåller endast besökare som såg en del av innehållet som valts ut av Target:s personaliseringsmodeller (d.v.s. inte kontrolltrafik eller trafik som betjänas av den övergripande vinnarmodellen). Denna trafiktyp kallas för&quot;personaliserad&quot; trafik. Den sammanfattande prestandarapporten i AP/AT omfattar kontroll kontra&quot;riktad&quot; trafik. Målstyrd trafik omfattar personaliserad trafik, liksom trafik som betjänades med den övergripande vinnarmodellen och viss slumpmässigt betjänad trafik som brukade lära sig mer.

**Kan automatiserade segment inte användas samtidigt?**

Nej, det finns överlappning mellan de automatiserade segmenten.

**Är [!UICONTROL Personalization Insights] tillgängligt för intäktsbaserade modelleringsmål/primärt mål?**

För närvarande är [!UICONTROL Personalization Insights] bara tillgängligt för målaktiviteter för konverteringsoptimering. Adobe kommer att lägga till stöd för intäktsoptimeringsmålaktiviteter i en kommande release.

**Vilka olika sätt kan jag utnyttja informationen i Personalization Insights?**

* Upptäck nya målgrupper: Om du ser ett visst automatiserat segment som fungerar bra kan du skapa en målgrupp så att du kan återanvända det segmentet i andra rapporter.
* Testa era hypoteser om vilken typ av besökare som svarar på vilken av era upplevelser.
* Ta reda på vilket innehåll som fungerade för vilka typer av besökare: vilka erbjudanden som ansvarade för besökarnas lyft.
* Identifiera underpresterande innehåll.
* Förstå vilka attribut som var viktigast för hur modellen lärde sig.
* Se vilka attribut som används i personaliseringsmodellerna och hur viktiga de är.
* Identifiera möjligheter för ytterligare datapunkter som ni kan skicka till Target för att ytterligare informera er personalisering.

**Finns det någon logik i ordningen som attribut visas i ett segmentkort?**

Nej, kortens ordning baseras endast på en rankning som beskrivs ovan. Attributens ordning i ett kort baseras inte på någon logik.
