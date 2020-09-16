---
keywords: exclusions
description: Skapa ett undantag [!DNL Adobe Target Recommendations] för att förhindra att produkter eller innehåll rekommenderas för besökare.
title: Undantag i Adobe Target
feature: entities
uuid: 1970846e-37d8-4b69-a0d9-ff45bb840bef
translation-type: tm+mt
source-git-commit: af46453734f4ce185e0cd4282793a800fada8a98
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 0%

---


# Undantag{#exclusions}

Skapa ett undantag i [!DNL Adobe Target Recommendations] för att förhindra att produkter eller innehåll rekommenderas för besökare.

Ett undantag är en delmängd av produkter eller innehåll som inte bör rekommenderas för besökare. Du kan t.ex. använda undantag för att förhindra att produkter eller innehåll visas i rekommendationer som har upphört eller som är av känslig natur (t.ex. filmer med en gradering som inte passar för alla baserat på innehållsklassificeringar).

Undantag är tillgängliga för hela kontot.

>[!IMPORTANT]
>
>Statiska och dynamiska exkluderingsregler är kraftfulla funktioner som kan hjälpa er med marknadsföringen. Detaljerad information, exempel och användningsscenarier finns i [Använd regler](../../c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)för dynamisk och statisk infogning.

## Skapa ett undantag

1. Klicka **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** för att visa listan över befintliga undantag.

   ![](assets/exclusions_list.png)

   &quot;Antal objekt&quot; som rapporteras för varje undantag i listvyn är antalet produkter som matchar reglerna för undantaget i den konfigurerade Recommendations- [!UICONTROL Exclusions] standardvärdgruppen [](/help/administrating-target/hosts.md) (miljön). Se [Inställningar](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) för att ändra standardvärdgruppen.

1. Klicka på **[!UICONTROL Create Exclusion]**.

1. (Villkorligt) Välj en miljö i filtret när du skapar (eller uppdaterar) ett undantag för att förhandsvisa innehållet i undantaget i den miljön. **[!UICONTROL Environment]** Som standard visas resultat från standardvärdgruppen.

   ![Skapa undantag](/help/c-recommendations/c-products/assets/CreateExclusion.png)

1. Skriv ett undantag **[!UICONTROL Name]** och ange en valfri beskrivning.

1. Använd regelverktyget för att skapa undantag.

   Välj en parameter i listan Regler, markera en operator och ange sedan ett eller flera värden för att identifiera produkterna. Avgränsa flera värden med kommatecken.

1. Klicka på **[!UICONTROL Save]**.

## Skapa ett undantag med avancerad sökning

Du kan också skapa undantag med hjälp [!UICONTROL Advanced Search] av på sidan [Katalogsökning](/help/c-recommendations/c-products/catalog-search.md#save-as) ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Dialogrutan Spara som](/help/c-recommendations/c-products/assets/save-as.png)

När du har skapat en sökning med&quot;id > contains&quot; kan du till exempel klicka på [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>Funktionen är inte skiftlägeskänslig [!UICONTROL Advanced Search] ; men de produkter som returneras vid leveranstillfället bygger på skiftlägeskänslig sökning. Denna felmatchning kan leda till förvirring. Se till att du tar hänsyn till skiftlägeskänslighet när du skapar undantag baserat på resultat med funktionen Avancerad sökning. Om du till exempel söker efter Semester visas resultatet som innehåller Semester och Semester i den inledande sökningen. Om du sedan gör ett undantag med avsikten att utesluta produkter som innehåller &quot;semester&quot;, exkluderas endast produkter som innehåller &quot;semester&quot;. Produkter som innehåller &quot;Semester&quot; är inte undantagna.

## Redigera, kopiera eller ta bort ett undantag

Håll pekaren över det önskade undantaget i listan och klicka sedan på lämplig ikon: redigera, kopiera eller ta bort.

![Hovringsikoner för ett undantag](/help/c-recommendations/c-products/assets/hover-exclusions.png)

Du kan kopiera ett befintligt undantag för att skapa ett duplicerat undantag som du sedan kan ändra. På så sätt kan du skapa ett liknande undantag utan ansträngning.

Observera att det finns undantag för hela kontot. Tänk på detta innan du tar bort ett undantag. Borttagna undantag kan inte återställas.

## Utbildningsvideo: Skapa samlingar och undantag i Recommendations (7:05) ![självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa en samling
* Skapa ett undantag

>[!VIDEO](https://video.tv.adobe.com/v/27689)