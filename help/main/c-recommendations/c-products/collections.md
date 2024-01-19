---
keywords: samling;Riktning
description: Lär dig hur du använder samlingar i Adobe [!DNL Target] Recommendations. En samling är en uppsättning produkter eller artiklar som är berättigade till en rekommendation.
title: Hur använder jag samlingar i Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 0%

---

# Samlingar

En samling är en uppsättning produkter eller artiklar som är berättigade till en rekommendation. En samling definieras genom att ange de villkor som måste uppfyllas av objekt som ska ingå i den.

Vanligtvis är en samling en uppsättning med liknande eller relaterade artiklar, till exempel en enda produktsamling. Du kan dock gruppera vilka objekt som helst i en kategori som passar ditt företag, till exempel produkter i ett visst prisintervall eller en viss färg eller objekt som kan vara intressanta i ett visst geografiskt område.

Använd samlingar för att ordna produkterna i logiska områden. Om vissa objekt till exempel är tillgängliga i en region men inte i en annan, kan du skapa en samling som utesluter objekt som inte är tillgängliga i besökarens region. Du kan också använda samlingar för att ordna säsongsobjekt eller andra organisationsparametrar som gäller för ditt företag.

The [rekommendationer för säkerhetskopiering](/help/main/c-recommendations/c-algorithms/backup-recs.md) som genererats för varje villkor i rekommendationen använder även den här samlingen, så endast objekt i samlingen inkluderas i rekommendationen för säkerhetskopiering. Med samlingar kan du vara säker på att endast produkter som är bra att visa på en plats visas.

Samlingar byggs om eller uppdateras varje gång varje villkor körs.

Du kan gruppera dina objekt i kataloger och sedan skapa separata rekommendationer för varje samling.

Inkluderingsvillkor gör att du kan göra liknande saker som en samling, men de måste ställas in varje gång du skapar en aktivitet. Med samlingar kan du skapa en uppsättning objekt en gång och sedan använda den när det är lämpligt för att göra det utan att behöva konfigurera den igen.

När du skapar eller redigerar en [!DNL Recommendations] aktiviteten visas samlingsnamnet bredvid [!UICONTROL Criteria] aktivitetsdiagrammets etikett.

>[!NOTE]
>
>Samlingar används inte när du använder [!UICONTROL Recently Viewed Items] rekommendationsnyckel.

## Skapa en samling {#task_1256DFF6842141FCAADD9E1428EF7F08}

Skapa en samling för att ordna de produkter eller det innehåll som du vill visa i dina rekommendationer.

1. Klicka **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** om du vill visa en lista över befintliga samlingar.

   ![Samlingslista](assets/collections_list.png)

   The [!UICONTROL Collections] visas en lista med dina befintliga samlingar. Du skapar nya samlingar genom att klicka på [!UICONTROL Create Collection] -knappen. Du kan också redigera, kopiera och ta bort befintliga samlingar genom att hålla markören över den önskade samlingen och klicka på önskad ikon.

   ![Hovringsikoner: redigera, kopiera och ta bort](/help/main/c-recommendations/c-products/assets/hover-icons.png)

   Antal objekt som rapporteras för varje samling på [!UICONTROL Collections] listvyn är antalet produkter som matchar reglerna för den samlingen inom den konfigurerade standardversionen av Recommendations [värdgrupp](/help/main/administrating-target/hosts.md) (miljö). Se [Inställningar](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} om du vill ändra standardvärdgruppen.

1. Klicka på **[!UICONTROL Create Collection]**.

1. (Villkorligt) Välj en miljö på **[!UICONTROL Environment]** filtrera när du skapar (eller uppdaterar) en samling för att förhandsgranska innehållet i samlingen i den miljön. Som standard visas resultat från standardvärdgruppen.

   ![Skapa samling](/help/main/c-recommendations/c-products/assets/CreateCollection.png)

1. Skriv a **[!UICONTROL Name]** för samlingen.

   Du kan också ange ett valfritt **[!UICONTROL Description]**.

1. Ange de regler som ska användas för att skapa samlingen.

   Samlingen kan t.ex. bygga på ett produkt-ID eller en kategori, marginal eller någon annan parameter i listan.

   Du kan lägga till regler för att använda flera parametrar för att definiera en samling. Flera regler kopplas till en AND-operator. Alla angivna regler måste matchas för att samlingen ska kunna användas.

1. Klicka på **[!UICONTROL Save]**.

## Skapa en samling med avancerad sökning

Du kan också skapa samlingar med Avancerad sökning på [Katalogsökning](/help/main/c-recommendations/c-products/catalog-search.md#save-as) sida ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Spara som dialogruta](/help/main/c-recommendations/c-products/assets/save-as.png)

När du har skapat en sökning med&quot;id > contains&quot; kan du till exempel klicka på [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>Funktionen för avancerad sökning är inte skiftlägeskänslig, men de produkter som returneras vid leveranstillfället baseras på skiftlägeskänslig sökning. Denna felmatchning kan leda till förvirring. Se till att du tar hänsyn till skiftlägeskänslighet när du skapar samlingar baserat på resultat med funktionen Avancerad sökning. Om du till exempel söker efter Semester visas resultatet som innehåller Semester och Semester i den inledande sökningen. Om du sedan skapar en katalog med avsikten att returnera produkter som innehåller &quot;semester&quot; returneras endast produkter som innehåller &quot;semester&quot;. Produkter som innehåller &quot;Semester&quot; returneras inte.

## Redigera, kopiera eller ta bort en samling

Håll markören över önskad samling i listan och klicka sedan på lämplig ikon: redigera, kopiera eller ta bort.

![Hovringsikoner för en samling](/help/main/c-recommendations/c-products/assets/hover-collections.png)

Du kan kopiera en befintlig samling för att skapa en dubblettsamling som du sedan kan ändra. På så sätt kan du skapa ett liknande undantag utan ansträngning.

Observera att samlingar är tillgängliga för hela kontot. Tänk på detta innan du tar bort en samling. Borttagna samlingar kan inte återställas.

## Använda en samling i en Recommendations-aktivitet

1. Skapa en samling med någon av metoderna ovan.

1. Klicka **[!UICONTROL Activities]** och [skapa en ny Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) eller redigera en befintlig aktivitet.

1. När du har valt ett villkor och en design visas [!UICONTROL Options] visas där du har valt önskad samling.

   ![Välj samlingsalternativ](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. (Villkorligt) Om du vill ändra en befintlig samlingsinställning väljer du **[!UICONTROL Experiences]** sida (steg 2 i det guidade arbetsflödet i tre delar), klicka på en plats där du placerade dina rekommendationer, klicka **[!UICONTROL Change Collection]** väljer du sedan önskad samling.

   ![Ändra samlingsalternativ](/help/main/c-recommendations/c-products/assets/change-collection.png)

## Utbildningsvideo: Skapa samlingar och undantag i Recommendations (7:05) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa en samling
* Skapa ett undantag

>[!VIDEO](https://video.tv.adobe.com/v/27689)
