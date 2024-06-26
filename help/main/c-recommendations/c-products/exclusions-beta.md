---
keywords: undantag
description: Lär dig hur du skapar undantag i [!DNL Target Recommendations] för att förhindra att produkter eller innehåll rekommenderas för besökare.
title: Hur använder jag undantag i [!UICONTROL Recommendations] Verksamheter?
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: b6eaf89ef71ea3448584dcdadc926c45dba77504
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 0%

---

# Undantag

Skapa ett undantag i [!DNL Adobe Target Recommendations] för att förhindra att produkter eller innehåll rekommenderas för besökare. Ett undantag är en delmängd av produkter eller innehåll som inte bör rekommenderas för besökare.

Undantag är tillgängliga för hela kontot. Till skillnad från samlingar, där du anger en specifik samling för varje upplevelse när du skapar en [!UICONTROL Recommendations] verksamhet, undantag gäller för alla aktiviteter på kontot. Det finns inget alternativ för att tilldela en exkluderingsgrupp när en aktivitet skapas.

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

1. Klicka **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** för att visa en lista över befintliga undantag.

   ![exclusions_list image](assets/exclusions-list.png)

   Antal poster som rapporteras för varje undantag på [!UICONTROL Exclusions] listvyn är antalet produkter som matchar reglerna för undantaget inom den konfigurerade standardversionen av Recommendations [värdgrupp](/help/main/administrating-target/hosts.md) (miljö). Se [Planera och implementera [!DNL Recommendations]](https://experienceleague.adobe.com/en/docs/target-dev/developer/recommendations){target=_blank} i *Adobe Target Developer Guide* om du vill ha information om hur du ändrar standardvärdgruppen.

1. (Villkorligt) Klicka på [!UICONTROL Filter] -ikonen och sedan välja önskat [miljö](/help/main/administrating-target/environments.md) från **[!UICONTROL Environment]** nedrullningsbar lista när du skapar (eller uppdaterar) ett undantag för att förhandsvisa innehållet i undantaget i den miljön. Som standard visas resultat från standardvärdgruppen.

   ![Skapa undantag](/help/main/c-recommendations/c-products/assets/choose-environment.png)

1. Klicka på **[!UICONTROL Create Exclusion]**.

   ![Dialogrutan Skapa undantag](/help/main/c-recommendations/c-products/assets/create-exclusion.png)

1. Ange ett undantag **[!UICONTROL Name]** och ange en valfri beskrivning.

1. Använd regelverktyget för att skapa undantag.

   Välj en parameter i listan Regler, markera en operator och ange sedan ett eller flera värden för att identifiera produkterna. Avgränsa flera värden med kommatecken.

1. Klicka på **[!UICONTROL Create]**.

## Skapa ett undantag med avancerad sökning

Du kan också skapa undantag med [!UICONTROL Advanced Search] på [Katalogsökning](/help/main/c-recommendations/c-products/catalog-search.md#save-as) sida ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Spara som dialogruta](/help/main/c-recommendations/c-products/assets/save-as.png)

När du har skapat en sökning med&quot;id > contains&quot; kan du till exempel klicka på [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] är skiftlägeskänsligt, men de produkter som returneras vid leveranstillfället baseras på skiftlägeskänslig sökning. Denna felmatchning kan leda till förvirring. Se till att du tar hänsyn till skiftlägeskänslighet när du skapar undantag baserat på resultat med funktionen Avancerad sökning. Om du till exempel söker efter Semester visas resultatet som innehåller Semester och Semester i den inledande sökningen. Om du sedan gör ett undantag med avsikten att utesluta produkter som innehåller &quot;semester&quot;, exkluderas endast produkter som innehåller &quot;semester&quot;. Produkter som innehåller &quot;Semester&quot; är inte undantagna.

## Redigera, kopiera eller ta bort ett undantag

Klicka på **ellips** bredvid önskat undantag i listan och klicka sedan på lämplig ikon: redigera, kopiera eller ta bort.

![Alternativ: redigera, kopiera och ta bort](/help/main/c-recommendations/c-products/assets/edit-copy-delete.png)

Du kan kopiera ett befintligt undantag för att skapa ett duplicerat undantag som du sedan kan ändra. Med det här alternativet kan du skapa ett liknande undantag utan ansträngning.

Observera att det finns undantag för hela kontot. Se till att du tar hänsyn till den här kopian innan du tar bort ett undantag. Borttagna undantag kan inte återställas.

## Utbildningsvideo: Skapa samlingar och undantag i Recommendations (7:05) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa en samling
* Skapa ett undantag

>[!VIDEO](https://video.tv.adobe.com/v/27689)