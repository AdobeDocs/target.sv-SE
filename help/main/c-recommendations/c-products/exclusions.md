---
keywords: undantag
description: Lär dig hur du skapar undantag i  [!DNL Target Recommendations] för att förhindra att produkter eller innehåll rekommenderas för besökare.
title: Hur använder jag undantag i [!UICONTROL Recommendations] aktiviteter?
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Undantag

Skapa ett undantag i [!DNL Adobe Target Recommendations] för att förhindra att produkter eller innehåll rekommenderas för besökare. Ett undantag är en delmängd av produkter eller innehåll som inte bör rekommenderas för besökare.

Undantag är tillgängliga för hela kontot. Till skillnad från samlingar, där du anger en specifik samling för varje upplevelse när du skapar en [!UICONTROL Recommendations]-aktivitet, gäller undantag för alla aktiviteter på kontot. Det finns inget alternativ för att tilldela en exkluderingsgrupp när en aktivitet skapas.

Några exempel på hur du skulle kunna använda undantag är:

* Produkter som har upphört.
* Katalogen Fall och Winter är nu den enda katalog som ska finnas online. Objekt från sommarkatalogen går inte längre att köpa.
* Objekt som inte kan rekommenderas på de flesta sidor eller skärmar (vuxna produkter, NC-17-filmer osv.).
* Produkter med ofullständiga metadatafält (miniatyrbilder, pris eller andra viktiga metadata saknas).
* Produkter som aldrig bör rekommenderas (kanske en SKU finns i systemet för något men inte är en köpbar artikel. Eller så är det en falsk SKU för QA-teamet att simulera ett köp utan att faktiskt beställa något, och så vidare).

>[!IMPORTANT]
>
>Uteslutningsregler tillämpas globalt på alla [miljöer](/help/main/administrating-target/environments.md).
>
>Statiska och dynamiska exkluderingsregler är kraftfulla funktioner som kan hjälpa er med marknadsföringen. Detaljerad information, exempel och användningsscenarier finns i [Använd regler för dynamisk och statisk inkludering](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Skapa ett undantag

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** för att visa listan över befintliga undantag.

   Antalet objekt som rapporteras för varje undantag i listvyn [!UICONTROL Exclusions] är antalet produkter som matchar reglerna för undantaget i den konfigurerade standardrekommendationerna [värdgrupp](/help/main/administrating-target/hosts.md) (miljö). Mer information om hur du ändrar standardvärdgruppen finns i [Planera och implementera [!DNL Recommendations]](https://experienceleague.adobe.com/sv/docs/target-dev/developer/recommendations){target=_blank} i *Adobe Target Developer Guide* .

1. (Villkorligt) Klicka på ikonen **[!UICONTROL Show Filters]** ( ![Visa filterikon](/help/main/assets/icons/Filter.svg) ) och välj sedan önskad [miljö](/help/main/administrating-target/environments.md) i listrutan **[!UICONTROL Environment]** när du skapar (eller uppdaterar) ett undantag för att förhandsvisa innehållet i undantaget i den miljön. Som standard visas resultat från standardvärdgruppen.

1. Klicka på **[!UICONTROL Create Exclusion]**.

1. Skriv ett undantag **[!UICONTROL Name]** och ange en valfri beskrivning.

1. Använd regelverktyget för att skapa undantag.

   Välj en parameter i listan [!UICONTROL Rules], markera en operator och ange sedan ett eller flera värden för att identifiera produkterna. Avgränsa flera värden med kommatecken.

1. Klicka på **[!UICONTROL Create]**.

<!-- ## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded. -->

## Redigera, kopiera eller ta bort ett undantag

Klicka på ikonen Fler åtgärder ( ![Fler åtgärder &#x200B;](/help/main/assets/icons/MoreSmallList.svg) ) bredvid önskat undantag i listan och klicka sedan på lämplig ikon: [!UICONTROL Edit], [!UICONTROL Copy] eller [!UICONTROL Delete].

Du kan kopiera ett befintligt undantag för att skapa ett duplicerat undantag som du sedan kan ändra. Med det här alternativet kan du skapa ett liknande undantag utan ansträngning.

Observera att det finns undantag för hela kontot. Se till att du tar hänsyn till den här kopian innan du tar bort ett undantag. Borttagna undantag kan inte återställas.

## Utbildningsvideo: Skapa samlingar och undantag i rekommendationer (7:05) ![Självstudiekurs](/help/main/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa en samling
* Skapa ett undantag

>[!VIDEO](https://video.tv.adobe.com/v/27689)
