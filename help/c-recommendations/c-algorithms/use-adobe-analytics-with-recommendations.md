---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: Genom att använda Adobe Analytics som beteendedatakälla kan kunderna använda vybaserade och/eller inköpsbaserade beteendedata från Analytics i Adobe Recommendations.
title: Använda Adobe Analytics med Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: 205850df6108db962a4ab514c027b7d04effaa76
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 0%

---


# Använd Adobe Analytics med Recommendations

Med [!DNL Adobe Analytics] som beteendedatakälla kan kunderna använda vybaserade och/eller inköpsbaserade beteendedata från [!DNL Analytics] i [!DNL Adobe Target] rekommendationsaktiviteter. Den här funktionen är särskilt användbar i situationer där [!DNL Target Recommendations] konfigurationen är ny och [!DNL Analytics] har många historiska data att utnyttja.

Om du använder [!DNL Analytics] som beteendedatakälla kan det fungera som en rik källa till information om användarbeteenden. Detta kan omfatta data från en källa eller feed från tredje part som bara delas med [!DNL Analytics].

När du [skapar villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md) i Recommendations finns det två alternativknappar där du kan välja vilken datakälla som ska användas: [!UICONTROL mboxes] eller [!UICONTROL Analytics].

![Knappar för beteendedatakälla](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>Om de här två knapparna inte visas på ditt konto kan du kontakta [kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Användningsexempel

Genom [!DNL Analytics] att använda som beteendedatakälla för rekommendationer kan du även distribuera specifika användningsfall utan att behöva tagga enhetssidor med alla [!DNL Target] enhetsparametrar. Även om det kräver att vissa förutsättningar finns på plats, är tillgängligheten av&quot;produktvariabler&quot; det viktigaste för att den funktionen ska fungera smidigt. Regelbunden eVars och Props räcker inte för att den här handskakningen ska ske automatiskt mellan [!DNL Analytics] och [!DNL Target].

Du kan använda [!DNL Analytics] som beteendedatakälla för att:

* Visa rekommendationer på en återförsäljarwebbplats för användare på en PDP-sida, baserat på vad andra användare har köpt från samma kategori den senaste månaden, med hjälp av Analytics-data.
* Visa innehåll på startskärmen på en mediewebbplats för det populäraste innehållet i en viss kategori som för närvarande är trendbaserad, baserat på [!DNL Analytics] data.

## Implementering i Analytics

Följande avsnitt hjälper dig att implementera den här funktionen på [!DNL Analytics] sidan.

### Förutsättningar: produktvariabler i Analytics

Du måste implementera produktvariabler i [!DNL Analytics] med de attribut som krävs för [!DNL Target Recommendations].

Ett [!DNL Target Recommendations] exempel på ett feed-format fungerar som guide för vilka alla attribut måste definieras i produktvariablerna. Senare måste dessa värden&quot;mappas&quot; inom [!DNL Target] användargränssnittet för respektive [!DNL Target] enhetsvärden.

>[!NOTE]
>
>Om det är en innehållsplats måste respektive innehållskomponenter behandlas som&quot;produkter&quot; och tillhörande attribut om innehållet (till exempel: författarnamn, publiceringsdatum, innehållstitel, månad för publicering osv.) måste skickas som attribut. Företaget bör besluta om huruvida det är fråga om en viss kategori, eller en viss typ av kategori, baserat på ärendekraven.

Mer information om hur du ställer in produktvariabler finns i [produkterna](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/products.html) i *Analytics Implementation Guide*. Vissa av anteckningarna i den dokumentationen måste hanteras av det team som distribuerar den (exempel: Kategori). Rådfråga Adobe innan du utför denna åtgärd.

### Överväganden

[!DNL Analytics] data skickas via ett dagligt flöde. Beteenderesultaten kan ta upp till 24 timmar att återspeglas i rekommendationerna på din webbplats. Precis som med alla [!DNL Recommendations] kriterieinställningar kan och bör den här datakällan testas.

För att snabbt kunna fatta beslut om vilken datakälla som ska användas, om det finns många organiska data som genereras varje dag av användarna och inte mycket beroende av historiska data, kan det vara bra att använda en [!DNL Target] mbox som beteendedatakälla. Om det inte finns så många ekologiska data som genererats nyligen, och du vill lagra dem på [!DNL Analytics] data, passar det bra [!DNL Analytics] att använda som beteendedatakälla.

### Steg för distribution

Utför följande åtgärder om alla förutsättningar finns på plats:

1. I [!DNL Target]klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** för att hämta din [!DNL Target] klientkod.

   ![Klientkod](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. Skaffa en [!DNL Analytics] rapportsserie.

   Använd din [!DNL Analytics] webbplats för produktionsrapporter. Det här är rapportsviten som spårar den plats där du har [!DNL Recommendations] distribuerat.

1. Klicka [!DNL Analytics]på **[!UICONTROL Admin]** > **[!UICONTROL Data Feeds]**.

   ![Inställningar > Dataflöden](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. Klicka **[!UICONTROL Add]** för att skapa en ny feed.

   ![Lägg till feed](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. Fyll i feed-information:

   * **Namn**: Rec Prod Feed
   * **Report Suite**: Din förbestämda rapportsvit
   * **E-post**: Ange en lämplig adress för en Admin-användare
   * **Feedintervall**: Välj önskat intervall
   * **Fördröjningsbearbetning**: Ingen fördröjning.
   * **Start- och slutdatum**: Kontinuerlig feed

   ![Flödesinformationsavsnitt](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. Fyll i informationen i **[!UICONTROL Destination]** avsnittet:

   >[!NOTE]
   > 
   >Kontakta [!DNL Adobe Analytics] teamet innan du utför det här steget.

   * **Typ**: FTP
   * **Värd**: `xxx.yyy.com`
   * **Sökväg**: Din [!DNL Target] klientkod
   * **Användarnamn**: Ange ditt användarnamn
   * **Lösenord**: Ange ditt lösenord

   Skärmbilden är endast avsedd som referens. Distributionen kommer att ha olika autentiseringsuppgifter. Kontakta [!DNL Adobe Analytics] teamet eller kundtjänst medan du utför det här steget.

   ![Målsektion](/help/c-recommendations/c-algorithms/assets/destination.png)

1. Fyll i **[!UICONTROL Data Column]** definitionerna:

   * **Komprimeringsformat**: Gzip
   * **Pakettyp**:  En fil
   * **Manifest:** Slutför fil

      ![Inställningar för komprimeringsformat, paketeringstyp och manifest](/help/c-recommendations/c-algorithms/assets/compression.png)

   * **Inkluderade kolumner**:

      >[!IMPORTANT]
      >
      >Kolumnerna måste läggas till i samma ordning som dokumenteras här. Markera kolumnerna i följande ordning och klicka **[!UICONTROL Add]** för varje kolumn.

      * hit_time_gmt
      * visid_high
      * visid_low
      * event_list
      * product_list
      * besök_num

1. Klicka på **[!UICONTROL Save]**.

   ![Definitionsavsnitt för datakolumner](/help/c-recommendations/c-algorithms/assets/data-column-definitions.png)

Med detta är konfigurationen på [!DNL Analytics] sidan klar. Nu är det dags att kartlägga dessa variabler på [!DNL Target] sidan för kontinuerlig leverans av beteendedata.

## Implementering i mål

1. Klicka på Mål **[!UICONTROL Recommendations]** och sedan på **[!UICONTROL Feeds]** fliken.

   ![Feeds](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Klicka på **[!UICONTROL Create Feed]**.

1. Välj **[!UICONTROL Analytics Classifications]** och ange sedan rapportsviten.

   ![Analysklassificeringar, alternativ](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Klicka **[!UICONTROL Mapping]** och mappa sedan kolumnrubrikerna till rätt [!UICONTROL Recommendations] fältnamn.

   ![Mappningsavsnitt](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Klicka på **[!UICONTROL Save]**.