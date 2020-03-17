---
keywords: Analytics as reporting source;a4t;A4T
description: Krav för användarkonton för att skapa en Adobe Analytics-baserad aktivitet i Adobe Target (A4T).
title: Krav på användarbehörighet
solution: Target,Analytics
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Krav på användarbehörighet {#user-permission-requirements}

Information om användarkontokraven för att skapa en [!DNL Adobe Analytics]baserad aktivitet i [!DNL Adobe Target] (A4T).

Innan du kan välja en rapportsserie när du definierar en [!DNL Analytics] aktivitet måste du ha både ett [!DNL Analytics] användarkonto och ett [!DNL Target] användarkonto.

Dina användarkonton måste konfigureras enligt beskrivningen i följande avsnitt:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Utför följande uppgifter på [!DNL Adobe Experience Cloud] Admin Console [](https://adminconsole.adobe.com):

### Länka lösningskonton till ditt Adobe ID

Dina [!DNL Analytics] - och [!DNL Target] användarkonton måste länkas till ditt Adobe-ID.

Mer information finns i [Organisationer och kontolänkning](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### Konfigurera Experience Cloud-gruppmedlemskap

Du måste vara medlem i en eller flera [!DNL Experience Cloud] grupper som har åtkomst till [!DNL Analytics] och [!DNL Target].

Mer information finns i [Hantera Experience Cloud-användare och -produkter](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).


## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Utför följande uppgifter i [!DNL Adobe Analytics]:

### Konfigurera åtkomst till Analytics-rapportsviten

Innan du skapar eller visar rapporter för en analysdriven aktivitet måste du vara medlem i **[!UICONTROL All Report Access]** gruppen eller medlem i en grupp som har tillgång till minst en rapport i rapportsviten som du vill använda. Om du inte kan visa rapporter bör du kontrollera att du är medlem i någon av dessa grupper.

Mer information finns i [Produktprofiler och grupper](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html#section_AB50558124D541CF80A0D3D76D35A4BF).

### Konfigurera åtkomst till webbtjänståtkomstgruppen

Du måste tillhöra webbtjänståtkomstgruppen i [!DNL Adobe Analytics] för att kunna använda [!DNL Analytics] som rapportkälla för [!DNL Target].

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

Inga ytterligare behörigheter krävs.
