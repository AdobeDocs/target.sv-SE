---
keywords: Målgruppsanpassning;AP-rapporter;automatiserade personaliseringsrapporter;auto target;auto target;auto target report;auto target report;personalization;insights;faq;Vanliga frågor;viktiga attribut
description: Lär dig hur du använder rapporten [!UICONTROL Important Attributes] som visar de viktigaste attributen som påverkade personaliseringsmodellen och deras relativa betydelse.
title: Vilken är den viktiga attributrapporten?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Reports
exl-id: c1069ca7-e221-4865-a82e-6cff5b4c0055
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '1773'
ht-degree: 0%

---

# Viktiga attributrapporter

Information om rapporten [!UICONTROL Important Attributes], en av de två specialiserade rapporterna som är tillgängliga för användare av [!UICONTROL Automated Personalization]- (AP) och [!UICONTROL Auto-Target] (AT)-aktiviteter.

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

I olika aktiviteter är olika attribut viktigare eller mindre viktiga för hur modellen bestämmer sig för att personalisera. Den här rapporten visar de viktigaste attributen som påverkade modellen och deras relativa betydelse.

## Öppna rapporten [!UICONTROL Important Attributes] {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Klicka på **[!UICONTROL Activities]** och sedan på önskad aktivitet för [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) i listan.

   Om du har många aktiviteter klickar du på ikonen Filter ( ![Filterikon](/help/main/assets/icons/Filter.svg) ) för att filtrera listan genom att välja alternativ i listrutorna [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] och [!UICONTROL Activity Source] .

1. Klicka på **[!UICONTROL Reports]**.

   Rapporten [Automated Personalization Summary](/help/main/c-reports/personalization-reports/reports-ap.md) eller [Auto-Target Summary](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) visas, som innehåller information om hur dina aktiviteter fungerar, vilket representeras av ikonen för första skärmen. De två extra ikonerna representerar de två [!UICONTROL Personalization Insights]-rapporterna: **[!UICONTROL Automated Segments]** ( ![rapporten Automatiska segment &#x200B;](/help/main/assets/icons/AutomatedSegment.svg) ) och **[!UICONTROL Important Attributes]** ( ![ikonen Viktiga attribut](/help/main/assets/icons/ViewList.svg) ).


   Observera att [!UICONTROL Auto-Target] har en extra diagramikon för den grafiska vyn i rapporten [!UICONTROL Summary].

   >[!IMPORTANT]
   >
   >[!UICONTROL Important Attributes]-rapporten är inte tillgänglig förrän minst 15 dagar efter att du har aktiverat aktiviteten. Under den inledande perioden kommer du inte att kunna komma åt den här rapporten eller klicka på ikonen [!UICONTROL Important Attributes]. Efter 15 dagar är [!UICONTROL Important Attributes]-rapporten tillgänglig, förutsatt att det finns tillräckligt med personaliserad trafik i din aktivitet.

1. Efter 15 dagar från det att aktiviteten har aktiverats klickar du på ikonen **[!UICONTROL Important Attributes]** ( ![Viktiga attribut &#x200B;](/help/main/assets/icons/ViewList.svg) ).

1. Välj önskat datumintervall.

   Till skillnad från rapporten [!UICONTROL Summary] (prestandarapportering) är [!UICONTROL Personalization Insights], inklusive [!UICONTROL Important Attributes], bara tillgängligt för fasta datumintervall: 15 dagar, 30 dagar och 60 dagar.

   Med dessa fasta datumintervall kan [!UICONTROL Personalization Insights] använda tillräckligt många data för att minska sannolikheten för att du får insikter från ett kort mönster i din aktivitet. De två beslut som du kan fatta för datumintervallet är&quot;Slutdatum&quot; och&quot;Varaktighet&quot;. Du kommer att märka att &quot;Start&quot; är nedtonat. Startdatumet ändras automatiskt baserat på dina val för slutdatumet och varaktigheten.

   Du kommer åt de tillgängliga fasta datumintervallen i listrutan [!UICONTROL Preset Date Range].

1. Granska rapportdata för [!UICONTROL Important Attributes].

1. (Valfritt) Klicka på ikonen Hämta ( ![ikonen Hämta](/help/main/assets/icons/Download.svg) ) för att [hämta rapporten i CSV-format](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) för analys i Excel och andra verktyg.

   >[!NOTE]
   >
   >Personalization Insights-gränssnittsrapporten innehåller urvalsinformation. CSV-nedladdningen för rapporten Viktiga attribut innehåller ytterligare information. Nedladdningen av rapporten Viktiga attribut innehåller en fullständig lista över de 100 viktigaste attributen, medan rapporten för användargränssnittet endast innehåller de 10 översta. Om du letar efter ett specifikt attribut i rapporten men inte finns där, betyder det inte att attributet inte påverkade aktiviteten, utan bara inte listan för de 100 viktigaste attributen.

## Tolka rapporten Viktiga attribut

I följande tabell beskrivs hur du tolkar rapporten och dess element:

| Element | Information |
|--- |--- |
| Stolpdiagram | Med det flerfärgade stapeldiagrammet längst upp på skärmen kan du visualisera dessa relativa prioritetsklasser och mappa till punktens färg bredvid respektive attribut i tabellen. Du kan också hovra över en viss färg i stapeldiagrammet för att se vilket attribut det representerar.  Viktigt-poängen för de 100 översta attributen ökar till 100 %. Mer information om hur du lägger till fler attribut som kan användas av målets personaliseringsmodeller finns i [Överföra data för målets Personalization-algoritmer](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md). |
| Modellattribut - rangordningsdiagram | Model Attribute Ranking innehåller de 10 viktigaste attributen som var viktigast för hur Target personaliseringsmodell bestämde vilket innehåll som skulle visas för varje besökare. Viktigt-poängen visar, i förhållande till de 100 viktigaste attributen, hur viktigt ett specifikt attribut var för Target personaliseringsmodeller i den här aktiviteten. |

## Vanliga frågor om viktiga attribut {#section_740910A52FA646B4AC9452F98C2F5719}

I följande vanliga frågor och svar hittar du svar på vanliga frågor om hur du använder rapporten [!UICONTROL Important Attributes].

### Personalization Insights-rapporter är ännu inte tillgängliga för min aktivitet. Varför är det så?

Det finns flera orsaker till varför [!UICONTROL Personalization Insights]-rapporterna kanske inte är tillgängliga för din aktivitet än:

* 15 dagar har inte gått sedan du aktiverade aktiviteten. Automatiserade segment och viktiga attributrapporter är inte tillgängliga förrän tidigast 15 dagar efter att du har påbörjat aktiviteten. Under den inledande perioden kommer du inte att kunna komma åt dessa rapporter eller klicka på ikonerna Automatiserade segment och Viktiga attribut.
* Din aktivitet har inte haft tillräckligt med trafik under den angivna tidsramen. Efter 15 dagar har det gått, förutsatt att din aktivitet har [tillräcklig personlig trafik](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB) för att skapa personaliseringsmodeller, kommer rapporter om automatiska segment och viktiga attribut att vara tillgängliga.
* Din aktivitet har ett intäktsoptimeringsmål. För närvarande är [!UICONTROL Personalization Insights] bara tillgängligt för målaktiviteter för konverteringsoptimering. Vi kommer att lägga till stöd för intäktsoptimeringsmålaktiviteter i en kommande release.

### Vad är ett attribut?

Ett attribut är information om en besökare eller hans eller hennes specifika besök som används av personaliseringsalgoritmerna för att lära sig att personalisera trafik. Ett attribut kan till exempel vara webbläsartyp, plats, tidpunkt på besöksdagen och så vidare.

Mer information om vilka attribut [!DNL Target] använder i sina anpassningsmodeller finns i [Datainsamling för Target&#39;s Personalization Algorithms](/help/main/c-activities/t-automated-personalization/ap-data.md). Mer information om hur du överför nya attribut till Target för användning i Target-personaliseringsmodeller finns i [Metoder för att hämta data till Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=sv-SE){target=_blank}.

### Jag ser ett eller flera attribut som jag inte vill att modellen ska använda för utbildning. Kan jag ta bort dessa attribut från utbildningsmodellen? {#models-api}

Med [!UICONTROL Models API], som även kallas Blockeringslista API, kan användare visa och hantera listan med attribut (som också kallas funktioner) som används i maskininlärningsmodeller för [!UICONTROL Automated Personalization]- (AP) och [!UICONTROL Auto-Target] (AT)-aktiviteter. Om du vill utesluta ett eller flera attribut från att användas av modellerna för AP- eller AT-aktiviteter kan du använda API:t för modeller för att lägga till dessa attribut i blockeringslista.

Mer information finns i [Översikt över API:t för modeller](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html?lang=sv-SE){target=_blank} i *Adobe Target Developer Guide*. Information om hur du använder API:t för att blockera attribut finns i [Models API](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api-overview.html?lang=sv-SE){target=_blank}.

### Är informationen i [!UICONTROL Automated Segments]- och [!UICONTROL Important Attributes]-rapporterna densamma som i CSV-nedladdningen?

Nej, UI-rapporten innehåller urvalsinformation. CSV-nedladdningen innehåller ytterligare information. Nedladdningen av rapporten Automated Segment Insights innehåller ytterligare automatiserade segment utöver de främsta segmenten som ingår i användargränssnittet, tillsammans med hur dessa segment fungerade i förhållande till era erbjudanden eller upplevelser. Rapporten Viktiga attribut innehåller de 100 viktigaste besökarattributen och deras relativa betydelse, medan användargränssnittet endast innehåller de 10 viktigaste besökarattributen.

### Kan jag se Personalization Insights för ett anpassat datumintervall?

Personalization Insights-rapportering (både [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes]) är bara tillgängligt för fasta datumintervall: 15 dagar, 30 dagar, 45 dagar, 60 dagar och 90 dagar. Med dessa fasta datumintervall kan [!UICONTROL Personalization Insights] använda tillräckligt många data för att minska sannolikheten för att du får insikter från ett kort mönster i din aktivitet. Du kan välja de här varaktigheterna för ett slutdatum (där dessa data är tillräckligt många för att aktiviteten ska klara varaktigheten).

### Hur skapas [!UICONTROL Personalization Insights]?

[!UICONTROL Personalization Insights] har skapats med en patentsökt Adobe-teknik som heter MAGIX (Model Agnostic Global Interpretable Förklarings). Du kan läsa mer om MAGIX i Adobe forskningsgrupps publicerade rapport på webbplatsen [arXiv.org](https://arxiv.org/abs/1706.07160).

### Är [!UICONTROL Personalization Insights] tillgängligt för intäktsbaserade modelleringsmål/primärt mål?

För närvarande är [!UICONTROL Personalization Insights] bara tillgängligt för målaktiviteter för konverteringsoptimering. Vi kommer att lägga till stöd för intäktsoptimeringsmålaktiviteter i en kommande release.

### Vad är attributprioritetspoängen i rapporten Viktiga attribut?

Prioritetspoängen i delen&quot;Attributprioritet rankning&quot; i rapporten innehåller information om vilka variabler algoritmen använde för att lära sig var viktigast när den bestämde hur alla besökare skulle delas upp i de segment som den identifierade. Det tilldelade ett procentvärde till de 100 översta attributen som används av modellen.

### Varför får vissa erbjudanden/upplevelser med en lägre konverteringsgrad större trafik jämfört med andra erbjudanden/upplevelser för ett visst automatiserat segment?

Det finns flera möjliga orsaker till varför du kan se fler besök i ett erbjudande/en upplevelse med lägre konverteringsgrad inom ett automatiserat segment, bland annat:

* Ett litet antal vyer för vissa eller alla erbjudanden/upplevelser för ett visst automatiserat segment.
* Aktiviteter i mindre volymer där vissa erbjudanden eller upplevelser inte har några modeller.
* Aktiviteter i mindre volymer där modeller tidigare byggdes för vissa erbjudanden/upplevelser än andra. Anta till exempel att ytterligare en modell skapades dag 22 och att du tittar på data från dag 10-24.
* Skräddarsy regler för ett specifikt erbjudande som begränsar vilka besökare som kan se vilka erbjudanden/upplevelser som finns.
* Det finns inga konfidensintervall för insiktsrapporteringen. Men om konverteringsgraden är tillräckligt hög kan modellen generera trafik så att den är högre i punktbeloppet, men de är inte &quot;statistiskt olika&quot; siffror.

Det kan vara bra att veta hur modellen fungerar som en trafiktjänst. Varje enskild person får sin tjänst baserat på hans eller hennes totala profil. Insikterna-rapporterna generaliserar dock det här beteendet så att det blir lättare att tolka av en människa. Därför utesluter inte segment varandra. Detta kan leda till att enskilda segment visar den här typen av beteende eftersom samma person kan visas i flera segment.

### Hur kan jag utnyttja informationen i Personalization Insights på olika sätt?

* Upptäck nya målgrupper: Om du ser ett visst automatiserat segment som fungerar särskilt bra kan du skapa en målgrupp så att du kan återanvända det segmentet i andra rapporter.
* Testa era hypoteser om vilken typ av besökare som kommer att svara på vilken av era upplevelser.
* Ta reda på vilket innehåll som fungerade för vilka typer av besökare: vilka erbjudanden som ansvarade för besökarnas lyft.
* Identifiera underpresterande innehåll.
* Förstå vilka attribut som var viktigast för hur modellen lärde sig.
* Se vilka attribut som används i personaliseringsmodellerna och hur viktiga de är.
* Identifiera möjligheter för ytterligare datapunkter som ni kan skicka till Target för att ytterligare informera er personalisering.

## Kända fel

Följande problem utreds för närvarande av [!DNL Target]-tekniker.

* [!DNL Adobe Experience Platform] segmentnamn visas inte i [!UICONTROL Important Attributes]-rapporten för [!UICONTROL Automated Personalization]- (AP) och [!UICONTROL Auto-Target] (AT)-aktiviteter. (TOP-3813)
