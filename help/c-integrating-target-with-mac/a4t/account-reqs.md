---
keywords: Analytics as reporting source;a4t;A4T;requirements
description: Krav för användarkonto för att skapa en Adobe Analytics-baserad aktivitet i Adobe Target (A4T).
title: Krav på användarbehörighet
feature: a4t implementation
solution: Target,Analytics
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---


# Krav på användarbehörighet

Information om användarkontokraven för att skapa en [!DNL Adobe Analytics]baserad aktivitet i [!DNL Adobe Target] (A4T).

Innan du kan välja en rapportsserie när du definierar en [!DNL Analytics] aktivitet måste du ha både ett [!DNL Analytics] användarkonto och ett [!DNL Target] användarkonto.

Dina användarkonton måste konfigureras enligt beskrivningen i följande avsnitt:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Utför följande uppgifter i [!DNL Adobe Experience Cloud][Admin Console](https://adminconsole.adobe.com):

### Länka lösningskonton till din Adobe ID

Dina [!DNL Analytics] - och [!DNL Target] användarkonton måste länkas till din Adobe ID.

Mer information finns i [Organisationer och kontolänkning](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### Konfigurera Experience Cloud-gruppmedlemskap

Du måste vara medlem i en eller flera [!DNL Experience Cloud] grupper som har åtkomst till [!DNL Analytics] och [!DNL Target].

Mer information finns i [Hantera användare och produkter](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)i Experience Cloud.

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Konfigurera åtkomst till [!DNL Analytics] rapportsviten:

Om du vill använda A4T på en viss rapportserie måste du ha tillgång till den rapportsviten.

1. I **[!UICONTROL Admin Console]** klickar du på en [!DNL Analytics] produktprofil och sedan på **[!UICONTROL Permissions]** fliken.

   Du kan sedan se vilka rapportsviter profilen har åtkomst till.

1. Se till att den rapportserie som du vill ha tillgång till i [!DNL Target] är en av de som finns i produktprofilen som du är en del av.

   Följande bild är ett exempel på en produktprofil som har tillgång till alla rapportsviter:

   ![Behörighetsfliken Admin Console](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

Inga ytterligare behörigheter krävs.
