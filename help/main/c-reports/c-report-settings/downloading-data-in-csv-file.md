---
keywords: rapporter;ladda ned rapporter;csv;success metrics;order details
description: Lär dig hur du hämtar data från Adobe [!DNL Target] aktiviteter i ett CVS-format för snabb import till Excel, Access eller andra dataanalysprogram.
title: Hur hämtar jag rapportdata i en CSV-fil?
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: c0342f51d998d27eef9af189c7ebb364095699ed
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 0%

---

# Hämta data i en CSV-fil

Hämta data i CSV-format för snabb import till [!DNL Excel], [!DNL Access] eller andra dataanalysprogram.

Så här hämtar du data i en CSV-fil:

1. Klicka på **[!UICONTROL Activities]** och sedan på önskad aktivitet i listan.

   Om du har många aktiviteter klickar du på ikonen Filter ( ![Filterikon](/help/main/assets/icons/Filter.svg) ) för att filtrera listan genom att välja alternativ i listrutorna [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] och [!UICONTROL Activity Source] .

1. Klicka på fliken **[!UICONTROL Reports]**.
1. Klicka på ikonen **[!UICONTROL Download]** ( ![ikonen Hämta](/help/main/assets/icons/Download.svg) ) och välj sedan en rapporttyp att hämta för analys i Excel och andra verktyg.

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

## [!UICONTROL Export Report to CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

Rapporten [!UICONTROL Success Metrics] visar information om dina framgångsmått och följande mått som inte är tillgängliga i användargränssnittet i [!DNL Target]:

* Genomsnittlig tid för konvertering i timmar, så att du kan se hur lång tid det tar för den genomsnittliga besökaren att nå konverteringspunkten
* Summan av intäkter, fyrkantiga, för beräkningar av statistisk säkerhet offline

Data sparas till aktivitetens slut.

>[!NOTE]
>
>CSV-rapporten innehåller endast rådata och innehåller inte beräknade värden som intäkter per besökare, lyft eller förtroende som används för A/B-tester. Om du vill beräkna de beräknade måtten hämtar du Excel-filen [!DNL Target] [Complete Confidence Calculator](/help/main/assets/complete_confidence_calculator.xlsx) för att ange aktivitetens värde, eller granskar [statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL Export Order Details to CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

Rapporten [!UICONTROL Order Details] visar information om dina beställningar, inklusive:

* Orderdatum och -tid
* Orderbelopp (om du har infogat en monteringsorder)

  Rapporten [!UICONTROL Order Details] fungerar bara om du har beställningar.

* Orderflagga (duplicerad eller extrem ordning)

  En order markeras som extrem om den är mer än +/- 3 standardavvikelser från det genomsnittliga ordervärdet. I den här beräkningen används den sista månaden med data (fram till den tidpunkt då beräkningen gjordes). En aktivitet kommer att få sina extrema order exkluderade när aktiviteten har pågått i en timme eller tills efter 15 order, beroende på vilket som kommer först. Mer information finns i [Exkludera extrema order](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* Produkt-ID

  Den totala längden på produkt-ID:n, sammanfogade med kommatecken, får inte överstiga 255 tecken eller så visas ID:n inte korrekt i rapporten. Om din beställning till exempel innehåller produkter med ID:n &quot;aa, bb&quot; är den totala längden &quot;aa,bb&quot; = 5.

* Upplevelse

  I [!UICONTROL Order Details]-rapporten för [!UICONTROL A/B Test]-, [!UICONTROL Experience Targeting] (XT)- och [!UICONTROL Multivariate Test] (MVT)-aktiviteter innehåller kolumnen [!UICONTROL Experience] upplevelsen `localId`. Detta är värdeutdata från `$campaign.recipe.id` i erbjudandetokens.

  Det finns ingen [!UICONTROL Experience]-kolumn för [!UICONTROL Automated Personalization] (AP)-aktiviteter. Den aktuella [!UICONTROL Algorithm Name]-kolumnen har ersatts med &quot;Kontroll&quot; och &quot;Riktad&quot;-terminologi, vilket visas någon annanstans i [!DNL Target].

  Det har inte påverkat [!UICONTROL Recommendations] aktiviteter.

>[!NOTE]
>
>* Orderrapportdata innehåller fyra veckors data för standardmiljön (värdgrupp) och två veckor för alla miljöer som inte är standard.
>* Intäktsmått som är inställda på [!UICONTROL Increment count and keep the user in the activity], loggordningsinformation endast för den första ordern som görs av samma besökare. Alla efterföljande order ökar antalet konverteringar, men lägger inte till intäkter till RPV/AOV/Sales, och inkluderas inte i [!UICONTROL Order Details]-rapporten.

## Hämtningsformat för CSV för popularitet och nyckelbaserade algoritmer {#format}

CSV-nedladdningsfilen återspeglar konsekvent resultat som genererats efter körning av backend-kriterier.

**För popularitetsalgoritmer (icke-nyckelbaserade) innehåller filen:**

* En rad med rekommendationer för säkerhetskopiering med prefixet *
* En separat rad med rekommendationer baserade på algoritminställningar

**För nyckelbaserade algoritmer innehåller filen:**

* En säkerhetskopieringsrad som liknar popularitetsalgoritmer
* Flera rader i nyckelvärdesformat, där den första posten är produkt-ID för nyckeln, följt av kommaseparerade produkt-ID:n som representerar rekommendationskandidater

## Bästa praxis

* Om du vill spela in en orderpost måste parametern `orderTotal` skickas.
* Värden som skickas via parametern `ProductPurchasedId` visas i rapporten [!UICONTROL Order Details].
* Det bästa sättet är att inkludera en `orderID` och en `orderTotal`. Detta gör att dubblettorder automatiskt ignoreras.

## Caveats {#section_49B9590904A645B18E694B4EFFFC1DEF}

Följande information gäller för alternativet [!UICONTROL Download]:

* Du kan hämta båda rapporterna för [!UICONTROL A/B Test]-, [!UICONTROL Automated Personalization]-, [!UICONTROL Experience Targeting]- och [!UICONTROL Multivariate]-aktiviteter. Du kan inte hämta rapporten [!UICONTROL Success Metrics] för [!UICONTROL Recommendations]-aktiviteter.
* Alternativet [!UICONTROL Download] är inte tillgängligt för [!UICONTROL A/B Test]- och [!UICONTROL Experience Targeting]-aktiviteter som skapats före [!DNL Target] version 15.7.1 (juli 2015).
* Erfarenheter utan tillhörande data registreras inte i den hämtade rapporten.
* Publiker som används i rapportgränssnittet [!DNL Target] överförs inte till hämtningsrapporten.
* Rapporter som genererats för hämtning som CSV-filer är inkonsekventa om aktiviteten använder mer än ett mätvärde. Den hämtningsbara rapporten genereras endast baserat på rapportinställningarna och tar hänsyn till samma värde för andra mätvärden som används. Sanningens källa är alltid den rapport som visas i användargränssnittet för [!DNL Target].
