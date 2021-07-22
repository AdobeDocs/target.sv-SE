---
keywords: Riktning;trafikkällor;måltrafikkällor;målsökmotor;sökmotor;landningssida;målstartsida;hänvisande landningssida
description: Lär dig hur du skapar målgrupper i Adobe [!DNL Target] för att rikta in besökare baserat på sökmotorn eller landningssidan som refererar till dem på din webbplats.
title: Kan jag rikta in besökare baserat på sökmotor eller referenswebbplats?
feature: Målgrupper
exl-id: 61902d29-36ea-4d9a-8650-f6f6690a545b
source-git-commit: c02a22723b38d4cd2e3d338eab4e4b19b7e3d68c
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Trafikkällor

Skapa målgrupper i [!DNL Adobe Target] för att rikta in er på besökare baserat på den sökmotor eller landningssida som refererar dem till er webbplats.

Du kan till exempel ange mål baserat på besökarens webbläsare, sökmotor eller den hänvisande landningssidan. Den hänvisande landningssidan är den sida besökaren klickade på för att nå den aktuella platsen under sessionen. (Om besökaren till exempel klickade på en annons på Google och det leder honom till startsidan för `adobe.com` är den refererande landningssidan `google.com`.)

Du kan kombinera flera trafikkällor för att skapa en komplex målarregel.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. 
   1. Namnge målgruppen och lägg till en valfri beskrivning.
1. Dra och släpp **[!UICONTROL Traffic Sources]** i rutan för målgruppsbyggaren.

   ![](assets/target_traffic_source.png)

1. Klicka på **[!UICONTROL Select]** och välj sedan ett av följande alternativ:

   * **[!UICONTROL From Baidu]**
   * **[!UICONTROL From Bing]**
   * **[!UICONTROL From Google]**
   * **[!UICONTROL From Yahoo]**
   * **[!UICONTROL Referring Landing Page: URL]**
   * **[!UICONTROL Referring Landing Page: Domain]**
   * **[!UICONTROL Referring Landing Page: Query]**

   Beroende på vad du väljer kan du behöva ange ytterligare information (utvärderare och/eller värden).

1. (Valfritt) Ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Done]**.

Du kan rikta in dig på användare som hänvisas till din webbplats av en specifik sökmotor eller från en specifik landningssida.

## Utbildningsvideo: Skapar publikation ![Översikt](/help/assets/overview.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
