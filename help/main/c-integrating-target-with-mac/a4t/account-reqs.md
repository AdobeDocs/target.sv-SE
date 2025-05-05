---
keywords: Analyser som rapportkälla;a4t;A4T;requirements
description: Lär dig hur du konfigurerar de användarkontokrav som krävs för att skapa en Adobe Analytics-baserad aktivitet i Adobe [!DNL Target] med Analytics for [!DNL Target] (A4T).
title: Vilka behörighetskrav krävs för A4T?
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# Krav på användarbehörighet

Information om användarkontokraven för att skapa en [!DNL Adobe Analytics]-baserad aktivitet i [!DNL Adobe Target] (A4T).

Innan du kan välja en rapportserie när du definierar en [!DNL Analytics]-aktivitet måste du ha både ett [!DNL Analytics]-användarkonto och ett [!DNL Target]-användarkonto.

Dina användarkonton måste konfigureras enligt beskrivningen i följande avsnitt:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Utför följande uppgifter i [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com):

### Länka konton till din Adobe ID

Dina [!DNL Analytics]- och [!DNL Target]-användarkonton måste länkas till din Adobe ID.

Mer information finns i [Organisationer och kontolänkning](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=sv-SE).

### Konfigurera Experience Cloud-gruppmedlemskap

Du måste vara medlem i en eller flera [!DNL Experience Cloud]-grupper som har åtkomst till [!DNL Analytics] och [!DNL Target].

Mer information finns i [Hantera användare och produkter i Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=sv-SE).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Om du vill använda A4T på en viss rapportserie måste du ha tillgång till den rapportsviten och ge åtkomst till gruppen [!DNL Web Services Access].

1. I **[!UICONTROL Admin Console]** klickar du på en [!DNL Analytics]-produktprofil och sedan på fliken **[!UICONTROL Permissions]**.

   Du kan sedan se vilka rapportsviter profilen har åtkomst till.

1. Kontrollera att den rapportsvit som du vill ha åtkomst till i [!DNL Target] är en av de som finns i produktprofilen som du är en del av.

   Följande bild är ett exempel på en produktprofil som har tillgång till alla rapportsviter:

   ![Behörighetsfliken Admin Console](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. Konfigurera åtkomst till gruppen [!UICONTROL Web Services Access].

   Åtkomst till gruppen [!UICONTROL Web Services Access] i [!DNL Analytics] krävs för att [!DNL Analytics] ska kunna användas som rapportkälla för [!DNL Target].


## Adobe [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

Inga ytterligare behörigheter krävs.
