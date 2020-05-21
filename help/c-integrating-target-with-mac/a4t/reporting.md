---
keywords: analytics for target;a4t;analytics as the reporting source
description: Genom att använda Analytics som rapportkälla för Target (A4T) får ni tillgång till analysrapporter för era Target-aktiviteter.
title: A4T-rapportering
subtopic: Multivariate Test
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 68f356b0711abf9acf7ef631edf3656bd3dd49e3
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 0%

---


# A4T-rapportering{#a-t-reporting}

Med [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T) får du tillgång till [!DNL Analytics] rapporter för dina [!DNL Target] aktiviteter.

Du kan visa rapporter för dina aktiviteter i både [!DNL Analytics] och [!DNL Target].

Rapportera bästa praxis [!DNL Analytics] för med hjälp av [!DNL Target]for [på den här Adobe Spark-sidan](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Översikt {#section_035A62D65608423285D8A5A54731E2C5}

Både [!DNL Analytics] och [!DNL Target] rapporter mäter deltagare (de som deltar i testerna) snarare än besökare på webbplatsen.

Varje gång en besökare ser aktivitetsinnehåll på sidan gör han/hon ett direkt server-till-server-anrop till [!DNL Target] [!DNL Analytics], inklusive vilken aktivitet och upplevelse besökaren såg. [!DNL Target] anropar också [!DNL Analytics] när konverteringen görs. [!DNL Analytics] lägger till konverteringen som en ny [!DNL Analytics] händelse med namnet&quot;Aktivitetskonvertering&quot;, som spåras tillsammans med andra data som samlas in av [!DNL Analytics].

När [!UICONTROL Select] åtgärden används och du sorterar efter *tävlingsbidrag* visas endast de upplevelser som tog emot tävlingsbidrag under den valda tidsperioden i rapporterna.

>[!NOTE]
>
>Rapporter som drivs av [!DNL Target] har en latens på fyra minuter. För aktiviteter som drivs av A4T kan det i både rapporten [!DNL Target] och [!DNL Analytics] rapporten ta upp till 24 timmar efter att aktiviteten ursprungligen sparats innan rapportdata kan delas upp efter upplevelser. De data som samlas in under dessa första 24 timmar är fortfarande korrekta och tilldelas rätt upplevelse.

## Rapporter i analyser {#section_F6884872DC864AE7913587FAED4CD11C}

I [!DNL Analytics]klickar du på **[!UICONTROL Target]** > **[!UICONTROL Target Activities]** i den vänstra menyn. I [!DNL Target]aktivitetens rapporter visas automatiskt [!DNL Analytics] data, mått och segment. Data visas i dessa rapporter ungefär en timme efter det att de samlats in från platsen. Alla mätvärden, målgrupper och värden i rapporterna kommer från rapportsviten som du valde när du konfigurerade aktiviteten.

I [!DNL Analytics]kan du använda [!UICONTROL Target Activities] rapporten för att visa resultatet av din [!DNL Target] aktivitet. Test&amp;Target-rapporter (äldre) innehåller information om den gamla formatsidintegreringen för Test&amp;Target-plugin och innehåller inte [!DNL Analytics] information om [!DNL Target] data. Visa information om era [!UICONTROL Activities] upplevelser i [!DNL Target] rapporten. Klicka **[!UICONTROL Metrics]** och välj sedan **[!UICONTROL Target]** måtttyp. Det finns två mätvärden för rapporten:

* **Aktivitetsposter:** Matchar inmatningsnumret i [!DNL Target] rapporten.
* **Aktivitetskonverteringar:** Matchar numret för anpassade konverteringar i [!DNL Target] rapporten.

>[!NOTE]
>
>[!DNL Target] lift and trust details are also available in [!DNL Analytics]. Mer information finns i [MålLyft och förtroende](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/report-target-lift-confidence.html) i *guiden* för analyskomponenter.

>[!IMPORTANT]
>
>Om din [!UICONTROL Target Activities] rapport i [!DNL Analytics] listan&quot;ospecificerad&quot; istället för att visa dina aktiviteter, krävs en uppdatering av ditt provisionerade konto. Kontakta kundtjänst för att lösa problemet.

## Rapporter i mål {#section_C0D1F17F88374B6690BF904D7B83B42E}

När [!DNL Analytics] används som rapportkälla visar rapporter i [!DNL Target] de data som samlats in från [!DNL Analytics]. Rapporten skiljer sig något från andra [!DNL Target] rapporter:

* I [!UICONTROL Audiences] listan visas vilka målgrupper som är tillgängliga för din [!DNL Analytics] rapportserie.
* I [!UICONTROL Metric] listan visas alla mätvärden som är tillgängliga via [!DNL Analytics].

   Alla mätvärden är tillgängliga, inklusive anpassade eller beräknade mätvärden som är inbyggda [!DNL Analytics].

   Tänk på att alla siffror som ökar visas som positiva i rapporten, även när en ökning egentligen inte är önskvärd. Även om du till exempel vill ha en lägre avhoppsfrekvens visas den högre avhoppsfrekvensen som vinnare med den högsta avhoppsfrekvensen. Tänk på dessa och liknande mätvärden och om du hellre vill öka eller minska siffrorna när du fattar beslut baserat på rapporter.

Du kan använda måttet eller målgruppen för rapporten i [!DNL Target] efter att aktiviteten har startats, eller till och med efter att testet har slutförts. Du behöver inte veta exakt vad du vill mäta i förväg.

Klicka för att visa den fullständiga [!DNL Analytics] rapporten direkt från aktivitetsrapportsidan.

## Rapporter på analysarbetsytan {#reports-in-analysis-workspace}

Du kan använda [!DNL Adobe Analysis Workspace] för att fördjupa och visualisera data eller upptäcka dolda insikter under ytan.

Om du vill ha detaljerad information och exempel öppnar du [Analytics &amp; Target: Självstudiekursen](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)Best Practices for Analysis, från [!DNL Adobe Experience League].

## Skapa aktivitet {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

När du skapar en aktivitet måste du ange ett mål för aktiviteten på [!UICONTROL Settings] sidan. Det här målet blir standardmåttet för rapporten och anges alltid som det första alternativet i mätväljaren. Du kan inte välja segment för rapportering på samma sätt som för en vanlig Target-aktivitet. Ett test med [!DNL Analytics] användning av [!DNL Adobe Analytics] segment i stället för [!DNL Target] målgrupper.

## Utföra offlineberäkningar för Analytics för Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Du kan utföra offlineberäkningar för A4T, men det krävs ett steg med dataexport i [!DNL Analytics].

Mer information finns i [Utföra offlineberäkningar för analys av mål (A4T)](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
