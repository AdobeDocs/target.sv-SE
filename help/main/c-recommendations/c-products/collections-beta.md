---
keywords: samling;Riktning
description: Lär dig hur du använder produktsamlingar eller objekt i  [!DNL Target Recommendations].
title: Hur använder jag samlingar i Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
exl-id: da477e5c-1ce7-4042-b56d-8ae1b50ceb88
source-git-commit: b7c7e8d85f7f39024ed5e57177e5c9f628460e9c
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# Samlingar

En samling är en uppsättning produkter eller artiklar som är berättigade till en rekommendation. En samling definieras genom att ange de villkor som måste uppfyllas av objekt som ska ingå i den.

Vanligtvis är en samling en uppsättning med liknande eller relaterade artiklar, till exempel en enda produktsamling. Du kan dock gruppera vilka objekt som helst i en kategori som passar ditt företag, till exempel produkter i ett visst prisintervall eller en viss färg eller objekt som kan vara intressanta i ett visst geografiskt område.

Använd samlingar för att ordna produkterna i logiska områden. Om vissa objekt till exempel är tillgängliga i en region men inte i en annan, kan du skapa en samling som utesluter objekt som inte är tillgängliga i besökarens region. Du kan också använda samlingar för att ordna säsongsobjekt eller andra organisationsparametrar som gäller för ditt företag.

[Säkerhetskopieringsrekommendationer](/help/main/c-recommendations/c-algorithms/backup-recs.md) som genererats för varje villkor i rekommendationen använder även den här samlingen, så endast objekt i samlingen inkluderas i säkerhetskopieringsrekommendationen. Med samlingar kan du vara säker på att endast produkter som är bra att visa på en plats visas.

Samlingar byggs om eller uppdateras varje gång varje villkor körs.

Du kan gruppera dina objekt i kataloger och sedan skapa separata rekommendationer för varje samling.

Inkluderingsvillkor gör att du kan göra liknande saker som en samling, men de måste ställas in varje gång du skapar en aktivitet. Med samlingar kan du skapa en uppsättning objekt en gång och sedan använda den när det är lämpligt för att göra det utan att behöva konfigurera den igen.

När du skapar eller redigerar en [!DNL Recommendations]-aktivitet visas samlingsnamnet bredvid aktivitetsdiagrammets [!UICONTROL Criteria]-etikett.

>[!NOTE]
>
>Samlingar används inte när du använder rekommendationsnyckeln [!UICONTROL Recently Viewed Items].

## Skapa en samling {#task_1256DFF6842141FCAADD9E1428EF7F08}

Skapa en samling för att ordna de produkter eller det innehåll som du vill visa i dina rekommendationer.

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** för att visa listan över befintliga samlingar.

   Sidan [!UICONTROL Collections] visar en lista över dina befintliga samlingar. Du skapar nya samlingar genom att klicka på knappen [!UICONTROL Create Collection]. Du kan också redigera, kopiera och ta bort befintliga samlingar genom att klicka på ikonen Fler åtgärder ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmallList.svg) ) bredvid önskad samling och sedan klicka på önskat alternativ.

   Antalet objekt som rapporteras för varje samling i listvyn [!UICONTROL Collections] är antalet produkter som matchar reglerna för den samlingen i den konfigurerade standardvärdgruppen [Recommendations](/help/main/administrating-target/hosts.md) (miljö). Se [Inställningar](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} om du vill ändra standardvärdgruppen.

1. Klicka på **[!UICONTROL Create Collection]**.

1. Ange en **[!UICONTROL Name]** för samlingen.

   Du kan även ange ett valfritt **[!UICONTROL Description]**.

1. (Villkorligt) Välj en [miljö](/help/main/administrating-target/environments.md) från filtret **[!UICONTROL Environment]** när du skapar (eller uppdaterar) en samling för att förhandsgranska innehållet i samlingen i den miljön. Som standard visas resultat från standardvärdgruppen.

1. Ange de regler som ska användas för att skapa samlingen.

   Samlingen kan t.ex. bygga på ett produkt-ID eller en kategori, marginal eller någon annan parameter i listan.

   Du kan lägga till regler för att använda flera parametrar för att definiera en samling. Flera regler kopplas till en AND-operator. Alla angivna regler måste matchas för att samlingen ska kunna användas.

1. Klicka på **[!UICONTROL Create]**.

<!-- ## Create a collection using [!UICONTROL Advanced Search]

You can also create collections using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. -->

## Redigera, kopiera eller ta bort en samling

Klicka på ikonen ( ![Fler åtgärder](/help/main/assets/icons/MoreSmallList.svg) ) bredvid önskad samling i listan och klicka sedan på lämplig ikon: [!UICONTROL Edit], [!UICONTROL Copy] eller [!DNL Delete].

Du kan kopiera en befintlig samling för att skapa en dubblettsamling som du sedan kan ändra. På så sätt kan du skapa en liknande samling med mindre ansträngning.

Observera att samlingar är tillgängliga för hela kontot. Tänk på detta innan du tar bort en samling. Borttagna samlingar kan inte återställas.

## Använd en samling i en [!DNL Recommendations]-aktivitet

1. Skapa en samling med någon av metoderna ovan.

1. Klicka på **[!UICONTROL Activities]** och [skapa en ny Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)-aktivitet eller redigera en befintlig aktivitet.

1. När du har valt ett villkor och en design visas sidan [!UICONTROL Options] där du väljer önskad samling.

1. (Villkorligt) Om du vill ändra en befintlig samlingsinställning klickar du på en plats där du har placerat rekommendationer på sidan **[!UICONTROL Experiences]** (steg 1 i det guidade arbetsflödet med tre delar), klickar på **[!UICONTROL Change Collection]** och väljer sedan önskad samling.
