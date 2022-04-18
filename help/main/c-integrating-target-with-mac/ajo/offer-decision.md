---
keywords: alternativ för visuell upplevelsedisposition;alternativ för upplevelsedisposition;alternativ för upplevelsedisposition;beslut om erbjudande;offer decisioning;ajo;reseoptimering
description: Lär dig hur du lägger till ett offertbeslut som skapats i [!DNL Adobe Journey Optimizer] till en aktivitet.
title: Hur använder jag erbjudandebeslut?
feature: Visual Experience Composer (VEC)
exl-id: cec46d5c-bb5e-4cc9-8785-370f158d3f8e
source-git-commit: 4a2b0f52d00ca40609f3bfbddf7cb2b2bee6a33e
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 0%

---

# Använd offertbeslut

Använd [!DNL Adobe Target] med [!DNL Adobe Journey Optimizer] kan fatta beslut om att bestämma och leverera nästa bästa erbjudande för era besökare på webben och i mobilen.

Lägg till offertbeslut som skapats i [!DNL Adobe Journey Optimizer] till [!DNL Target] verksamhet (manuell [!UICONTROL A/B Test] eller [!UICONTROL Experience Targeting]) med antingen [!UICONTROL Visual Experience Composer] (VEC) eller [!UICONTROL Form-Based Composer] för att testa och leverera personaliserade erbjudanden till besökarna via era inkommande kanaler som drivs av [!DNL Target].

Mer information om [!DNL Adobe Journey Optimizer], se [Kom igång med Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) i *Journey Optimizer* dokumentation.

Mer information om offertbeslut finns i [Om beslutshantering](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html) i *[!DNL Journey Optimizer]* dokumentation.

## Förutsättningar

Använda offertbeslut i [!DNL Target]behöver du följande:

* [!DNL Adobe Target Standard] eller [!DNL Adobe Target Premium] implementerat med [Adobe Experience Platform Web SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md).

   Funktionen är inte tillgänglig vid implementering [!DNL Target] med at.js eller andra [!DNL Target] SDK:er.

* [!DNL Adobe Journey Optimizer Ultimate] (AJ0 + Offer decisioning) eller [!DNL Adobe Experience Platform] och [!UICONTROL Offer Decisioning] programtjänsttillägg.

## Exempel på användningsområden

Följande exempel är exempel på hur du kan använda [!DNL Target]/[!DNL Adobe Journey Optimizer] integration att använda offertbeslut i [!DNL Target] verksamhet:

### Sportförsäljning

Som marknadsförare för en idrottsklass vill ni personalisera innehåll på er hemsida (både på datorsidan och på mobilwebbplatsen). Ni vill personalisera innehåll baserat på flera dimensioner och presentera ett erbjudande till butiksrelaterade franchise-produkter. Du är intresserad av:

* Besökarens favoritteam
* Senaste idrott-/spelaraktivitet (till exempel lagrörelser, kontraktsuppdateringar eller skador)

Du vill till exempel leverera en personaliserad upplevelse för var och en av följande regioner: Dortmund, Frankfurt och Bochum och för användare som är implicita och explicita fans för dessa team. Som mätvärden vill du titta på besök och klicka på webbplatsen för varor.

Du vill designa en [!UICONTROL A/B Test] aktivitet (delning 50/50) mellan standardupplevelsen och den personaliserade upplevelsen (som innefattar ett beslut om erbjudanden för varje region och team). Du vill använda den här aktiviteten för att avgöra konverteringen och lyften för den personaliserade upplevelsen jämfört med kontrollen.

### Plattformar för spelströmning

Som marknadsförare för en spelorganisation vill ni kunna leverera ett personaliserat erbjudande för en spelplattform för användare på datorer och mobila enheter från olika platser: Tyskland, Frankrike, Mexiko och Brasilien. När en besökare kommer till en dator- eller mobilwebbplats från någon av dessa platser vill ni leverera ett erbjudande om spelströmning på det lokala språket och till motsvarande pris för den lokala valutan.

I [!DNL Adobe Journey Optimizer]kan ni skapa ett personligt hemsideshjältererbjudande för var och en av de avsedda geografiska områdena plus ett reserverbjudande med en standardhjälte för hemsidan. Du kan sedan skapa ett beslut om erbjudandet som innehåller dessa erbjudanden och deras regler för behörighet. Sedan [!DNL Target]kan du skapa en [!DNL Experience Targeting] (XT) och infoga erbjudandebeslutet på din dator eller mobila webbplats för att leverera den personaliserade upplevelsen till besökarna.

## Skapa en upplevelse som utnyttjar ett erbjudandebeslut:

1. När du redigerar eller skapar en handbok [!UICONTROL A/B Test] eller [!UICONTROL Experience Targeting] (XT) i [!UICONTROL Visual Experience Composer] (VEC) klickar du på ett sidelement för att visa [alternativmeny](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   ![Menyn Alternativ i Visual Experience Composer](assets/options-menu1.png)

   >[!NOTE]
   >
   >Du kan också skapa en upplevelse som använder [!UICONTROL Offer Decisions] i [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md).

1. Klicka **[!UICONTROL Insert Before]**, **[!UICONTROL Insert After]**, eller **[!UICONTROL Replace Content]** och sedan klicka **[!UICONTROL Offer Decision]**.

   The [!UICONTROL Offer Decision] är tillgängligt när du redigerar eller skapar [manuell [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) eller [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) endast aktiviteter. Det här alternativet är inte tillgängligt för andra aktivitetstyper. Vilka alternativ som är tillgängliga på menyn varierar beroende på vilket element som är markerat.

   ![Menyn Alternativ i Visual Experience Composer](assets/options-menu.png)

1. I **[!UICONTROL Add Offer Decision]** väljer du önskad sandlåda och placering.

   A [sandlåda](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/overview.html){target=_blank} i [!DNL Adobe Experience Platform] I kan du partitionera instansen i virtuella miljöer. Du kan till exempel ha en produktionsmiljö och en staging-miljö. A [placering](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/create-components/creating-placements.html){target=_blank} i [!DNL Adobe Journey Optimizer] hjälper till att säkerställa att rätt erbjudandeinnehåll visas på rätt plats.

   ![Sandbox- och Placements-listrutor i dialogrutan Lägg till erbjudandebeslut](/help/main/c-integrating-target-with-mac/ajo/assets/sandbox-placement.png)

1. Välj önskat erbjudande och klicka sedan på **[!UICONTROL Create]**.

   ![Valt erbjudandebeslut i dialogrutan Lägg till erbjudandebeslut](assets/offer-decision.png)

   Din webbplats visas i VEC där du kan se det nya erbjudandebeslutet i [!UICONTROL Modifications] till höger. Du kan hålla muspekaren över ändringen och klicka på [!UICONTROL Preview] ikonen för att undersöka erbjudandebeslutet.

   ![Ikonen Förhandsgranska](assets/preview-icon.png)

   Du kan titta närmare på de olika erbjudandena genom att klicka på motsvarande ikon längst ned i [!UICONTROL Offer Preview] -dialogrutan, inklusive reserverbjudandet. Ett reserverbjudande är standarderbjudande som visas när en besökare inte är berättigad till något av de personaliserade erbjudandena i samlingen.

   ![Förhandsgranska erbjudande](assets/offer-preview.png)

1. Slutför skapandet av aktiviteten genom att slutföra [!UICONTROL Targeting] och [!UICONTROL Goals & Settings] steg i det guidade arbetsflödet i tre delar.

   >[!IMPORTANT]
   >
   >Se till att [!DNL Target] aktiviteten är personaliserad, kontrollera att de aktuella start-/slutdatumen för aktiviteten är synkroniserade med startdatum/slutdatum för erbjudandebeslutet i [!DNL Adobe Journey Optimizer]. Om [!DNL Target] start-/slutdatum ligger utanför erbjudandebeslutets start-/slutdatumintervall, standardvärdet [!DNL Target] innehållet visas för besökarna.

   ![Meddelande om beslutsvarning](/help/main/c-integrating-target-with-mac/ajo/assets/offer-decision-warning.png)

## Anteckningar och begränsningar

Tänk på följande när du arbetar med offertbeslut:

* Integreringen av offera decisioningar fungerar för [!DNL Target] implementeringar baserade på [Adobe Experience Platform Web SDK](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md). Den här funktionen är inte tillgänglig vid implementering [!DNL Target] med at.js eller andra [!DNL Target] SDK:er.

* Integreringen mellan Target och Adobe Journey Optimizer stöder [manuell [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) och [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) endast aktiviteter. Den här funktionen är inte tillgänglig för andra aktivitetstyper.

* Erbjudanden med innehållstypen text/html stöder inte leveransURL-innehållsleverans. deliveryURL stöds endast via den formulärbaserade Experience Composer där klienten ansvarar för att hämta och disponera innehållet explicit.

* [!DNL Target] rapportering inte ger rapportering på beslutsnivå.

* Visualiserar [QA-länkar](/help/main/c-activities/c-activity-qa/activity-qa.md) for [!DNL Target] upplevelser som innehåller offertbeslut påverkar frekvensbegränsningen som anges i [!DNL Adobe Journey Optimizer] för dessa erbjudandebeslut.
