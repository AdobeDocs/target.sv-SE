---
keywords: rapporter;ladda ned rapporter;csv;success metrics;order details
description: Lär dig hur du hämtar data från Adobe [!DNL Target] aktiviteter i CVS-format för snabb import till Excel, Access eller andra dataanalysprogram.
title: Hur hämtar jag rapportdata i en CSV-fil?
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: fc1dcc2b6de1248c35191c1ecd7b36aeb891fd3f
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 0%

---

# Hämta data i en CSV-fil

Ladda ned data i CSV-format för snabb import till Excel, Access eller andra dataanalysprogram.

Så här hämtar du data i en CSV-fil:

1. Klicka **[!UICONTROL Activities]** klickar du sedan på önskad aktivitet i listan.

   Om du har många aktiviteter kan du filtrera listan genom att välja alternativ på menyn [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type]och [!UICONTROL Activity Source] nedrullningsbara listor.

1. Klicka på **[!UICONTROL Reports]** -fliken.
1. Klicka på **[!UICONTROL Download]** väljer du sedan en rapporttyp att hämta för analys i Excel och andra verktyg.

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

   ![Hämtningsalternativ](/help/main/c-reports/assets/download-options.png)

## [!UICONTROL Export Report to CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

The [!UICONTROL Success Metrics] rapporten visar information om dina framgångsmått och följande mätvärden som inte är tillgängliga i [!DNL Target] Gränssnitt:

* Genomsnittlig tid för konvertering i timmar, så att du kan se hur lång tid det tar för den genomsnittliga besökaren att nå konverteringspunkten
* Summan av intäkter, fyrkantiga, för beräkningar av statistisk säkerhet offline

Data sparas till aktivitetens slut.

>[!NOTE]
>
>CSV-rapporten innehåller endast rådata och innehåller inte beräknade värden som intäkter per besökare, lyft eller förtroende som används för A/B-tester. Om du vill beräkna dessa beräknade värden hämtar du [!DNL Target] [Slutför konfidensberäkning](/help/main/assets/complete_confidence_calculator.xlsx) Excel-fil för att ange aktivitetens värde eller granska [Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL Export Order Details to CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

The [!UICONTROL Order Details] rapporten innehåller information om dina beställningar, inklusive:

* Orderdatum och -tid
* Orderbelopp (om du har infogat en monteringsorder)

   The [!UICONTROL Order Details] fungerar bara om du har beställningar.

* Orderflagga (duplicerad eller extrem ordning)

   En order markeras som extrem om den är mer än +/- 3 standardavvikelser från det genomsnittliga ordervärdet. I den här beräkningen används den sista månaden med data (fram till den tidpunkt då beräkningen gjordes). En aktivitet kommer att få sina extrema order exkluderade när aktiviteten har pågått i en timme eller tills efter 15 order, beroende på vilket som kommer först. Mer information finns i [Exklusive extrema order](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* Produkt-ID

   Den totala längden på produkt-ID:n, sammanfogade med kommatecken, får inte överstiga 255 tecken eller så visas ID:n inte korrekt i rapporten. Om din beställning till exempel innehåller produkter med ID:n &quot;aa, bb&quot; är den totala längden &quot;aa,bb&quot; = 5.

* Upplevelse

   I [!UICONTROL Order Details] rapport för [!UICONTROL A/B Test], [!UICONTROL Experience Targeting] (XT), och [!UICONTROL Multivariate Test] MVT-verksamhet, [!UICONTROL Experience] kolumnen innehåller upplevelsen `localId`. Det här är värdeutdata från `$campaign.recipe.id` i erbjudandetoken.

   Det finns ingen [!UICONTROL Experience] kolumn för [!UICONTROL Automated Personalization] (AP) aktiviteter. Aktuell [!UICONTROL Algorithm Name] kolumnen har ersatts med termen&quot;Kontroll&quot; kontra&quot;Riktad&quot;, vilket visas någon annanstans i [!DNL Target].

   Ingen effekt på [!UICONTROL Recommendations] verksamhet.

>[!NOTE]
>
>* Orderrapportdata innehåller fyra veckors data för standardmiljön (värdgrupp) och två veckor för alla miljöer som inte är standard.
>* Intäktsmått som är inställda på[!UICONTROL Increment count and keep the user in the activity]&quot; loggordningsinformation endast för den första ordern som gjorts av samma besökare. Alla efterföljande order ökar antalet konverteringar, men lägger inte till några intäkter till RPV/AOV/Sales och ingår inte i [!UICONTROL Order Details] rapport.


## Bästa praxis

* Om du vill spela in en orderpost väljer du `orderTotal` -parametern måste skickas.
* Värden som skickas via `ProductPurchasedId` mbox-parametern finns i [!UICONTROL Order Details] rapport.
* Bästa praxis är att inkludera en `orderID` och `orderTotal`. Detta gör att dubblettorder automatiskt ignoreras.

## Caveats {#section_49B9590904A645B18E694B4EFFFC1DEF}

Följande information gäller för [!UICONTROL Download] alternativ:

* Du kan hämta båda rapporterna för [!UICONTROL A/B Test], [!UICONTROL Automated Personalization], [!UICONTROL Experience Targeting]och [!UICONTROL Multivariate] verksamhet. Du kan inte hämta [!UICONTROL Success Metrics] rapport för [!UICONTROL Recommendations] verksamhet.
* The [!UICONTROL Download] alternativ är inte tillgängligt för [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] aktiviteter skapade före [!DNL Target] version 15.7.1 (juli 2015).
* Erfarenheter utan tillhörande data registreras inte i den hämtade rapporten.
* Målgrupper som används i [!DNL Target] rapportanvändargränssnittet överförs inte till hämtningsrapporten.
* Rapporter som genererats för hämtning som CSV-filer är inkonsekventa om aktiviteten använder mer än ett mätvärde. Den hämtningsbara rapporten genereras endast baserat på rapportinställningarna och tar hänsyn till samma värde för andra mätvärden som används. Sanningens källa är alltid den rapport som visas i [!DNL Target] Gränssnitt.
