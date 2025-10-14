---
keywords: analys för mål;a4t;analys som rapportkälla;analys
description: Lär dig hur du använder Analytics för  [!DNL Target] (A4T). A4T ger åtkomst till Analytics-rapporter för  [!DNL Target] aktiviteter som använder analysstatistik och målgruppssegment.
title: Hur använder jag rapportering i A4T?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---

# A4T-rapportering

Om du använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T) får du tillgång till [!DNL Analytics]-rapporter för dina [!DNL Target]-aktiviteter.

Du kan visa rapporter för dina aktiviteter i både [!DNL Analytics] och [!DNL Target].

[!DNL Analytics] [!DNL Target]Gå till den här Adobe Spark-sidan[&#x200B; om du vill få information om bästa praxis för  för &#x200B;](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Ökning {#section_035A62D65608423285D8A5A54731E2C5}

Både [!DNL Analytics] och [!DNL Target] rapporterar mått på deltagare (de personer som deltar i testerna), i stället för besökare på webbplatsen.

Varje gång en besökare ser aktivitetsinnehåll på sidan gör [!DNL Target] ett direkt server-till-server-anrop till [!DNL Analytics], inklusive vilken aktivitet och upplevelse besökaren såg. [!DNL Target] anropar även [!DNL Analytics] när konverteringen görs. [!DNL Analytics] lägger till konverteringen som en ny [!DNL Analytics]-händelse med namnet &quot;Aktivitetskonvertering&quot;, som spåras tillsammans med andra data som samlas in av [!DNL Analytics].

När åtgärden [!UICONTROL Select] används och du sorterar på *Intrants* visas endast de upplevelser som tog emot tävlingsbidrag under den valda tidsperioden i rapporterna.

>[!NOTE]
>
>Rapporter från [!DNL Target] har en fördröjning på fyra minuter. För aktiviteter som drivs av A4T kan det i både [!DNL Target]- och [!DNL Analytics]-rapporterna ta upp till 24 timmar efter att aktiviteten ursprungligen sparats innan rapportdata kan delas upp efter upplevelser. De data som samlas in under dessa första 24 timmar är fortfarande korrekta och tilldelas rätt upplevelse.

## Rapporter i analyser {#analytics}

I [!DNL Analytics] finns flera dimensioner och mått tillgängliga efter att A4T-integreringen har aktiverats.

### Dimensioner

* [!UICONTROL Analytics for Target] - Det överordnade ID som skickas via integreringen. Dimensionens format är `Activity ID:Experience ID:3rd ID`. Dimensionerna nedan är klassificeringar av den här dimensionen.
* [!UICONTROL Target Activities]
* [!UICONTROL Target Experiences]
* [!UICONTROL Target Activity] > [!UICONTROL Experience]
* [!UICONTROL 3rd ID] - kan ignoreras

### Mått

* [!UICONTROL Activity Impressions] - Matchar [!UICONTROL Entrants]-talet i [!DNL Target]-rapporten.
* [!UICONTROL Activity Conversions] - Matchar [!UICONTROL Custom Conversions]-talet i [!DNL Target]-rapporten.

I [!DNL Analysis Workspace] använder du panelen [!UICONTROL Analytics for Target] för att analysera dina [!DNL Target]-aktiviteter och -upplevelser med lyft och självförtroende. Mer information finns i [Analytics for Target (A4T) Panel &#x200B;](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=sv-SE) i *Analytics Tools Guide*.

>[!IMPORTANT]
>
>Om din [!UICONTROL Target Activities]-rapport i [!DNL Analytics] visar&quot;ospecificerad&quot; i stället för att visa dina aktiviteter, krävs en uppdatering av ditt provisionerade konto. Kontakta kundtjänst för att lösa problemet.

Om du vill ha mer information och exempel öppnar du självstudiekursen [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), som tillhandahålls av Adobe Experience League.

## Rapporter i [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

När [!DNL Analytics] används som rapportkälla visar rapporter i [!DNL Target] de data som samlats in från [!DNL Analytics]. Rapporten skiljer sig något från andra [!DNL Target]-rapporter:

* Listan [!UICONTROL Audiences] visar vilka målgrupper som är tillgängliga för rapportsviten [!DNL Analytics].
* I listan [!UICONTROL Metric] visas alla mätvärden som är tillgängliga via [!DNL Analytics].

  Alla mått är tillgängliga, inklusive anpassade eller beräknade värden som är inbyggda i [!DNL Analytics].

  Alla tal som ökar visas som positiva i rapporten, även när en ökning inte är önskad. Även om du till exempel vill ha en lägre avhoppsfrekvens visas den högre avhoppsfrekvensen som vinnare med den högsta avhoppsfrekvensen. Tänk på dessa och liknande mätvärden och om du hellre vill öka eller minska siffrorna när du fattar beslut baserat på rapporter.

Du kan tillämpa måttet eller målgruppen på rapporten om [!DNL Target] efter att aktiviteten har startats, eller till och med efter att testet har slutförts. Du behöver inte veta exakt vad du vill mäta i förväg.

Klicka för att visa den fullständiga [!DNL Analytics]-rapporten direkt från aktivitetsrapportsidan.

## Skapa aktivitet {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

När aktiviteten skapas måste du ange ett mål för aktiviteten på sidan [!UICONTROL Settings]. Det här målet blir standardmåttet för rapporten och anges alltid som det första alternativet i mätväljaren. Du kan inte välja segment för rapportering på samma sätt som för en vanlig Target-aktivitet. Ett test med [!DNL Analytics] använder [!DNL Adobe Analytics] segment i stället för [!DNL Target] målgrupper.

## Utföra offlineberäkningar för analys för Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Du kan utföra offlineberäkningar för konfidensintervall för A4T med Excel-filen [!DNL Target] [Complete Confidence Calculator](/help/main/assets/complete_confidence_calculator.xlsx) , men det krävs ett steg med dataexporter i [!DNL Analytics].

För A4T använder vi en [Welchs t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}-beräkning för kontinuerliga variabler (i stället för binära värden). I Analytics spåras alltid en besökare, och alla åtgärder som vidtas räknas. Om besökaren köper flera gånger eller besöker ett framgångsmått flera gånger räknas de ytterligare träffarna. Detta gör mätvärdet till en kontinuerlig variabel. För att utföra Welchs t-test-beräkning krävs ’summan av kvadrater’ för att beräkna variansen, som används i t-statistikens nämnare. [Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md) förklarar detaljerna för de matematiska formler som används. Summan av fyrkanter kan hämtas från [!DNL Analytics]. Om du vill få summan av kvadratdata måste du utföra en export på besökarnivå för det mätresultat som du optimerar för, under en provtidsperiod.

Om du till exempel optimerar till sidvisningar per besökare, kan du exportera ett exempel på det totala antalet sidvisningar per besökare för en viss tidsperiod, kanske några dagar (ett par tusen datapunkter är allt du behöver). Därefter fyrkantiga varje värde och summerar summan (operationsordningen är viktig här). Värdet&quot;summan av kvadrater&quot; används sedan i Complete Confidence Calculator. Använd avsnittet &quot;intäkt&quot; i kalkylbladet för dessa värden.

**Så här använder du dataexportfunktionen [!DNL Analytics]:**

1. Logga in på [!DNL Adobe Analytics].
1. Klicka på **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]**.
1. Fyll i fälten på fliken **[!UICONTROL Data Warehouse Request]**.

   Mer information om de olika fälten finns i&quot;Data Warehouse Descriptions&quot; i [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=sv-SE).

   | Fält | Instruktioner |
   |--- |--- |
   | Namn på begäran | Ange ett namn för din begäran. |
   | Rapportdatum | Ange en tidsperiod och granularitet.<br>Som bästa praxis bör du välja högst en timme eller en dag med data för din första begäran.  Data Warehouse-filer tar längre tid att bearbeta längre tid än vad som begärts, så det är alltid en god vana att först begära data från en liten tidsperiod för att vara säker på att filen returnerar det förväntade resultatet. Gå sedan till Request Manager, duplicera din begäran och be om fler data vid andra gången. Om du växlar granularitet till något annat än &quot;Inget&quot; ökar filstorleken drastiskt.<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | Tillgängliga segment | Använd ett segment efter behov. |
   | Uppdelningar | Välj önskade mått: Standard är förberett (OTB), medan Custom innehåller eVars &amp; Props. Vi rekommenderar att du använder&quot;besökar-ID&quot; om information på besökar-ID-nivå behövs, i stället för&quot;Experience Cloud Visitor-ID&quot;.<ul><li>Besökar-ID är det sista ID som används av Analytics. Det blir antingen ett ID (om kunden är äldre) eller ett MID (om kunden är ny eller rensad på cookies sedan besökar-ID-tjänsten för MC startades).</li><li>Experience Cloud Visitor ID kommer endast att anges för kunder som är nya eller rensade cookies sedan besöks-ID-tjänsten startades.</li></ul> |
   | Mått | Välj önskade mätvärden. Standard är OTB, medan Anpassad innehåller anpassade händelser. |
   | Förhandsgranska rapport | Granska inställningarna innan du schemalägger rapporten.<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | Schemalägg leverans | Ange en e-postadress som filen ska skickas till, ge filen ett namn och välj sedan [!UICONTROL Send Immediately].<br>Obs! Filen kan levereras via FTP under [!UICONTROL Advanced Delivery Options]<br>![Schemalägg leverans](/help/main/c-reports/assets/datawarehouse3.png). |

1. Klicka på **[!UICONTROL Request this Report]**.

   Filleveransen kan ta upp till 72 timmar, beroende på mängden data som begärs. Du kan när som helst kontrollera förloppet för din begäran genom att klicka på [!UICONTROL Tools] > [!UICONTROL Data Warehouse] > [!UICONTROL Request Manager].

   Om du vill begära om data som du har begärt tidigare kan du duplicera en gammal begäran från [!UICONTROL Request Manager] efter behov.

Mer information om [!DNL Data Warehouse] finns i följande länkar i hjälpdokumentationen för [!DNL Analytics]:

* [Skapa en Data Warehouse-förfrågan](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html?lang=sv-SE)
* [Data Warehouse bästa praxis](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html?lang=sv-SE)
