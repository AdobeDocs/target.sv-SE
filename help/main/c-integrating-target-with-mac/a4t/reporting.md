---
keywords: analys för mål;a4t;analys som rapportkälla;analys
description: Lär dig använda Analytics för [!DNL Target] (A4T). A4T ger åtkomst till Analytics-rapporter för [!DNL Target] aktiviteter som använder analysstatistik och målgruppssegment.
title: Hur använder jag rapportering i A4T?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 0%

---

# A4T-rapportering

Använda [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T) ger dig tillgång till [!DNL Analytics] rapporter för [!DNL Target] verksamhet.

Du kan visa rapporter för dina aktiviteter i båda [!DNL Analytics] och [!DNL Target].

Rapportera bästa praxis med [!DNL Analytics] for [!DNL Target], [här kommer Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Översikt {#section_035A62D65608423285D8A5A54731E2C5}

Båda [!DNL Analytics] och [!DNL Target] rapporterar mäter deltagare (de personer som deltar i testerna) i stället för besökare på webbplatsen.

Varje gång en besökare ser aktivitetsinnehåll på sidan, [!DNL Target] gör ett direktanrop från server till server till [!DNL Analytics], inklusive vilken aktivitet och upplevelse besökaren såg. [!DNL Target] anrop [!DNL Analytics] när konverteringen görs. [!DNL Analytics] lägger till konverteringen som en specifik ny [!DNL Analytics] händelse med namnet&quot;Activity Conversion&quot;, som spåras tillsammans med andra data som samlats in av [!DNL Analytics].

När [!UICONTROL Select] används och du sorterar efter *Deltagare* så visas bara de upplevelser som har tagit emot tävlingsbidrag under den valda tidsperioden i rapporterna.

>[!NOTE]
>
>Rapporter från [!DNL Target] har en latens på fyra minuter. För aktiviteter som drivs av A4T, i båda [!DNL Target] och [!DNL Analytics] -rapporter kan det ta upp till 24 timmar efter att aktiviteten har sparats först innan rapportdata kan delas upp efter upplevelser. De data som samlas in under dessa första 24 timmar är fortfarande korrekta och tilldelas rätt upplevelse.

## Rapporter i analyser {#analytics}

I [!DNL Analytics], finns det flera dimensioner och mätvärden som är tillgängliga efter att A4T-integreringen har aktiverats.

### Dimensioner

* [!UICONTROL Analytics for Target] - Det överordnade ID som skickas via integreringen. Dimensionens format är `Activity ID:Experience ID:3rd ID`. Dimensionerna nedan är klassificeringar av den här dimensionen.
* [!UICONTROL Target Activities]
* [!UICONTROL Target Experiences]
* [!UICONTROL Target Activity] > [!UICONTROL Experience]
* [!UICONTROL 3rd ID] - kan ignoreras

### Mått

* [!UICONTROL Activity Impressions] - Matchar [!UICONTROL Entrants] talet i [!DNL Target] rapport.
* [!UICONTROL Activity Conversions] - Matchar [!UICONTROL Custom Conversions] talet i [!DNL Target] rapport.

I [!DNL Analysis Workspace], använder du [!UICONTROL Analytics for Target] panel för att analysera [!DNL Target] aktiviteter och upplevelser med lyft och självförtroende. Mer information finns i [Analyser för målpanelen (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) i *Handbok för analysverktyg*.

>[!IMPORTANT]
>
>Om [!UICONTROL Target Activities] rapportera i [!DNL Analytics] visar&quot;unspecified&quot; (ej specificerad) istället för att lista dina aktiviteter krävs en uppdatering av ditt provisionerade konto. Kontakta kundtjänst för att lösa problemet.

Detaljerad information och exempel finns i [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) självstudiekurs från Adobe Experience League.

## Rapporter i [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

När [!DNL Analytics] används som rapportkälla, rapporter i [!DNL Target] visa de data som samlats in från [!DNL Analytics]. Rapporten skiljer sig något från andra [!DNL Target] rapporter:

* The [!UICONTROL Audiences] listan visar vilka målgrupper som är tillgängliga för er [!DNL Analytics] rapportsvit.
* The [!UICONTROL Metric] listan visar alla mätvärden som är tillgängliga via [!DNL Analytics].

   Alla mätvärden är tillgängliga, inklusive anpassade eller beräknade mätvärden som är inbyggda [!DNL Analytics].

   Alla tal som ökar visas som positiva i rapporten, även när en ökning inte är önskad. Även om du till exempel vill ha en lägre avhoppsfrekvens visas den högre avhoppsfrekvensen som vinnare med den högsta avhoppsfrekvensen. Tänk på dessa och liknande mätvärden och om du hellre vill öka eller minska siffrorna när du fattar beslut baserat på rapporter.

Du kan använda måttet eller målgruppen i rapporten i [!DNL Target] efter det att aktiviteten har startats, eller till och med efter det att testet har slutförts. Du behöver inte veta exakt vad du vill mäta i förväg.

Klicka för att visa hela [!DNL Analytics] direkt från aktivitetsrapportsidan.

## Skapa aktivitet {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

När du skapar en aktivitet måste du ange ett mål för aktiviteten på [!UICONTROL Settings] sida. Det här målet blir standardmåttet för rapporten och anges alltid som det första alternativet i mätväljaren. Du kan inte välja segment för rapportering på samma sätt som för en vanlig Target-aktivitet. Ett test med [!DNL Analytics] använder [!DNL Adobe Analytics] segment i stället för [!DNL Target] målgrupper.

## Utföra offlineberäkningar för Analytics för Adobe Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Du kan utföra offlineberäkningar för A4T, men det kräver ett steg med dataexport i [!DNL Analytics].

Mer information finns i [Utföra offlineberäkningar för analys av mål (A4T)](/help/main/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
