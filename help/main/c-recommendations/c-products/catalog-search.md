---
keywords: katalogsökning;katalog;sökning;exkludering;samling;filter;rekommendationer
description: Lär dig hur du använder  [!DNL Recommendations] [!UICONTROL Catalog Search] för att hitta produkter eller innehåll, ta bort objekt från katalogen och mycket mer.
title: Hur använder jag  [!DNL Recommendations] [!UICONTROL Catalog Search]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 0%

---

# [!UICONTROL Catalog Search]

Sidan [!UICONTROL Catalog Search] i [!DNL Adobe Recommendations] hjälper dig att hitta produkterna eller innehållet i katalogen. Den mest grundläggande uppgiften du kan utföra på den här sidan är att söka efter ett objekt. Dessutom kan du ändra miljö, filtrera aspekter, ändra kolumner i tabellen, lägga till nya sökfaktorer och mycket mer.

Kataloger avser hela produktuppsättningen (enheter). Katalogen kan innehålla många samlingar, ett sätt att ordna dina produkter i logiska områden.

## Åtkomst [!UICONTROL Catalog Search]

1. Du öppnar sidan [!UICONTROL Catalog Search] genom att klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

1. (Valfritt) Om du vill använda filter i sökningen klickar du på ikonen **[!UICONTROL Show Filters]** ( ![Visa filter-ikon](/help/main/assets/icons/Filter.svg) ). Du kan filtrera efter [!UICONTROL Environment], [!UICONTROL Collections], [!UICONTROL Category], [!UICONTROL Brand], [!UICONTROL Inventory] och [!UICONTROL Value].

## Utför en enkel sökning

1. Skriv ett sökord i fältet **[!UICONTROL Search In]**.

1. (Valfritt) Du kan förfina sökningen genom att välja ett sökalternativ på Alternativ-menyn som visas när du klickar på nedpilen i fältet [!UICONTROL Search In].

   Sökalternativen omfattar följande:

   * ID
   * Namn
   * Meddelande

1. Bläddra bland objekten i sökresultaten om du vill visa miniatyrbilder och annan produktinformation.

   >[!NOTE]
   >
   > När du gör en katalogsökning i ett anpassat attribut med ett numeriskt värde behandlas det anpassade attributet som en strängtyp i stället för ett numeriskt värde.
   >
   >Det finns för närvarande ingen funktion som gör att du kan ändra attributtypen. Om du vill göra en ändring [öppnar du ett kundproblem](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) som refererar till de attribut som behöver typen ändrad från sträng till numerisk.

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

Indexet för din katalog skapas automatiskt när du överför din första feed och uppdateras enligt det [angivna schemat](/help/main/c-recommendations/c-products/feeds.md#steps).

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

Med [miljöer](/help/main/administrating-target/environments.md) kan du ordna dina platser och förproduktionsmiljöer för enkel hantering och separat rapportering.

1. Klicka på ikonen Visa filter ( ![ikonen Visa filter](/help/main/assets/icons/Filter.svg) ).

1. Välj önskad miljö i listrutan **[!UICONTROL Environment]**.

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

Du kan ändra de aktiva kolumnerna på sidan [!UICONTROL Catalog Search].

1. Klicka på ikonen **[!UICONTROL Customize Table]** ( ![Anpassa tabell &#x200B;](/help/main/assets/icons/ColumnSetting.svg) ).

1. Markera eller avmarkera de kolumner som du vill visa eller dölja.

Alla ändringar du gör är permanenta mellan sessionerna.
