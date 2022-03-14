---
keywords: inkluderingsregler;inklusionskriterier;rekommendationer;befordran;kampanjer;dynamisk filtrering;dynamisk;profilattributsmatchning
description: Lär dig filtrera dynamiskt i Adobe [!DNL Target] Recommendations genom att jämföra artiklar (entiteter) med ett värde i användarens profil.
title: Hur filtrerar jag efter matchning av profilattribut i Recommendations-aktiviteter?
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Matchning av profilattribut

Filtrera dynamiskt i [!DNL Adobe Target] [!DNL Recommendations] genom att jämföra artiklar (entiteter) med ett värde i användarens profil.

Använd [!UICONTROL Profile Attribute Matching] när du vill visa rekommendationer som matchar ett värde som lagras i besökarens profil, till exempel storlek eller favoritmärke.

>[!NOTE]
>
>The [process för att skapa och använda inkluderingsregler](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) för villkor och kampanjer är lika, liksom för användningsexempel och exempel.

Följande scenarier visar hur du kan använda [!UICONTROL Profile Attribute Matching]:

* Ett företag som säljer glasögon lagrar besökarens favoritfärg som &quot;valnöt&quot;. För den specifika besökaren har vi skapat en rekommendation som bara returnerar ögongruppsbildrutor som matchar&quot;valnöt&quot; i färg.
* En profilparameter kan definieras för en besökares kläder (t.ex. liten, mellanstor eller stor) när de navigerar på företagets webbplats. En rekommendation kan ställas in för att matcha profilparametern och returnera produkter som bara är specifika för användarens önskade klädstorlek.

## Exempel på matchning av profilattribut {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Profile Attribute Matching] I kan du bara rekommendera de objekt som matchar ett attribut från besökarens profil, som i exemplen nedan.

### Rekommendera objekt från användarens favoritvarumärke

Du kan till exempel använda [!UICONTROL Profile Attribute Matching] alternativ för att skapa en regel som bara rekommenderar objekt där varumärket är lika med värdet eller texten som lagras i `profile.favoritebrand`. Om en besökare tittar på att skapa kortkommandon från ett visst varumärke är det bara rekommendationer som motsvarar användarens favoritvarumärke (värdet som lagras i `profile.favoritebrand` i besökarens profil).

![Favoritmärke](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Matcha jobb till arbetssökande

Anta att du försöker matcha jobb till arbetssökande. Du vill bara rekommendera jobb som finns i samma stad som jobbsökaren.

Du kan använda inkluderingsregler för att matcha en jobbsökares plats från besökarens profil till en jobblista, som i följande exempel:

![Användarens ort](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Rekommendera objekt baserat på storlek

Ett visuellt exempel på hur profilattributsmatchning påverkar rekommendationer finns på en webbplats som säljer elektriska fläktar.

När en besökare klickar på olika bilder av fans på den här webbplatsen anger varje sida värdet för `entity.size` parametern baseras på om bildens fläkt är liten eller stor.

Anta att du har skapat ett profilskript som spårar och räknar antalet gånger värdet för `entity.size` är inställt på small kontra large.

Om besökaren sedan kommer tillbaka till hemsidan, kommer han eller hon att se filtrerade rekommendationer baserat på om användaren klickade på fler små fans eller stora fans.

Recommendations bygger på en webbplats där fler små fans finns:

![rekommendationer för små fans](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations bygger på fler stora fans på webbplatsen:

![rekommendationer för stora fläktar](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
