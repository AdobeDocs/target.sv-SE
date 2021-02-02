---
keywords: analys för target;a4t;analytics as reporting source
description: Genom att använda Analytics som rapportkälla för Target (A4T) får ni tillgång till analysrapporter för era Target-aktiviteter.
title: A4T-rapportering
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 0%

---


# A4T-rapportering{#a-t-reporting}

Om du använder [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T) får du tillgång till [!DNL Analytics]-rapporter för dina [!DNL Target]-aktiviteter.

Du kan visa rapporter för dina aktiviteter i både [!DNL Analytics] och [!DNL Target].

[Om du vill rapportera bästa praxis med [!DNL Analytics] för [!DNL Target] ska du besöka den här Adobe Spark-sidan](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Översikt {#section_035A62D65608423285D8A5A54731E2C5}

Både [!DNL Analytics] och [!DNL Target] mäter deltagare (de som deltar i testerna) i stället för besökare på webbplatsen.

Varje gång en besökare ser aktivitetsinnehåll på sidan gör [!DNL Target] ett direkt server-till-server-anrop till [!DNL Analytics], inklusive vilken aktivitet och upplevelse besökaren såg. [!DNL Target] anropar också  [!DNL Analytics] när konverteringen görs. [!DNL Analytics] lägger till konverteringen som en ny  [!DNL Analytics] händelse med namnet&quot;Aktivitetskonvertering&quot;, som spåras tillsammans med andra data som samlas in av  [!DNL Analytics].

När [!UICONTROL Select]-åtgärden används och du sorterar på *Deltagare*, visas endast de upplevelser som tog emot deltagare under den valda tidsperioden i rapporterna.

>[!NOTE]
>
>Rapporter som körs med [!DNL Target] har en fördröjning på fyra minuter. För aktiviteter som drivs av A4T kan det i både [!DNL Target]- och [!DNL Analytics]-rapporterna ta upp till 24 timmar efter att aktiviteten ursprungligen sparats innan rapportdata kan delas upp efter upplevelser. De data som samlas in under dessa första 24 timmar är fortfarande korrekta och tilldelas rätt upplevelse.

## Rapporter i analys {#analytics}

I [!DNL Analytics] finns det flera dimensioner och mått tillgängliga efter att A4T-integreringen har aktiverats.

### Dimensioner

* [!UICONTROL Analytics for Target] - Det överordnade ID som skickas via integreringen. Dimensionens format är `Activity ID:Experience ID:3rd ID`. Dimensionerna nedan är klassificeringar av den här dimensionen.
* [!UICONTROL Target Activities]
* [!UICONTROL Target Experiences]
* [!UICONTROL Target Activity] >  [!UICONTROL Experience]
* [!UICONTROL 3rd ID] - kan ignoreras

### Mått

* [!UICONTROL Activity Impressions] - Matchar  [!UICONTROL Entrants] talet i  [!DNL Target] rapporten.
* [!UICONTROL Activity Conversions] - Matchar  [!UICONTROL Custom Conversions] talet i  [!DNL Target] rapporten.

I [!DNL Analysis Workspace] använder du panelen [!UICONTROL Analytics for Target] för att analysera dina [!DNL Target]-aktiviteter och -upplevelser med lyft och självförtroende. Mer information finns i [Analytics for Target (A4T) Panel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) i *Analytics Tools Guide*.

>[!IMPORTANT]
>
>Om din [!UICONTROL Target Activities]-rapport i [!DNL Analytics] visar &quot;unspecified&quot; i stället för att visa dina aktiviteter, krävs en uppdatering av ditt provisionerade konto. Kontakta kundtjänst för att lösa problemet.

Mer information och exempel finns i [Analytics &amp; Target: Självstudiekursen&quot;Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)&quot; från Adobe Experience League.

## Rapporter i målet {#section_C0D1F17F88374B6690BF904D7B83B42E}

När [!DNL Analytics] används som rapportkälla visar rapporter i [!DNL Target] de data som samlats in från [!DNL Analytics]. Rapporten skiljer sig något från andra [!DNL Target]-rapporter:

* Listan [!UICONTROL Audiences] visar vilka målgrupper som är tillgängliga för din [!DNL Analytics]-rapportsvit.
* I [!UICONTROL Metric]-listan visas alla mått som är tillgängliga via [!DNL Analytics].

   Alla mått är tillgängliga, inklusive anpassade eller beräknade värden som är inbyggda i [!DNL Analytics].

   Tänk på att alla siffror som ökar visas som positiva i rapporten, även när en ökning egentligen inte är önskvärd. Även om du till exempel vill ha en lägre avhoppsfrekvens visas den högre avhoppsfrekvensen som vinnare med den högsta avhoppsfrekvensen. Tänk på dessa och liknande mätvärden och om du hellre vill öka eller minska siffrorna när du fattar beslut baserat på rapporter.

Du kan använda måttet eller målgruppen för rapporten om [!DNL Target] efter att aktiviteten har startats, eller till och med efter att testet har slutförts. Du behöver inte veta exakt vad du vill mäta i förväg.

Klicka för att visa den fullständiga [!DNL Analytics]-rapporten direkt från aktivitetsrapportsidan.

## Skapa aktivitet {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

När aktiviteten skapas måste du ange ett mål för aktiviteten på [!UICONTROL Settings]-sidan. Det här målet blir standardmåttet för rapporten och anges alltid som det första alternativet i mätväljaren. Du kan inte välja segment för rapportering på samma sätt som för en vanlig Target-aktivitet. Ett test med [!DNL Analytics] använder [!DNL Adobe Analytics] segment i stället för [!DNL Target] målgrupper.

## Utföra offlineberäkningar för Analytics för Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Du kan utföra offlineberäkningar för A4T, men det krävs ett steg med dataexporter i [!DNL Analytics].

Mer information finns i [Utföra offlineberäkningar för analys av mål (A4T)](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).
