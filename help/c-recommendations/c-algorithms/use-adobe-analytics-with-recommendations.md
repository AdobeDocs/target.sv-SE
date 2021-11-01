---
keywords: beteendedatakälla;analys;rekommendationer;kriterier;produktvariabler
description: Lär dig hur du använder Adobe Analytics som beteendedatakälla för att använda vybaserade och/eller inköpsbaserade beteendedata från Analytics i [!DNL Target] Recommendations.
title: Hur använder jag Adobe Analytics med [!DNL Target] Recommendations?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 2a4cae206bf634bf3fbec65c5c4b289aadefede1
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Använd Adobe Analytics med Recommendations

Använda [!DNL Adobe Analytics] eftersom beteendedatakällan låter kunderna använda vybaserade och/eller inköpsbaserade beteendedata från [!DNL Analytics] in [!DNL Adobe Target] Rekommendationsaktiviteter. Den här funktionen är särskilt användbar i situationer där [!DNL Target Recommendations] är nytt och [!DNL Analytics] har många historiska data att utnyttja.

Använda [!DNL Analytics] eftersom beteendedatakällan kan fungera som en omfattande källa till information om användarbeteenden. Detta kan inkludera data från en källa eller feed från tredje part som bara delas med [!DNL Analytics].

while [skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md) I Recommendations finns det två alternativknappar som du kan använda för att välja vilken datakälla som ska användas: [!UICONTROL mboxes] eller [!UICONTROL Analytics].

![Knappar för beteendedatakälla](assets/behavioral-data-source.png)

>[!NOTE]
>
>Om de här två knapparna inte visas i ditt konto kan du kontakta [Kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Använd exempel för analysdata i Target

Använda [!DNL Analytics] som den beteendemässiga datakällan för rekommendationer också ger möjlighet att distribuera specifika användningsfall utan att behöva tagga enhetssidor med alla [!DNL Target] enhetsparametrar. Även om det kräver att vissa förutsättningar finns på plats, är tillgängligheten av&quot;produktvariabler&quot; det viktigaste för att den funktionen ska fungera smidigt. Regelbundna eVars- och Props-variabler är inte tillräckliga för att den här handskakningen ska ske automatiskt mellan [!DNL Analytics] och [!DNL Target].

Du kan använda [!DNL Analytics] som den beteendebaserade datakällan för att

* Visa rekommendationer på en återförsäljarwebbplats för användare på en PDP-sida, baserat på vad andra användare har köpt från samma kategori den senaste månaden, med hjälp av Analytics-data.
* Visa innehåll på startskärmen på en mediawebbplats för det populäraste innehållet i en viss kategori som för närvarande är trendbaserad, baserat på [!DNL Analytics] data.

## Implementering i Analytics

Följande avsnitt hjälper dig att implementera den här funktionen i [!DNL Analytics] sida.

### Förutsättningar: ställa in produktvariabler i Analytics

Du måste implementera produktvariabler i [!DNL Analytics] med de attribut som krävs för [!DNL Target Recommendations].

A [!DNL Target Recommendations] exempelmatningsformatet fungerar som riktlinjer för vilka alla attribut måste definieras i produktvariablerna. Senare måste dessa värden&quot;mappas&quot; inom [!DNL Target] Gränssnittet för respektive [!DNL Target] enhetsvärden.

>[!NOTE]
>
>Om det är en innehållsplats måste respektive innehållskomponenter behandlas som&quot;produkter&quot; och tillhörande attribut om innehållet (till exempel: författarnamn, publiceringsdatum, innehållstitel, månad för publicering osv.) måste skickas som attribut. Företaget bör besluta om huruvida det är fråga om en viss kategori, eller en viss typ av kategori, baserat på ärendekraven.

Mer information om hur du ställer in produktvariabler finns i [produkter](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) i *Implementeringshandbok för analyser*. Vissa av anteckningarna i den dokumentationen måste hanteras av det team som distribuerar den (exempel: Kategori). Rådfråga Adobe innan du utför denna åtgärd.

### Överväganden

[!DNL Analytics] data skickas via ett dagligt flöde. Beteenderesultaten kan ta upp till 24 timmar att återspeglas i rekommendationerna på din webbplats. Som med alla [!DNL Recommendations] villkorsinställningar, kan och bör den här datakällan testas.

För att snabbt kunna fatta beslut om vilken datakälla som ska användas, om det finns många organiska data som genereras varje dag av användarna och inte så mycket beroende som krävs av historiska data, använder man en [!DNL Target] mbox som beteendedatakälla kan vara en bra passform. Om det finns mindre tillgång till ekologiska data som genererats nyligen, om du vill använda [!DNL Analytics] data, sedan använder [!DNL Analytics] eftersom beteendedatakällan passar bra.

Nu är det dags att mappa dessa variabler på [!DNL Target] sidan för kontinuerlig tillgång till beteendedata.

## Implementera i mål

1. I Mål klickar du på **[!UICONTROL Recommendations]** klickar du på **[!UICONTROL Feeds]** -fliken.

   ![Feeds](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Klicka på **[!UICONTROL Create Feed]**.

1. Välj **[!UICONTROL Analytics Classifications]** anger du sedan rapportsviten.

   ![Analysklassificeringar, alternativ](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Klicka **[!UICONTROL Mapping]** mappa sedan kolumnrubrikerna i fältet till rätt [!UICONTROL Recommendations] fältnamn.

   ![Mappningsavsnitt](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Klicka på **[!UICONTROL Save]**.

## Vanliga frågor

Ta till exempel följande frågor och svar när du använder [!DNL Analytics] med [!DNL Target]:

### Är `entity.id` och `entity.categoryId` värden som måste skickas inom [!DNL Target] mbox-samtal?

Ja, dessa två värden krävs fortfarande. Resten av attributen kan skickas via en [!DNL Analytics] feed, enligt vad som beskrivs i det här dokumentet.

### Kan jag använda dynamiska inkluderingsregler, t.ex. enhetsparametern matchar profilattribut med [!DNL Analytics] mata in?

Ja, det kan du. Metoden är densamma när du använder [!DNL Target] fristående. I det här fallet måste du dock tänka på timingfaktorn. De entitetsvariabler som ska matcha profilvariablerna är beroende av datalagret som kan visas mycket senare på sidan.
