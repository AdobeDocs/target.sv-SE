---
keywords: scene7;dynamic media classic;digital asset management;assets;dam;content library;swap image
description: Lär dig integrera Adobe [!DNL Target] med Adobe Dynamic Media Classic (tidigare Scene7) för att tillhandahålla DAM (Digital Asset Management) i innehållsbiblioteket.
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

[!DNL Adobe Target] kan integreras med [!DNL Adobe Dynamic Media Classic] (tidigare [!DNL Scene7]) för att tillhandahålla DAM (Digital Asset Management) i [!UICONTROL Content Library].

>[!NOTE]
>
>Integrera [!DNL Target] med [!DNL Dynamic Media Classic] möjliggör leverans av tillgångar (som en del av aktiviteter) som överförts till [!DNL Adobe Experience Cloud] resursmapp. Den här integreringen aktiverar inte åtkomst till alla resurser som överförts i [!DNL Dynamic Media Classic] för leverans i [!DNL Target] verksamhet.

Om du redan har en [!DNL Dynamic Media] kan du ange dina befintliga uppgifter. Om du inte har något konto kan du begära begränsad användning [!DNL Dynamic Media Classic] konto utan extra kostnad från [!DNL Adobe] -representant. Det här kontot kan användas för ändamål som är begränsade för användning i [!DNL Target] endast. Den här tjänsten är tillgänglig för kunder med arbetsflöden som behöver funktioner för bildbyte.

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

Om den här inställningen inte är konfigurerad [!UICONTROL Swap Image offer] alternativet i arbetsflödet för att skapa aktivitet är inte tillgängligt. När den här inställningen har konfigurerats är alternativet att byta/ändra bildeerbjudanden tillgängligt i båda [Visual Experience Composer (VEC) och i den formulärbaserade Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Du kan sedan utnyttja bilderbjudandena med bilder som har överförts från [!DNL Adobe Experience Cloud] för användning i [!DNL Target] verksamhet.

Om du vill referera till en URL för en offentlig bild direkt i ett erbjudande eller en anpassad kod när du skapar en aktivitet, ska du distribuera bilden till dina egna webbservrar och använda din egen URL i koden. Det går inte att hämta den publicerade URL:en för en bild som överförts till [!DNL Experience Cloud] att förbruka arbetsflöden direkt eller externt med [!DNL Target]. Den här funktionen är inte tillåten enligt avtal.

Observera att lagrings-URL:en och den slutliga publicerings-URL:en för bilder från [!DNL Dynamic Media] är olika och en måste *NOT* skapa erbjudanden med hjälp av lagringslänken för bilder eftersom leveransen inte fungerar i sådana fall. Du måste använda bilderbjudandefunktionen enligt anvisningarna i vår hjälpdokumentation.

Integrera med [!DNL Dynamic Media Classic] ([!DNL Scene7]) måste du ange följande information.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Scene7 Configuration]**.

   ![Scene7 page](/help/main/administrating-target/assets/scene7.png)

1. Ange följande [!DNL Dynamic Media Classic] kontoinformation:

   **Region:** Regionen för din [!DNL Dynamic Media] konto: Nordamerika, Europa eller Asien.

   **Adhoc-mapp:** Platsen för innehåll som finns utanför målmappen och som överförs manuellt till [!DNL Dynamic Media].

   **E-postadress:** E-postadressen som används för att logga in på [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Lösenord:** Lösenordet som används för att logga in på [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Klicka på **[!UICONTROL Submit]**.
