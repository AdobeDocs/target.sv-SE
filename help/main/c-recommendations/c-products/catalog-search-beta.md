---
keywords: katalogsökning;katalog;sökning;exkludering;samling;filter;rekommendationer
description: Lär dig använda [!DNL Recommendations] [!UICONTROL Catalog Search] om du vill hitta produkter eller innehåll tar du bort objekt från katalogen och mycket mer.
title: Hur jag använder [!DNL Recommendations] [!UICONTROL Catalog Search]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
exl-id: 6b0175b1-0eee-498d-8a08-513cf6695114
source-git-commit: 16a7c11e8b9b1a08b1e467519f997d0b05e47529
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 0%

---

# [!UICONTROL Catalog Search]

The [!UICONTROL Catalog Search] sida in [!DNL Adobe Recommendations] hjälper dig att hitta produkterna eller innehållet i katalogen. Den mest grundläggande uppgiften du kan utföra på den här sidan är att söka efter ett objekt. Dessutom kan du ändra miljö, filtrera aspekter, ändra kolumner i tabellen, lägga till nya sökfaktorer och mycket mer.

Kataloger avser hela produktuppsättningen (enheter). Katalogen kan innehålla många samlingar, ett sätt att ordna dina produkter i logiska områden.

## Åtkomst [!UICONTROL Catalog Search]

Så här öppnar du [!UICONTROL Catalog Search] sida, klicka **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

![Katalogsöksida](/help/main/c-recommendations/c-products/assets/catalog-search-new.png)

## Utför en enkel sökning

1. Ange ett sökord i **[!UICONTROL Search In]** fält.

1. (Valfritt) Du kan förfina sökningen genom att välja ett sökalternativ på Alternativ-menyn som visas när du klickar på nedpilen i dialogrutan [!UICONTROL Search In] fält.

   Sökalternativen omfattar följande:

   * ID
   * Namn
   * Meddelande

1. Bläddra bland objekten i sökresultaten om du vill visa miniatyrbilder och annan produktinformation.

   >[!NOTE]
   >
   > När du gör en katalogsökning i ett anpassat attribut med ett numeriskt värde behandlas det anpassade attributet som en strängtyp i stället för ett numeriskt värde.
   >
   >Det finns för närvarande ingen funktion som gör att du kan ändra attributtypen. Om du vill göra en ändring [öppna ett kundproblem](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) som refererar till de attribut som behöver typen ändrad från sträng till numerisk.

   Du kan också använda filter för att hitta önskade produkter. Genom att klicka på **[!UICONTROL Show Filters]** ikon ( ![Ikonen Visa filter](/help/main/c-recommendations/c-products/assets/icon-show-filters.png) ), expandera [!UICONTROL Collections] och sedan välja en eller flera samlingar, alla produkter som tillhör de valda samlingarna i din katalog, visas.

<!-- ### Perform an advanced search {#advanced-search}

You can use [!UICONTROL Advanced Search] to further refine your search results or to save your search results as a [collection](/help/main/c-recommendations/c-products/collections.md) or [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Click the **[!UICONTROL Advanced Search]** link.

   ![Advanced Search page](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use the drop-down lists to specify the parameter, operator, and values for your search.

1. (Optional) Click **[!UICONTROL Add Rule]** to add an additional search rule.

   Each additional search rule is joined with the AND operator.

1. Click **[!UICONTROL Search]**.

1. (Optional) Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   For more information, see [Create a collection or exclusion based on Advanced Search](#save-as) below.-->

## Visa information om ett objekt

Du kan visa information om ett enskilt objekt, inklusive ID, namn, meddelande, kategori och annat genom att visa informationen om det.

1. Klicka på ett objekt i sökresultatet för att visa information om det.

## Ta bort ett objekt från katalogen

1. Klicka på ett objekt i sökresultatet för att visa information om det.

1. Klicka på **[!UICONTROL Remove from Catalog]**.

1. Bekräfta att du vill ta bort objektet.

All information om det objektet tas bort från katalogindexet. Objektet tas endast med i katalogen om det läggs till igen i en datafeed. Ett borttaget objekt måste tas bort separat från feeds.

## Uppdatera katalogen

Indexet för katalogen skapas automatiskt när du överför din första feed och uppdateras enligt [angivet schema](/help/main/c-recommendations/c-products/feeds.md#steps).

Katalogen uppdateras automatiskt när uppdateringar tas emot via feedsfiler, API eller mbox-uppdateringar. Uppdateringarna slutförs vanligtvis inom en timme. Om uppdateringar pågår visas den tid då den senaste uppdateringen startades. Om inga uppdateringar pågår visas den tid då den senaste uppdateringen startades och avslutades.

<!-- ## Create a collection or exclusion based on Advanced Search {#save-as}

You can create [collections](/help/main/c-recommendations/c-products/collections.md) or [exclusions](/help/main/c-recommendations/c-products/exclusions.md) using [!UICONTROL Advanced Search] on the [!UICONTROL Catalog Search] page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Perform an [advanced search](#advanced-search).

1. Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections or exclusions based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. Exclusions are handled in a similar fashion.-->

## Byt miljö

[Miljö](/help/main/administrating-target/environments.md) kan ni ordna era sajter och förproduktionsmiljöer för enkel hantering och separat rapportering.

1. Klicka på ikonen Visa filter ( ![Ikonen Visa filter](/help/main/c-recommendations/c-products/assets/icon-show-filters.png) ).

1. Välj önskad miljö i dialogrutan **[!UICONTROL Environment]** listruta.

<!-- ## Modify the Catalog Search page (filters and columns)

You can temporarily modify the available filters and columns on the [!UICONTROL Catalog Search] page for the current session.

### Modify filters

You can add additional filter facets to the [!UICONTROL Catalog Search] page.

1. In the **[!UICONTROL Filters]** panel, click **[!UICONTROL Modify]**.

   ![Modify filters link](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Select the desired search facets (ID, name, message, etc.), then click **[!UICONTROL Save]**.

   ![Add filters](/help/main/c-recommendations/c-products/assets/add-filters.png)

Keep in mind that the additional filter facets are available in the current session only.-->

## Ändra kolumner

Du kan tillfälligt ändra de aktiva kolumnerna i [!UICONTROL Catalog Search] sida.

1. Klicka på **[!UICONTROL Customize Table]** ikon (  ![Ikonen Anpassa tabell](/help/main/c-recommendations/c-products/assets/icon-customize-table.png) ).

1. Markera eller avmarkera de kolumner som du vill visa eller dölja.

Kom ihåg att alla ändringar du gör endast gäller den aktuella sessionen.
