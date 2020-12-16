---
keywords: catalog;search
description: Katalogsökningen i Adobe Target hjälper dig att hitta produkterna eller innehållet i din katalog.
title: Katalogsökning i Adobe Target
feature: catalog
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '959'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMCatalogsökning  {#catalog-search}

Sidan [!UICONTROL Catalog Search] hjälper dig att hitta produkterna eller innehållet i din katalog.

Kataloger avser hela produktuppsättningen (enheter). Katalogen kan innehålla många samlingar - ett sätt att ordna produkterna i logiska intervall.

Du öppnar sidan [!UICONTROL Catalog Search] genom att klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

![Katalogsöksida](/help/c-recommendations/c-products/assets/catalog-search.png)

Den mest grundläggande uppgiften du kan utföra på den här sidan är att söka efter ett objekt. Dessutom kan du ändra miljön; spara sökresultat i samlingar eller uteslutningar, lägg till, ta bort eller ordna om kolumner i tabellen och lägg till nya sökfaktorer på panelen [!UICONTROL Filters].

## Söka efter ett objekt

Du kan söka efter objekt i katalogen med hjälp av en enkel sökning eller en avancerad sökning.

### Gör en enkel sökning

1. Skriv en sökterm i fältet **[!UICONTROL Search Products]**.

1. (Valfritt) Du kan förfina sökningen genom att välja ett sökalternativ på Alternativ-menyn som visas när du klickar på nedpilen i sökfältet.

   ![](assets/searchproductsmenu.png)

   Sökalternativen omfattar följande:

   * ALL - Söker igenom alla andra sökvillkor med hjälp av ELLER-logik.
   * Namn
   * Varumärke
   * Kategori
   * ID
   * Meddelande

1. Nu kan du bläddra bland objekten i sökresultaten för att visa miniatyrbilder och annan produktinformation.

   I följande bild visas resultatet för &quot;cykel&quot; med alternativet Alla.

   ![Katalogsökning för cykel](/help/c-recommendations/c-products/assets/bike-results.png)

   Numret som visas bredvid&quot;Produkter&quot; är antalet produkter som matchar söktermen, av det totala antalet som finns i den angivna miljön.

   Observera att du kan använda funktionen för automatisk komplettering av sökningar. På följande bild returneras alla produkter som innehåller ordet &quot;cykel&quot; när du skriver &quot;bik&quot;.

   ![Automatisk sökning slutförd](/help/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >När du gör en katalogsökning i ett anpassat attribut med ett numeriskt värde behandlas det anpassade attributet som en strängtyp i stället för ett numeriskt värde.
   >
   >För närvarande finns det ingen tillgänglig funktion som gör att kunderna kan ändra typen av attribut. Om du vill göra en ändring [öppnar du en kundutgåva](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) som refererar till de attribut som behöver typen ändrad från sträng till numerisk.

1. Du kan också använda filter för att hitta önskad produkt. I följande exempel expanderar du funktionen [!UICONTROL Collections] och väljer &quot;Cykelverktyg&quot;, så visas alla cykelverktyg i katalogvisningen.

   ![Skakverktyg](/help/c-recommendations/c-products/assets/bike-results-3.png)

1. Du kan söka ytterligare i resultatlistan genom att ange en sökterm, t.ex. &quot;kedja&quot;.

   ![Sök efter kedja](/help/c-recommendations/c-products/assets/bike-results-4.png)

### Utför en avancerad sökning {#advanced-search}

Du kan använda [!UICONTROL Advanced Search] för att förfina sökresultaten ytterligare eller för att spara sökresultaten som en [samling](/help/c-recommendations/c-products/collections.md) eller [exkludering](/help/c-recommendations/c-products/exclusions.md).

1. Klicka på länken **[!UICONTROL Advanced Search]**.

   ![Sidan Avancerad sökning](/help/c-recommendations/c-products/assets/advances-search.png)

1. Använd listrutorna för att ange parametrar, operator och värden för sökningen.

1. (Valfritt) Klicka på **[!UICONTROL Add Rule]** om du vill lägga till ytterligare en sökregel.

   Varje ytterligare sökregel kopplas till operatorn AND.

1. Klicka på **[!UICONTROL Search]**.

1. (Valfritt) Klicka på **[!UICONTROL Save As]** och sedan på **[!UICONTROL Collection]** eller **[!UICONTROL Exclusion]**.

   ![Alternativ för Spara som](/help/c-recommendations/c-products/assets/save-as.png)

   Mer information finns i [Skapa en samling eller ett undantag baserat på avancerad sökning](#save-as) nedan.

## Visa information om ett objekt

Du kan visa information om ett enskilt objekt, inklusive ID, namn, meddelande, kategori och annat genom att visa informationen om det.

1. Klicka på ett objekt i sökresultatet för att visa information om det.

   ![Produktinformation](/help/c-recommendations/c-products/assets/bike-results-5.png)

## Ta bort ett objekt från katalogen

1. Klicka på ett objekt i sökresultatet för att visa information om det.

1. Klicka på **[!UICONTROL Remove from Catalog]**.

1. Bekräfta att du vill ta bort objektet.

All information om det objektet tas bort från katalogindexet. Objektet tas endast med i katalogen om det läggs till igen i en datafeed. Ett borttaget objekt måste tas bort separat från feeds.

## Uppdatera katalogen

Katalogens index skapas automatiskt när du överför din första feed och uppdateras enligt det [angivna schemat](/help/c-recommendations/c-products/feeds.md#steps).

Katalogen uppdateras automatiskt när uppdateringar tas emot via feedsfiler, API eller mbox-uppdateringar. Uppdateringarna slutförs normalt på en timme. Om uppdateringar pågår visas den tid då den senaste uppdateringen startades. Om inga uppdateringar pågår visas den tid då den senaste uppdateringen startades och avslutades.

## Skapa en samling eller ett undantag baserat på avancerad sökning {#save-as}

Du kan skapa [samlingar](/help/c-recommendations/c-products/collections.md) eller [undantag](/help/c-recommendations/c-products/exclusions.md) med [!UICONTROL Advanced Search] på [!UICONTROL Catalog Search]-sidan ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Utför en [avancerad sökning](#advanced-search).

1. Klicka på **[!UICONTROL Save As]** och sedan på **[!UICONTROL Collection]** eller **[!UICONTROL Exclusion]**.

   ![Alternativ för Spara som](/help/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >Funktionen [!UICONTROL Advanced Search] är inte skiftlägeskänslig; men de produkter som returneras vid leveranstillfället bygger på skiftlägeskänslig sökning. Denna felmatchning kan leda till förvirring. Se till att du tar hänsyn till skiftlägeskänslighet när du skapar samlingar eller uteslutningar baserat på resultat med funktionen [!UICONTROL Advanced Search]. Om du till exempel söker efter Semester visas resultatet som innehåller Semester och Semester i den inledande sökningen. Om du sedan skapar en katalog med avsikten att returnera produkter som innehåller &quot;semester&quot; returneras endast produkter som innehåller &quot;semester&quot;. Produkter som innehåller &quot;Semester&quot; returneras inte. Uteslutningar hanteras på liknande sätt.

## Byt miljö

[Med ](/help/administrating-target/environments.md) en miljö kan du ordna dina webbplatser och förproduktionsmiljöer för enkel hantering och separat rapportering.

1. Klicka på länken Miljö.

   ![Länk till miljö](/help/c-recommendations/c-products/assets/environment.png)

1. Välj önskad miljö.

## Ändra sidan Katalogsökning (filter och kolumner)

Du kan tillfälligt ändra tillgängliga filter och kolumner på [!UICONTROL Catalog Search]-sidan för den aktuella sessionen.

### Ändra filter

Du kan lägga till fler filteransikten på sidan [!UICONTROL Catalog Search].

1. Klicka på **[!UICONTROL Modify]** på panelen **[!UICONTROL Filters]**.

   ![Länken Ändra filter](/help/c-recommendations/c-products/assets/modify-filters.png)

1. Markera önskade sökfaktorer (ID, namn, meddelande, osv.).

   ![Lägg till filter](/help/c-recommendations/c-products/assets/add-filters.png)

Tänk på att de ytterligare filteransiktena endast är tillgängliga i den aktuella sessionen.

### Ändra kolumner

Du kan tillfälligt ändra de aktiva kolumnerna på sidan [!UICONTROL Catalog Search].

1. Klicka på länken **[!UICONTROL Columns]**.

   ![Kolumnalternativ](/help/c-recommendations/c-products/assets/columns.png)

1. (Villkorligt) Om du vill ändra ordningen på de aktiva kolumnerna drar och släpper du kolumnerna i **[!UICONTROL Active Columns]**-avsnittet i önskad ordning.

1. (Villkorligt) Dra och släpp objekt från **[!UICONTROL Active Columns]** till **[!UICONTROL Inactive Columns]** (och vice versa) efter behov.

   Du kan också klicka på borttagningsikonen ( x ) bredvid den kolumn som du vill flytta från det aktiva till det inaktiva avsnittet.

Kom ihåg att alla ändringar du gör endast gäller den aktuella sessionen.

