---
keywords: besökarprofil;målbesökarprofil
description: Lär dig hur du skapar målgrupper i [!DNL Adobe Target] för att rikta in dig på besökare som uppfyller specifika profilparametrar som nya eller återkommande besökare, kategoritillhörighet med mera.
title: Kan jag rikta in mig på besökare som uppfyller specifika profilparametrar?
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Besökarprofil

Skapa målgrupper i [!DNL Adobe Target] för att inrikta dig på besökare som uppfyller specifika profilparametrar.

1. I gränssnittet [!DNL Target] klickar du på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Namnge målgruppen och lägg till en valfri beskrivning.
1. Dra och släpp **[!UICONTROL Visitor Profile]** i rutan för målgruppsbyggaren.

1. Klicka på **[!UICONTROL Select]** och välj sedan ett av följande alternativ:

   ![target_visitor_profile image](assets/target_visitor_profile.png)

   Parametrar för besökarprofiler skickas via mbox (profil). Du kan ange nya eller återkommande besökare som mål, eller inkludera alla användare.

   * [!UICONTROL New Visitor]
   * [!UICONTROL Returning Visitor]
   * [!UICONTROL In Other Tests]
   * [!UICONTROL Not In Other Tests]
   * [!UICONTROL First Page of Session]
   * [!UICONTROL Not First Page of Session]
   * [!UICONTROL Category Affinity]

   En besökarprofil skapas i det lokala edge-minnet för varje mbox-anrop med nya `mboxPC`. Efter 30 minuters inaktivitet sparas profilen i databasen [!DNL Target] och är tillgänglig från andra kanter.

   När en besökare loggar in i mitten av sessionen och får en `3rdpartyId` är alla tidigare inlästa profilattribut som är kopplade till `3rdPartyId` omedelbart tillgängliga.

   Du kan ange anpassade profilparametrar och `user.` parametrar som mål. Välj den parameter som du vill använda som mål för aktiviteten. Om den önskade parametern inte visas har parametern inte utlösts av en mbox.

1. (Valfritt) Ange ytterligare regler för målgruppen.
1. Klicka på **[!UICONTROL Done]**.

## Utbildningsvideo: Skapar märket ![Översikt](/help/main/assets/overview.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
