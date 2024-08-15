---
keywords: optimera;personalisering;adobe-reseoptimering;ajo;användningsfall;scenarier;innehållsändring/ab test;profilattribut;change image;swap image
description: Lås upp hemligheterna för effektiv A/B-testning av innehållsändringar i Adobe Journey Optimizer
title: Innehållet ändras via A/B-testning i  [!DNL Adobe Journey Optimizer]
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="Vad är Beta-funktioner i  [!DNL Adobe Target]?"
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: bbf56b2d041ea6537116d900278242a7a679dedd
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 0%

---

# Innehållet ändras via A/B-testning i [!DNL Adobe Journey Optimizer]

Det här användningsexemplet hjälper dig att låsa upp hemligheter för effektiva ändringar av A/B-testinnehåll i [!DNL Adobe Journey Optimizer].

## Scenario

Ett klädföretag ökade konverteringarna genom att testa olika bilder och personalisera kampanjlandningssidor med användarnas förnamn från sina profilattribut.

## Fördelar och värde

* **Optimera innehållseffektivitet**: Identifiera vilka innehållsvariationer och element som fungerar bäst tillsammans med era kunder, vilket leder till ökat engagemang och fler konverteringar.
* **Datadrivna beslut**: Utnyttja data för att fatta välgrundade beslut i hela innehållsstrategin, vilket ger maximal effekt.
* **Personlig användarupplevelse**: Anpassa innehållet efter de unika preferenserna och behoven för alla era målgruppssegment.

## Stegvisa instruktioner

Utför följande steg för att optimera en webbsida genom att testa olika bilder och anpassa meddelanden med användarnas förnamn:

1. I [!DNL Adobe Journey Optimizer] klickar du på **Kampanjer** i den vänstra listen för att visa sidan [!UICONTROL Campaigns].

   ![Adobe Journey Optimizer landningssida med fliken Kampanjer markerad.](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. Klicka på **[!UICONTROL Create Campaign]** i det övre högra hörnet på sidan [!UICONTROL Campaigns].

1. Välj **[!UICONTROL Scheduled - Marketing]** (standard) och klicka sedan på **Skapa** för att visa informationssidan för [!UICONTROL Campaign].

   ![Kampanjinformationssida i Adobe Journey Optimizer](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. Ange ett beskrivande namn och en valfri beskrivning av kampanjen.

1. (Villkorligt) Klicka på **[!UICONTROL Select Audience]** och välj önskade målgrupper.

   I det här fallet valde vi att aktivera kampanjen för alla besökare (standardinställningen).

1. Välj **[!UICONTROL Web]** i listrutan **[!UICONTROL Action]** och välj eller skapa en ny webbkonfiguration.

   En webbkonfiguration, eller kanalyta, är en konfiguration som har definierats av en systemadministratör. Webbkonfigurationen innehåller alla tekniska parametrar för att skicka meddelandet, som rubrikparameter, underdomän, mobilappar och så vidare.

   Mer information finns i [Konfigurera kanalytor](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} i *Journey Optimizer-dokumentationen*.

1. Klicka på **[!UICONTROL Edit Content]** för att öppna din webbplats i webbdesignern [!DNL Journey Optimizer].

   ![Yoga-landningssida på LUMA-webbplatsen](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Klicka på **[!UICONTROL Edit Web Page]** i den högra listen.

   ![Sidan Redigera innehåll på Yoga-landningssidan](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. Om du vill ändra hjältebilden klickar du på bilden som du vill ändra och sedan på knappen **[!UICONTROL Choose Image]**.

   ![Välj bildknapp](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. Bläddra till och markera önskad bild och klicka sedan på **[!UICONTROL Use This Image]**.

   ![Ny hjältebild på Yoga-sidan](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. Om du vill anpassa meddelandet med användarens förnamn med hjälp av profilattribut klickar du på texten som du vill anpassa och klickar sedan på **[!UICONTROL Add Personalization]** för att visa sidan [!UICONTROL Add Personalization].

   ![Knappen Lägg till Personalization.](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

1. Sök efter och markera profilattributet för förnamn, justera texten efter behov och klicka sedan på **[!UICONTROL Save]**.

   ![Lägg till profilattribut för namnet](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)

   Mer information finns i [Kom igång med personaliseringsredigeraren](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} i *Journey Optimizer-dokumentationen*.

1. Klicka på bakåtpilen i det övre vänstra hörnet för att gå tillbaka till webbdesignern.

   ![Bakåtpil](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. Klicka på **[!UICONTROL Review to Activate]**, kontrollera att allt ser ut som förväntat och klicka sedan på **Aktivera**.

>[!MORELIKETHIS]
>
>[Redigera webbinnehåll](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} i *Journey Optimizer-dokumentationen*
>[Instruktionsvideo](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/web-spa#video){target=_blank} i *Journey Optimizer-dokumentationen*
>[Skapa en kampanj ](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} i *Journey Optimizer Tutorials*

