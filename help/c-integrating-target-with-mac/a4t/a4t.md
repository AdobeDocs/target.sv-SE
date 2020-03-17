---
keywords: a4t;analytics;analytics for target;analytics reporting source;adobe analytics as the reporting source for target
description: Adobe"Analytics for Target" (A4T) är en integrerad lösning som gör att ni kan skapa aktiviteter baserat på analysstatistik om konvertering och målgruppssegment. Tack vare den här integreringen kan ni använda Analytics-rapporter för att undersöka era resultat. Om du använder Analytics som rapportkälla för en aktivitet, baseras all rapportering och segmentering för den aktiviteten på insamling av analysdata.
title: Adobe Analytics som rapportkälla för Adobe Target (A4T)
subtopic: Integrating
topic: Standard
uuid: 616798a6-1587-410f-9ac6-473beb39e3fc
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Adobe Analytics som rapportkälla för Adobe Target (A4T){#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

Adobe&quot;Analytics for Target&quot; (A4T) är en integrerad lösning som gör att ni kan skapa aktiviteter baserat på analysstatistik om konvertering och målgruppssegment. Med A4T-integreringen kan ni använda Analytics-rapporter för att undersöka era resultat. Om du använder Analytics som rapportkälla för en aktivitet, baseras all rapportering och segmentering för den aktiviteten på insamling av analysdata.

## A4T - översikt {#section_92B66069210C40DBA937790E8CC596CF}

Analytics för Target-integrering mellan Analytics och Target ger kraftfulla analyser och tidsbesparande verktyg för ert optimeringsprogram.

De tre främsta fördelarna med att använda analysdata i Target är:

* Marknadsförarna kan när som helst dynamiskt tillämpa analysresultat eller rapporteringssegment på Target-aktivitetsrapporter. Du behöver inte ange allt innan du kör aktiviteten.
* En enda datakälla eliminerar den varians som uppstår när data samlas in i två olika system.
* Din befintliga Adobe Analytics-implementering samlar in alla nödvändiga data. Det finns ingen anledning att implementera mbox på sidor enbart i syfte att samla in data för rapporter. Även om vi fortfarande rekommenderar att du implementerar en orderbekräftelseruta för aktiviteter inom Automated Personalization (AP).

>[!IMPORTANT]
>
>Innan du kan börja använda A4T måste du begära att ditt konto etableras för integreringen. Använd [det här formuläret](https://www.adobe.com/go/audiences) för att begära etablering.
>
>Integrationen som möjliggör Adobe Analytics som datakälla för Adobe Target (A4T) representerar nästa generation av plugin-programmet Test&amp;Target till SiteCatalyst. Detta plugin-program har tagits bort, men stöds fortfarande för kunder som redan använder det.

Om du använder Analytics som rapportkälla för en aktivitet, baseras alla rapporter och segmenteringar för den aktiviteten på Analytics.

Alla analysvärden, inklusive beräknade värden, finns i Target Standard/Premium och rapporten Target Activities i Analytics. På samma sätt kan alla segment som är tillgängliga i Analytics tillämpas på båda lösningarna. Du kan använda måttet eller målgruppen för rapporten i Target Standard/Premium när testet har startats, eller till och med efter att testet har slutförts.

Alla mätvärden ingår, inklusive alla kundvärden eller beräknade mätvärden som är inbyggda i Analytics.

Efter klassificeringsperioden visas data i dessa rapporter ungefär en timme efter det att de samlats in från webbplatsen. Alla mätvärden, segment och värden i rapporterna kommer från den rapportsserie du valde när du konfigurerade aktiviteten.

Tänk på följande när du funderar på att använda A4T:

* Om du vill använda Adobe Analytics som rapportkälla för Adobe Target måste både du och ditt företag ha tillgång till Adobe Analytics och Adobe Target. [Kontakta din kontorepresentant](../../cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) om du behöver någon av lösningarna.
* Rapporteringskällan anges för varje aktivitet. Target fortsätter att samla in data som ska användas för rapportering och Target-data är fortfarande tillgängliga om du föredrar att basera en aktivitet på data som samlats in av Target.
* Du måste använda en rapportkälla eller en annan. Du kan inte samla in data för en enskild aktivitet från båda källor.
* När du använder A4T är alla framgångsmått som är tillgängliga för dina aktiviteter analysvärden. Måttet för ditt mål kan dock baseras på ett mbox-anrop. Du kan t.ex. använda Target-funktionen för klick-spårning som är färdig med programmet med A4T i stället för att behöva implementera kod för klickspårning i Analytics.
* När du visar rapporter om en A4T-aktivitet i målgränssnittet, visar du analysdata. Om du till exempel använder Visitor-måttet i Target, använder du Analytics Visitor-mätvärdet, inte Target Visitors-mätvärdet, som nu kallas Entrants. Den här skillnaden är särskilt viktig för grundläggande trafikstatistik (besökare, besök, sidvyer) och konverteringsmått.
* Alla befintliga Target-aktiviteter fortsätter att använda Target-datainsamling och påverkas inte av att A4T aktiveras.
* Endast ett mbox-baserat mått tillåts när Analytics används som rapportkälla.
* Ett server-till-server-anrop från Target till Analytics skickar aktivitets- och upplevelseinformation till Analytics. Den här integreringen resulterar inte i ytterligare serveranrop för antingen Target eller Analytics.

   I vissa situationer kan klassificeringsanropet från Target till Analytics misslyckas och aktiviteterna visar inte data i Analytics. Om detta händer ska du läsa [Felsöka integreringen med Analytics och Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Du kan också [kontakta kundtjänst](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) om du behöver mer hjälp.

## Aktivitetstyper som stöds {#section_F487896214BF4803AF78C552EF1669AA}

I följande tabell visas vilka aktivitetstyper som stöder Analytics som rapportkälla (A4T):

| Typ av aktivitet | A4T-kompatibel? | Anteckningar, om tillämpligt |
|--- |--- |--- |
| A/B-aktivitet med manuell trafikdelning | Ja |  |
| A/B-aktivitet med automatisk fördelning | Nej |  |
| A/B-aktivitet med automål | Nej |  |
| Experience Targeting (XT) | Ja |  |
| Multivariata tester (MVT) | Ja | Kräver mbox-baserat målmätningsmål för att få fram Element Contribute-rapporten.  Elementbidragsrapporten stöder för närvarande inte analysstatistik. |
| Automatiserad personaliseringsaktivitet | Nej |  |
| Rekommendationsaktivitet | Ja |  |
| Mobilapp | Ja | Stöds med Mobile Services SDK, version 4.13.1 eller senare.  Mer information finns i dokumentationen [för](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)mobila tjänster. |
| E-post | Nej |  |
| Leverans-API på serversidan | Ja | Mer information finns i [Serversida: implementera Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| NodeJS SDK | Ja | Mer information finns i [Serversida: implementera Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Integrering av AEM 6.1 (eller tidigare) molntjänst | Nej |  |
| Integrering av AEM 6.2 (eller senare)-molntjänst | Ja | Mer information finns i [Integrera med Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) i dokumentationen för Adobe Experience Manager 6.2. |
| Alla aktiviteter som använder ett omdirigeringserbjudande | Ja | Det finns strängare minimikrav för användning av omdirigeringserbjudanden med A4T. Mer information finns i [Omdirigeringserbjudanden - A4T Frågor och svar](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Ja |  |

Eftersom alla aktivitetstyper ännu inte har stöd för A4T rekommenderar vi att du behåller eller implementerar viktiga konverteringsrutor, till exempel &quot;orderConfirmPage&quot;-rutan.

## Exempel på A4T-rapporter {#section_F0A43A1CB2F04E8282B909E4D7034361}

Om du vill visa A4T-rapporter i [!DNL Target]klickar du **[!UICONTROL Activities]** på önskad aktivitet i listan som använder [!DNL Analytics] som rapportkälla > och sedan på **[!UICONTROL Reports]** fliken.

>[!NOTE]
>
>Du kan använda den [!UICONTROL Reporting Source] nedrullningsbara listan högst upp på [!UICONTROL Activities] sidan om du bara vill visa aktiviteter som använder [!DNL Analytics] som rapportkälla.

Du kan växla mellan tabellvyn och [!UICONTROL Graph View] rapporten genom att klicka på lämplig ikon längst upp till höger i rapporten.

Följande bild visar hur en A4T-rapport ser ut [!UICONTROL Graph View] i [!UICONTROL Report Metric] listrutan med tillgängliga [!DNL Analytics] målvärden:

![](assets/a4t_report_graph1.png)

Följande bild visar hur en A4T-rapport ser ut [!UICONTROL Graph View] i [!UICONTROL Audience] listrutan med tillgängliga [!DNL Analytics] målgrupper:

![](assets/a4t_report_graph2.png)

Följande bild visar hur en A4T- [!UICONTROL Table View] rapport ser ut:

![](assets/a4t_report_table.png)

Om du vill visa rapporten i [!DNL Analytics] stället för i [!DNL Target]klickar du **[!UICONTROL View in Analytics]** längst upp i rapporten.

## Analys och mål: Självstudiekurs om metodtips för analys {#section_3438E6E77A464424B717A4FD333B84B2}

Öppna [Analytics &amp; Target: Självstudiekursen Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) , som tillhandahålls av Adobe Experience League.

## Utbildningsvideor:

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Analyser för målemblem (A4T) (4:32) ![Översikt](/help/assets/overview.png)

I den här videon förklaras hur du använder Adobe Analytics som en rapportkälla i Adobe Target för att analysera optimeringsprogrammet.

* Förklara vad A4T är och varför du ska använda det
* Förklara hur A4T fungerar
* Förstå de krav som krävs innan A4T används

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analys/målintegrering (A4T) (40:33) !![Tutorial badge](/help/assets/tutorial.png

Den här videon handlar om inspelningen av&quot; [kontorstid](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)&quot;, ett projekt som leds av Adobes kundtjänstteam.

* Konfigurera och verifiera att integreringen fungerar
* Hur integreringen fungerar
* Läs mer om de idealiska rapporterna som ska användas i Analytics
* Svar på vanliga frågor om A4T

[Kontorstimmar för analys/målintegrering (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)