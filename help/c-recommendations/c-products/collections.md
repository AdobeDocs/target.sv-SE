---
keywords: samling;Riktning
description: Lär dig hur du använder samlingar i Adobe Target Recommendations. En samling är en uppsättning produkter eller artiklar som är berättigade till en rekommendation.
title: Hur använder jag samlingar i Recommendations?
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMCollections  {#collections}

En samling är en uppsättning produkter eller artiklar som är berättigade till en rekommendation. En samling definieras genom att ange de villkor som måste uppfyllas av objekt som ska ingå i den.

Vanligtvis är en samling en uppsättning med liknande eller relaterade artiklar, till exempel en enda produktsamling. Du kan dock gruppera vilka objekt som helst i en kategori som passar ditt företag, till exempel produkter i ett visst prisintervall eller en viss färg eller objekt som kan vara intressanta i ett visst geografiskt område.

Använd samlingar för att ordna produkterna i logiska områden. Om vissa objekt till exempel är tillgängliga i en region men inte i en annan, kan du skapa en samling som utesluter objekt som inte är tillgängliga i besökarens region. Du kan också använda samlingar för att ordna säsongsobjekt eller andra organisationsparametrar som gäller för ditt företag.

[Rekommendationerna för säkerhetskopiering](/help/c-recommendations/c-algorithms/backup-recs.md) som genereras för varje villkor i rekommendationen använder även den här samlingen, så endast objekt i samlingen inkluderas i rekommendationen för säkerhetskopiering. Med samlingar kan du vara säker på att endast produkter som är bra att visa på en plats visas.

Samlingar byggs om eller uppdateras varje gång varje villkor körs.

Du kan gruppera dina objekt i kataloger och sedan skapa separata rekommendationer för varje samling.

Inkluderingsvillkor gör att du kan göra liknande saker som en samling, men de måste ställas in varje gång du skapar en aktivitet. Med samlingar kan du skapa en uppsättning objekt en gång och sedan använda den när det är lämpligt för att göra det utan att behöva konfigurera den igen.

När du skapar eller redigerar en [!DNL Recommendations]-aktivitet visas samlingsnamnet bredvid etiketten [!UICONTROL Criteria] i aktivitetsdiagrammet.

>[!NOTE]
>
>Samlingar används inte när du använder [!UICONTROL Recently Viewed Items]-rekommendationsnyckeln.

## Skapa en samling {#task_1256DFF6842141FCAADD9E1428EF7F08}

Skapa en samling för att ordna de produkter eller det innehåll som du vill visa i dina rekommendationer.

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** för att visa listan över befintliga samlingar.

   ![Samlingslista](assets/collections_list.png)

   Sidan [!UICONTROL Collections] visar en lista över dina befintliga samlingar. Du skapar nya samlingar genom att klicka på knappen [!UICONTROL Create Collection]. Du kan också redigera, kopiera och ta bort befintliga samlingar genom att hålla markören över den önskade samlingen och klicka på önskad ikon.

   ![Hovringsikoner: redigera, kopiera och ta bort](/help/c-recommendations/c-products/assets/hover-icons.png)

   Antalet objekt som rapporteras för varje samling i listvyn [!UICONTROL Collections] är antalet produkter som matchar reglerna för samlingen i den konfigurerade standardvärdgruppen [Recommendations](/help/administrating-target/hosts.md) (miljö). Se [Inställningar](/help/c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) om du vill ändra standardvärdgruppen.

1. Klicka på **[!UICONTROL Create Collection]**.

1. (Villkorligt) Välj en miljö från **[!UICONTROL Environment]**-filtret när du skapar (eller uppdaterar) en samling för att förhandsgranska innehållet i samlingen i den miljön. Som standard visas resultat från standardvärdgruppen.

   ![Skapa samling](/help/c-recommendations/c-products/assets/CreateCollection.png)

1. Ange en **[!UICONTROL Name]** för samlingen.

   Du kan också ange ett valfritt **[!UICONTROL Description]**.

1. Ange reglerna som används för att skapa samlingen.

   Samlingen kan t.ex. bygga på ett produkt-ID eller en kategori, marginal eller någon annan parameter i listan.

   Du kan lägga till regler för att använda flera parametrar för att definiera en samling. Flera regler kopplas till en AND-operator. Alla angivna regler måste matchas för att samlingen ska kunna användas.

1. Klicka på **[!UICONTROL Save]**.

## Skapa en samling med avancerad sökning

Du kan också skapa samlingar med avancerad sökning på [katalogsöksidan](/help/c-recommendations/c-products/catalog-search.md#save-as) ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Dialogrutan Spara som](/help/c-recommendations/c-products/assets/save-as.png)

När du har skapat en sökning med&quot;id > contains&quot; kan du till exempel klicka på [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>Funktionen för avancerad sökning är inte skiftlägeskänslig; men de produkter som returneras vid leveranstillfället bygger på skiftlägeskänslig sökning. Denna felmatchning kan leda till förvirring. Se till att du tar hänsyn till skiftlägeskänslighet när du skapar samlingar baserat på resultat med funktionen Avancerad sökning. Om du till exempel söker efter Semester visas resultatet som innehåller Semester och Semester i den inledande sökningen. Om du sedan skapar en katalog med avsikten att returnera produkter som innehåller &quot;semester&quot; returneras endast produkter som innehåller &quot;semester&quot;. Produkter som innehåller &quot;Semester&quot; returneras inte.

## Redigera, kopiera eller ta bort en samling

Håll muspekaren över önskad samling i listan och klicka sedan på lämplig ikon: redigera, kopiera eller ta bort.

![Hovringsikoner för en samling](/help/c-recommendations/c-products/assets/hover-collections.png)

Du kan kopiera en befintlig samling för att skapa en dubblettsamling som du sedan kan ändra. På så sätt kan du skapa ett liknande undantag utan ansträngning.

Observera att samlingar är tillgängliga för hela kontot. Tänk på detta innan du tar bort en samling. Borttagna samlingar kan inte återställas.

## Använda en samling i en Recommendations-aktivitet

1. Skapa en samling med någon av metoderna ovan.

1. Klicka på **[!UICONTROL Activities]** och [skapa en ny Recommendations](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md)-aktivitet eller redigera en befintlig aktivitet.

1. När du har valt ett villkor och en design visas [!UICONTROL Options]-sidan där du valde önskad samling.

   ![Välj samlingsalternativ](/help/c-recommendations/c-products/assets/choose-collection.png)

1. (Villkorligt) Om du vill ändra en befintlig samlingsinställning klickar du på **[!UICONTROL Experiences]**-sidan (steg 2 i det guidade arbetsflödet med tre delar) på den plats där du placerade rekommendationer, sedan på **[!UICONTROL Change Collection]** och väljer önskad samling.

   ![Ändra samlingsalternativ](/help/c-recommendations/c-products/assets/change-collection.png)

## Utbildningsvideo: Skapa samlingar och uteslutningar i Recommendations (7:05) ![Självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa en samling
* Skapa ett undantag

>[!VIDEO](https://video.tv.adobe.com/v/27689)