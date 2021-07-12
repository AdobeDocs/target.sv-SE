---
keywords: integration;roller;användarbehörigheter;Admin Console
description: Lär dig hur du ger integreringar med Adobe I/O tillgång till alla arbetsytor med önskad roll i Adobe Target.
title: Hur ger jag Adobe I/O åtkomst till arbetsytor och tilldelar roller?
feature: Administration och konfiguration
role: Admin
exl-id: 62f6399f-c590-470c-ac3b-e0c84db63112
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# ![](/help/assets/premium.png) PREMIUMGrant Adobe I/O integrerar åtkomst till arbetsytor och tilldelar roller

[!UICONTROL Enterprise Permissions] ger  [!DNL Target] kunderna möjlighet att använda en enda organisation, men dela upp den i arbetsytor för sina olika team eller arbetsflöden.

>[!NOTE]
>
>Egenskaper och behörigheter är tillgängliga som en del av [Target Premium](/help/c-intro/intro.md#premium)-lösningen. De är inte tillgängliga i [!DNL Target Standard] utan en [!DNL Target Premium]-licens.

Funktionen [!UICONTROL Enterprise Permissions] underlättar effektiv skalning av optimeringsprogram mellan olika team. Även om funktionen var tillgänglig i användargränssnittet för [!DNL Target] saknade API:erna för administratörer motsvarande stöd fram till tidigare år 2019. I [!DNL Target] februari 2019 uppdaterade Adobe Admin API:erna så att du kan använda integrationskontot för att komma åt alla arbetsytor som skapats i organisationen. Tidigare var Admin API:er begränsade till endast standardarbetsytan, men uppdateringen från februari 2019 gav åtkomst till alla arbetsytor med åtkomsten [!UICONTROL Approver].

Med [!DNL Target]-versionen från september 2019 ger [!DNL Target] [!UICONTROL Enterprise Permissions] kunderna följande åtkomstkontroller:

* Du kan välja vilka arbetsytor som integreringen kan användas på
* Du kan använda en roll för integreringen av Adobe I/O: [!UICONTROL Approver], [!UICONTROL Editor] eller [!UICONTROL Observer].

Uppdateringen stöder följande användningsexempel:

* Ge integreringsåtkomst till alla arbetsytor med rollen [!UICONTROL Observer] för rapportering utan behörighet att skapa eller redigera resurser.
* Ge integreringen av Adobe I/O åtkomst till utvalda arbetsytor med rätt roll så att ett centralt team kan göra API-drivna ändringar på bara ett fåtal arbetsytor.
* Låt varje team som äger arbetsytan ha en egen integrering när teamet är redo att utforska API:er och välja rollen i enlighet med detta.
* Blanda och matcha ovanstående scenarier.

**Åtgärd krävs**: De kunder som för närvarande utnyttjar API:er för CRUD-operationer på resurser (aktiviteter, målgrupper, erbjudanden och rapporter) på alla arbetsytor måste ge sin befintliga Adobe I/O-integration tillgång till alla arbetsytor med den roll de vill ha i respektive användningsfall. Du kan göra det genom att markera varje [!DNL Target] [!UICONTROL Product Profile] i [!DNL Adobe Admin Console] och lägga till integreringen/integrationerna på fliken [!UICONTROL Integration]. Före versionen från september användes alla integreringar med åtkomsten [!UICONTROL Approver], oavsett vilket alternativ som gjordes i listrutan [!UICONTROL Product Role]. Du kan nu välja önskad roll.

>[!NOTE]
>
>Om den här åtgärden inte utförs aktiveras åtkomstkontrollerna efter [!DNL Target]-versionen från september 2019, och du observerar bara åtkomst till standardarbetsytan om det är så du är konfigurerad. Det finns ingen negativ reaktion på att upprätta integreringar i förväg. Ju tidigare du gör den här ändringen, desto bättre. Beroende på antalet arbetsytor i organisationen tar den här processen bara några klick för att lägga till en befintlig integrering i arbetsytor med den önskade rollen.

**Så här ger du integreringar med Adobe I/O tillgång till arbetsytor och tilldelar roller:**

1. Öppna **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Klicka på fliken **[!UICONTROL Products]** och välj sedan namnet på önskad produkt.

   ![Välj produkt i Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Välj önskad arbetsyta (produktprofil).

   ![Välj produktprofil](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Klicka på fliken **[!UICONTROL Integrations]**.

   ![Fliken Integrationer](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Villkorligt) Om du vill lägga till en ny integrering klickar du på **[!UICONTROL Add Integration]**, väljer önskad integrering och klickar sedan på **[!UICONTROL Save]**.

1. Välj önskad roll för arbetsytan i listrutan **[!UICONTROL Product Role]**:

   | Roll | Beskrivning |
   |--- |--- |
   | Godkännare | Kan skapa, redigera och aktivera eller stoppa aktiviteter. |
   | Redigerare | Kan skapa och redigera aktiviteter innan de är aktiva, men kan inte godkänna att en aktivitet startas. |
   | Observer | Kan visa aktiviteter, men kan inte skapa eller redigera dem. |
   | Utgivare | Liknar observationsrollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Utgivarrollen har dock ytterligare behörighet att aktivera aktiviteter. |
