---
keywords: implementation;api;profile;profile api settings;authentication token
description: Aktivera eller inaktivera autentisering för batchuppdateringar via API och generera en profilautentiseringstoken.
title: Profil-API-inställningar
feature: api
subtopic: Getting Started
topic: Standard
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---


# Profil-API-inställningar{#profile-api-settings}

Aktivera eller inaktivera autentisering för batchuppdateringar via API och generera en profilautentiseringstoken.

[!DNL Adobe Target] skapar och underhåller en profil för varje enskild användare. Den här profilen lagras i [!DNL Target] edge-klustret och uppdateras i realtid efter varje besök, men du kan uppdatera en profil individuellt eller gruppvis via API.

För ökad säkerhet kan du kräva att API-anropet för gruppuppdatering kräver att en giltig åtkomsttoken skickas i huvudet för begäran. Användare med [!UICONTROL Approver] behörigheter kan generera och aktivera autentiseringstoken för profil-API.

**Så här kräver du autentisering och genererar en åtkomsttoken med hjälp av målgränssnittet:**

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.
1. Under **[!UICONTROL Profile API]** skjutreglaget **[!UICONTROL Require Authentication]** växlar du till aktiverad eller inaktiverad position.

   ![](assets/profile_api_settings.png)

1. (Villkorligt) Om du har aktiverat autentiseringskrav klickar du på **[!UICONTROL Generate New Pfofile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   Token förfaller enligt den tid som anges i [!UICONTROL Expires In] rutan.

   >[!NOTE]
   >
   >Du kan också generera en profilautentiseringstoken via API. Mer information finns i [Profiler](https://developers.adobetarget.com/api/#profiles) på webbplatsen [för](https://developers.adobetarget.com/)Adobe Target-utvecklare.

1. Kopiera token och inkludera den i begärans huvud i formatet: &quot;Behörighet&quot;: &quot;Bearer&quot;

Klicka [!UICONTROL Generate New Profile Authentication Token] för att återskapa token efter behov.

>[!IMPORTANT]
>
>Om du återställer den här token kommer API-anrop som använder den aktuella token att misslyckas. Detta kräver uppdatering av skript eller appar som använder denna token.
