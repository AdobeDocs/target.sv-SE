---
keywords: implementering;api;profil;profil-API-inställningar;autentiseringstoken
description: Lär dig hur du konfigurerar autentisering för batchuppdateringar via Adobe [!DNL Target] API:er och generera en profilautentiseringstoken.
title: Hur använder jag API-inställningar för profil för att aktivera eller inaktivera batchuppdateringar?
feature: APIs/SDKs
role: Developer
exl-id: 6346e11b-0853-47f1-9706-69e8635a6f25
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Profil-API-inställningar

Aktivera eller inaktivera autentisering för batchuppdateringar via [!DNL Adobe Target] API:er och generera en profilautentiseringstoken.

[!DNL Adobe Target] skapar och underhåller en profil för varje enskild användare. Den här profilen lagras på [!DNL Target] Edge Cluster och uppdateras i realtid efter varje besök. Du kan dock uppdatera en profil individuellt eller gruppvis via API.

För ökad säkerhet kan du kräva att API-anropet för gruppuppdatering kräver att en giltig åtkomsttoken skickas i huvudet för begäran.

**Så här kräver du autentisering och genererar en åtkomsttoken med hjälp av målgränssnittet:**

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.
1. Under **[!UICONTROL Profile API]** visa **[!UICONTROL Require Authentication]** växla till aktiverad eller inaktiverad position.

   ![](assets/profile_api_settings.png)

1. (Villkorligt) Om du har aktiverat autentiseringskrav klickar du på **[!UICONTROL Generate New Profile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   Token förfaller enligt den tid som anges i [!UICONTROL Expires In] box.

   Du måste ha någon av följande användarbehörigheter för att generera en autentiseringstoken:

   * Minst [!UICONTROL Editor] behörighet (eller [!UICONTROL Approver])

      Mer information om [!DNL Target Standard] kunder, se [Ange roller och behörigheter](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) in *Användare*. Mer information om [!DNL Target Premium] kunder, se [Konfigurera företagsbehörigheter](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Administratörsroll på arbetsyta/produktprofilnivå

      Arbetsytor är tillgängliga för [!DNL Target Premium] endast kunder. Mer information finns i [Konfigurera företagsbehörigheter](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Administratörsrättigheter (behörighet som systemadministratör) på [!DNL Adobe Target] produktnivå
   >[!NOTE]
   >
   >Du kan också generera en profilautentiseringstoken via API. Mer information finns i [Profiler](https://developers.adobetarget.com/api/#profiles) på [Adobe Target Developers webbplats](https://developers.adobetarget.com/).

1. Kopiera token och inkludera den i begärans huvud i formatet: &quot;Behörighet&quot;: &quot;Bearer&quot;

Klicka [!UICONTROL Generate New Profile Authentication Token] för att återskapa token efter behov.

>[!IMPORTANT]
>
>Om du återställer den här token kommer API-anrop som använder den aktuella token att misslyckas. Detta kräver uppdatering av skript eller appar som använder denna token.
