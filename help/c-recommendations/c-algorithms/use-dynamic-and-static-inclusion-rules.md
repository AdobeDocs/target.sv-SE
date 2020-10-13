---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: Information om hur du skapar inkluderingsregler i Adobe Target Recommendations för villkor och kampanjer och lägger till ytterligare dynamiska eller statiska filtreringsregler för att få bättre resultat.
title: Använd dynamiska och statiska inkluderingsregler i Adobe Target Recommendations
feature: criteria
mini-toc-levels: 3
uuid: f0ee2086-1126-44a4-9379-aa897dc0e06b
translation-type: tm+mt
source-git-commit: f1df23d94ab81002945b22c6468ba1d3a9030388
workflow-type: tm+mt
source-wordcount: '2091'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Använd dynamiska och statiska inkluderingsregler{#use-dynamic-and-static-inclusion-rules}

Information om hur du skapar inkluderingsregler för villkor och kampanjer i Adobe Target och lägger till ytterligare dynamiska eller statiska filtreringsregler för att få bättre resultat för dina rekommendationer.

Processen för att skapa och använda inkluderingsregler för kriterier och kampanjer liknar den för användningsexempel och exempel. Både kriterier och kampanjer och användningen av inkluderingsregler omfattas av detta ämne.

## Lägga till filtreringsregler i villkor {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

När du [skapar villkor](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)klickar du **[!UICONTROL Add Filtering Rule]** under **[!UICONTROL Inclusion Rules]**.

![](assets/inclusion_options_new.png)

Vilka alternativ som är tillgängliga varierar beroende på vilken bransch- och rekommendationsnyckel som valts.

## Lägga till filtreringsregler i kampanjer {#section_D59AFB62E2EE423086281CF5D18B1076}

När du [skapar en befordran](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)väljer du **[!UICONTROL Promote by Attribute]** och klickar sedan på **[!UICONTROL Add Filtering Rule]**.

![](assets/inclusion_options.png)

## Filtertyper {#section_0125F1ED10A84C0EB45325122460EBCD}

I följande tabell visas olika filtreringsalternativ för både villkor och kampanjer:

### Dynamisk filtrering

Dynamiska inkluderingsregler är kraftfullare än statiska inkluderingsregler och ger bättre resultat och engagemang. Tänk på följande:

* Dynamiska inkluderingsregler ger rekommendationer genom att matcha ett attribut i en användares profilparameter eller i ett mbox-anrop.

   Du kan t.ex. skapa en rekommendation för de mest populära villkoren och sedan filtrera bort eventuella, i realtid, mot ett attribut som skickas när användaren öppnar en sida där rekommendationerna visas.

* Använd statiska regler för att begränsa vilka objekt som ska tas med i rekommendationen (i stället för samlingar).

* Du kan skapa så många dynamiska inkluderingsregler som behövs. Inkluderingsreglerna kopplas till en AND-operator. Alla regler måste uppfyllas för att ett objekt ska kunna inkluderas i en rekommendation.

Följande alternativ är tillgängliga för dynamisk filtrering:

#### Matchande entitetsattribut

Filtrera dynamiskt genom att jämföra en pool med potentiella rekommendationsobjekt med ett specifikt objekt som användarna har interagerat med.

Rekommendera till exempel endast objekt som matchar det aktuella objektets varumärke som i följande exempel:

Om rutan på en Varumärkeslandningssida returneras `entity.brand=Nike`returneras endast Nike-produkter och visas på den sidan. På samma sätt returneras endast Adidas-produkter på varumärkets landningssida för Adidas. Med den här typen av regel för dynamisk inkludering behöver användaren bara ange en rekommendationsregel som returnerar relevanta varumärkesresultat på alla varumärkessidor i stället för att ange en samling eller ett statiskt filter som matchar varje varumärkesnamn.

Tillgängliga operatorer:

* är lika med
* är inte lika med
* är mellan
* innehåller
* innehåller inte
* börjar med
* slutar med
* värde finns
* värdet finns inte
* är större än eller lika med
* är mindre än eller lika med

#### Matchning av profilattribut

Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i användarens profil.

Använd [!UICONTROL Profile Attribute Matching] när du vill visa rekommendationer som matchar ett värde som lagras i besökarens profil, till exempel storlek eller favoritmärke.

I följande exempel visas hur du kan använda [!UICONTROL Profile Attribute Matching]:

* Ett företag som säljer glasögon lagrar besökarens favoritfärg som &quot;valnöt&quot;. För just den besökaren har vi skapat en rekommendation som bara returnerar ögongruppsbildrutor som matchar&quot;valnöt&quot; i färg.
* En profilparameter kan definieras för en besökares kläder (t.ex. liten, mellanstor eller stor) när de navigerar på företagets webbplats. En rekommendation kan ställas in för att matcha profilparametern och returnera produkter som bara är specifika för användarens önskade klädstorlek.

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

Ett visuellt exempel på hur profilattributsmatchning påverkar rekommendationer finns på en webbplats som säljer fans.

När en besökare klickar på olika bilder av fans på den här webbplatsen anger varje sida parameterns värde baserat på om storleken på fläkten i bilden är liten eller stor. `entity.size`

Anta att du har skapat ett profilskript för att spåra och räkna antalet gånger som värdet för `entity.size` är inställt på small kontra large.

Om besökaren sedan kommer tillbaka till hemsidan, kommer han eller hon att se filtrerade rekommendationer baserat på om användaren klickade på fler små fans eller stora fans.

Recommendations bygger på en webbplats där fler små fans finns:

![rekommendationer för små fans](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations bygger på fler stora fans på webbplatsen:

![rekommendationer för stora fläktar](/help/c-recommendations/c-algorithms/assets/large-fans.png)

#### Parametermatchning

Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).

Rekommendera t.ex. bara innehåll som matchar parametern&quot;branschsida&quot; eller andra parametrar som enhetsdimensioner eller geolokalisering, som i följande exempel.

* Mbox-parametrar för skärmbredd och -höjd kan användas för att rikta sig till mobilbesökare och endast rekommendera mobila enheter och tillbehör.
* Regionala geopositioneringsparametrar kan användas för att returnera rekommendationer för verktyg under vintern. Snöblåsare och andra verktyg för att minska snön kan rekommenderas för besökare i områden där det snöar men inte för besökare i områden där det inte snöar.

>[!NOTE]
>
>Om aktiviteten skapades före 31 oktober 2016 misslyckas leveransen om det använder filtret Parametermatchning. Så här undviker du problemet:
>
>* Skapa en ny aktivitet och lägg till dina villkor i den.
>* Använd ett villkor som inte innehåller filtret Parametermatchning.
>* Ta bort filtret &quot;Parametermatchning&quot; från villkoren.


Tillgängliga operatorer:

* är lika med
* är inte lika med
* innehåller
* innehåller inte
* börjar med
* slutar med
* är större än eller lika med
* är mindre än eller lika med
* är mellan

### Filtrera efter värde

Följande alternativ är tillgängliga för dynamisk filtrering:

#### Statiskt filter

Ange manuellt ett eller flera statiska värden som ska filtreras.

Rekommendera t.ex. endast innehåll med MPAA-klassificeringen &quot;G&quot; eller &quot;PG&quot;.

Tillgängliga operatorer:

* är lika med
* är inte lika med
* innehåller
* innehåller inte
* börjar med
* slutar med
* värde finns
* värdet finns inte
* är större än eller lika med
* är mindre än eller lika med

>[!NOTE]
>
>Om du känner till hur inkluderingsregler konfigurerades före Target 17.6.1-versionen (juni 2017) kommer du att märka att vissa alternativ och operatorer har ändrats. Endast de operatorer som kan användas för den valda alternativvisningen och vissa operatorer har bytt namn (&quot;match&quot; är nu lika med) för att vara mer konsekventa och intuitiva. Alla befintliga undantagsregler som skapades före den här versionen migrerades automatiskt till den nya strukturen. Ni behöver inte göra någon omstrukturering.

Du kan skapa så många inkluderingsregler som behövs. Inkluderingsreglerna kopplas till en AND-operator. Alla regler måste uppfyllas för att ett objekt ska kunna inkluderas i en rekommendation.

## Dynamiska kriterier och exempel på kampanjer

Dynamiska kriterier och kampanjer är mycket kraftfullare än statiska kriterier och kampanjer, och ger bättre resultat och engagemang.

I följande exempel får du idéer om hur du kan använda dynamiska kampanjer i dina marknadsföringssatsningar:

### Lika med

När en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film) kan du använda operatorn lika i dynamiska kampanjer för att marknadsföra andra objekt från:

* samma varumärke
* samma kategori
* samma kategori OCH från varumärket
* samma butik

### Är inte lika med

Om du använder operatorn&quot;inte jämför&quot; i dynamiska kampanjer kan du befordra andra saker när en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film):

* en annan TV-serie
* en annan genre
* en annan produktserie
* ett annat format-ID

### Är mellan

När en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film) kan du använda operatorn&quot;är mellan&quot; i dynamiska kampanjer för att marknadsföra andra element som är:

* mer kostsam
* billigare
* kostnad plus eller minus 30 %
* senare avsnitt under samma säsong
* tidigare böcker i en serie

## Hantera tomma värden vid filtrering efter entitetsattributmatchning, matchning av profilattribut och parametermatchning {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Du kan välja flera alternativ för att hantera tomma värden vid filtrering efter [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching]och [!UICONTROL Parameter Matching] för avslutningskriterier och kampanjer.

Tidigare returnerades inga resultat om ett värde var tomt. Med listrutan&quot;Om *x* är tom&quot; kan du välja vilken åtgärd som ska utföras om villkoret har tomma värden, vilket visas på följande bild:

![](assets/empty_value.png)

Om du vill välja önskad åtgärd håller du pekaren över kugghjulsikonen (![](assets/icon_gear.png)) och väljer önskad åtgärd:

| Åtgärd | Finns för | Detaljer |
|--- |--- |--- |
| Ignorera den här filtreringsregeln | Matchning<br>av profilattribut för MatchingParameter | Detta är standardåtgärden för Matchning av profilattribut och Parametermatchning.<br>Det här alternativet anger att regeln ignoreras. Om det till exempel finns tre filtreringsregler och den tredje regeln inte skickar några värden, i stället för att inte returnera några resultat, kan du helt enkelt ignorera den tredje regeln med de tomma värdena. |
| Befordra inga objekt | Matchning av<br>matchningsprofilattribut<br>för entitetsattribut | Det här är standardåtgärden för entitetsattributmatchning.<br>Den här åtgärden är hur tomma värden [!DNL Target] hanteras innan det här alternativet läggs till: inga resultat kommer att visas för dessa kriterier. |
| Använd ett statiskt värde | Matchning av<br>matchningsprofilattribut<br>för entitetsattribut | Om ett värde är tomt kan du välja att använda ett statiskt värde. |

## Exempel på matchning av profilattribut {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Profile Attribute Matching] I kan du bara rekommendera de objekt som matchar ett attribut från besökarens profil, som i exemplen nedan.

### Exempel 1: Rekommendera objekt från användarens favoritvarumärke

Du kan till exempel använda alternativet för att skapa en regel som bara rekommenderar objekt där varumärket är lika med värdet eller texten som lagras i [!UICONTROL Profile Attribute Matching] `profile.favoritebrand`. Om en besökare tittar på kortkommandon från ett visst varumärke är det bara rekommendationer som motsvarar användarens favoritvarumärke (värdet som lagras i `profile.favoritebrand` besökarens profil) som visas.

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Exempel 2: Matcha jobb till arbetssökande

Anta att du försöker matcha jobb till arbetssökande. Du vill bara rekommendera jobb som finns i samma stad som jobbsökaren.

Du kan använda inkluderingsregler för att matcha en jobbsökares plats från besökarens profil till en jobblista, som i följande exempel:

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

## Exempel på matchning av enhetsattribut

[!UICONTROL Entity Attribute Matching] I kan du endast rekommendera de objekt som matchar ett attribut från det objekt som användaren för närvarande visar, det objekt som användaren senast visade, det objekt som användaren senast köpte, det objekt som användaren oftast visade eller från ett objekt som sparats i ett anpassat attribut i besökarens profil, som i exemplen nedan.

### Exempel 3: Merförsäljning av en dyrare produkt

Anta att du är en klädhandlare och vill uppmuntra användarna att överväga högre priser och därmed mer lönsamma artiklar. Du kan använda operatorerna &quot;equals&quot; och &quot;is between&quot; för att marknadsföra dyrare objekt från samma kategori och samma varumärke. En skohandlare kan till exempel marknadsföra dyrare skor i ett försök att sälja in en besökare som tittar på skor.

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

### Exempel 4: Marknadsföring av privata märkesprodukter

Du kan blanda dynamiska och statiska filter för att marknadsföra privata etikettprodukter. Ett kontorsföretag kan till exempel marknadsföra tonerkassetter för företagets varumärke för att få en mer lönsam försäljning för en besökare som tittar på toner - och marknadsföra pennor från företagets varumärke för att få en mer lönsam försäljning för en besökare som tittar på pennor.

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

## Caveats {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>Olika datatypsattribut kanske inte är kompatibla med operatorerna &quot;equals&quot; och &quot;does not equal&quot; under körning. Du bör använda [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory]och [!UICONTROL Environment] värden klokt på den högra sidan om den vänstra sidan har fördefinierade attribut eller anpassade attribut.

![](assets/left_right.png)

I följande tabell visas gällande regler och regler som kanske inte är kompatibla under körning:

| Kompatibla regler | Regler som kan vara inkompatibla |
|--- |--- |
| värde - är mellan - 90 % och 110 % av aktuell artikels - salesValue | salesValue - är mellan - 90 % och 110 % av aktuell artikels - värde |
| värde - är mellan - 90 % och 110 % av det aktuella objektets - värde | clearancePrice - är mellan - 90 % och 110 % av aktuell artikels - marginal |
| marginal - är mellan - 90 % och 110 % av aktuell artikels - marginal | storeInventory - lika med - aktuell artikel - lager |
| lager - är lika med - aktuell artikel - lager |  |
