---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: Information om hur du skapar inkluderingsregler i Adobe Target Recommendations för villkor och kampanjer och lägger till ytterligare dynamiska eller statiska filtreringsregler för att få bättre resultat.
title: Använd dynamiska och statiska inkluderingsregler i Adobe Target Recommendations
feature: criteria
mini-toc-levels: 3
uuid: f0ee2086-1126-44a4-9379-aa897dc0e06b
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Använd dynamiska och statiska inkluderingsregler{#use-dynamic-and-static-inclusion-rules}

Information om hur du skapar inkluderingsregler för villkor och kampanjer i [!DNL Adobe Target] och lägger till ytterligare dynamiska eller statiska filtreringsregler för att få bättre resultat för dina rekommendationer.

Processen för att skapa och använda inkluderingsregler för kriterier och kampanjer liknar den för användningsexempel och exempel. Både kriterier och kampanjer och användningen av inkluderingsregler omfattas av detta avsnitt.

## Lägga till filtreringsregler i villkor {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

När du [skapar villkor](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)klickar du **[!UICONTROL Add Filtering Rule]** under **[!UICONTROL Inclusion Rules]**.

![](assets/inclusion_options_new.png)

Vilka alternativ som är tillgängliga varierar beroende på vilken bransch- och rekommendationsnyckel som valts.

## Lägga till filtreringsregler i kampanjer {#section_D59AFB62E2EE423086281CF5D18B1076}

När du [skapar en befordran](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)väljer du **[!UICONTROL Promote by Attribute]** och klickar sedan på **[!UICONTROL Add Filtering Rule]**.

![](assets/inclusion_options.png)

## Filtertyper {#section_0125F1ED10A84C0EB45325122460EBCD}

I följande avsnitt visas olika filtreringsalternativ för både villkor och kampanjer, dynamisk filtrering och Filter efter värde:

### Dynamisk filtrering

Dynamiska inkluderingsregler är kraftfullare än statiska inkluderingsregler och ger bättre resultat och engagemang. Tänk på följande:

* Dynamiska inkluderingsregler ger rekommendationer genom att matcha ett attribut i en användares profilparameter eller i ett mbox-anrop.

   Du kan t.ex. skapa en rekommendation för&quot;De mest populära villkoren&quot; och sedan filtrera bort eventuella, i realtid, mot ett attribut som skickas när användaren öppnar en sida där rekommendationerna visas.

* Använd statiska regler för att begränsa vilka objekt som ska tas med i rekommendationen (i stället för samlingar).

* Du kan skapa så många dynamiska inkluderingsregler som behövs. Inkluderingsreglerna kopplas till en AND-operator. Alla regler måste uppfyllas för att ett objekt ska kunna inkluderas i en rekommendation.

Följande alternativ är tillgängliga för dynamisk filtrering:

| Alternativet för dynamisk filtrering | Detaljer |
| --- | --- |
| [Matchande entitetsattribut](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtrera dynamiskt genom att jämföra en pool med potentiella rekommendationsobjekt med ett specifikt objekt som användarna har interagerat med.<br>Använd Matchning av entitetsattribut när du vill visa rekommendationer som mest lockar besökaren, till exempel besökarens favoritvarumärke. |
| [Matchning av profilattribut](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i användarens profil.<br>Använd [!UICONTROL Profile Attribute Matching] när du vill visa rekommendationer som matchar ett värde som lagras i besökarens profil, till exempel storlek eller favoritmärke. |
| [Parametermatchning](/help/c-recommendations/c-algorithms/parameter-matching.md) | Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).<br>Använd Parametermatchning för att rekommendera innehåll som matchar sidparametrarna eller besöksparametrarna, till exempel enhetsdimensioner eller geopositionering. |

### Filtrera efter värde

Följande alternativ är tillgängliga för filtrering efter värde:

| Filtrera efter värde, alternativ | Detaljer |
| --- | --- |
| [Statiskt filter](/help/c-recommendations/c-algorithms/static-value.md) | Ange manuellt ett eller flera statiska värden som ska filtreras. |

## Dynamiska kriterier och exempel på kampanjer

Dynamiska kriterier och kampanjer är mycket kraftfullare än statiska kriterier och kampanjer, och ger bättre resultat och engagemang.

Följande exempel ger dig allmänna idéer om hur du kan använda dynamiska kampanjer i dina marknadsföringssatsningar:

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
