---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;entity attribute matching
description: Filtrera dynamiskt i Adobe Target Recommendations genom att jämföra en pool med möjliga rekommendationsobjekt med ett specifikt objekt som användaren har interagerat med.
title: Filtrera efter entitetsattributmatchning i dynamiska inkluderingsregler i Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---


# ![Matchning av PREMIUM](/help/assets/premium.png) -entitetsattribut

Filtrera dynamiskt i [!DNL Adobe Target] genom [!DNL Recommendations] att jämföra en pool med potentiella rekommendationsobjekt med ett specifikt objekt som användaren har interagerat med.

Rekommendera till exempel endast objekt som matchar det aktuella objektets varumärke som i följande exempel:

Om rutan på en Varumärkeslandningssida returneras `entity.brand=Nike`returneras endast Nike-produkter och visas på den sidan. På samma sätt returneras endast Adidas-produkter på varumärkets landningssida för Adidas. Med den här typen av regel för dynamisk inkludering behöver användaren bara ange en rekommendationsregel som returnerar relevanta varumärkesresultat på alla varumärkessidor i stället för att ange en samling eller ett statiskt filter som matchar varje varumärkesnamn.

## Exempel på matchning av enhetsattribut

[!UICONTROL Entity Attribute Matching] I kan du bara rekommendera de objekt som matchar, till exempel:

* Ett attribut från det objekt som användaren för närvarande visar
* Det objekt som användaren senast visade
* Objektet som användaren senast köpte
* Det objekt som användaren mest visade
* Ett objekt som lagras i ett anpassat attribut i besökarens profil

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
