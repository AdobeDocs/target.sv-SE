---
description: Target Standard kan integreras med Adobe Dynamic Media Classic (tidigare Scene7) för att ge DAM (Digital Asset Management) i innehållsbiblioteket.
title: Integrering med Dynamic Media Classic
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: bbc1c9282007c180f30023b6f15d693a31683243
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---


# Dynamisk integrering med Media Classic{#scene-settings}

Target kan integreras med Adobe Dynamic Media Classic (tidigare Scene7) för att ge DAM (Digital Asset Management) i innehållsbiblioteket.

>[!NOTE]
>
>Genom att integrera Target med Dynamic Media Classic kan du leverera resurser (som en del av aktiviteter) som överförts till resursmappen i Adobe Experience Cloud. Den här integreringen ger inte åtkomst till alla resurser som överförts i Dynamic Media Classic för leverans i Target-aktiviteter.

Om du redan har ett Dynamic Media-konto kan du ange dina befintliga autentiseringsuppgifter. Om du inte har något konto kan du beställa ett begränsat Dynamic Media Classic-konto utan extra kostnad från din Adobe-representant. Det här kontot kan användas endast för syften som är begränsade för användning i Target. Den här tjänsten är tillgänglig för kunder med arbetsflöden som behöver funktioner för bildbyte.

Om den här inställningen inte är konfigurerad är inte erbjudandealternativet Växla bild tillgängligt i arbetsflödet för att skapa aktivitet. När den här inställningen har konfigurerats är alternativet att byta/ändra bildeffekter tillgängligt både i [Visual Experience Composer (VEC) och i den formulärbaserade Experience Composer](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Sedan kan ni utnyttja bilderbjudandena med bilder som har överförts från Adobe Experience Cloud för användning i Target-aktiviteter.

Om du vill referera till en URL för en offentlig bild direkt i ett erbjudande eller en anpassad kod när du skapar en aktivitet, ska du distribuera bilden till dina egna webbservrar och använda din egen URL i koden. Det finns inget sätt att hämta den publicerade URL:en för en bild som överförts till Experience Cloud för att använda arbetsflöden för målinriktning direkt eller utanför Adobe Target. Den här funktionen är inte tillåten enligt avtal.

Observera att lagrings-URL:en och de slutliga publicerings-URL:erna för bilder från Dynamic Media är olika och att man INTE får skapa erbjudanden med hjälp av lagringslänken för bilder eftersom leveransen inte fungerar i sådana fall. Man måste använda de funktioner för bilderbjudanden som beskrivs i vår hjälpdokumentation.

Om du vill integrera med Dynamic Media Classic (Scene7) måste du ange följande information.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Scene7 Settings]**.

   ![Scene7 page](/help/administrating-target/assets/scene7.png)

1. Ange följande kontoinformation för Dynamic Media Classic:

   **Region:** Regionen för ditt Dynamic Media-konto: Nordamerika, Europa eller Asien.

   **Adhoc-mapp:** Platsen för innehåll som finns utanför målmappen och som överförs manuellt till Dynamic Media.

   **E-postadress:** E-postadressen som används för att logga in på Dynamic Media Classic (Scene7).

   **Lösenord:** Lösenordet som används för att logga in på Dynamic Media Classic (Scene7).

1. Klicka på **[!UICONTROL Submit]**.
