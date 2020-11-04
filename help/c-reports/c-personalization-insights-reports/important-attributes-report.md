---
keywords: Targeting;AP reports;automated personalization reports;auto-target;auto target;auto target report;auto-target report;personalization;insights;faq;frequently asked questions;important attributes
description: Information om rapporten Viktiga attribut, en av de två specialrapporter som är tillgängliga för användare av Automated Personalization- (AP) och AutoTarget-aktiviteter (AT).
title: Viktiga attributrapporter
feature: reports
uuid: c03bf806-0b03-4315-a176-4eaa9250a271
translation-type: tm+mt
source-git-commit: 55ee85188ec80a4dcc7dbb39cd0ce24f829ea331
workflow-type: tm+mt
source-wordcount: '1562'
ht-degree: 0%

---


# ![Rapport om PREMIUM](/help/assets/premium.png) Viktiga attribut{#important-attributes-report}

Information om rapporten Viktiga attribut, en av de två specialrapporter som är tillgängliga för användare av Automated Personalization- (AP) och AutoTarget-aktiviteter (AT).

>[!NOTE]
>
>Tänk på följande när du använder personaliseringsInsights-rapporter:
>
>* AP- och AT-aktiviteter är tillgängliga som en del av [!DNL Target Premium] lösningen. De ingår inte [!DNL Target Standard] utan [!DNL Target Premium] licens.
   >
   >
* [!UICONTROL Personalization Insights] rapporter är bara tillgängliga för AP- och AT-aktiviteter som använder ett konverteringsoptimeringsmål. Aktiviteter där optimeringsmålet ändrades till konvertering från intäkt efter att aktiviteten redan var aktiv stöds inte heller.
   >
   >
* [!UICONTROL Personalization Insights] -rapporter är bara tillgängliga om du [!UICONTROL Primary Goal] har valt dem i [!UICONTROL Report Metric] listrutan.
   >
   >
* [!UICONTROL Personalization Insights] rapporter stöds endast i [standardmiljön](../../administrating-target/hosts.md) .
   >
   >
* [!UICONTROL Personalization Insights] Rapporterna genereras endast för aktiviteter som är i [!UICONTROL Live] status och har aktiverats och tagit emot trafik i minst 15 dagar.


I olika aktiviteter är olika attribut viktigare eller mindre viktiga för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.

## Öppna rapporten Viktiga attribut {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Klicka på **[!UICONTROL Activities]** och sedan på önskad aktivitet för [Automated Personalization](../../c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) eller [Automatiskt mål](/help/c-activities/auto-target-to-optimize.md) i listan.

   Om du har många aktiviteter kan du filtrera listan genom att välja alternativ i listrutorna [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer][!UICONTROL Metrics Type]och [!UICONTROL Activity Source] .

1. Klicka på **[!UICONTROL Reports]**.

   Sammanfattningsrapporten för [Automated Personalization](/help/c-reports/reports-ap.md) eller [Automatisk målsammanfattning](/help/c-reports/auto-target-summary-report.md) visas med information om hur dina aktiviteter fungerar, vilket visas med ikonen för första skärmen. De två ytterligare ikonerna representerar de två personaliseringsinsikterna: Automatiska segment och viktiga attribut. Observera att Automatiskt mål har en extra diagramikon för den grafiska vyn av [!UICONTROL Summary] rapporten.

   ![](assets/personalization_insights.png)

   >[!IMPORTANT]
   >
   >Rapporten kommer inte att vara tillgänglig förrän minst 15 dagar efter att du har aktiverat din aktivitet. [!UICONTROL Important Attributes] Under den inledande perioden kan du inte komma åt den här rapporten eller klicka på [!UICONTROL Important Attributes] ikonen. Efter 15 dagar, och förutsatt att det finns tillräckligt med personaliserad trafik i din aktivitet, kommer rapporten att finnas tillgänglig [!UICONTROL Important Attributes] .

1. Efter 15 dagar kan du klicka på **[!UICONTROL Important Attributes]** -ikonen.

   ![](assets/model_attribute_ranking.png)

1. Välj önskat datumintervall.

   Till skillnad från [!UICONTROL Summary] rapporten (resultatrapportering), [!UICONTROL Personalization Insights]inklusive [!UICONTROL Important Attributes], är endast tillgänglig för fasta datumintervall: 15 dagar, 30 dagar, 45 dagar, 60 dagar och 90 dagar. Med dessa fasta datumintervall kan du [!UICONTROL Personalization Insights] använda tillräckligt många data för att minska sannolikheten för att du får insikter från ett kort mönster i din aktivitet. De två beslut som du kan fatta för datumintervallet är&quot;Slutdatum&quot; och&quot;Varaktighet&quot;. Du kommer att märka att &quot;Start&quot; är nedtonat. Startdatumet ändras automatiskt baserat på dina val för slutdatumet och varaktigheten.

   ![](assets/personalization_insights_calendar_1.png)

   Du kan komma åt de tillgängliga fasta datumintervallen i den [!UICONTROL Choose Duration] nedrullningsbara listan.

   ![](assets/personalization_insights_calendar_2.png)

1. Granska [!UICONTROL Important Attributes] rapportdata.

   ![](assets/model_attribute_ranking_report.png)


1. (Valfritt) [Hämta rapporten i CSV-format](../../c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) för analys i Excel och andra verktyg.

   >[!NOTE]
   >
   >Användargränssnittsrapporten Personalization Insights innehåller urvalsinformation. CSV-nedladdningen för rapporten Viktiga attribut innehåller ytterligare information. Nedladdningen av rapporten Viktiga attribut innehåller en fullständig lista över de 100 viktigaste attributen, medan rapporten för användargränssnittet endast innehåller de 10 översta. Om du letar efter ett specifikt attribut i rapporten men inte finns där, betyder det inte att attributet inte påverkade aktiviteten, utan bara inte listan för de 100 viktigaste attributen.

## Tolka rapporten Viktiga attribut

I följande tabell beskrivs hur du tolkar rapporten och dess element:

| Element | Detaljer |
|--- |--- |
| Stolpdiagram | Med det flerfärgade stapeldiagrammet längst upp på skärmen kan du visualisera dessa relativa prioritetsklasser och mappa till punktens färg bredvid respektive attribut i tabellen. Du kan också hovra över en viss färg i stapeldiagrammet för att se vilket attribut det representerar.  Viktigt-poängen för de 100 översta attributen ökar till 100 %. Mer information om hur du lägger till fler attribut som Target personaliseringsmodeller kan använda finns i [Överföra data för målets personaliseringsalgoritmer](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md). |
| Diagram över modellattribut | Model Attribute Ranking innehåller de 10 viktigaste attributen som var viktigast för hur Target personaliseringsmodell bestämde vilket innehåll som skulle visas för varje besökare. Viktigt-poängen visar, i förhållande till de 100 viktigaste attributen, hur viktigt ett specifikt attribut var för Target personaliseringsmodeller i den här aktiviteten. |

## Vanliga frågor om viktiga attribut {#section_740910A52FA646B4AC9452F98C2F5719}

**Personaliseringsinsikter - rapporter är inte tillgängliga än för min aktivitet. Varför det?**

Det finns flera anledningar till att rapporterna kanske inte är tillgängliga för din aktivitet ännu: [!UICONTROL Personalization Insights]

* 15 dagar har inte gått sedan du aktiverade aktiviteten. Automatiserade segment och viktiga attributrapporter är inte tillgängliga förrän tidigast 15 dagar efter att du har påbörjat aktiviteten. Under den inledande perioden kommer du inte att kunna komma åt dessa rapporter eller klicka på ikonerna Automatiserade segment och Viktiga attribut.
* Din aktivitet har inte haft tillräckligt med trafik under den angivna tidsramen. Efter 15 dagar kommer rapporter om automatiserade segment och viktiga attribut att finnas tillgängliga, förutsatt att det finns [tillräckligt med personaliserad trafik](/help/c-activities/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB) i din aktivitet för att skapa personaliseringsmodeller.
* Din aktivitet har ett intäktsoptimeringsmål. För närvarande [!UICONTROL Personalization Insights] är endast tillgängligt för målaktiviteter för konverteringsoptimering. Vi kommer att lägga till stöd för intäktsoptimeringsmålaktiviteter i en kommande release.

**Vad är ett attribut?**

Ett attribut är information om en besökare eller hans eller hennes specifika besök som används av personaliseringsalgoritmerna för att lära sig att personalisera trafik. Ett attribut kan till exempel vara webbläsartyp, plats, tidpunkt på besöksdagen och så vidare.

Mer information om vilka attribut som [!DNL Target] används i dess anpassningsmodeller finns i [Datainsamling för Target&#39;s Personalization Algorithms](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058). Mer information om hur du överför nya attribut till Target för användning i Target-personaliseringsmodeller finns i [Metoder för att hämta data till Target](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17).

**Är informationen i [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes] rapporter densamma som i CSV-nedladdningen?**

Nej, UI-rapporten innehåller urvalsinformation. CSV-nedladdningen innehåller ytterligare information. Nedladdningen av rapporten Automated Segment Insights innehåller ytterligare automatiserade segment utöver de främsta segmenten som ingår i användargränssnittet, tillsammans med hur dessa segment fungerade i förhållande till era erbjudanden eller upplevelser. Rapporten Viktiga attribut innehåller de 100 viktigaste besökarattributen och deras relativa betydelse, medan användargränssnittet endast innehåller de 10 viktigaste besökarattributen.

**Kan jag se personaliseringsinsikter för ett anpassat datumintervall?**

Insikter-rapportering om personalisering (både [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes]) är bara tillgängligt för fasta datumintervall: 15 dagar, 30 dagar, 45 dagar, 60 dagar och 90 dagar. Med dessa fasta datumintervall kan du [!UICONTROL Personalization Insights] använda tillräckligt många data för att minska sannolikheten för att du får insikter från ett kort mönster i din aktivitet. Du kan välja de här varaktigheterna för ett slutdatum (där dessa data är tillräckligt många för att aktiviteten ska klara varaktigheten).

**Hur [!UICONTROL Personalization Insights] skapas?**

[!UICONTROL Personalization Insights] skapas med en patentsökt teknik i Adobe som kallas MAGIX (Model Agnostic Global Interpretable Förklarations). Du kan läsa mer om MAGIX i Adobe forskningsteamets publicerade rapport på [webbplatsen](https://arxiv.org/abs/1706.07160)arXiv.org.

**Är [!UICONTROL Personalization Insights] det möjligt för intäktsbaserade modelleringsmål/primärt mål?**

För närvarande [!UICONTROL Personalization Insights] är endast tillgängligt för målaktiviteter för konverteringsoptimering. Vi kommer att lägga till stöd för intäktsoptimeringsmålaktiviteter i en kommande release.

**Vad är attributprioritetspoängen i rapporten Viktiga attribut?**

Prioritetspoängen i delen&quot;Attributprioritet rankning&quot; i rapporten innehåller information om vilka variabler algoritmen använde för att lära sig var viktigast när den bestämde hur alla besökare skulle delas upp i de segment som den identifierade. Det tilldelade ett procentvärde till de 100 översta attributen som används av modellen.

**Varför får vissa erbjudanden/upplevelser med en lägre konverteringsgrad större trafik jämfört med andra erbjudanden/upplevelser för ett visst automatiserat segment?**

Det finns flera möjliga orsaker till varför du kan se fler besök i ett erbjudande/en upplevelse med lägre konverteringsgrad inom ett automatiserat segment, bland annat:

* Ett litet antal vyer för vissa eller alla erbjudanden/upplevelser för ett visst automatiserat segment.
* Aktiviteter i mindre volymer där vissa erbjudanden eller upplevelser inte har några modeller.
* Aktiviteter i mindre volymer där modeller tidigare byggdes för vissa erbjudanden/upplevelser än andra. Anta till exempel att ytterligare en modell skapades dag 22 och att du tittar på data från dag 10-24.
* Skräddarsy regler för ett specifikt erbjudande som begränsar vilka besökare som kan se vilka erbjudanden/upplevelser som finns.
* Det finns inga konfidensintervall för insiktsrapporteringen. Men om konverteringsgraden är tillräckligt hög kan modellen generera trafik så att den är högre i punktbeloppet, men de är inte &quot;statistiskt olika&quot; siffror.

Det kan vara bra att veta hur modellen fungerar som en trafiktjänst. Var och en får sin tjänst baserat på sin totala profil. Insikterna-rapporterna generaliserar dock det här beteendet så att det blir lättare att tolka av en människa. Därför utesluter inte segment varandra. Detta kan leda till att enskilda segment visar den här typen av beteende eftersom samma person kan visas i flera segment.

**Hur kan jag utnyttja informationen i personaliseringsinsikter på olika sätt?**

* Upptäck nya målgrupper att inrikta sig på: Om du ser ett visst automatiserat segment som fungerar särskilt bra kan du skapa en målgrupp så att du kan återanvända det segmentet i andra rapporter.
* Testa era hypoteser om vilken typ av besökare som kommer att svara på vilken av era upplevelser.
* Ta reda på vilket innehåll som fungerade för vilka typer av besökare: Vilka erbjudanden som låg till grund för besökarnas lyft.
* Identifiera underpresterande innehåll.
* Förstå vilka attribut som var viktigast för hur modellen lärde sig.
* Se vilka attribut som används i personaliseringsmodellerna och hur viktiga de är.
* Identifiera möjligheter för ytterligare datapunkter som ni kan skicka till Target för att ytterligare informera er personalisering.