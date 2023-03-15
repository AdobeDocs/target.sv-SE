---
keywords: integration;roller;användarbehörigheter;Admin Console
description: Lär dig hur du ger integreringar med Adobe I/O tillgång till alla arbetsytor med önskad roll i Adobe Target.
title: Hur ger jag Adobe I/O åtkomst till arbetsytor och tilldelar roller?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 62f6399f-c590-470c-ac3b-e0c84db63112
source-git-commit: fa11f93058b69e5e59e0ee20c65cffa4a1344ca0
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# Ge Adobe I/O integreringar åtkomst till arbetsytor och tilldela roller

[!UICONTROL Enterprise Permissions] tillåter [!DNL Target] kunder som vill använda en enda organisation, men dela upp den i arbetsytor för sina olika team eller arbetsflöden.

>[!NOTE]
>
>Egenskaper och behörigheter är tillgängliga som en del av [Mål Premium](/help/main/c-intro/intro.md#premium) lösning. De är inte tillgängliga i [!DNL Target Standard] utan [!DNL Target Premium] licens.

The [!UICONTROL Enterprise Permissions] funktionen underlättar effektiv skalning av optimeringsprogram mellan olika team. Även om funktionen var tillgänglig i [!DNL Target] Gränssnittet i Admin API:erna saknade motsvarande stöd fram till tidigare år 2019. I [!DNL Target] I februari 2019 uppdaterade Adobe Admin API:erna så att du kan använda integrationskontot för att komma åt alla arbetsytor som skapats i organisationen. Tidigare var Admin API:er begränsade till standardarbetsytan, men uppdateringen från februari 2019 gav åtkomst till alla arbetsytor med [!UICONTROL Approver] åtkomst.

Med [!DNL Target] September 2019-utgåvan, [!DNL Target] [!UICONTROL Enterprise Permissions] ger kunderna följande åtkomstkontroller:

* Du kan välja vilka arbetsytor som integreringen kan användas på
* Du kan använda en roll för integreringen av Adobe I/O: [!UICONTROL Approver], [!UICONTROL Editor], eller [!UICONTROL Observer].

Uppdateringen stöder följande användningsexempel:

* Ge integreringsåtkomst till alla arbetsytor med Adobe I/O [!UICONTROL Observer] roll för rapportering utan behörighet att skapa eller redigera resurser.
* Ge integreringen av Adobe I/O åtkomst till utvalda arbetsytor med rätt roll så att ett centralt team kan göra API-drivna ändringar på bara ett fåtal arbetsytor.
* Låt varje team som äger arbetsytan ha en egen integrering när teamet är redo att utforska API:er och välja rollen i enlighet med detta.
* Blanda och matcha ovanstående scenarier.

**Åtgärd krävs**: De kunder som för närvarande utnyttjar API:er för CRUD-operationer på resurser (aktiviteter, målgrupper, erbjudanden och rapporter) på alla arbetsytor måste ge sin befintliga Adobe I/O-integration tillgång till alla arbetsytor med den roll de vill ha i respektive användningsfall. Du kan göra det genom att markera varje [!DNL Target] [!UICONTROL Product Profile] i [!DNL Adobe Admin Console] och lägga till integreringen i [!UICONTROL Integration] -fliken. Före versionen från september var det alla integreringar som fungerade med [!UICONTROL Approver] åtkomst, oavsett vilket val som görs på [!UICONTROL Product Role] nedrullningsbar lista. Du kan nu välja önskad roll.

>[!NOTE]
>
>Om den här åtgärden inte utförs, efter [!DNL Target] I versionen från september 2019 kommer åtkomstkontrollerna att aktiveras och du kommer att se åtkomsten till standardarbetsytan om det är så du är konfigurerad. Det finns ingen negativ reaktion på att upprätta integreringar i förväg. Ju tidigare du gör den här ändringen, desto bättre. Beroende på antalet arbetsytor i organisationen tar den här processen bara några klick för att lägga till en befintlig integrering i arbetsytor med den önskade rollen.

**Så här ger du integreringar med Adobe I/O tillgång till arbetsytor och tilldelar roller:**

1. Öppna **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Klicka på **[!UICONTROL Products]** och sedan välja namnet på den önskade produkten.

   ![Välj produkt i Adobe Admin Console](/help/main/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Välj önskad arbetsyta (produktprofil).

   ![Välj produktprofil](/help/main/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Klicka på **[!UICONTROL Integrations]** -fliken.

   ![Fliken Integrationer](/help/main/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Villkorligt) Om du vill lägga till en ny integrering klickar du på **[!UICONTROL Add Integration]**, välj önskad integrering och klicka sedan på **[!UICONTROL Save]**.

1. Från **[!UICONTROL Product Role]** väljer du önskad roll för den arbetsytan:

   | Roll | Beskrivning |
   |--- |--- |
   | Godkännare | Kan skapa, redigera och aktivera eller stoppa aktiviteter. |
   | Redigerare | Kan skapa och redigera aktiviteter innan de är aktiva, men kan inte godkänna att en aktivitet startas. |
   | Observer | Kan visa aktiviteter, men kan inte skapa eller redigera dem. |
   | Utgivare | Liknar observationsrollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Utgivarrollen har dock ytterligare behörighet att aktivera aktiviteter. |
