---
keywords: Målgruppsanpassning;AP-rapporter;automatiserade personaliseringsrapporter;auto target;auto target;auto target report;auto target report;personalization;insights;faq;Vanliga frågor;viktiga attribut
description: Lär dig använda [!UICONTROL Important Attributes] som visar de viktigaste attributen som påverkade personaliseringsmodellen och deras relativa betydelse.
title: Vilken är den viktiga attributrapporten?
feature: Reports
exl-id: c1069ca7-e221-4865-a82e-6cff5b4c0055
source-git-commit: 79d51e39b733ee13270f924912251e45c8597917
workflow-type: tm+mt
source-wordcount: '1659'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Viktiga attributrapporter

Information om [!UICONTROL Important Attributes] rapport, en av de två specialrapporterna som är tillgängliga för användare av [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] (AT) verksamhet.

>[!NOTE]
>
>Tänk på följande när du använder [!UICONTROL Personalization Insights] rapporter:
>
>* AP- och AT-aktiviteter är tillgängliga som en del av [!DNL Target Premium] lösning. De ingår inte i [!DNL Target Standard] utan [!DNL Target Premium] licens.
>
>* [!UICONTROL Personalization Insights] rapporter är bara tillgängliga för AP- och AT-aktiviteter som använder ett konverteringsoptimeringsmål. Aktiviteter där optimeringsmålet ändrades till konvertering från intäkt efter att aktiviteten redan var aktiv stöds inte heller.
>
>* [!UICONTROL Personalization Insights] rapporter är bara tillgängliga om [!UICONTROL Primary Goal] är markerat på menyn [!UICONTROL Report Metric] nedrullningsbar lista.
>
>* [!UICONTROL Personalization Insights] rapporter stöds i [standardmiljö](/help/main/administrating-target/hosts.md) endast.
>
>* [!UICONTROL Personalization Insights] rapporter genereras bara för aktiviteter som finns i [!UICONTROL Live] status och har aktiverats och tagit emot trafik i minst 15 dagar.


I olika aktiviteter är olika attribut viktigare eller mindre viktiga för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.

## Öppna [!UICONTROL Important Attributes] rapport {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Klicka **[!UICONTROL Activities]** och klickar sedan på [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) från listan.

   Om du har många aktiviteter kan du filtrera listan genom att välja alternativ på menyn [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type]och [!UICONTROL Activity Source] nedrullningsbara listor.

1. Klicka på **[!UICONTROL Reports]**.

   The [Automated Personalization Summary](/help/main/c-reports/personalization-reports/reports-ap.md) eller [Automatisk målsammanfattning](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) visas, som innehåller information om hur dina aktiviteter fungerar, som representeras av ikonen för första skärmen. De två extra ikonerna representerar de två [!UICONTROL Personalization Insights] rapporter: [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes].

   ![Sammanfattningsrapport för Automated Personalization-aktivitet](/help/main/c-reports/assets/summary-report-ap.png)

   Observera att [!UICONTROL Auto-Target] har en extra diagramikon för den grafiska vyn i [!UICONTROL Summary] rapport.

   ![Sammanfattningsrapport för aktiviteten Automatiskt mål](/help/main/c-reports/assets/personalization_insights.png)

   >[!IMPORTANT]
   >
   >The [!UICONTROL Important Attributes] rapporten är inte tillgänglig förrän minst 15 dagar efter att du har aktiverat aktiviteten. Under den inledande perioden kan du inte komma åt den här rapporten eller klicka på [!UICONTROL Important Attributes] ikon. Efter 15 dagar, och förutsatt att det finns tillräckligt med personaliserad trafik i din verksamhet, har [!UICONTROL Important Attributes] rapporten är tillgänglig.

1. Efter 15 dagar från det att aktiviteten har aktiverats klickar du på **[!UICONTROL Important Attributes]** ikon.

   ![Viktiga attributikoner i en Adobe Target-rapport](/help/main/c-reports/assets/model_attribute_ranking.png)

1. Välj önskat datumintervall.

   Till skillnad från [!UICONTROL Summary] rapport (resultatrapportering), [!UICONTROL Personalization Insights], inklusive [!UICONTROL Important Attributes], är bara tillgängligt för fasta datumintervall: 15 dagar, 30 dagar och 60 dagar.

   >[!NOTE]
   >
   >The [!DNL Target] I användargränssnittet kan du välja datumintervall på 45 dagar och 90 dagar. Men [!DNL Target] I backend bearbetas inte dessa två intervall. På grund av användningsmönster och i ett försök att förbättra prestandan har datumintervallen tagits bort. Gränssnittet uppdateras för att återspegla de aktuella tillåtna intervallen: 15, 30 och 60 dagar.

   Dessa fasta datumintervall tillåter [!UICONTROL Personalization Insights] om du vill använda ett stort och tillräckligt stort dataområde för att minska sannolikheten för att ni får insikter från ett kort mönster i din aktivitet. De två beslut som du kan fatta för datumintervallet är&quot;Slutdatum&quot; och&quot;Varaktighet&quot;. Du kommer att märka att &quot;Start&quot; är nedtonat. Startdatumet ändras automatiskt baserat på dina val för slutdatumet och varaktigheten.

   ![Kalender i en Adobe Target-rapport](/help/main/c-reports/assets/personalization_insights_calendar_1.png)

   Du kan komma åt de tillgängliga fasta datumintervallen från [!UICONTROL Choose Duration] nedrullningsbar lista.

   ![Välj listrutan Varaktighet i en rapport](/help/main/c-reports/assets/personalization_insights_calendar_2.png)

1. Granska [!UICONTROL Important Attributes] rapportdata.

   ![Viktiga attributrapporter i Adobe Target](/help/main/c-reports/assets/model_attribute_ranking_report.png)

1. (Valfritt) [Ladda ned rapporten i CSV-format](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) för analys i Excel och andra verktyg.

   >[!NOTE]
   >
   >Användargränssnittsrapporten Personalization Insights innehåller urvalsinformation. CSV-nedladdningen för rapporten Viktiga attribut innehåller ytterligare information. Nedladdningen av rapporten Viktiga attribut innehåller en fullständig lista över de 100 viktigaste attributen, medan rapporten för användargränssnittet endast innehåller de 10 översta. Om du letar efter ett specifikt attribut i rapporten men inte finns där, betyder det inte att attributet inte påverkade aktiviteten, utan bara inte listan för de 100 viktigaste attributen.

## Tolka rapporten Viktiga attribut

I följande tabell beskrivs hur du tolkar rapporten och dess element:

| Element | Detaljer |
|--- |--- |
| Stolpdiagram | Med det flerfärgade stapeldiagrammet längst upp på skärmen kan du visualisera dessa relativa prioritetsklasser och mappa till punktens färg bredvid respektive attribut i tabellen. Du kan också hovra över en viss färg i stapeldiagrammet för att se vilket attribut det representerar.  Viktigt-poängen för de 100 översta attributen ökar till 100 %. Mer information om hur du lägger till fler attribut som kan användas i Target personaliseringsmodeller finns i [Överför data för målets anpassningsalgoritmer](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md). |
| Diagram över modellattribut | Model Attribute Ranking innehåller de 10 viktigaste attributen som var viktigast för hur Target personaliseringsmodell bestämde vilket innehåll som skulle visas för varje besökare. Viktigt-poängen visar, i förhållande till de 100 viktigaste attributen, hur viktigt ett specifikt attribut var för Target personaliseringsmodeller i den här aktiviteten. |

## Vanliga frågor om viktiga attribut {#section_740910A52FA646B4AC9452F98C2F5719}

**Personaliseringsinsikter - rapporter är inte tillgängliga än för min aktivitet. Varför det?**

Det finns flera skäl till att [!UICONTROL Personalization Insights] rapporter kanske inte är tillgängliga för din aktivitet ännu:

* 15 dagar har inte gått sedan du aktiverade aktiviteten. Automatiserade segment och viktiga attributrapporter är inte tillgängliga förrän tidigast 15 dagar efter att du har påbörjat aktiviteten. Under den inledande perioden kommer du inte att kunna komma åt dessa rapporter eller klicka på ikonerna Automatiserade segment och Viktiga attribut.
* Din aktivitet har inte haft tillräckligt med trafik under den angivna tidsramen. Efter 15 dagar har passerat, förutsatt att det finns [tillräcklig personlig trafik](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB) i din aktivitet för att skapa personaliseringsmodeller kommer rapporter om automatiserade segment och viktiga attribut att finnas tillgängliga.
* Din aktivitet har ett intäktsoptimeringsmål. För närvarande [!UICONTROL Personalization Insights] är bara tillgängligt för målaktiviteter för konverteringsoptimering. Vi kommer att lägga till stöd för intäktsoptimeringsmålaktiviteter i en kommande release.

**Vad är ett attribut?**

Ett attribut är information om en besökare eller hans eller hennes specifika besök som används av personaliseringsalgoritmerna för att lära sig att personalisera trafik. Ett attribut kan till exempel vara webbläsartyp, plats, tidpunkt på besöksdagen och så vidare.

Mer information om vilka attribut [!DNL Target] i sina personaliseringsmodeller, se [Datainsamling för målets personaliseringsalgoritmer](/help/main/c-activities/t-automated-personalization/ap-data.md). Mer information om hur du överför nya attribut till Target för användning i Target personaliseringsmodeller finns i [Metoder för att hämta data till Target](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}.

**Finns informationen i [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes] rapporterar samma som i CSV-nedladdningen?**

Nej, UI-rapporten innehåller urvalsinformation. CSV-nedladdningen innehåller ytterligare information. Nedladdningen av rapporten Automated Segment Insights innehåller ytterligare automatiserade segment utöver de främsta segmenten som ingår i användargränssnittet, tillsammans med hur dessa segment fungerade i förhållande till era erbjudanden eller upplevelser. Rapporten Viktiga attribut innehåller de 100 viktigaste besökarattributen och deras relativa betydelse, medan användargränssnittet endast innehåller de 10 viktigaste besökarattributen.

**Kan jag se personaliseringsinsikter för ett anpassat datumintervall?**

Insiktsrapportering för personalisering (båda [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes]) är bara tillgängligt för fasta datumintervall: 15 dagar, 30 dagar, 45 dagar, 60 dagar och 90 dagar. Dessa fasta datumintervall tillåter [!UICONTROL Personalization Insights] om du vill använda ett stort och tillräckligt stort dataområde för att minska sannolikheten för att ni får insikter från ett kort mönster i din aktivitet. Du kan välja de här varaktigheterna för ett slutdatum (där dessa data är tillräckligt många för att aktiviteten ska klara varaktigheten).

**Hur [!UICONTROL Personalization Insights] skapad?**

[!UICONTROL Personalization Insights] skapas med en patentsökt teknik i Adobe som kallas MAGIX (Model Agnostic Global Interpretable Förklarations). Du kan läsa mer om MAGIX i Adobe forskningsgruppens publicerade rapport på [arXiv.org webbplats](https://arxiv.org/abs/1706.07160).

**Är [!UICONTROL Personalization Insights] finns det för intäktsbaserade modelleringsmål/primärt mål?**

För närvarande [!UICONTROL Personalization Insights] är bara tillgängligt för målaktiviteter för konverteringsoptimering. Vi kommer att lägga till stöd för intäktsoptimeringsmålaktiviteter i en kommande release.

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
