---
keywords: Analytics as reporting source;a4t;A4T
description: Krav för användarkonto för att skapa en Adobe Analytics-baserad aktivitet i Adobe Target (A4T).
title: Krav på användarbehörighet
feature: a4t implementation
solution: Target,Analytics
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: 3215aa7c5ce986ff335dd2669c250ef5900d8789
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---


# Krav på användarbehörighet {#user-permission-requirements}

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

Mer information finns i [Hantera användare och produkter](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)i Experience Cloud.

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Utför följande uppgifter i [!DNL Adobe Analytics]:

### Konfigurera åtkomst till Analytics-rapportsviten

Om du vill använda A4T på en viss rapportserie måste du ha tillgång till den rapportsviten. Klicka på en [!UICONTROL Admin Console]produktprofil och klicka sedan på [!DNL Analytics] [!UICONTROL Permissions] fliken om du vill få tillgång till den i . Du kan sedan se vilka rapportsviter profilen har åtkomst till. Se till att den rapportserie som du vill ha tillgång till i [!DNL Target] är en av de som finns i produktprofilen som du är en del av.

Följande bild är ett exempel på en produktprofil som har tillgång till alla rapportsviter:

![Behörighetsfliken Admin Console](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

Inga ytterligare behörigheter krävs.
