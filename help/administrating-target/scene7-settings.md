---
keywords: scene7;dynamic media classic;digital asset management;assets;dam;content library
description: Target Standard kan integreras med Adobe Dynamic Media Classic för att ge DAM (Digital Asset Management) i innehållsbiblioteket.
title: Integrering med Dynamic Media Classic
feature: administration general
translation-type: tm+mt
source-git-commit: 76ab5aef33f5e9c5de08b33e83e459b588bb0fba
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 0%

---


# Scene7-konfiguration {#scene-settings}

[!DNL Target] kan integreras med [!DNL Adobe Dynamic Media Classic] DAM (Digital Asset Management) i [!UICONTROL Content Library].

>[!NOTE]
>
>Integrering [!DNL Target] med [!DNL Dynamic Media Classic] möjliggör leverans av resurser (som en del av aktiviteter) som överförts till mappen [!DNL Adobe Experience Cloud] assets. Den här integreringen tillåter inte åtkomst till alla resurser som överförts [!DNL Dynamic Media Classic] för leverans i [!DNL Target] aktiviteter.

Om du redan har ett [!DNL Dynamic Media] konto kan du ange dina befintliga autentiseringsuppgifter.

>[!NOTE]
>
>Ett begränsat, kostnadsfritt [!DNL Dynamic Media Classic] konto för [!DNL Adobe Target] nya kunder eller nya användare stöds inte längre. Befintliga inloggningsuppgifter fungerar som vanligt.

Om den här inställningen inte är konfigurerad är alternativet i arbetsflödet för att skapa aktivitet inte tillgängligt. [!UICONTROL Swap Image offer] När den här inställningen har konfigurerats är alternativet att byta/ändra bildeffekter tillgängligt både i [Visual Experience Composer (VEC) och i den formulärbaserade Experience Composer](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Du kan sedan utnyttja bilderbjudandena med bilder som har överförts från [!DNL Adobe Experience Cloud] programmet för att användas i [!DNL Target] aktiviteter.

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
