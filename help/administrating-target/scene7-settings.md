---
description: Target Standard kan integreras med Adobe Dynamic Media Classic (tidigare Scene7) för att tillhandahålla DAM (Digital Asset Management) i innehållsbiblioteket.
title: Integrering med Dynamic Media Classic
feature: administration general
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---


# Scene7-konfiguration {#scene-settings}

Target kan integreras med [!DNL Adobe Dynamic Media Classic] (tidigare [!DNL Scene7]) för att ge DAM (Digital Asset Management) i innehållsbiblioteket.

>[!NOTE]
>
>Integrering [!DNL Target] med [!DNL Dynamic Media Classic] möjliggör leverans av resurser (som en del av aktiviteter) som överförts till mappen [!DNL Adobe Experience Cloud] assets. Den här integreringen tillåter inte åtkomst till alla resurser som överförts [!DNL Dynamic Media Classic] för leverans i [!DNL Target] aktiviteter.

Om du redan har ett [!DNL Dynamic Media] konto kan du ange dina befintliga autentiseringsuppgifter. Om du inte har något konto kan du begära ett [!DNL Dynamic Media Classic] konto med begränsad användning utan extra kostnad från din [!DNL Adobe] representant. Det här kontot kan användas endast för ändamål som är begränsade för användning i [!DNL Target] . Den här tjänsten är tillgänglig för kunder med arbetsflöden som behöver funktioner för bildbyte.

Om den här inställningen inte är konfigurerad är alternativet i arbetsflödet för att skapa aktivitet inte tillgängligt. [!UICONTROL Swap Image offer] När den här inställningen har konfigurerats är alternativet att byta/ändra bildeffekter tillgängligt både i [Visual Experience Composer (VEC) och i den formulärbaserade Experience Composer](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Du kan sedan utnyttja bilderbjudandena med bilder som har överförts från [!DNL Adobe Experience Cloud] programmet för att användas i [!DNL Target] aktiviteter.

Om du vill referera till en URL för en offentlig bild direkt i ett erbjudande eller en anpassad kod när du skapar en aktivitet, ska du distribuera bilden till dina egna webbservrar och använda din egen URL i koden. Det finns inget sätt att hämta den publicerade URL:en för en bild som överförts till [!DNL Experience Cloud] för att använda direkt eller utanför arbetsflöden för målinriktning med [!DNL Target]. Den här funktionen är inte tillåten enligt avtal.

Observera att lagrings-URL:en och de slutliga publicerings-URL:erna för bilder från [!DNL Dynamic Media] är olika och att en får *INTE* skapa erbjudanden med hjälp av lagringslänken för bilder eftersom leveransen inte fungerar i sådana fall. Du måste använda bilderbjudandefunktionen enligt anvisningarna i vår hjälpdokumentation.

Om du vill integrera med [!DNL Dynamic Media Classic] ([!DNL Scene7]) måste du ange följande information.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Scene7 Configuration]**.

   ![Scene7 page](/help/administrating-target/assets/scene7.png)

1. Ange följande [!DNL Dynamic Media Classic] kontoinformation:

   **Region:** Regionen för ditt [!DNL Dynamic Media] konto: Nordamerika, Europa eller Asien.

   **Adhoc-mapp:** Platsen för innehåll som finns utanför målmappen och som överförs manuellt till [!DNL Dynamic Media].

   **E-postadress:** E-postadressen som används för att logga in i [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Lösenord:** Lösenordet som används för att logga in på [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Klicka på **[!UICONTROL Submit]**.
