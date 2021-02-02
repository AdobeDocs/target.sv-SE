---
keywords: implementering;api;profil;profil-API-inställningar;autentiseringstoken
description: Aktivera eller inaktivera autentisering för batchuppdateringar via Adobe Target API:er och generera en profilautentiseringstoken.
title: Profil-API-inställningar
feature: APIs/SDKs
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---


# Profil-API-inställningar

Aktivera eller inaktivera autentisering för batchuppdateringar via [!DNL Adobe Target] API:er och generera en profilautentiseringstoken.

[!DNL Adobe Target] skapar och underhåller en profil för varje enskild användare. Den här profilen lagras på edge-klustret [!DNL Target] och uppdateras i realtid efter varje besök; Du kan dock uppdatera en profil individuellt eller gruppvis via API.

För ökad säkerhet kan du kräva att API-anropet för gruppuppdatering kräver att en giltig åtkomsttoken skickas i huvudet för begäran.

**Så här kräver du autentisering och genererar en åtkomsttoken med hjälp av målgränssnittet:**

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.
1. Under **[!UICONTROL Profile API]** flyttar du växlingsknappen **[!UICONTROL Require Authentication]** till den aktiverade eller inaktiverade positionen.

   ![](assets/profile_api_settings.png)

1. (Villkorligt) Om du har aktiverat autentiseringskrav klickar du på **[!UICONTROL Generate New Profile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   Token förfaller enligt den tid som anges i rutan [!UICONTROL Expires In].

   Du måste ha någon av följande användarbehörigheter för att generera en autentiseringstoken:

   * Minst [!UICONTROL Editor] behörighet (eller [!UICONTROL Approver])

      Mer information för [!DNL Target Standard]-kunder finns i [Ange roller och behörigheter](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) i *Användare*. Mer information om [!DNL Target Premium]-kunder finns i [Konfigurera företagsbehörigheter](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Administratörsroll på arbetsyta/produktprofilnivå

      Arbetsytor är bara tillgängliga för [!DNL Target Premium]-kunder. Mer information finns i [Konfigurera företagsbehörigheter](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Administratörsrättigheter (systemadministratörsbehörighet) på [!DNL Adobe Target]-produktnivå
   >[!NOTE]
   >
   >Du kan också generera en profilautentiseringstoken via API. Mer information finns i [Profiler](https://developers.adobetarget.com/api/#profiles) på webbplatsen [Adobe Target Developers](https://developers.adobetarget.com/).

1. Kopiera token och inkludera den i begärans huvud i formatet: &quot;Behörighet&quot;: &quot;Bearer&quot;

Klicka på [!UICONTROL Generate New Profile Authentication Token] för att återskapa token efter behov.

>[!IMPORTANT]
>
>Om du återställer den här token kommer API-anrop som använder den aktuella token att misslyckas. Detta kräver uppdatering av skript eller appar som använder denna token.
