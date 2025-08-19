---
keywords: beteendedatakälla;analys;rekommendationer;kriterier;produktvariabler
description: Lär dig hur du använder  [!DNL Adobe Analytics]  som beteendedatakälla i [!DNL Target Recommendations].
title: Hur använder jag [!DNL Adobe Analytics] med [!DNL Target Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%

---

# Använd [!DNL Adobe Analytics] med [!DNL Recommendations]

Om du använder [!DNL Adobe Analytics] som beteendedatakälla kan klienterna använda vybaserade och inköpsbaserade beteendedata från [!DNL Analytics] i [!DNL Adobe Target Recommendations]-aktiviteter. Den här funktionen är särskilt användbar i situationer där [!DNL Target Recommendations]-konfigurationen är ny och [!DNL Analytics] har många historiska data att använda.

Om du använder [!DNL Analytics] som beteendedatakälla kan det fungera som en omfattande källa till information om användarbeteenden. Den här informationen kan innehålla data från en källa eller feed från tredje part som bara delas med [!DNL Analytics].

När [skapar villkor](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) i [!DNL Recommendations] finns det två alternativknappar som gör att du kan välja vilken datakälla som ska användas: [!UICONTROL mboxes] eller [!UICONTROL Analytics]. Om du vill skapa ett villkor klickar du på [!UICONTROL Recommendations] > [!UICONTROL Criteria] > [!UICONTROL Create Criteria] > [!UICONTROL Create Criteria]. Mer information finns i [Skapa villkor](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

>[!NOTE]
>
>Om de här två knapparna inte visas på ditt konto kan du kontakta [kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Använd ärenden för [!DNL Analytics] data i [!DNL Target]

Om du använder [!DNL Analytics] som beteendedatakälla för rekommendationer kan du även distribuera specifika användningsfall utan att behöva tagga enhetssidor med alla [!DNL Target] -enhetsparametrar. Även om det kräver att vissa förutsättningar finns på plats, är tillgängligheten av&quot;produktvariabler&quot; det viktigaste för att den funktionen ska fungera smidigt. Vanliga eVars och Props räcker inte för att den här handskakningen ska ske automatiskt mellan [!DNL Analytics] och [!DNL Target].

Du kan använda [!DNL Analytics] som beteendedatakälla för att:

* Visa rekommendationer på en butiksplats för användare på en produktinformationssida, baserat på vad andra användare har köpt från samma kategori den senaste månaden, med hjälp av [!DNL Analytics]-data.
* Visa innehåll på startskärmen på en mediewebbplats för det populäraste innehållet i en viss kategori som för närvarande är trendbaserad, baserat på [!DNL Analytics]-data.

## Implementering i [!DNL Analytics]

Följande avsnitt hjälper dig att implementera den här funktionen på [!DNL Analytics]-sidan.

### Krav: konfigurera produktvariabler i [!DNL Analytics]

Implementera produktvariabler i [!DNL Analytics] med nödvändiga attribut som krävs för [!DNL Target Recommendations].

Ett [!DNL Target Recommendations]-exempelformat fungerar som guide för vilka alla attribut måste definieras i produktvariablerna. Senare måste dessa värden&quot;mappas&quot; inom användargränssnittet [!DNL Target] för respektive [!DNL Target]-entitetsvärde.

>[!NOTE]
>
>Om det är en innehållsplats måste respektive innehållskomponenter behandlas som&quot;produkter&quot; och tillhörande attribut om innehållet måste skickas som attribut. Sådana attribut kan vara författarnamn, publiceringsdatum, innehållstitel, publiceringsmånad och så vidare. Företaget bör besluta om huruvida det är fråga om en viss kategori, eller en viss typ av kategori, baserat på ärendekraven.

Mer information om hur du ställer in produktvariabler finns i [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html?lang=sv-SE) i guiden *Implementera Adobe Analytics*. Vissa av anteckningarna i den dokumentationen måste hanteras av det team som distribuerar den (exempel: Kategori). Du bör alltid rådfråga [!DNL Adobe] innan du utför den här aktiviteten.

### Överväganden

[!DNL Analytics] data skickas via en daglig feed. Beteenderesultat kan ta upp till 24 timmar att reflektera inom rekommendationerna på din webbplats. Precis som med alla [!DNL Recommendations]-kriterieinställningar kan och bör den här datakällan testas.

För att snabbt kunna fatta beslut om vilken datakälla som ska användas, om det finns mycket organiska data som genereras varje dag av användare och inte mycket beroende av historiska data, kan det vara bra att använda en [!DNL Target]-ruta som beteendedatakälla. Om det inte finns tillräckligt med organiska data som genererats nyligen, och du vill lagra på [!DNL Analytics] data, passar det bra att använda [!DNL Analytics] som beteendedatakälla.

Nu är det dags att mappa dessa variabler på [!DNL Target]-sidan för kontinuerlig leverans av beteendedata.

## Implementera i [!DNL Target]

1. I [!DNL Target] klickar du på **[!UICONTROL Recommendations]** och sedan på fliken **[!UICONTROL Feeds]**.

1. Klicka på **[!UICONTROL Create Feed]**.

1. Välj **[!UICONTROL Analytics Classifications]** och ange sedan rapportsviten.

1. Klicka på **[!UICONTROL Next]** om du vill gå vidare till inställningarna för **[!UICONTROL Schedule]** och välj en frekvensperiod för feeden:

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 weeks]
   * [!UICONTROL Never]

   Du kan också välja vilken tid på dagen som flödet ska bearbetas.

1. Klicka på **[!UICONTROL Next]** om du vill gå vidare till inställningarna för **[!UICONTROL Mapping]** och mappa sedan fältkolumnrubrikerna till rätt [!UICONTROL Recommendations]-fältnamn.

1. Klicka på **[!UICONTROL Save]**.

## Vanliga frågor

Tänk på följande vanliga frågor när du använder [!DNL Analytics] med [!DNL Target]:

### Måste värdena `entity.id` och `entity.categoryId` skickas inom mbox-anropet [!DNL Target]?

Ja, dessa två värden krävs fortfarande. Resten av attributen kan skickas via en [!DNL Analytics]-feed, vilket beskrivs i det här dokumentet.

### Kan jag använda dynamiska inkluderingsregler, som entitetsparametern matchar profilattribut med matningsmetoden [!DNL Analytics]?

Ja, det kan du. Metoden liknar den för fristående [!DNL Target]. I det här fallet måste du dock tänka på timingfaktorn. Vilka entitetsvariabler som ska matcha profilvariablerna beror på vilket datalager som kan visas mycket senare på sidan.
