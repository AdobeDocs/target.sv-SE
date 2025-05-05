---
keywords: inkluderingsregler;inklusionskriterier;rekommendationer;befordran;kampanjer;dynamisk filtrering;dynamisk;profilattributsmatchning
description: Lär dig hur du filtrerar dynamiskt i [!DNL Target Recommendations] genom att jämföra objekt (entiteter) med ett värde i användarens profil.
title: Hur filtrerar jag efter matchning av profilattribut i Recommendations-aktiviteter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Matchning av profilattribut

Filtrera dynamiskt i [!DNL Adobe Target Recommendations] genom att jämföra objekt (entiteter) med ett värde i användarens profil.

Använd [!UICONTROL Profile Attribute Matching] när du vill visa rekommendationer som matchar ett värde som lagras i besökarens profil, till exempel storlek eller favoritmärke.

>[!NOTE]
>
>Processen [för att skapa och använda inkluderingsregler](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) för villkor och kampanjer är liknande, liksom användningsexempel och exempel.

Följande scenarier visar hur du kan använda [!UICONTROL Profile Attribute Matching]:

* Ett företag som säljer glasögon lagrar besökarens favoritfärg som &quot;valnöt&quot;. För den specifika besökaren har rekommendationer konfigurerats så att endast ögongruppsbildrutor som matchar&quot;valnöt&quot; i färg returneras.
* En profilparameter kan definieras för en besökares klädstorlek (till exempel Liten, Medium eller Stor) när de navigerar på företagets webbplats. En rekommendation kan ställas in för att matcha profilparametern och returnera produkter som bara är specifika för användarens önskade klädstorlek.

## Exempel på matchning av profilattribut {#section_9873E2F22E094E479569D05AD5BB1D40}

Med [!UICONTROL Profile Attribute Matching] kan du bara rekommendera de objekt som matchar ett attribut från besökarens profil, som i exemplen nedan.

### Rekommendera objekt från användarens favoritvarumärke

Du kan till exempel använda alternativet [!UICONTROL Profile Attribute Matching] för att skapa en regel som bara rekommenderar objekt där varumärket är lika med värdet eller texten som lagras i `profile.favoritebrand`. Om en besökare tittar på att köra kortkommandon från ett visst varumärke visar endast rekommendationer som matchar användarens favoritvarumärke (värdet som lagras i `profile.favoritebrand` i besökarens profil).

![Favoritmärke](/help/main/c-recommendations/c-algorithms/assets/favorite-brand-new.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Matcha jobb till arbetssökande

Anta att du försöker matcha jobb till arbetssökande. Du vill bara rekommendera jobb som finns i samma stad som jobbsökaren.

Du kan använda inkluderingsregler för att matcha en jobbsökares plats från besökarens profil till en jobblista, som i följande exempel:

![Användarens ort](/help/main/c-recommendations/c-algorithms/assets/city-new.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Rekommendera objekt baserat på storlek

Ett visuellt exempel på hur profilattributsmatchning påverkar rekommendationer finns på en webbplats som säljer elektriska fläktar.

När en besökare klickar på olika bilder av fans på den här webbplatsen anger varje sida värdet för parametern `entity.size` baserat på om bildens fläkt är liten eller stor.

Anta att du har skapat ett profilskript för att spåra och räkna antalet gånger som värdet för `entity.size` har angetts till litet eller stort.

Om besökaren sedan återgår till hemsidan ser de filtrerade rekommendationer som baseras på om användaren har klickat på fler små fans eller stora fans.

Recommendations bygger på en webbplats där fler små fans finns:

![rekommendationer för små fans](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations bygger på fler stora fans på webbplatsen:

![rekommendationer för stora fans](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
