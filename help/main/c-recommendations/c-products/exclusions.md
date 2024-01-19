---
keywords: undantag
description: Lär dig hur du skapar undantag i Adobe [!DNL Target] Recommendations för att förhindra att produkter eller innehåll rekommenderas för besökare.
title: Hur använder jag undantag i Recommendations-aktiviteter?
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---

# Undantag

Skapa ett undantag i [!DNL Adobe Target Recommendations] för att förhindra att produkter eller innehåll rekommenderas för besökare. Ett undantag är en delmängd av produkter eller innehåll som inte bör rekommenderas för besökare.

Undantag är tillgängliga för hela kontot. Till skillnad från samlingar, där du anger en specifik samling för varje upplevelse när du skapar en [!UICONTROL Recommendations] verksamhet, undantag gäller för alla aktiviteter på kontot. Det finns inget alternativ för att tilldela en exkluderingsgrupp när en aktivitet skapas.

Några exempel på hur du skulle kunna använda undantag är:

* Produkter som har upphört
* Fall-/vinterkatalog är nu den enda katalogen som ska finnas online. Objekt från sommarkatalogen går inte längre att köpa.
* Objekt som kan vara olämpliga att rekommendera på de flesta sidor/skärmar (vuxna produkter, NC-17-filmer osv.)
* Produkter med ofullständiga metadatafält (miniatyrbild, pris eller andra viktiga metadata saknas)
* Produkter som aldrig bör rekommenderas (det kanske finns en SKU i systemet för något, men det är inte en köpbar artikel, eller kanske en falsk SKU för att QA-teamet ska simulera ett köp utan att faktiskt beställa något, osv.)

>[!IMPORTANT]
>
>Uteslutningsreglerna tillämpas globalt på alla miljöer.
>
>Statiska och dynamiska exkluderingsregler är kraftfulla funktioner som kan hjälpa er med marknadsföringen. Detaljerad information, exempel och användningsscenarier finns i [Använd regler för dynamisk och statisk inkludering](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Skapa ett undantag

1. Klicka **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** för att visa en lista över befintliga undantag.

   ![exclusions_list image](assets/exclusions_list.png)

   Antal poster som rapporteras för varje undantag på [!UICONTROL Exclusions] listvyn är antalet produkter som matchar reglerna för undantaget inom den konfigurerade standardversionen av Recommendations [värdgrupp](/help/main/administrating-target/hosts.md) (miljö). Se [Inställningar](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} om du vill ändra standardvärdgruppen.

1. Klicka på **[!UICONTROL Create Exclusion]**.

1. (Villkorligt) Välj en miljö på **[!UICONTROL Environment]** filtrera när du skapar (eller uppdaterar) ett undantag för att förhandsvisa innehållet i undantaget i den miljön. Som standard visas resultat från standardvärdgruppen.

   ![Skapa undantag](/help/main/c-recommendations/c-products/assets/CreateExclusion.png)

1. Ange ett undantag **[!UICONTROL Name]** och ange en valfri beskrivning.

1. Använd regelverktyget för att skapa undantag.

   Välj en parameter i listan Regler, markera en operator och ange sedan ett eller flera värden för att identifiera produkterna. Avgränsa flera värden med kommatecken.

1. Klicka på **[!UICONTROL Save]**.

## Skapa ett undantag med avancerad sökning

Du kan också skapa undantag med [!UICONTROL Advanced Search] på [Katalogsökning](/help/main/c-recommendations/c-products/catalog-search.md#save-as) sida ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Spara som dialogruta](/help/main/c-recommendations/c-products/assets/save-as.png)

När du har skapat en sökning med&quot;id > contains&quot; kan du till exempel klicka på [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] är skiftlägeskänsligt, men de produkter som returneras vid leveranstillfället baseras på skiftlägeskänslig sökning. Denna felmatchning kan leda till förvirring. Se till att du tar hänsyn till skiftlägeskänslighet när du skapar undantag baserat på resultat med funktionen Avancerad sökning. Om du till exempel söker efter Semester visas resultatet som innehåller Semester och Semester i den inledande sökningen. Om du sedan gör ett undantag med avsikten att utesluta produkter som innehåller &quot;semester&quot;, exkluderas endast produkter som innehåller &quot;semester&quot;. Produkter som innehåller &quot;Semester&quot; är inte undantagna.

## Redigera, kopiera eller ta bort ett undantag

Håll pekaren över det önskade undantaget i listan och klicka sedan på lämplig ikon: redigera, kopiera eller ta bort.

![Hovringsikoner för ett undantag](/help/main/c-recommendations/c-products/assets/hover-exclusions.png)

Du kan kopiera ett befintligt undantag för att skapa ett duplicerat undantag som du sedan kan ändra. På så sätt kan du skapa ett liknande undantag utan ansträngning.

Observera att det finns undantag för hela kontot. Tänk på detta innan du tar bort ett undantag. Borttagna undantag kan inte återställas.

## Utbildningsvideo: Skapa samlingar och undantag i Recommendations (7:05) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa en samling
* Skapa ett undantag

>[!VIDEO](https://video.tv.adobe.com/v/27689)
