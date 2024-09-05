---
keywords: optimera;personalisering;adobe-reseoptimering;ajo;användningsfall;scenarier;lägga till innehåll;dölja innehåll;lägga till komponenter;dölja komponenter
description: Lär dig hur du lägger till eller döljer komponenter på din webbsida med  [!DNL Adobe Journey Optimizer].
title: Lägg till eller dölj komponenter på webbsidan i  [!DNL Adobe Journey Optimizer]
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="Vad är Beta-funktioner i  [!DNL Adobe Target]?"
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: 000c41efa783889bcb2af20c84956411f73baf40
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 0%

---

# Lägga till eller dölja komponenter på webbsidan

Det här användningsexemplet hjälper dig att låsa upp hemligheter för effektiva ändringar av A/B-testinnehåll i [!DNL Adobe Journey Optimizer].

I det här användningsexemplet visas hur du utför välkända uppgifter, till exempel A/B-testning med en [A/B-testaktivitet](/help/main/c-activities/t-test-ab/test-ab.md), med [!DNL Journey Optimizer] i stället för [!DNL Adobe Target].

Det här användningsexemplet är utformat för att visa hur du utför välkända uppgifter som du kan ha utfört med [!DNL Adobe Target], A/B-testning med en [A/B-testaktivitet](/help/main/c-activities/t-test-ab/test-ab.md), men med [!DNL Journey Optimizer].

## Fördelar och värde

* **Förbättra användarengagemanget**: Fånga användarnas uppmärksamhet med en optimerad siddesign som framhäver relevant information, till exempel kampanjer.
* **Förbättra upptäckten**: Placera nya komponenter eller nytt innehåll på webben eller i mobilappar för att effektivisera åtgärder och förbättra navigeringen.
* **Öka ytterligare kontaktytor**: Vägled användare effektivt mot konverteringshändelser och mål för att öka effekten på verksamheten.

## Möjliga scenarier

* Ett företag inom finanssektorn planerar att lägga till en ny avdelning på sin hemsida för snabb åtkomst till lånekalkylatorn, vilket minskar söktiden och ökar låneansökningarna.

* Ett klädföretag ökade konverteringarna genom att lägga till en ny knapp på sin webbsida.

## Steg

>[!NOTE]
>
>Instruktionerna i det här avsnittet visar de nödvändiga stegen för att ändra en bild och för att använda profilattribut för att anpassa textmeddelanden. Mer information om tillgängliga alternativ i webbdesignern [!DNL Journey Optimizer] finns i [Redigera webbinnehåll](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank} i *Journey Optimizer-dokumentationen*.
>
>Videon längst ned på sidan är särskilt användbar.

Utför följande steg för att lägga till komponenter eller för att dölja komponenter på webbsidan:

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

   ![Yoga-landningssida på LUMA-webbplatsen](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. Om du vill lägga till en knapp för att ringa upp till åtgärd klickar du på **[!UICONTROL Edit Web Page]** i den högra listen.

1. Klicka på

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