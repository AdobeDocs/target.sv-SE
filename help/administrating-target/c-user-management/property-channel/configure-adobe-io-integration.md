---
keywords: integration;roles;user permissions;admin console
description: Information om hur du ger befintliga Adobe I/O-integreringar åtkomst till alla arbetsytor med önskad roll i Adobe Target
title: Ge Adobe I/O-integrationer åtkomst till arbetsytor och tilldela roller i Adobe Target
feature: user management
subtopic: Getting Started
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Bevilja Adobe I/O-integreringar åtkomst till arbetsytor och tilldela roller

[!UICONTROL Enterprise Permissions] gör det möjligt för [!DNL Target] kunderna att använda en enda organisation, men dela upp den i arbetsytor för sina olika team eller arbetsflöden.

>[!NOTE]
>
>Egenskaper och behörigheter är tillgängliga som en del av [Target Premium](/help/c-intro/intro.md#premium) -lösningen. De finns inte i [!DNL Target Standard] utan [!DNL Target Premium] licens.

Funktionen gör det enklare att [!UICONTROL Enterprise Permissions] effektivt skala optimeringsprogram mellan olika team. Även om funktionen var tillgänglig i [!DNL Target] användargränssnittet saknade administratörs-API:erna motsvarande stöd fram till tidigare år 2019. I [!DNL Target] februari 2019 uppdaterade Adobe Admin API:erna så att du kan använda integrationskontot för att komma åt alla arbetsytor som skapats i organisationen. Tidigare var Admin API:er begränsade till standardarbetsytan, men uppdateringen från februari 2019 gav åtkomst till alla arbetsytor med [!UICONTROL Approver] åtkomst.

Med versionen från [!DNL Target] september 2019 [!DNL Target] får [!UICONTROL Enterprise Permissions] kunderna följande åtkomstkontroller:

* Du kan välja vilka arbetsytor som integreringen kan användas på
* Du kan använda en roll för I/O-integrering i Adobe: [!UICONTROL Approver], [!UICONTROL Editor]eller [!UICONTROL Observer].

Uppdateringen stöder följande användningsexempel:

* Ge Adobe I/O-integrering åtkomst till alla arbetsytor med rollen för [!UICONTROL Observer] rapportering utan behörighet att skapa eller redigera resurser.
* Ge Adobe I/O-integrering åtkomst till utvalda arbetsytor med rätt roll så att ett centralt team kan göra API-drivna ändringar på bara ett fåtal arbetsytor.
* Låt varje team som äger arbetsytan ha en egen integrering när teamet är redo att utforska API:er och välja rollen i enlighet med detta.
* Blanda och matcha ovanstående scenarier.

**Åtgärd krävs**: De kunder som för närvarande utnyttjar API:er för CRUD-åtgärder på resurser (aktiviteter, målgrupper, erbjudanden och rapporter) på alla arbetsytor måste ge sin befintliga Adobe I/O-integrering tillgång till alla arbetsytor med den önskade rollen beroende på användningsfallet. Du kan göra det genom att markera varje [!DNL Target] objekt [!UICONTROL Product Profile] i [!DNL Adobe Admin Console] och lägga till integreringen/integrationerna på [!UICONTROL Integration] fliken. Före versionen från september användes alla integreringar med [!UICONTROL Approver] åtkomst, oavsett vilket alternativ som gjordes i [!UICONTROL Product Role] listrutan. Du kan nu välja önskad roll.

>[!NOTE]
>
>Om den här åtgärden inte utförs aktiveras åtkomstkontrollerna efter [!DNL Target] versionen från september 2019, och du ser bara åtkomst till standardarbetsytan om det är så du är konfigurerad. Det finns ingen negativ reaktion på att upprätta integreringar i förväg. Ju tidigare du gör den här ändringen, desto bättre. Beroende på antalet arbetsytor i organisationen tar den här processen bara några klick för att lägga till en befintlig integrering i arbetsytor med den önskade rollen.

**Så här ger du Adobe I/O-integreringar åtkomst till arbetsytor och tilldelar roller:**

1. Öppna **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Klicka på **[!UICONTROL Products]** fliken och välj sedan namnet på önskad produkt.

   ![Välj produkt i Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Välj önskad arbetsyta (produktprofil).

   ![Välj produktprofil](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Klicka på **[!UICONTROL Integrations]** fliken.

   ![Fliken Integrationer](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Villkorligt) Om du vill lägga till en ny integrering klickar du **[!UICONTROL Add Integration]** på, väljer önskad integrering och klickar sedan på **[!UICONTROL Save]**.

1. Välj önskad roll för arbetsytan i den **[!UICONTROL Product Role]** nedrullningsbara listan:

   | Roll | Beskrivning |
   |--- |--- |
   | Godkännare | Kan skapa, redigera och aktivera eller stoppa aktiviteter. |
   | Redigerare | Kan skapa och redigera aktiviteter innan de är aktiva, men kan inte godkänna att en aktivitet startas. |
   | Observer | Kan visa aktiviteter, men kan inte skapa eller redigera dem. |
   | Utgivare | Liknar observationsrollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Utgivarrollen har dock ytterligare behörighet att aktivera aktiviteter. |
