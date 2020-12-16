---
keywords: exclusions
description: Skapa ett undantag i [!DNL Adobe Target Recommendations] för att förhindra att produkter eller innehåll rekommenderas för besökare.
title: Undantag i Adobe Target
feature: entities
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---


# Undantag{#exclusions}

Skapa ett undantag i [!DNL Adobe Target Recommendations] för att förhindra att produkter eller innehåll rekommenderas för besökare. Ett undantag är en delmängd av produkter eller innehåll som inte bör rekommenderas för besökare.

Undantag är tillgängliga för hela kontot. Till skillnad från samlingar, där du anger en specifik samling för varje upplevelse när du skapar en [!UICONTROL Recommendations]-aktivitet, gäller undantag för alla aktiviteter på kontot. Det finns inget alternativ för att tilldela en exkluderingsgrupp när en aktivitet skapas.

Några exempel på hur du skulle kunna använda undantag är:

* Produkter som har upphört
* Fall-/vinterkatalog är nu den enda katalogen som ska finnas online. Objekt från sommarkatalogen går inte längre att köpa.
* Objekt som kan vara olämpliga att rekommendera på de flesta sidor/skärmar (vuxna produkter, NC-17-filmer osv.)
* Produkter med ofullständiga metadatafält (miniatyrbild, pris eller andra viktiga metadata saknas)
* Produkter som aldrig bör rekommenderas (det kanske finns en SKU i systemet för något, men det är inte en köpbar artikel, eller kanske en falsk SKU för att QA-teamet ska simulera ett köp utan att faktiskt beställa något, osv.)

>[!IMPORTANT]
>
>Statiska och dynamiska exkluderingsregler är kraftfulla funktioner som kan hjälpa er med marknadsföringen. Detaljerad information, exempel och användningsscenarier finns i [Använd regler för dynamisk och statisk inkludering](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Skapa ett undantag

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** för att visa listan över befintliga undantag.

   ![](assets/exclusions_list.png)

   Antalet objekt som rapporteras för varje undantag i listvyn [!UICONTROL Exclusions] är antalet produkter som matchar reglerna för undantaget i den konfigurerade standardvärdgruppen [Recommendations](/help/administrating-target/hosts.md) (miljö). Se [Inställningar](/help/c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) om du vill ändra standardvärdgruppen.

1. Klicka på **[!UICONTROL Create Exclusion]**.

1. (Villkorligt) Välj en miljö från filtret **[!UICONTROL Environment]** när du skapar (eller uppdaterar) ett undantag för att förhandsvisa innehållet i undantaget i den miljön. Som standard visas resultat från standardvärdgruppen.

   ![Skapa undantag](/help/c-recommendations/c-products/assets/CreateExclusion.png)

1. Skriv ett undantag **[!UICONTROL Name]** och ange en valfri beskrivning.

1. Använd regelverktyget för att skapa undantag.

   Välj en parameter i listan Regler, markera en operator och ange sedan ett eller flera värden för att identifiera produkterna. Avgränsa flera värden med kommatecken.

1. Klicka på **[!UICONTROL Save]**.

## Skapa ett undantag med avancerad sökning

Du kan också skapa undantag med [!UICONTROL Advanced Search] på sidan [Katalogsökning](/help/c-recommendations/c-products/catalog-search.md#save-as) ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Dialogrutan Spara som](/help/c-recommendations/c-products/assets/save-as.png)

När du har skapat en sökning med&quot;id > contains&quot; kan du till exempel klicka på [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>Funktionen [!UICONTROL Advanced Search] är inte skiftlägeskänslig; men de produkter som returneras vid leveranstillfället bygger på skiftlägeskänslig sökning. Denna felmatchning kan leda till förvirring. Se till att du tar hänsyn till skiftlägeskänslighet när du skapar undantag baserat på resultat med funktionen Avancerad sökning. Om du till exempel söker efter Semester visas resultatet som innehåller Semester och Semester i den inledande sökningen. Om du sedan gör ett undantag med avsikten att utesluta produkter som innehåller &quot;semester&quot;, exkluderas endast produkter som innehåller &quot;semester&quot;. Produkter som innehåller &quot;Semester&quot; är inte undantagna.

## Redigera, kopiera eller ta bort ett undantag

Håll pekaren över det önskade undantaget i listan och klicka sedan på lämplig ikon: redigera, kopiera eller ta bort.

![Hovringsikoner för ett undantag](/help/c-recommendations/c-products/assets/hover-exclusions.png)

Du kan kopiera ett befintligt undantag för att skapa ett duplicerat undantag som du sedan kan ändra. På så sätt kan du skapa ett liknande undantag utan ansträngning.

Observera att det finns undantag för hela kontot. Tänk på detta innan du tar bort ett undantag. Borttagna undantag kan inte återställas.

## Utbildningsvideo: Skapa samlingar och uteslutningar i Recommendations (7:05) ![Självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa en samling
* Skapa ett undantag

>[!VIDEO](https://video.tv.adobe.com/v/27689)