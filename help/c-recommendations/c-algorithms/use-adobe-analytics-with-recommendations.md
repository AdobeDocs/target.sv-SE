---
keywords: beteendedatakälla;analys;rekommendationer;kriterier;produktvariabler
description: Lär dig använda [!DNL Adobe Analytics] as the behavioral data source to use the view-based and/or purchase-based behavioral data from [!DNL Analytics] in [!DNL Target Recommendations].
title: Hur jag använder [!DNL Adobe Analytics] med [!DNL Target Recommendations]?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 2dc134d064b0707bcc8a24a08e9831e1cfa0b08e
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%

---

# ![PREMIUM](/help/assets/premium.png) Använd [!DNL Adobe Analytics] med [!DNL Recommendations]

Använda [!DNL Adobe Analytics] eftersom beteendedatakällan låter kunderna använda vybaserade och/eller inköpsbaserade beteendedata från [!DNL Analytics] in [!DNL Adobe Target] [!DNL Recommendations] verksamhet. Den här funktionen är särskilt användbar i situationer där [!DNL Target Recommendations] är nytt och [!DNL Analytics] har mycket historiska data att använda.

Använda [!DNL Analytics] eftersom beteendedatakällan kan fungera som en omfattande källa till information om användarbeteenden. Den här informationen kan innehålla data från en källa eller ett flöde från tredje part som bara delas med [!DNL Analytics].

while [skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md) in [!DNL Recommendations], det finns två alternativknappar som du kan använda för att välja vilken datakälla som ska användas: [!UICONTROL mboxes] eller [!UICONTROL Analytics]. Om du vill skapa ett villkor klickar du på [!UICONTROL Recommendations] > [!UICONTROL Criteria] > [!UICONTROL Create Criteria] > [!UICONTROL Create Criteria]. Mer information finns i [Skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md).

![Knappar för beteendedatakälla](assets/behavioral-data-source.png)

>[!NOTE]
>
>Om de här två knapparna inte visas i ditt konto kan du kontakta [Kundtjänst](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Använd exempel för analysdata i Target

Använda [!DNL Analytics] som den beteendebaserade datakällan för rekommendationer också gör att ni kan driftsätta specifika användningsfall utan att behöva tagga enhetssidor med alla [!DNL Target] enhetsparametrar. Även om det kräver att vissa förutsättningar finns på plats, är tillgängligheten av&quot;produktvariabler&quot; det viktigaste för att den funktionen ska fungera smidigt. Regelbundna eVars- och Props-variabler är inte tillräckliga för att den här handskakningen ska ske automatiskt mellan [!DNL Analytics] och [!DNL Target].

Du kan använda [!DNL Analytics] som den beteendebaserade datakällan för att

* Visa rekommendationer för användare på en produktinformationssida utifrån vad andra användare har köpt från samma kategori den senaste månaden, med [!DNL Analytics] data.
* Visa innehåll på startskärmen på en mediawebbplats för det populäraste innehållet i en viss kategori som för närvarande är trendbaserad, baserat på [!DNL Analytics] data.

## Implementering i [!DNL Analytics]

Följande avsnitt hjälper dig att implementera den här funktionen i [!DNL Analytics] sida.

### Förutsättningar: konfigurera produktvariabler i [!DNL Analytics]

Implementera produktvariabler i [!DNL Analytics] med de attribut som krävs för [!DNL Target Recommendations].

A [!DNL Target Recommendations] exempelfeedformatet fungerar som en guide för vilka alla attribut måste definieras i produktvariablerna. Senare måste dessa värden&quot;mappas&quot; inom [!DNL Target] Gränssnittet för respektive [!DNL Target] enhetsvärden.

>[!NOTE]
>
>Om det är en innehållsplats måste respektive innehållskomponenter behandlas som&quot;produkter&quot; och tillhörande attribut om innehållet måste skickas som attribut. Sådana attribut kan vara författarnamn, publiceringsdatum, innehållstitel, publiceringsmånad och så vidare. Företaget bör besluta om huruvida det är fråga om en viss kategori, eller en viss typ av kategori, baserat på ärendekraven.

Mer information om hur du ställer in produktvariabler finns i [produkter](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) i *Implementera Adobe Analytics* guide. Vissa av anteckningarna i den dokumentationen måste hanteras av det team som distribuerar den (exempel: Kategori). Det rekommenderas alltid att du använder [!DNL Adobe] innan du utför den här aktiviteten.

### Överväganden

[!DNL Analytics] data skickas via ett dagligt flöde. Beteenderesultat kan ta upp till 24 timmar att reflektera inom rekommendationerna på din webbplats. Som med alla [!DNL Recommendations] villkorsinställningar, kan och bör den här datakällan testas.

För att snabbt kunna fatta beslut om vilken datakälla som ska användas, om det finns mycket organisk information som genereras varje dag av användarna och inte mycket beroende av historiska data, använder man en [!DNL Target] mbox som beteendedatakälla kan vara en bra passform. Om det finns mindre tillgång till ekologiska data som genererats nyligen, om du vill använda [!DNL Analytics] data, sedan använder [!DNL Analytics] eftersom beteendedatakällan passar bra.

Nu är det dags att mappa dessa variabler på [!DNL Target] sidan för kontinuerlig tillgång till beteendedata.

## Implementera i [!DNL Target]

1. I [!DNL Target], klicka **[!UICONTROL Recommendations]** klickar du på **[!UICONTROL Feeds]** -fliken.

   ![Feeds](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Klicka på **[!UICONTROL Create Feed]**.

1. Välj **[!UICONTROL Analytics Classifications]** anger du sedan rapportsviten.

   ![Analysklassificeringar, alternativ](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Klicka **[!UICONTROL Next]** för att gå vidare till **[!UICONTROL Schedule]** -inställningar väljer du en frekvensperiod för feeden:

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 weeks]
   * [!UICONTROL Never]

   Du kan också välja vilken tid på dagen som flödet ska bearbetas.

1. Klicka **[!UICONTROL Next]** för att gå vidare till  **[!UICONTROL Mapping]** inställningar, mappa sedan kolumnrubrikerna i fältet till lämpliga [!UICONTROL Recommendations] fältnamn.

   ![Mappningsavsnitt](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Klicka på **[!UICONTROL Save]**.

## Vanliga frågor

Ta till exempel följande frågor och svar när du använder [!DNL Analytics] med [!DNL Target]:

### Är `entity.id` och `entity.categoryId` värden som måste skickas inom [!DNL Target] mbox-samtal?

Ja, dessa två värden krävs fortfarande. Resten av attributen kan skickas via en [!DNL Analytics] feed, enligt vad som beskrivs i det här dokumentet.

### Kan jag använda dynamiska inkluderingsregler, t.ex. enhetsparametern matchar profilattribut med [!DNL Analytics] mata in?

Ja, det kan du. Metoden är densamma när du använder [!DNL Target] fristående. I det här fallet måste du dock tänka på timingfaktorn. Vilka entitetsvariabler som ska matcha profilvariablerna beror på vilket datalager som kan visas mycket senare på sidan.
