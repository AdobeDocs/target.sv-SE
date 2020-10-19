---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;profile attribute matching
description: Filtrera dynamiskt i Adobe Target Recommendations genom att jämföra objekt (enheter) med ett värde i användarens profil.
title: Filtrera efter profilattributmatchning i dynamiska inkluderingsregler i Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 0%

---


# ![Matchning av PREMIUM](/help/assets/premium.png) -profilattribut

Filtrera dynamiskt i [!DNL Adobe Target] [!DNL Recommendations] genom att jämföra artiklar (entiteter) med ett värde i användarens profil.

Använd [!UICONTROL Profile Attribute Matching] när du vill visa rekommendationer som matchar ett värde som lagras i besökarens profil, till exempel storlek eller favoritmärke.

Följande scenarier visar hur du kan använda [!UICONTROL Profile Attribute Matching]:

* Ett företag som säljer glasögon lagrar besökarens favoritfärg som &quot;valnöt&quot;. För just den besökaren har vi skapat en rekommendation som bara returnerar ögongruppsbildrutor som matchar&quot;valnöt&quot; i färg.
* En profilparameter kan definieras för en besökares kläder (t.ex. liten, mellanstor eller stor) när de navigerar på företagets webbplats. En rekommendation kan ställas in för att matcha profilparametern och returnera produkter som bara är specifika för användarens önskade klädstorlek.

## Exempel på matchning av profilattribut {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Profile Attribute Matching] I kan du bara rekommendera de objekt som matchar ett attribut från besökarens profil, som i exemplen nedan.

### Rekommendera objekt från användarens favoritvarumärke

Du kan till exempel använda alternativet för att skapa en regel som bara rekommenderar objekt där varumärket är lika med värdet eller texten som lagras i [!UICONTROL Profile Attribute Matching] `profile.favoritebrand`. Om en besökare tittar på kortkommandon från ett visst varumärke är det bara rekommendationer som motsvarar användarens favoritvarumärke (värdet som lagras i `profile.favoritebrand` besökarens profil) som visas.

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Matcha jobb till arbetssökande

Anta att du försöker matcha jobb till arbetssökande. Du vill bara rekommendera jobb som finns i samma stad som jobbsökaren.

Du kan använda inkluderingsregler för att matcha en jobbsökares plats från besökarens profil till en jobblista, som i följande exempel:

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Rekommendera kläder som matchar besökarens storlek

Låt oss titta på ett exempel för att rekommendera kläder som matchar den klädstorlek som angetts i besökarens profil.

Produktsidan skickas `entity.size` i mbox-anropet (röd pil i bilden nedan).

Du kan skapa ett [profilskript](/help/c-target/c-visitor-profile/profile-parameters.md) för att hämta besökarens profilattribut och värden från den sista sidan som besökaren besökte.

Exempel:

```
if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'small')) { return 'small';
}

else if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'medium')) { return 'medium';
}

else if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'large')) { return 'large';
}
```

Profilskriptet hämtar `entity.size` värdet från rutan `target-global-mbox` och returnerar det som ett profilattribut med namnet `user.size` (blå pil i bilden nedan).

![storleksanrop](/help/c-recommendations/c-algorithms/assets/size.png)

När du skapar rekommendationskriterierna klickar du på [!UICONTROL Add Filtering Rule]och väljer [!UICONTROL Profile Attribute Matching].

![Bild på matchning av profilattribut](/help/c-recommendations/c-algorithms/assets/profile-attribute-matching.png)

Om din `user.size` profil har lästs in i [!DNL Target]visas den i listrutan för matchning när du ställer in regeln så att den matchar värdet som skickades i mbox-anropet (`size`) till profilskriptnamnet (`user.size`).

Du kan sedan välja &quot;size&quot; &quot;equals&quot; (storlek) som är lika med värdet/texten i &quot;user.size&quot; för din profilattributsmatchning.

När profilattributreglerna har skapats filtrerar de bort alla rekommendationer som har attribut som inte matchar besökarens lagrade profilattribut.

### Rekommendera objekt baserat på storlek

Ett visuellt exempel på hur profilattributsmatchning påverkar rekommendationer finns på en webbplats som säljer fans.

När en besökare klickar på olika bilder av fans på den här webbplatsen anger varje sida parameterns värde baserat på om storleken på fläkten i bilden är liten eller stor. `entity.size`

Anta att du har skapat ett profilskript för att spåra och räkna antalet gånger som värdet för `entity.size` är inställt på small kontra large.

Om besökaren sedan kommer tillbaka till hemsidan, kommer han eller hon att se filtrerade rekommendationer baserat på om användaren klickade på fler små fans eller stora fans.

Recommendations bygger på en webbplats där fler små fans finns:

![rekommendationer för små fans](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations bygger på fler stora fans på webbplatsen:

![rekommendationer för stora fläktar](/help/c-recommendations/c-algorithms/assets/large-fans.png)