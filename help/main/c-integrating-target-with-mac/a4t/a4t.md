---
keywords: a4t;analytics;analytics;analytics for target;analytics reporting source;adobe analytics as reporting source for target;atjs;at.js;adobe experience platform web sdk;platform web sdk;platform sdk
description: Använd  [!DNL Analytics] for [!DNL Target] (A4T) om du vill skapa aktiviteter baserade på  [!DNL Analytics] konverteringsvärden och målgruppssegment och använda  [!DNL Analytics] rapporter om du vill undersöka resultatet.
title: Vad är  [!DNL Analytics] för [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: e45ac15a60c83e35b8b2b2ba29a42727faf746df
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 0%

---

# [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T)

[!DNL Adobe Analytics for Target] (A4T) är en integrering med flera lösningar som gör att du kan skapa aktiviteter baserade på [!DNL Analytics] konverteringsvärden och målgruppssegment. Med A4T-integreringen kan du använda [!DNL Analytics]-rapporter för att undersöka dina resultat. Om du använder [!DNL Analytics] som rapportkälla för en aktivitet, baseras all rapportering och segmentering för den aktiviteten på [!DNL Analytics]-datainsamling.

## Ökning {#section_92B66069210C40DBA937790E8CC596CF}

Integrationen [!DNL Analytics for Target] mellan [!DNL Analytics] och [!DNL Target] ger kraftfulla analys- och tidsbesparande verktyg för optimeringsprogrammet.

De tre viktigaste fördelarna med att använda [!DNL Analytics]-data i [!DNL Target] är:

* Marknadsförarna kan när som helst tillämpa [!DNL Analytics]-framgångsmått eller rapportsegment på [!DNL Target]-aktivitetsrapporter. Du behöver inte ange allt innan du kör aktiviteten.
* En enda datakälla eliminerar den varians som uppstår när data samlas in i två olika system.
* Din befintliga [!DNL Analytics]-implementering samlar in alla nödvändiga data. Det finns ingen anledning att implementera mbox på sidor enbart i syfte att samla in data för rapporter.

Om du använder [!DNL Analytics] som rapportkälla för en aktivitet, baseras alla rapporter och segmenteringar för den aktiviteten på [!DNL Analytics].

Alla [!DNL Analytics]-mått, inklusive beräknade värden, är tillgängliga i [!DNL Target] och rapporten [!UICONTROL Target Activities] i [!DNL Analytics], med ett undantag. Beräknade mått för [!UICONTROL Lift & Confidence] stöds inte. På samma sätt kan alla segment som är tillgängliga i [!DNL Analytics] användas för båda lösningarna. Du kan tillämpa måttet eller målgruppen på rapporten om [!DNL Target] efter att aktiviteten har startats, eller till och med efter att aktiviteten har slutförts.

Alla mått inkluderas, inklusive anpassade eller beräknade värden som är inbyggda i [!DNL Analytics].

Efter klassificeringsperioden visas data i dessa rapporter ungefär en timme efter det att de samlats in från webbplatsen. Alla mätvärden, segment och värden i rapporterna kommer från den rapportsserie du valde när du konfigurerade aktiviteten.

Tänk på följande när du ska använda A4T:

* Om du vill använda [!DNL Analytics] som rapportkälla för [!DNL Target] måste både du och ditt företag ha tillgång till [!DNL Analytics] och till [!DNL Target]. [Kontakta din kontorepresentant](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) om du behöver någon av lösningarna.
* Rapporteringskällan anges för varje aktivitet. [!DNL Target] fortsätter att samla in data som ska användas för rapportering och [!DNL Target] data är fortfarande tillgängliga om du föredrar att basera en aktivitet på data som samlats in av [!DNL Target].
* Använd en rapportkälla eller en annan. Du kan inte samla in data för en enskild aktivitet från båda källor.
* När du använder A4T är alla framgångsmått som är tillgängliga för dina aktiviteter [!DNL Analytics]-värden. Måttet för ditt mål kan dock baseras på ett mbox-anrop om at.js används. Du kan t.ex. använda Target-funktionen för klick-spårning som är klar att användas med A4T i stället för att behöva implementera [!DNL Analytics] klick-tracking-kod.
* När du visar rapporter om en A4T-aktivitet i användargränssnittet för [!DNL Target] visar du [!DNL Analytics]-data. Om du till exempel använder måttet [!UICONTROL Visitor] i [!DNL Target] använder du måttet [!DNL Analytics] [!UICONTROL Visitor], inte måttet [!DNL Target] [!UICONTROL Visitors] som nu kallas [!UICONTROL Entrants]. Den här skillnaden är särskilt viktig för grundläggande trafikstatistik ([!UICONTROL Visitors], [!UICONTROL Visits], [!UICONTROL Page Views]) och konverteringsmått.
* Befintliga [!DNL Target]-aktiviteter fortsätter att använda datainsamlingen [!DNL Target] och påverkas inte av A4T-aktivering.
* Endast ett mbox-baserat mått tillåts när A4T används.
* Ett server-till-server-anrop från [!DNL Target] till [!DNL Analytics] skickar aktivitets- och upplevelseinformation till [!DNL Analytics]. Integrationen resulterar inte i extra serveranrop för [!DNL Target] eller [!DNL Analytics].

  I vissa situationer misslyckas klassificeringarna från [!DNL Target] till [!DNL Analytics] och aktiviteterna visar inte data i [!DNL Analytics]. Se [Felsöka integreringen med Analytics och Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Du kan även [kontakta kundtjänst](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) om du behöver mer hjälp.

## Implementera A4T

Mer information om hur du implementerar A4T med at.js och [!DNL Adobe Experience Platform Web SDK] finns i [Analytics for [!DNL Target] implementation](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Aktivitetstyper som stöds {#section_F487896214BF4803AF78C552EF1669AA}

Följande avsnitt innehåller information om vilka aktivitetstyper som stöds när du använder [!DNL Adobe Experience Platform Web SDK] eller at.js:

| Typ av aktivitet | A4T-kompatibel? | Anteckningar, om tillämpligt |
|--- |--- |--- |
| [A/B-aktivitet med manuell trafikdelning](/help/main/c-activities/t-test-ab/test-ab.md) | Ja |  |
| [A/B-aktivitet med Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Ja | Se [Stöd för A4T för aktiviteter som Automatisk allokering och Automatisk målning](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md). |
| [A/B-aktivitet med Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Ja | A4T-stöd för Automatisk målaktivitet stöds nu för både [!DNL Platform Web SDK] och at.js. |
| [Experience Targeting (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Ja |  |
| [Multivariata tester (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Ja | Kräver mbox-baserat målmåttsmål för att få fram rapporten [!UICONTROL Element Contribution]. Rapporten [!UICONTROL Element Contribution] stöder för närvarande inte [!DNL Analytics]-mått. |
| [Automated Personalization-aktivitet (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Nej |  |
| [Rekommendationsaktivitet](/help/main/c-recommendations/recommendations.md) | Ja |  |
| [Alla aktiviteter som använder ett omdirigeringserbjudande](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Ja |  |

Eftersom alla aktivitetstyper ännu inte har stöd för A4T rekommenderar vi att du behåller eller implementerar viktiga konverteringsrutor, som mbox `orderConfirmPage`.

## Exempel på A4T-rapporter {#section_F0A43A1CB2F04E8282B909E4D7034361}

Om du vill visa A4T-rapporter i [!DNL Target] klickar du på **[!UICONTROL Activities]**, klickar på önskad aktivitet i listan som använder [!DNL Analytics] som rapportkälla och klickar sedan på fliken **[!UICONTROL Reports]**.

>[!NOTE]
>
>Du kan använda listrutan [!UICONTROL Reporting Source] högst upp på sidan [!UICONTROL Activities] om du bara vill visa aktiviteter som använder A4T.

Du kan växla mellan [!UICONTROL Table View] och [!UICONTROL Graph View] för rapporten genom att klicka på lämplig ikon i rapportens övre högra hörn.

Följande bild visar [!UICONTROL Graph View] i en A4T-rapport med listrutan [!UICONTROL Report Metric] som visar tillgängliga [!DNL Analytics] målmått:

![a4t_report_graph1 image](assets/a4t_report_graph1.png)

Följande bild visar [!UICONTROL Graph View] i en A4T-rapport med listrutan [!UICONTROL Audience] som visar tillgängliga [!DNL Analytics] målgrupper:

![a4t_report_graph2 image](assets/a4t_report_graph2.png)

Följande bild visar [!UICONTROL Table View] för en A4T-rapport:

![a4t_report_table image](assets/a4t_report_table.png)

Om du vill visa rapporten i [!DNL Analytics] i stället för i [!DNL Target] klickar du på **[!UICONTROL View in Analytics]** längst upp i rapporten.

## Analytics &amp; Target: Best Practices for Analysis Tutorial {#section_3438E6E77A464424B717A4FD333B84B2}

Öppna självstudiekursen [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), som tillhandahålls av [!DNL Adobe Experience League].

## Utbildningsvideor:

I följande videofilmer finns mer information om de begrepp som beskrivs i det här avsnittet.

### Analyser för Adobe Target (A4T) (4:32) ![Märket Översikt](/help/main/assets/overview.png)

I den här videon förklaras hur du använder [!DNL Analytics] som rapportkälla i [!DNL Target] för att analysera optimeringsprogrammet.

* Förklara vad A4T är och varför du ska använda det
* Förklara hur A4T fungerar
* Förstå de krav som krävs innan A4T används

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analys/Adobe Target-integrering (A4T) (40:33) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon är en inspelning av [Kontorstid](/help/main/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7), ett initiativ som leds av Adobe kundtjänstteam.

* Konfigurera och verifiera att integreringen fungerar
* Hur integreringen fungerar
* Läs mer om de idealiska rapporterna som ska användas i Analytics
* Svar på vanliga frågor om A4T

[Kontorstimmar för analys/målintegrering (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* [Analys för  [!DNL Target] implementering](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md): Innehåller implementeringsinformation för at.js och Platform Web SDK.
>* [Omdirigeringserbjudanden - Vanliga frågor om A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
>* [Vad är Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html): Innehåller översiktsinformation om Platform Web SDK.
>* [Målöversikt](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html): Innehåller information som är specifik för [!DNL Target] och [!DNL Platform Web SDK].
