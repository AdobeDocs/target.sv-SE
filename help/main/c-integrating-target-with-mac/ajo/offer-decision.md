---
keywords: alternativ för visuell upplevelsedisposition;alternativ för upplevelsedisposition;alternativ för upplevelsedisposition;beslut om erbjudande;ajo;reseoptimering
description: Lär dig hur du lägger till ett erbjudandebeslut som skapats i [!DNL Adobe Journey Optimizer]  till en aktivitet.
title: Hur använder jag erbjudandebeslut?
feature: Integrations
exl-id: cec46d5c-bb5e-4cc9-8785-370f158d3f8e
source-git-commit: d31c9a6f47ea73342cfb638600f351ade4be7013
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 0%

---

# Använd offertbeslut

Använd [!DNL Adobe Target] med [!DNL Adobe Journey Optimizer] för att bestämma och leverera nästa bästa erbjudande för dina besökare på webben och i mobilen.

Lägg till offertbeslut som har skapats i [!DNL Adobe Journey Optimizer] till [!DNL Target]-aktiviteter (manuell [!UICONTROL A/B Test] eller [!UICONTROL Experience Targeting]) med [!UICONTROL Visual Experience Composer] (VEC) eller [!UICONTROL Form-Based Composer] för att testa och leverera personaliserade erbjudanden till dina besökare i dina inkommande kanaler som drivs av [!DNL Target].

Mer information om [!DNL Adobe Journey Optimizer] och erbjudandebeslut finns i följande avsnitt i *[!DNL Journey Optimizer]*-dokumentationen:

* [Kom igång med Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=sv-SE)

* [Om beslutshantering](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=sv-SE)

## Förutsättningar

Om du vill använda erbjudandebeslut i [!DNL Target] behöver du följande:

* [!DNL Adobe Target Standard] eller [!DNL Adobe Target Premium] som har implementerats med [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

  Funktionen är inte tillgänglig vid implementering av [!DNL Target] med at.js eller andra [!DNL Target] SDK:er.

* [!DNL Adobe Journey Optimizer Ultimate] (AJO + Offer Decisioning) eller [!DNL Adobe Experience Platform] och programtjänsttillägget [!UICONTROL Offer Decisioning].

## Exempel på användningsområden

Följande exempel är exempel på hur du kan använda integreringen [!DNL Target]/[!DNL Adobe Journey Optimizer] för att använda offertbeslut i [!DNL Target]-aktiviteter:

### Sportförsäljning

Som marknadsförare för en idrottsklass vill ni personalisera innehåll på er hemsida (både på datorsidan och på mobilwebbplatsen). Ni vill personalisera innehåll baserat på flera dimensioner och presentera ett erbjudande till butiksrelaterade franchise-produkter. Du är intresserad av:

* Besökarens favoritteam
* Senaste idrott-/spelaraktivitet (till exempel lagrörelser, kontraktsuppdateringar eller skador)

Du vill till exempel leverera en personlig upplevelse för var och en av följande regioner: Dortmund, Frankfurt och Bochum och för användare som är implicita och explicita fans för dessa team. Som mätvärden vill du titta på besök och klicka på webbplatsen för varor.

Du vill utforma en [!UICONTROL A/B Test]-aktivitet (delning 50/50) mellan standardupplevelsen och den personaliserade upplevelsen (som inkluderar ett erbjudandebeslut med erbjudanden för varje region och team). Du vill använda den här aktiviteten för att avgöra konverteringen och lyften för den personaliserade upplevelsen jämfört med kontrollen.

### Plattformar för spelströmning

Som marknadsförare för en spelorganisation vill ni leverera ett personaliserat erbjudande för en spelplattform för användare på datorer och mobila enheter från olika platser: Tyskland, Frankrike, Mexiko och Brasilien. När en besökare kommer till en dator- eller mobilwebbplats från någon av dessa platser vill ni leverera ett erbjudande om spelströmning på det lokala språket och till motsvarande pris för den lokala valutan.

I [!DNL Adobe Journey Optimizer] kan du skapa ett personligt startsidans hjälteerbjudande för var och en av de avsedda geografiska områdena plus ett reserverbjudande med en standardstartsidans hjälte. Du kan sedan skapa ett beslut om erbjudandet som innehåller dessa erbjudanden och deras regler för behörighet. I [!DNL Target] kan du sedan skapa en [!DNL Experience Targeting] (XT)-aktivitet och infoga erbjudandebeslutet på din stationära eller mobila webbplats för att leverera den personaliserade upplevelsen till besökarna.

## Skapa en upplevelse som utnyttjar ett erbjudandebeslut:

1. När du redigerar eller skapar en manuell [!UICONTROL A/B Test]- eller [!UICONTROL Experience Targeting] (XT)-aktivitet i [!UICONTROL Visual Experience Composer] (VEC) klickar du på ett sidelement för att visa [alternativmenyn](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   ![Alternativ-menyn i Visual Experience Composer](assets/options-menu1.png)

   >[!NOTE]
   >
   >Du kan också skapa en upplevelse som använder [!UICONTROL Offer Decisions] i [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md).

1. Klicka på **[!UICONTROL Replace Content]** och sedan på **[!UICONTROL Offer Decision]**.

   Alternativet [!UICONTROL Offer Decision] är endast tillgängligt när du redigerar eller skapar [&#x200B; manuella [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) - eller [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)-aktiviteter. Det här alternativet är inte tillgängligt för andra aktivitetstyper. Vilka alternativ som är tillgängliga på menyn varierar beroende på vilket element som är markerat.

   ![Alternativ-menyn i Visual Experience Composer](assets/options-menu.png)

1. Markera önskad sandlåda i fältet **[!UICONTROL Add Offer Decision]** till höger om VEC och klicka sedan på Välj erbjudande.placering.

   Med en [sandlåda](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/overview.html?lang=sv-SE){target=_blank} i [!DNL Adobe Experience Platform] kan du partitionera instansen i virtuella miljöer. Du kan till exempel ha en produktionsmiljö och en staging-miljö. En [placering](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/create-components/creating-placements.html?lang=sv-SE){target=_blank} i [!DNL Adobe Journey Optimizer] säkerställer att rätt erbjudandeinnehåll visas på rätt plats.

   ![Listrutorna Sandlåda och Placeringar i dialogrutan Lägg till erbjudandebeslut](/help/main/c-integrating-target-with-mac/ajo/assets/sandbox-placement.png)

1. Välj önskat erbjudande och välj erbjudande och klicka sedan på **[!UICONTROL Add]**.

   ![Välj beslutsdialogruta för erbjudande](/help/main/c-integrating-target-with-mac/ajo/assets/select-offer-decision.png)

   Din webbplats visas i VEC där du kan se erbjudandebeslutet som nyligen har skapats i [!UICONTROL Modifications]-spåret. Du kan klicka på ett erbjudande under [!UICONTROL Offer Preview] längst ned på [!UICONTROL Offer Decision] för att undersöka erbjudandebeslutet.

   <!--You can examine the various offers contained in the offer by clicking the appropriate icon at the bottom of the [!UICONTROL Offer Preview] dialog box, including the fallback offer. A fallback offer is the default offer displayed when a visitor is not eligible for any of the personalized offers in the collection.-->

   ![Förhandsgranska erbjudande](assets/offer-preview2.png)

1. Slutför skapandet av aktiviteten genom att slutföra [!UICONTROL Targeting]- och [!UICONTROL Goals & Settings]-stegen i det guidade arbetsflödet i tre delar.

   >[!IMPORTANT]
   >
   >Om du vill vara säker på att aktiviteten [!DNL Target] är anpassad kontrollerar du att de aktuella start-/slutdatumen för aktiviteten är synkroniserade med startdatumet/slutdatumet för erbjudandebeslutet i [!DNL Adobe Journey Optimizer]. Om [!DNL Target] start-/slutdatum ligger utanför erbjudandebeslutets start-/slutdatumintervall visas standardinnehållet för [!DNL Target] för besökarna.

## Anteckningar och begränsningar

Tänk på följande när du arbetar med offertbeslut:

* Faktisk integrering av erbjudandebeslut fungerar för [!DNL Target] implementeringar baserat på [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}. Den här funktionen är inte tillgänglig vid implementering av [!DNL Target] med at.js eller andra [!DNL Target] SDK:er.

* Integrationen [!DNL Target]/[!DNL Adobe Journey Optimizer] stöder endast [&#x200B; manuella [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types)- och [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT)-aktiviteter. Den här funktionen är inte tillgänglig för andra aktivitetstyper.

* Du kan inte använda [[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) om du använder erbjudandebeslut i en aktivitet. Välj [!DNL Target] som rapportkälla på sidan [!UICONTROL Goals and Settings] under aktivitetsinställningar om du använder offertbeslut i aktiviteten.

* Erbjudanden med innehållstypen text/html stöder inte leveransURL-innehållsleverans. DeliveryURL stöds endast via [formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) där klienten ansvarar för att hämta och disponera innehållet explicit.

* [!DNL Target]-rapportering tillhandahåller inte rapportering på beslutsnivå.

* Visualisering av [QA-länkar](/help/main/c-activities/c-activity-qa/activity-qa.md) för [!DNL Target] upplevelser som innehåller erbjudandebeslut påverkar den frekvensbegränsning som angetts i [!DNL Adobe Journey Optimizer] för dessa erbjudandebeslut.
