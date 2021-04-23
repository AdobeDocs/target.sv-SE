---
keywords: beteendedatakälla;analys;rekommendationer;kriterier;produktvariabler
description: Lär dig hur du använder Adobe Analytics som beteendedatakälla för att använda vybaserade och/eller inköpsbaserade beteendedata från Analytics i [!DNL Target] Recommendations.
title: Hur använder jag Adobe Analytics med  [!DNL Target] Recommendations?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 0%

---

# Använd Adobe Analytics med Recommendations

Om du använder [!DNL Adobe Analytics] som beteendedatakälla kan klienterna använda vybaserade och/eller inköpsbaserade beteendedata från [!DNL Analytics] i [!DNL Adobe Target] rekommendationsaktiviteter. Den här funktionen är särskilt användbar i situationer där [!DNL Target Recommendations]-konfigurationen är ny och [!DNL Analytics] har många historiska data att utnyttja.

Om du använder [!DNL Analytics] som beteendedatakälla kan det fungera som en rik källa till information om användarbeteenden. Detta kan inkludera data från en källa eller feed från tredje part som bara delas med [!DNL Analytics].

När du [skapar villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md) i Recommendations finns det två alternativknappar som du kan använda för att välja vilken datakälla som ska användas: [!UICONTROL mboxes] eller [!UICONTROL Analytics].

![Knappar för beteendedatakälla](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>Om de här två knapparna inte visas på ditt konto kan du kontakta [kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Använd exempel för analysdata i Target

Om du använder [!DNL Analytics] som beteendedatakälla för rekommendationer kan du även distribuera specifika användningsfall utan att behöva tagga enhetssidor med alla [!DNL Target]-enhetsparametrar. Även om det kräver att vissa förutsättningar finns på plats, är tillgängligheten av&quot;produktvariabler&quot; det viktigaste för att den funktionen ska fungera smidigt. Regelbunden eVars och Props räcker inte för att den här handskakningen ska ske automatiskt mellan [!DNL Analytics] och [!DNL Target].

Du kan använda [!DNL Analytics] som beteendedatakälla för att:

* Visa rekommendationer på en återförsäljarwebbplats för användare på en PDP-sida, baserat på vad andra användare har köpt från samma kategori den senaste månaden, med hjälp av Analytics-data.
* Visa innehåll på startskärmen på en mediewebbplats för det populäraste innehållet i en viss kategori som för närvarande är trendbaserad, baserat på [!DNL Analytics]-data.

## Implementering i Analytics

Följande avsnitt hjälper dig att implementera den här funktionen på [!DNL Analytics]-sidan.

### Förutsättningar: ställa in produktvariabler i Analytics

Du måste implementera produktvariabler i [!DNL Analytics] med nödvändiga attribut som krävs för [!DNL Target Recommendations].

Ett [!DNL Target Recommendations]-exempelformat fungerar som guide för vilka alla attribut måste definieras i produktvariablerna. Senare måste dessa värden&quot;mappas&quot; inom användargränssnittet för [!DNL Target] för respektive [!DNL Target]-entitetsvärde.

>[!NOTE]
>
>Om det är en innehållsplats måste respektive innehållskomponenter behandlas som&quot;produkter&quot; och tillhörande attribut om innehållet (till exempel: författarnamn, publiceringsdatum, innehållstitel, månad för publicering osv.) måste skickas som attribut. Företaget bör besluta om huruvida det är fråga om en viss kategori, eller en viss typ av kategori, baserat på ärendekraven.

Mer information om hur du ställer in produktvariabler finns i [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) i *implementeringshandboken för analyser*. Vissa av anteckningarna i den dokumentationen måste hanteras av det team som distribuerar den (exempel: Kategori). Rådfråga Adobe innan du utför denna åtgärd.

### Överväganden

[!DNL Analytics] data skickas via ett dagligt flöde. Beteenderesultaten kan ta upp till 24 timmar att återspeglas i rekommendationerna på din webbplats. Precis som med alla [!DNL Recommendations]-kriterieinställningar kan och bör den här datakällan testas.

För att snabbt kunna fatta beslut om vilken datakälla som ska användas, om det finns många organiska data som genereras varje dag av användare och inte så mycket beroende av historiska data, kan det vara bra att använda en [!DNL Target]-ruta som beteendedatakälla. Om det inte finns tillräckligt med organiska data som genererats nyligen, och du vill lagra på [!DNL Analytics]-data, passar det bra att använda [!DNL Analytics] som datakälla för beteendet.

Nu är det dags att mappa dessa variabler på [!DNL Target]-sidan för kontinuerlig leverans av beteendedata.

## Implementera i mål

1. I Mål klickar du på **[!UICONTROL Recommendations]** och sedan på fliken **[!UICONTROL Feeds]**.

   ![Feeds](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Klicka på **[!UICONTROL Create Feed]**.

1. Välj **[!UICONTROL Analytics Classifications]** och ange sedan rapportsviten.

   ![Analysklassificeringar, alternativ](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Klicka på **[!UICONTROL Mapping]** och mappa sedan fältkolumnrubrikerna till lämpliga [!UICONTROL Recommendations]-fältnamn.

   ![Mappningsavsnitt](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Klicka på **[!UICONTROL Save]**.

## Vanliga frågor

Tänk på följande vanliga frågor när du använder [!DNL Analytics] med [!DNL Target]:

### Måste värdena `entity.id` och `entity.categoryId` skickas inom mbox-anropet för [!DNL Target]?

Ja, dessa två värden krävs fortfarande. Resten av attributen kan skickas via en [!DNL Analytics]-feed, vilket beskrivs i det här dokumentet.

### Kan jag använda regler för dynamisk inkludering, t.ex. enhetsparametern matchar profilattribut med matningsmetoden [!DNL Analytics]?

Ja, det kan du. Metoden liknar den för fristående [!DNL Target]. I det här fallet måste du dock tänka på timingfaktorn. De entitetsvariabler som ska matcha profilvariablerna är beroende av datalagret som kan visas mycket senare på sidan.
