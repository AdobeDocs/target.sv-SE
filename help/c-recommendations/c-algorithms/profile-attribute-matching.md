---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;profile attribute matching
description: Filtrera dynamiskt i Adobe Target Recommendations genom att jämföra objekt (enheter) med ett värde i användarens profil.
title: Filtrera efter profilattributmatchning i dynamiska inkluderingsregler i Adobe Target Recommendations
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 0%

---


# ![Matchning av ](/help/assets/premium.png) PREMIUMProfile-attribut

Filtrera dynamiskt i [!DNL Adobe Target] [!DNL Recommendations] genom att jämföra objekt (entiteter) med ett värde i användarens profil.

Använd [!UICONTROL Profile Attribute Matching] när du vill visa rekommendationer som matchar ett värde som lagras i besökarens profil, till exempel storlek eller favoritmärke.

>[!NOTE]
>
>Processen [för att skapa och använda inkluderingsregler](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) för villkor och kampanjer är liknande, liksom användningsexempel och exempel.

Följande scenarier visar hur du kan använda [!UICONTROL Profile Attribute Matching]:

* Ett företag som säljer glasögon lagrar besökarens favoritfärg som &quot;valnöt&quot;. För just den besökaren har vi skapat en rekommendation som bara returnerar ögongruppsbildrutor som matchar&quot;valnöt&quot; i färg.
* En profilparameter kan definieras för en besökares kläder (t.ex. liten, mellanstor eller stor) när de navigerar på företagets webbplats. En rekommendation kan ställas in för att matcha profilparametern och returnera produkter som bara är specifika för användarens önskade klädstorlek.

## Exempel på matchning av profilattribut {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Profile Attribute Matching] I kan du bara rekommendera de objekt som matchar ett attribut från besökarens profil, som i exemplen nedan.

### Rekommendera objekt från användarens favoritvarumärke

Du kan till exempel använda alternativet [!UICONTROL Profile Attribute Matching] för att skapa en regel som bara rekommenderar objekt där varumärket är lika med värdet eller texten som lagras i `profile.favoritebrand`. Om en besökare tittar på att köra kortkommandon från ett visst varumärke visar bara rekommendationer som matchar användarens favoritvarumärke (värdet som lagras i `profile.favoritebrand` i besökarens profil).

![Favoritmärke](/help/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Matcha jobb till arbetssökande

Anta att du försöker matcha jobb till arbetssökande. Du vill bara rekommendera jobb som finns i samma stad som jobbsökaren.

Du kan använda inkluderingsregler för att matcha en jobbsökares plats från besökarens profil till en jobblista, som i följande exempel:

![Användarens ort](/help/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Rekommendera objekt baserat på storlek

Ett visuellt exempel på hur profilattributsmatchning påverkar rekommendationer finns på en webbplats som säljer elektriska fläktar.

När en besökare klickar på olika bilder av fans på den här webbplatsen anger varje sida värdet för parametern `entity.size` baserat på om storleken på fläkten i bilden är liten eller stor.

Anta att du har skapat ett profilskript för att spåra och räkna antalet gånger som värdet för `entity.size` är inställt på small vs. large.

Om besökaren sedan kommer tillbaka till hemsidan, kommer han eller hon att se filtrerade rekommendationer baserat på om användaren klickade på fler små fans eller stora fans.

Recommendations bygger på en webbplats där fler små fans finns:

![rekommendationer för små fans](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations bygger på fler stora fans på webbplatsen:

![rekommendationer för stora fläktar](/help/c-recommendations/c-algorithms/assets/large-fans.png)