---
keywords: inkluderingsregler;inklusionskriterier;rekommendationer;befordran;kampanjer;dynamisk filtrering;dynamisk;entitetsattributmatchning
description: Lär dig hur du filtrerar dynamiskt i [!DNL Target Recommendations] genom att jämföra en pool med potentiella objekt med ett specifikt objekt som användaren har interagerat med.
title: Hur filtrerar jag efter entitetsattribut som matchar i rekommendationer?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# Matchande entitetsattribut

Filtrera dynamiskt i [!DNL Adobe Target Recommendations] genom att jämföra en pool med potentiella rekommendationsobjekt med ett specifikt objekt som användaren har interagerat med.

>[!NOTE]
>
>Processen [för att skapa och använda inkluderingsregler](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) för villkor och kampanjer är liknande, liksom användningsexempel och exempel.

Rekommendera till exempel endast objekt som matchar det aktuella objektets varumärke som i följande exempel:

Om mbox på en varumärkeslandningssida returnerar `entity.brand=brandA` returneras endast produkter av typen Brand A och visas på den sidan. På samma sätt returneras endast produkter av typen Varumärkeslandning för Varumärke B. Med den här typen av regel för dynamisk inkludering behöver användaren bara ange en rekommendationsregel som returnerar relevanta varumärkesresultat på alla varumärkessidor i stället för att ange en samling eller ett statiskt filter som matchar varje varumärkesnamn.

Observera att du måste leverera `entity.brand` i mbox på dessa landningssidor för att den här processen ska fungera.

## Exempel på matchning av enhetsattribut

I [!UICONTROL Entity Attribute Matching] kan du bara rekommendera de objekt som matchar, till exempel:

* Ett attribut från det objekt som användaren för närvarande visar
* Det objekt som användaren senast visade
* Objektet som användaren senast köpte
* Det objekt som användaren mest visade
* Ett objekt som lagras i ett anpassat attribut i besökarens profil

### Rekommendera objekt baserat på varumärke

När entitetsattributreglerna har skapats filtrerar de bort alla rekommendationer med attribut som inte matchar det enhetsvärde som skickats på sidan.

I följande exempel visas rekommendationer för att matcha produktvarumärket som visas på sidan:

När du besöker en sida som innehåller en produkt av typen Varumärke A, ställer sidan in värdet för parametern `entity.brand` till &quot;VarumärkeA&quot;.

![Exempel på målanrop](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

I rekommendationerna på sidan visas endast produkter från varumärket A.

![Varumärke A rekommendationer](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

Om du sedan visar en produktsida för varumärke B återställs värdet `entity.brand` till&quot;varumärkeB&quot; och du ser vilka produkter för varumärket B som rekommenderas på produktsidorna för varumärket B.

![Varumärkesrekommendationer B](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### Merförsäljning av en dyrare produkt

Anta att du är en klädhandlare och vill uppmuntra användarna att överväga högre priser och därmed mer lönsamma artiklar. Du kan använda operatorerna &quot;equals&quot; och &quot;is between&quot; för att marknadsföra dyrare objekt från samma kategori och samma varumärke. En skohandlare kan till exempel marknadsföra dyrare skor i ett försök att sälja in en besökare som tittar på skor, som i följande exempel:

![Merförsäljning](/help/main/c-recommendations/c-algorithms/assets/upsell-new.png)

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

Du kan blanda dynamiska och statiska filter för att marknadsföra privata etikettprodukter. Ett kontorsföretag kan till exempel marknadsföra tonerkassetter för företagets varumärke för att få en mer lönsam försäljning för en besökare som tittar på toner - och marknadsföra pennor från företagets varumärke för att få en mer lönsam försäljning för en besökare som tittar på pennor, som i följande exempel:

![House Brand](/help/main/c-recommendations/c-algorithms/assets/housebrand-new.png)
)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
