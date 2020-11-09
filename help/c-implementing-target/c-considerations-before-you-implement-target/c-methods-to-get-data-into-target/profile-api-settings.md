---
keywords: implementation;api;profile;profile api settings;authentication token
description: Aktivera eller inaktivera autentisering för batchuppdateringar via Adobe Target API:er och generera en profilautentiseringstoken.
title: Profil-API-inställningar i Adobe Target
feature: api
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# Profil-API-inställningar

Aktivera eller inaktivera autentisering för batchuppdateringar via Adobe Target API:er och generera en profilautentiseringstoken.

[!DNL Adobe Target] skapar och underhåller en profil för varje enskild användare. Den här profilen lagras i [!DNL Target] edge-klustret och uppdateras i realtid efter varje besök. Du kan dock uppdatera en profil individuellt eller gruppvis via API.

För ökad säkerhet kan du kräva att API-anropet för gruppuppdatering kräver att en giltig åtkomsttoken skickas i huvudet för begäran.

**Så här kräver du autentisering och genererar en åtkomsttoken med hjälp av målgränssnittet:**

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.
1. Under **[!UICONTROL Profile API]** skjutreglaget **[!UICONTROL Require Authentication]** växlar du till aktiverad eller inaktiverad position.

   ![](assets/profile_api_settings.png)

1. (Villkorligt) Om du har aktiverat autentiseringskrav klickar du på **[!UICONTROL Generate New Profile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   Token förfaller enligt den tid som anges i [!UICONTROL Expires In] rutan.

   Du måste ha någon av följande användarbehörigheter för att generera en autentiseringstoken:

   * Åtminstone [!UICONTROL Editor] tillstånd (eller [!UICONTROL Approver])

      Mer information för [!DNL Target Standard] kunder finns i [Ange roller och behörigheter](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) i *Användare*. Mer information om [!DNL Target Premium] kunder finns i [Konfigurera företagsbehörigheter](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Administratörsroll på arbetsyta/produktprofilnivå

      Arbetsytor är bara tillgängliga för [!DNL Target Premium] kunder. Mer information finns i [Konfigurera företagsbehörigheter](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Administratörsrättigheter (systemadministratörsbehörighet) på [!DNL Adobe Target] produktnivå
   >[!NOTE]
   >
   >Du kan också generera en profilautentiseringstoken via API. Mer information finns i [Profiler](https://developers.adobetarget.com/api/#profiles) på webbplatsen [för](https://developers.adobetarget.com/)Adobe Target-utvecklare.

1. Kopiera token och inkludera den i begärans huvud i formatet: &quot;Behörighet&quot;: &quot;Bearer&quot;

Klicka [!UICONTROL Generate New Profile Authentication Token] för att återskapa token efter behov.

>[!IMPORTANT]
>
>Om du återställer den här token kommer API-anrop som använder den aktuella token att misslyckas. Detta kräver uppdatering av skript eller appar som använder denna token.
