---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;entity attribute matching
description: Filtrera dynamiskt i Adobe Target Recommendations genom att jämföra en pool med möjliga rekommendationsobjekt med ett specifikt objekt som användaren har interagerat med.
title: Filtrera efter entitetsattributmatchning i dynamiska inkluderingsregler i Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: c814215476ef6e40f4f175fe3f9dbb2c26b966eb
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 0%

---


# ![Matchning av PREMIUM](/help/assets/premium.png) -entitetsattribut

Filtrera dynamiskt i [!DNL Adobe Target] genom [!DNL Recommendations] att jämföra en pool med potentiella rekommendationsobjekt med ett specifikt objekt som användaren har interagerat med.

>[!NOTE]
>
>Processen [för att skapa och använda inkluderingsregler](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) för kriterier och kampanjer är liknande, liksom användningsexempel och exempel.

Rekommendera till exempel endast objekt som matchar det aktuella objektets varumärke som i följande exempel:

Om rutan på en Varumärkeslandningssida returneras `entity.brand=Nike`returneras endast Nike-produkter och visas på den sidan. På samma sätt returneras endast Adidas-produkter på varumärkets landningssida för Adidas. Med den här typen av regel för dynamisk inkludering behöver användaren bara ange en rekommendationsregel som returnerar relevanta varumärkesresultat på alla varumärkessidor i stället för att ange en samling eller ett statiskt filter som matchar varje varumärkesnamn.

Observera att du måste skicka `entity.brand` i mbox på landningssidorna för att det ska fungera.

## Exempel på matchning av enhetsattribut

[!UICONTROL Entity Attribute Matching] I kan du bara rekommendera de objekt som matchar, till exempel:

* Ett attribut från det objekt som användaren för närvarande visar
* Det objekt som användaren senast visade
* Objektet som användaren senast köpte
* Det objekt som användaren mest visade
* Ett objekt som lagras i ett anpassat attribut i besökarens profil

### Rekommendera objekt baserat på varumärke

När entitetsattributreglerna har skapats filtrerar de bort alla rekommendationer med attribut som inte matchar det enhetsvärde som skickats på sidan.

I följande exempel visas rekommendationer för att matcha produktvarumärket som visas på sidan:

När du besöker en sida som innehåller en Nike-produkt, ställer sidan in värdet för `entity.brand` parametern till &quot;Nike&quot;.

![Exempel på Target-anrop](/help/c-recommendations/c-algorithms/assets/example-target-call.png)

I rekommendationerna på sidan visas endast Nike-produkter.

![Nikes rekommendationer](/help/c-recommendations/c-algorithms/assets/nike.png)

Om du sedan visar en Adidas-produktsida återställs `entity.brand` värdet till &quot;Adidas&quot; och du ser Adidas-produkter som rekommenderas på Adidas-produktsidor.

![Adidas-rekommendationer](/help/c-recommendations/c-algorithms/assets/adidas.png)

### Merförsäljning av en dyrare produkt

Anta att du är en klädhandlare och vill uppmuntra användarna att överväga högre priser och därmed mer lönsamma artiklar. Du kan använda operatorerna &quot;equals&quot; och &quot;is between&quot; för att marknadsföra dyrare objekt från samma kategori och samma varumärke. En skohandlare kan till exempel marknadsföra dyrare skor i ett försök att sälja in en besökare som tittar på skor, som i följande kodexempel:

```
Entity Attribute Matching
category - equals - current item's - category 
And 
Entity Attribute Matching
brand - equals - current item's - brand 
And 
Entity Attribute Matching
value - is between - 100% and 1000% of - current item's - value
```

### Marknadsföring av privata märkesprodukter

Du kan blanda dynamiska och statiska filter för att marknadsföra privata etikettprodukter. Ett kontorsföretag kan till exempel marknadsföra tonerkassetter för företagets varumärke för att få en mer lönsam försäljning för en besökare som tittar på toner - och marknadsföra pennor från företagets varumärke för att få en mer lönsam försäljning för en besökare som tittar på pennor, som i följande kodexempel:

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
