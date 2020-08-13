---
keywords: collection;Targeting
description: En samling är en uppsättning produkter eller artiklar i Adobe Target som är berättigade till en rekommendation.
title: Samlingar i Adobe Target
feature: entities
uuid: aa1afdcf-e51c-4e44-a229-3c21fc9d0514
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) -samlingar {#collections}

En samling är en uppsättning produkter eller artiklar som är berättigade till en rekommendation.

Vanligtvis är en samling en uppsättning med liknande eller relaterade artiklar, till exempel en enda produktsamling. Du kan dock gruppera vilka objekt som helst i en kategori som passar ditt företag, till exempel produkter i ett visst prisintervall eller en viss färg, eller objekt som kan vara intressanta i ett visst geografiskt område.

Använd samlingar för att ordna produkterna i logiska områden. Om vissa objekt till exempel är tillgängliga i en region men inte i en annan kanske du vill skapa en samling som utesluter objekt som inte är tillgängliga i besökarens region. Du kan också använda samlingar för att ordna säsongsobjekt eller andra organisationsparametrar som gäller för ditt företag.

Rekommendationer [för](/help/c-recommendations/c-algorithms/backup-recs.md) säkerhetskopiering som genereras för varje villkor i rekommendationen använder också den här samlingen, så endast objekt i samlingen inkluderas i rekommendationen för säkerhetskopiering. Med samlingar kan du vara säker på att endast produkter som är bra att visa på en plats visas.

Samlingar byggs om eller uppdateras varje gång varje villkor körs.

Du kan gruppera dina objekt i kataloger och sedan skapa separata rekommendationer för varje samling.

Inkluderingsvillkor gör att du kan göra liknande saker som en samling, men de måste ställas in varje gång du skapar en aktivitet. Med samlingar kan du skapa en uppsättning objekt en gång och sedan använda den när det är lämpligt för att göra det utan att behöva konfigurera den igen.

När du skapar eller redigerar en [!DNL Recommendations] aktivitet visas samlingsnamnet bredvid [!UICONTROL Criteria] aktivitetsdiagrammets etikett.

>[!NOTE]
>
>Samlingar används inte när du använder [!UICONTROL Recently Viewed Items] rekommendationsnyckeln.

## Skapa en samling {#task_1256DFF6842141FCAADD9E1428EF7F08}

Skapa en samling för att ordna de produkter som du vill visa i dina rekommendationer.

1. Klicka **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** för att visa listan över befintliga samlingar.

   ![Samlingslista](assets/collections_list.png)

   Antalet objekt som rapporteras för varje samling i listvyn är antalet produkter som matchar reglerna för den samlingen i den konfigurerade Recommendations- [!UICONTROL Collections] standardvärdgruppen [](/help/administrating-target/hosts.md) (miljö). Se [Inställningar](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) för att ändra standardvärdgruppen.

1. Klicka på **[!UICONTROL Create Collection]**.

1. (Villkorligt) Välj en miljö i filtret när du skapar (eller uppdaterar) en samling för att förhandsgranska innehållet i samlingen i den miljön. **[!UICONTROL Environment]** Som standard visas resultat från standardvärdgruppen.

   ![Skapa samling](/help/c-recommendations/c-products/assets/CreateCollection.png)

1. Skriv ett **[!UICONTROL Name]** för samlingen.

   Du kan också ange ett valfritt värde **[!UICONTROL Description]**.

1. Ange reglerna som används för att skapa samlingen.

   Samlingen kan t.ex. bygga på ett produkt-ID eller en kategori, marginal eller någon annan parameter i listan.

   Du kan lägga till regler för att använda flera parametrar för att definiera en samling. Flera regler förenas med en AND. Alla angivna regler måste matchas för att samlingen ska kunna användas.

1. Klicka på **[!UICONTROL Save]**.

## Skapa en samling med avancerad sökning

Du kan också skapa samlingar med avancerad sökning på [katalogsökningssidan](/help/c-recommendations/c-products/catalog-search.md) ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Dialogrutan Spara som](/help/c-recommendations/c-products/assets/save-as-dialog.png)

När du har skapat en sökning med&quot;id > contains&quot; kan du till exempel klicka på [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>Funktionen för avancerad sökning är inte skiftlägeskänslig; men de produkter som returneras vid leveranstillfället bygger på skiftlägeskänslig sökning. Denna felmatchning kan leda till förvirring. Se till att du tar hänsyn till skiftlägeskänslighet när du skapar samlingar baserat på resultat med funktionen Avancerad sökning. Om du till exempel söker efter Semester visas resultatet som innehåller Semester och Semester i den inledande sökningen. Om du sedan skapar en katalog med avsikten att returnera produkter som innehåller &quot;semester&quot; returneras endast produkter som innehåller &quot;semester&quot;. Produkter som innehåller &quot;Semester&quot; returneras inte.

## Utbildningsvideo: Skapa samlingar och undantag i Recommendations (7:05) ![självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa en samling
* Skapa ett undantag

>[!VIDEO](https://video.tv.adobe.com/v/27689)