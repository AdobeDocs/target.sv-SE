---
keywords: scene7;dynamic media classic;digital asset management;assets;dam;content library;swap image
description: Lär dig hur du integrerar Adobe [!DNL Target]  med Adobe Dynamic Media Classic (tidigare Scene7) för att tillhandahålla DAM (Digital Asset Management) i innehållsbiblioteket.
title: Hur konfigurerar jag integreringen av Dynamic Media Classic (Scene7)?
feature: Administration & Configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# Dynamic Media Classic (tidigare Scene7)-konfiguration

[!DNL Adobe Target] kan integreras med [!DNL Adobe Dynamic Media Classic] (tidigare [!DNL Scene7]) för att ge DAM (Digital Asset Management) i [!UICONTROL Content Library].

>[!NOTE]
>
>Genom att integrera [!DNL Target] med [!DNL Dynamic Media Classic] kan du leverera resurser (som en del av aktiviteter) som överförts till resursmappen [!DNL Adobe Experience Cloud]. Den här integreringen aktiverar inte åtkomst till alla resurser som överförts i [!DNL Dynamic Media Classic] för leverans i [!DNL Target]-aktiviteter.

Om du redan har ett [!DNL Dynamic Media]-konto kan du ange dina befintliga autentiseringsuppgifter. Om du inte har något konto kan du begära ett [!DNL Dynamic Media Classic]-konto med begränsad användning utan extra kostnad från din [!DNL Adobe]-representant. Det här kontot kan endast användas för syften som är begränsade för användning i [!DNL Target]. Den här tjänsten är tillgänglig för kunder med arbetsflöden som behöver funktioner för bildbyte.

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

Om den här inställningen inte är konfigurerad är alternativet [!UICONTROL Swap Image offer] i arbetsflödet för att skapa aktivitet inte tillgängligt. När den här inställningen har konfigurerats är alternativet att byta ut/ändra bilderbjudanden tillgängligt både i [Visual Experience Composer (VEC) och i den formulärbaserade Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Du kan sedan utnyttja bilderbjudanden med bilder som har överförts från [!DNL Adobe Experience Cloud] för användning i [!DNL Target]-aktiviteter.

Om du vill referera till en URL för en offentlig bild direkt i ett erbjudande eller en anpassad kod när du skapar en aktivitet, ska du distribuera bilden till dina egna webbservrar och använda din egen URL i koden. Det finns inget sätt att hämta den publicerade URL:en för en bild som har överförts till [!DNL Experience Cloud] för att använda direkt eller utanför målarbetsflöden med [!DNL Target]. Den här funktionen är inte tillåten enligt avtal.

Observera att lagrings-URL:en och de slutliga publicerings-URL:erna för bilder från [!DNL Dynamic Media] är olika och att du måste *INTE* skapa erbjudanden med hjälp av lagringslänken för bilder, eftersom leveransen inte fungerar i sådana fall. Du måste använda bilderbjudandefunktionen enligt anvisningarna i vår hjälpdokumentation.

Om du vill integrera med [!DNL Dynamic Media Classic] ([!DNL Scene7]) måste du ange följande information.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Scene7 Configuration]**.

   ![Scene7-sida](/help/main/administrating-target/assets/scene7.png)

1. Ange följande kontoinformation för [!DNL Dynamic Media Classic]:

   **Region:** Regionen för ditt [!DNL Dynamic Media]-konto: Nordamerika, Europa eller Asien.

   **Adhoc-mapp:** Platsen för innehåll som ligger utanför målmappen och som överförs manuellt till [!DNL Dynamic Media].

   **E-postadress:** E-postadressen som används för att logga in på [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Lösenord:** Lösenordet som används för att logga in på [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Klicka på **[!UICONTROL Submit]**.
