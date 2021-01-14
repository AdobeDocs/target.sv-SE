---
keywords: reports;download reports;csv;success metrics;order details
description: Hämta data i CSV-format för snabb import till Excel, Access eller andra dataanalysprogram med Adobe Target.
title: Hämta data i en CSV-fil med Adobe Target
feature: Reports
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 0%

---


# Hämta data i en CSV-fil{#downloading-data-in-a-csv-file}

Ladda ned data i CSV-format för snabb import till Excel, Access eller andra dataanalysprogram.

Så här hämtar du data i en CSV-fil:

1. Klicka på **[!UICONTROL Activities]** och sedan på önskad aktivitet i listan.

   Om du har många aktiviteter kan du filtrera listan genom att välja alternativ i listrutorna [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] och [!UICONTROL Activity Source].

1. Klicka på fliken **[!UICONTROL Reports]**.
1. Klicka på ikonen **[!UICONTROL Download]** och välj sedan en rapporttyp att hämta för analys i Excel och andra verktyg.

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

   ![Hämtningsalternativ](/help/c-reports/assets/download-options.png)

## Exportera rapport till CSV {#section_38BD9743EB254453B5F4A0A6F2720CD3}

Rapporten Success Metrics visar information om dina framgångsmått, samt följande mått som inte finns tillgängliga i målgränssnittet:

* Genomsnittlig tid för konvertering i timmar, så att du kan se hur lång tid det tar för den genomsnittliga besökaren att nå konverteringspunkten
* Summan av intäkter, fyrkantiga, för beräkningar av statistisk säkerhet offline

Data sparas till aktivitetens slut.

>[!NOTE]
>
>CSV-rapporten innehåller endast rådata och innehåller inte beräknade värden som intäkter per besökare, lyft eller förtroende som används för A/B-tester. Om du vill beräkna dessa beräknade värden hämtar du målets [Complete Confidence Calculator](/help/assets/complete_confidence_calculator.xlsx) Excel-fil för att ange aktivitetens värde, eller läser de [statistiska beräkningar som används av Target](/help/assets/statistical-calculations.pdf).

## Exportera beställningsinformation till CSV {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

I rapporten Orderdetaljer visas information om dina beställningar, inklusive:

* Orderdatum och -tid
* Orderbelopp (om du har infogat en monteringsorder)

   Orderdetaljrapporten fungerar bara om du har beställningar.

* Orderflagga (duplicerad eller extrem ordning)

   En order markeras som extrem om den är mer än +/- 3 standardavvikelser från det genomsnittliga ordervärdet med hjälp av den sista månaden med data (fram till den tidpunkt då beräkningen gjordes). En aktivitet kommer att få sina extrema order exkluderade när aktiviteten har pågått i en timme eller tills efter 15 order, beroende på vilket som kommer först. Mer information finns i [Exkludera extrema order](/help/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* Produkt-ID

   Den totala längden på produkt-ID:n, sammanfogade med kommatecken, får inte överstiga 255 tecken, annars visas inte ID:n korrekt i rapporten. Om din beställning till exempel innehåller produkter med ID:n &quot;aa, bb&quot; är den totala längden &quot;aa,bb&quot; = 5.

* Upplevelse

   I [!UICONTROL Order Details]-rapporten för [!UICONTROL A/B Test], [!UICONTROL Experience Targeting] (XT) och [!UICONTROL Multivariate Test] (MVT)-aktiviteter innehåller kolumnen [!UICONTROL Experience] upplevelsen `localId`. Det här är värdeutdata från `$campaign.recipe.id` i erbjudandetokens.

   Det finns ingen [!UICONTROL Experience]-kolumn för [!UICONTROL Automated Personalization]-aktiviteter (AP). Den aktuella [!UICONTROL Algorithm Name]-kolumnen har ersatts med &quot;Kontroll&quot; jämfört med &quot;Riktad&quot;-terminologi, vilket visas någon annanstans i [!DNL Target].

   Ingen påverkan på [!UICONTROL Recommendations]-aktiviteter.

>[!NOTE]
>
>* Orderrapportdata innehåller fyra veckors data för standardmiljön (värdgrupp) och två veckor för alla miljöer som inte är standard.
>* Inkomstmått som är inställda på Ökningsantal och behåller användaren i aktiviteten, loggordningsinformation endast för den första ordern som gjorts av samma besökare. Alla efterföljande order ökar antalet konverteringar, men lägger inte till intäkter till RPV/AOV/Sales och inkluderas inte i rapporten Orderdetaljer.


## Bästa praxis

* För att kunna registrera en orderpost måste parametern `orderTotal` skickas.
* Värden som skickas via parametern `ProductPurchasedId` visas i rapporten Orderdetaljer.
* Det bästa sättet är att inkludera en `orderID` och en `orderTotal`. Detta gör att dubblettorder automatiskt ignoreras.

## Caveats {#section_49B9590904A645B18E694B4EFFFC1DEF}

Följande information gäller för nedladdningsalternativet:

* Du kan hämta båda rapporterna för A/B-tester, Automated Personalization, Experience Targeting och Multivariate-aktiviteter. Du kan inte hämta rapporten Success Metrics för rekommendationsaktiviteter.
* Hämtningsalternativet är inte tillgängligt för aktiviteter av typen A/B och Experience Targeting som har skapats före målversion 15.7.1 (juli 2015).
* Erfarenheter utan tillhörande data registreras inte i den hämtade rapporten.
* Publiker som används i gränssnittet för målrapportering överförs inte till hämtningsrapporten.
