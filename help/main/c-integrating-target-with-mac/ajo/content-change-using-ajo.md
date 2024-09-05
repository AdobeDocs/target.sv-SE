---
keywords: optimera;personalisering;adobe-reseoptimering;ajo;användningsfall;scenarier;innehållsändring/ab test;profilattribut;change image;swap image
description: Lås upp hemligheterna för effektiv A/B-testning av innehållsändringar i Adobe Journey Optimizer
title: Innehållet ändras via A/B-testning i  [!DNL Adobe Journey Optimizer]
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="Vad är Beta-funktioner i  [!DNL Adobe Target]?"
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: a8d1ad897972edd4263901d411f57b4d22fdd1eb
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 0%

---

# Innehållet ändras via A/B-testning i [!DNL Adobe Journey Optimizer]

Det här användningsexemplet hjälper dig att låsa upp hemligheter för effektiva ändringar av A/B-testinnehåll i [!DNL Adobe Journey Optimizer].

I det här användningsexemplet visas hur du utför välkända uppgifter, till exempel A/B-testning med en [A/B-testaktivitet](/help/main/c-activities/t-test-ab/test-ab.md), med [!DNL Journey Optimizer] i stället för [!DNL Adobe Target].

Det här användningsexemplet är utformat för att visa hur du utför välkända uppgifter som du kan ha utfört med [!DNL Adobe Target], A/B-testning med en [A/B-testaktivitet](/help/main/c-activities/t-test-ab/test-ab.md), men med [!DNL Journey Optimizer].

## Fördelar och värde

* **Optimera innehållseffektivitet**: Identifiera vilka innehållsvariationer och element som fungerar bäst tillsammans med era kunder, vilket leder till ökat engagemang och fler konverteringar.
* **Datadrivna beslut**: Utnyttja data för att fatta välgrundade beslut i hela innehållsstrategin, vilket ger maximal effekt.
* **Personlig användarupplevelse**: Anpassa innehållet efter de unika preferenserna och behoven för alla era målgruppssegment.

## Möjliga scenarier

* Ett klädföretag ökade konverteringarna genom att testa olika bilder och personalisera kampanjlandningssidor med användarnas förnamn i texten som anropar till åtgärd.

* Ett e-handelsföretag fann att deras guldkunder hade högre konverteringsgrad genom att testa olika produktbeskrivningar och bilder på en kampanjstartsida, vilket ledde till ökad försäljning.

## Steg

>[!NOTE]
>
>Instruktionerna i det här avsnittet visar de nödvändiga stegen för att ändra en bild och för att använda profilattribut för att anpassa textmeddelanden. Mer information om tillgängliga alternativ i webbdesignern [!DNL Journey Optimizer] finns i [Redigera webbinnehåll](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} i *Journey Optimizer-dokumentationen*.
>
>Videon längst ned på sidan är särskilt användbar.

Utför följande steg för att optimera en webbsida genom att testa olika bilder och anpassa meddelanden med användarens förnamn med hjälp av ett profilskript:

1. I [!DNL Adobe Journey Optimizer] klickar du på **Kampanjer** i den vänstra listen för att visa sidan [!UICONTROL Campaigns].

   ![Adobe Journey Optimizer landningssida med fliken Kampanjer markerad.](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. Klicka på **[!UICONTROL Create Campaign]** i det övre högra hörnet på sidan [!UICONTROL Campaigns].

1. Välj **[!UICONTROL Scheduled - Marketing]** (standard) och klicka sedan på **Skapa** för att visa informationssidan för [!UICONTROL Campaign].

   ![Kampanjinformationssida i Adobe Journey Optimizer](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. I avsnittet **[!UICONTROL Properties]** anger du ett beskrivande namn och en valfri beskrivning för kampanjen.

1. (Villkorligt) Klicka på **[!UICONTROL Select Audience]** i avsnittet **[!UICONTROL Audience]** och välj önskad målgrupp.

   I det här fallet kan du aktivera kampanjen för [!UICONTROL All Visitors] (standardvärdet).

1. I avsnittet **[!UICONTROL Action]** väljer du **[!UICONTROL Web]** i listrutan **[!UICONTROL Action]** och väljer eller skapar sedan en ny webbkonfiguration.

   En webbkonfiguration, eller kanalyta, är en konfiguration som definieras av en systemadministratör. Webbkonfigurationen innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparameter, underdomän, mobilappar och så vidare.

   Mer information finns i [Konfigurera kanalytor](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} i *Journey Optimizer-dokumentationen*.

1. Klicka på **[!UICONTROL Edit Content]** i avsnittet **[!UICONTROL Action]** för att öppna din webbplats i webbdesignern [!DNL Journey Optimizer].

   Två eller flera försök krävs för A/B-testning. Du kan använda din befintliga hemsida som första experiment. Efterföljande steg förklarar hur du skapar ett andra experiment.

   ![Yoga-landningssida på LUMA-webbplatsen](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Om du vill skapa ett experiment för att avgöra vilket innehåll som fungerar bättre klickar du på **[!UICONTROL Create Experiment]**.

   Med innehållsexperiment kan du variera meddelandeinnehåll, ämne eller avsändare för att definiera flera behandlingar och för att fastställa den bästa kombinationen för era målgrupper. Mer information finns i [Skapa ett innehållsexperiment](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/content-experiment/content-experiment){target=_blank} i *Journey Optimizer-dokumentationen*.

1. Välj ett framgångsmått och klicka på åtgärden.

   Klicka på hjälpikonerna om du vill ha mer information och länkar till relevanta artiklar.

1. Klicka på **[!UICONTROL Add Treatment]** och sedan på **[!UICONTROL Create]**.

   I det här fallet kan du lämna fördelningen på 50 % för varje experiment.

1. Klicka på **[!UICONTROL Edit Content]** under **[!UICONTROL Action]** på informationssidan för [!UICONTROL Campaign].

1. Klicka på Webb under Behandling B

   I det här fallet ska [!UICONTROL Treatment A] inte ändras om du vill använda den ursprungliga upplevelsen som första upplevelse i A/B-testet.

1. Klicka på **[!UICONTROL Edit Web Page]** i den högra listen.

   ![Sidan Redigera innehåll på Yoga-landningssidan](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. Om du vill ändra hjältebilden klickar du på bilden som du vill ändra och sedan på knappen **[!UICONTROL Choose Image]**.

   ![Välj bildknapp](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. Bläddra till och markera önskad bild och klicka sedan på **[!UICONTROL Use This Image]**.

   ![Ny hjältebild på Yoga-sidan](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. Om du vill anpassa meddelandet med användarens förnamn med hjälp av profilattribut klickar du på texten som du vill anpassa och klickar sedan på **[!UICONTROL Add Personalization]** för att visa sidan [!UICONTROL Add Personalization].

   ![Knappen Lägg till Personalization.](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

   Mer information om profilattribut finns i [Kom igång med personaliseringsredigeraren](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} i *Journey Optimizer-dokumentationen*.

1. Sök efter och klicka på plustecknet för att lägga till profilattributet för&quot;förnamn&quot;, justera texten efter behov och klicka sedan på **[!UICONTROL Save]**.

   ![Lägg till profilattribut för namnet](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)

   Mer information finns i [Kom igång med personaliseringsredigeraren](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} i *Journey Optimizer-dokumentationen*.

1. Klicka på bakåtpilen i det övre vänstra hörnet för att gå tillbaka till webbdesignern.

   ![Bakåtpil](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. Klicka på **[!UICONTROL Review to Activate]**, kontrollera att allt ser ut som förväntat och klicka sedan på **Aktivera**.

## Visa rapporter

Klicka på knappen [!UICONTROL Reports] och klicka sedan på önskad rapportperiod:

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

Mer information finns i [Kom igång med det nya rapporteringsgränssnittet](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank} i *Journey Optimizer-dokumentationen*.

>[!MORELIKETHIS]
>
>[Redigera webbinnehåll](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} i *Journey Optimizer-dokumentationen*
>[Instruktionsvideo](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content#video){target=_blank} i *Journey Optimizer-dokumentationen*
>[Skapa en kampanj ](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} i *Journey Optimizer Tutorials*

