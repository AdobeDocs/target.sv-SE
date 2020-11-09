---
keywords: visitor profile;target visitor profile
description: Skapa målgrupper i Adobe Target för att inrikta er på besökare som uppfyller specifika profilparametrar.
title: Alternativ för besökarprofiler i Adobe Target
feature: audiences
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# Besökarprofil{#visitor-profile}

Skapa målgrupper för målgrupper som uppfyller specifika profilparametrar.

1. I [!DNL Target] gränssnittet klickar du **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Ge publiken ett namn.
1. Klicka på **[!UICONTROL Add Rule]** > **[!UICONTROL Visitor Profile]**.

   ![](assets/target_visitor_profile.png)

1. Klicka på **[!UICONTROL Select]** och välj sedan något av följande alternativ:

   Parametrar för besökarprofiler skickas via mbox (profil). Du kan ange nya eller återkommande besökare som mål, eller inkludera alla användare.

   * Ny besökare
   * Returnerar besökare
   * I andra tester
   * Inte i andra tester
   * Första sidan av sessionen
   * Inte första sidan i sessionen
   * Kategoritillhörighet

   En besökarprofil skapas i det lokala edge-minnet för varje mbox-anrop med nya `mboxPC`. Efter 30 minuters inaktivitet sparas profilen i måldatabasen och är tillgänglig från andra kanter.

   När en besökare loggar in mitt i sessionen och får en `3rdpartyId`fil blir alla tidigare inlästa profilattribut som är kopplade till `3rdPartyId` den omedelbart tillgängliga.

   Du kan ange anpassade profilparametrar och `user.` parametrar som mål. Välj den parameter som du vill använda som mål för aktiviteten. Om den önskade parametern inte visas har parametern inte utlösts av en mbox.

1. (Valfritt) Klicka **[!UICONTROL Add Rule]** och ange ytterligare regler för publiken.
1. Klicka på **[!UICONTROL Save]**.

## Utbildningsvideo: Märket Skapa ![publiköversikt](/help/assets/overview.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
