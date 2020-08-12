---
keywords: catalog;search
description: Katalogsökningen i Adobe Target hjälper dig att hitta produkterna eller innehållet i din katalog.
title: Katalogsökning i Adobe Target
feature: null
uuid: e0876963-5905-4850-a615-953e435f26e9
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) -katalogsökning {#catalog-search}

Katalogsökningen hjälper dig att hitta produkterna eller innehållet i din katalog.

Klicka **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]** för att komma åt katalogsökningen.

Du kan förfina sökningen genom att välja ett sökalternativ på Alternativ-menyn som visas när du klickar på nedpilen i sökfältet.

![](assets/searchproductsmenu.png)

Sökalternativen omfattar följande:

* ALLA
* Namn
* Varumärke
* Kategori
* ID
* Meddelande

**[!UICONTROL ALL]** söker igenom alla andra sökvillkor med hjälp av ELLER-logik.

I sökresultaten klickar du på **[!UICONTROL Environment]** filtret för att ange den [produktionsvärdgruppsmiljö](/help/administrating-target/hosts.md) vars katalog du visar. Du kan även bläddra bland objekten i sökresultaten för att visa miniatyrbilder och annan produktinformation.

Numret som visas bredvid&quot;Produkter&quot; är antalet produkter som matchar söktermen, av det totala antalet som finns i den angivna miljön.

Katalogen uppdateras automatiskt när uppdateringar tas emot via feedsfiler, API eller mbox-uppdateringar. Uppdateringarna slutförs normalt på en timme. Om uppdateringar pågår visas den tid då den senaste uppdateringen startades. Om inga uppdateringar pågår visas den tid då den senaste uppdateringen startades och avslutades.

## Skapa en samling eller ett undantag baserat på avancerad sökning

Du kan skapa [samlingar](/help/c-recommendations/c-products/collections.md) eller [undantag](/help/c-recommendations/c-products/exclusions.md) med Avancerad sökning på katalogsöksidan ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Dialogrutan Spara som](/help/c-recommendations/c-products/assets/save-as-dialog.png)

När du har skapat en sökning med&quot;id > contains&quot; kan du till exempel klicka på [!UICONTROL Save As] > [!UICONTROL Collection or Exclusion].

>[!IMPORTANT]
>
>Funktionen för avancerad sökning är inte skiftlägeskänslig; men de produkter som returneras vid leveranstillfället bygger på skiftlägeskänslig sökning. Denna felmatchning kan leda till förvirring. Se till att du tar hänsyn till skiftlägeskänslighet när du skapar samlingar eller uteslutningar baserat på resultat med funktionen Avancerad sökning. Om du till exempel söker efter Semester visas resultatet som innehåller Semester och Semester i den inledande sökningen. Om du sedan skapar en katalog med avsikten att returnera produkter som innehåller &quot;semester&quot; returneras endast produkter som innehåller &quot;semester&quot;. Produkter som innehåller &quot;Semester&quot; returneras inte. Uteslutningar hanteras på liknande sätt.
