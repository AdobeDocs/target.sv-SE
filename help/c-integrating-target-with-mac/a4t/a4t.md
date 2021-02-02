---
keywords: a4t;analytics;analytics for target;analytics reporting source;adobe analytics as reporting source for target
description: Adobe"Analytics for Target" (A4T) är en integrerad lösning som gör att ni kan skapa aktiviteter baserat på analysstatistik om konvertering och målgruppssegment. Tack vare den här integreringen kan ni använda Analytics-rapporter för att undersöka era resultat. Om du använder Analytics som rapportkälla för en aktivitet, baseras all rapportering och segmentering för den aktiviteten på insamling av analysdata.
title: Adobe Analytics som rapportkälla (A4T)
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 0%

---


# Adobe Analytics som rapportkälla för Adobe Target (A4T)

[!DNL Adobe Analytics for Target] (A4T) är en integrerad lösning som gör att ni kan skapa aktiviteter baserat på  [!DNL Analytics] konverteringsstatistik och målgruppssegment. Med A4T-integreringen kan du använda [!DNL Analytics]-rapporter för att undersöka dina resultat. Om du använder [!DNL Analytics] som rapportkälla för en aktivitet, baseras all rapportering och segmentering för den aktiviteten på [!DNL Analytics]-datainsamling.

## A4T översikt {#section_92B66069210C40DBA937790E8CC596CF}

Integrationen [!DNL Analytics for Target] mellan [!DNL Analytics] och [!DNL Target] ger kraftfulla analys- och tidsbesparande verktyg för optimeringsprogrammet.

De tre viktigaste fördelarna med att använda [!DNL Analytics]-data i [!DNL Target] är:

* Marknadsförarna kan när som helst tillämpa [!DNL Analytics]-framgångsmått eller rapporteringssegment dynamiskt i [!DNL Target]-aktivitetsrapporter. Du behöver inte ange allt innan du kör aktiviteten.
* En enda datakälla eliminerar den varians som uppstår när data samlas in i två olika system.
* Din befintliga [!DNL Analytics]-implementering samlar in alla nödvändiga data. Det finns ingen anledning att implementera mbox på sidor enbart i syfte att samla in data för rapporter. Även om vi fortfarande rekommenderar att du implementerar en orderbekräftelseruta för [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP)-aktiviteter.

>[!IMPORTANT]
>
>Innan du kan börja använda A4T måste du begära att ditt konto etableras för integreringen. Använd [det här formuläret](https://www.adobe.com/go/audiences) för att begära att bli etablerad.
>
>Integrationen som aktiverar [!DNL Analytics] som datakälla för [!DNL Target] (A4T) representerar nästa generation av plugin-programmet Test&amp;Target till SiteCatalyst. Detta plugin-program har tagits bort, men stöds fortfarande för kunder som redan använder det.

Om du använder [!DNL Analytics] som rapportkälla för en aktivitet, baseras alla rapporter och segmenteringar för den aktiviteten på [!DNL Analytics].

Alla [!DNL Analytics]-mått, inklusive beräknade värden, är tillgängliga i [!DNL Target] och i [!UICONTROL Target Activities]-rapporten i [!DNL Analytics]. På samma sätt kan alla segment som är tillgängliga i [!DNL Analytics] användas för båda lösningarna. Du kan använda måttet eller målgruppen för rapporten om [!DNL Target] efter att aktiviteten har startats, eller till och med efter att aktiviteten har slutförts.

Alla mätvärden inkluderas, inklusive alla kundvärden eller beräknade värden som är inbyggda i [!DNL Analytics].

Efter klassificeringsperioden visas data i dessa rapporter ungefär en timme efter det att de samlats in från webbplatsen. Alla mätvärden, segment och värden i rapporterna kommer från den rapportsserie du valde när du konfigurerade aktiviteten.

Tänk på följande när du funderar på att använda A4T:

* Om du vill använda [!DNL Analytics] som rapporteringskälla för [!DNL Target] måste både du och ditt företag ha tillgång till [!DNL Analytics] och till [!DNL Target]. [Kontakta din kontorepresentant ](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) om du behöver någon av lösningarna.
* Rapporteringskällan anges för varje aktivitet. [!DNL Target] fortsätter att samla in data som ska användas vid rapportering och  [!DNL Target] data är fortfarande tillgängliga om du föredrar att basera en aktivitet på data som samlats in av  [!DNL Target].
* Du måste använda en rapportkälla eller en annan. Du kan inte samla in data för en enskild aktivitet från båda källor.
* När du använder A4T är alla framgångsmått som är tillgängliga för dina aktiviteter [!DNL Analytics]-mått. Måttet för ditt mål kan dock baseras på ett mbox-anrop. Du kan till exempel använda Target-funktionen för klick-spårning som är klar att användas med A4T i stället för att behöva implementera [!DNL Analytics] klickspårningskod.
* När du visar rapporter om en A4T-aktivitet i [!DNL Target]-gränssnittet visar du [!DNL Analytics]-data. Om du till exempel använder måttet [!UICONTROL Visitor] i [!DNL Target] använder du måttet [!DNL Analytics] [!UICONTROL Visitor], inte [!DNL Target] [!UICONTROL Visitors], som nu kallas [!UICONTROL Entrants]. Den här skillnaden är särskilt viktig för grundläggande trafikstatistik ([!UICONTROL Visitors], [!UICONTROL Visits], [!UICONTROL Page Views]) och konverteringsmått.
* Alla befintliga [!DNL Target]-aktiviteter fortsätter att använda [!DNL Target]-datainsamling och påverkas inte av att A4T aktiveras.
* Endast ett mbox-baserat mått tillåts när [!DNL Analytics] används som rapportkälla.
* Ett server-till-server-anrop från [!DNL Target] till [!DNL Analytics] skickar aktivitets- och upplevelseinformation till [!DNL Analytics]. Integrationen resulterar inte i ytterligare serveranrop för antingen [!DNL Target] eller [!DNL Analytics].

   I vissa situationer kan klassificeringsanropet från [!DNL Target] till [!DNL Analytics] misslyckas och aktiviteter visar inte data i [!DNL Analytics]. Om detta inträffar, se [Felsöka integreringen med Analytics och Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Du kan även [kontakta kundtjänst](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) om du behöver mer hjälp.

## Aktivitetstyper som stöds {#section_F487896214BF4803AF78C552EF1669AA}

I följande tabell visas vilka aktivitetstyper som stöder [!DNL Analytics] som rapportkälla i [!DNL Target] (A4T):

| Typ av aktivitet | A4T-kompatibel? | Anteckningar, om tillämpligt |
|--- |--- |--- |
| A/B-aktivitet med manuell trafikdelning | Ja |  |
| A/B-aktivitet med automatisk fördelning | Ja | Se [Stöd för A4T för Automatisk allokering och Automatisk målaktiviteter](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) |
| A/B-aktivitet med automål | Ja | Se [A4T-stöd för aktiviteterna Automatisk allokering och Automatisk målning](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md). |
| Experience Targeting (XT) | Ja |  |
| Multivariata tester (MVT) | Ja | Kräver mbox-baserat målmätningsmål för att hämta [!UICONTROL Element Contribution]-rapporten.  [!UICONTROL Element Contribution]-rapporten stöder för närvarande inte [!DNL Analytics]-mått. |
| Automated Personalization-aktivitet (AP) | Nej |  |
| Recommendations-aktivitet | Ja |  |
| Mobilapp | Ja | Stöds med Mobile Services SDK, version 4.13.1 eller senare.  Mer information finns i [Mobile Services-dokumentationen](https://experienceleague.adobe.com/docs/mobile-services/using/home.html). |
| E-post | Nej |  |
| Leverans-API på serversidan | Ja | Mer information finns i [Serversida: implementera Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| NodeJS SDK | Ja | Mer information finns i [Serversida: implementera Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| AEM 6.1 (eller tidigare) Cloud Service Integration | Nej |  |
| AEM 6.2 (eller senare) Cloud Service Integration | Ja | Mer information finns i [Integrera med Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) i dokumentationen för [!DNL Adobe Experience Manager] 6.2. |
| Alla aktiviteter som använder ett omdirigeringserbjudande | Ja | Det finns strängare minimikrav för användning av omdirigeringserbjudanden med A4T. Mer information finns i [Omdirigeringserbjudanden - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Ja | Mer information finns i [Node.js SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/nodejs-sdk) i guiden *Adobe Target SDK*. |
| Java SDK | Ja | Mer information finns i [Java SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/java-sdk) i guiden för *Adobe Target* SDK:er. |

Eftersom alla aktivitetstyper ännu inte har stöd för A4T rekommenderar vi att du behåller eller implementerar viktiga konverteringsrutor, till exempel `orderConfirmPage`-rutan.

## Exempel på A4T-rapporter {#section_F0A43A1CB2F04E8282B909E4D7034361}

Om du vill visa A4T-rapporter i [!DNL Target] klickar du på **[!UICONTROL Activities]**, klickar på önskad aktivitet i listan som använder [!DNL Analytics] som rapportkälla och klickar sedan på fliken **[!UICONTROL Reports]**.

>[!NOTE]
>
>Du kan använda listrutan [!UICONTROL Reporting Source] högst upp på [!UICONTROL Activities]-sidan för att visa endast aktiviteter som använder [!DNL Analytics] som rapportkälla.

Du kan växla mellan [!UICONTROL Table View] och [!UICONTROL Graph View] för rapporten genom att klicka på lämplig ikon längst upp till höger i rapporten.

Följande bild visar [!UICONTROL Graph View] för en A4T-rapport med listrutan [!UICONTROL Report Metric] som visar tillgängliga [!DNL Analytics]-målmått:

![](assets/a4t_report_graph1.png)

Följande bild visar [!UICONTROL Graph View] för en A4T-rapport med listrutan [!UICONTROL Audience] som visar tillgängliga [!DNL Analytics]-målgrupper:

![](assets/a4t_report_graph2.png)

Följande bild visar [!UICONTROL Table View] för en A4T-rapport:

![](assets/a4t_report_table.png)

Om du vill visa rapporten i [!DNL Analytics] i stället för i [!DNL Target] klickar du på **[!UICONTROL View in Analytics]** längst upp i rapporten.

## Analytics &amp; Target: Självstudiekursen om metodtips för analys {#section_3438E6E77A464424B717A4FD333B84B2}

Öppna [Analytics &amp; Target: Självstudiekursen Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), som tillhandahålls av [!DNL Adobe Experience League].

## Utbildningsvideor:

I följande videofilmer finns mer information om de begrepp som beskrivs i det här avsnittet.

### Analyser för mål (A4T) (4:32) ![Översikt](/help/assets/overview.png)

I den här videon förklaras hur du använder [!DNL Analytics] som rapportkälla i [!DNL Target] för att analysera optimeringsprogrammet.

* Förklara vad A4T är och varför du ska använda det
* Förklara hur A4T fungerar
* Förstå de krav som krävs innan A4T används

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analys/målintegrering (A4T) (40:33) ![Självstudiemärke](/help/assets/tutorial.png)

Den här videon handlar om inspelningen av &quot; [kontorstid](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)&quot;, ett projekt som leds av kundtjänstteamet på Adobe.

* Konfigurera och verifiera att integreringen fungerar
* Hur integreringen fungerar
* Läs mer om de idealiska rapporterna som ska användas i Analytics
* Svar på vanliga frågor om A4T

[Kontorstimmar för analys/målintegrering (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)