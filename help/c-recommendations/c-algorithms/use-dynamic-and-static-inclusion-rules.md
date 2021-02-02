---
keywords: inkluderingsregler;inkluderingskriterier;rekommendationer;skapa nya kriterier;befordran;kampanjer;dynamisk filtrering;dynamiska;tomma värden;ignorera filtreringsregel;statiskt filter;filter efter värde;entitetsattributmatchning;profilattributmatchning;parametermatchning;filter efter värde;statiskt filter
description: Information om hur du skapar inkluderingsregler i Adobe Target Recommendations för villkor och kampanjer och lägger till ytterligare dynamiska eller statiska filtreringsregler för att få bättre resultat.
title: Använd regler för dynamisk och statisk inkludering i Recommendations Target
feature: Recommendations
mini-toc-levels: 3
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMUnvänd dynamiska och statiska inkluderingsregler{#use-dynamic-and-static-inclusion-rules}

Information om hur du skapar inkluderingsregler för villkor och kampanjer i [!DNL Adobe Target] och lägger till ytterligare dynamiska eller statiska filtreringsregler för att få bättre resultat för dina rekommendationer.

>[!NOTE]
>
>Processen för att skapa och använda inkluderingsregler för kriterier och kampanjer liknar den för användningsexempel och exempel. Både kriterier och kampanjer och användningen av inkluderingsregler omfattas av detta avsnitt.

## Lägger till filtreringsregler i villkor {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

När du [skapar villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE) klickar du på **[!UICONTROL Add Filtering Rule]** under **[!UICONTROL Inclusion Rules]**.

![](assets/inclusion_options_new.png)

Vilka alternativ som är tillgängliga varierar beroende på vilken bransch- och rekommendationsnyckel som valts.

## Lägga till filtreringsregler i kampanjer {#section_D59AFB62E2EE423086281CF5D18B1076}

När du [skapar en befordran](/help/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14) väljer du **[!UICONTROL Promote by Attribute]** och klickar sedan på **[!UICONTROL Add Filtering Rule]**.

![](assets/inclusion_options.png)

## Filtertyper {#section_0125F1ED10A84C0EB45325122460EBCD}

I följande avsnitt visas olika filtreringsalternativ för [!UICONTROL Dynamic Filtering] och [!UICONTROL Filter by Value] för både villkor och kampanjer:

### Dynamisk filtrering

Dynamiska inkluderingsregler är kraftfullare än statiska inkluderingsregler och ger bättre resultat och engagemang. Tänk på följande:

* Dynamiska inkluderingsregler ger rekommendationer genom att matcha ett attribut i en användares profilparameter eller i ett mbox-anrop.

   Du kan t.ex. skapa en rekommendation för&quot;De mest populära villkoren&quot; och sedan filtrera bort alla rekommendationer (i realtid) mot ett attribut som skickas när användaren öppnar en sida där rekommendationerna visas.

* Använd statiska regler för att begränsa vilka objekt som ska tas med i rekommendationen (i stället för att använda samlingar).

* Du kan skapa så många dynamiska inkluderingsregler som behövs. Inkluderingsreglerna kopplas till en AND-operator. Alla regler måste uppfyllas för att ett objekt ska kunna inkluderas i en rekommendation.

Följande alternativ är tillgängliga för dynamisk filtrering:

| Alternativet för dynamisk filtrering | Detaljer |
| --- | --- |
| [Matchande entitetsattribut](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtrera dynamiskt genom att jämföra en pool med potentiella rekommendationsobjekt med ett specifikt objekt som användarna har interagerat med.<br>Använd  [!UICONTROL Entity Attribute Matching] när du vill visa rekommendationer som mest lockar besökaren, till exempel besökarens favoritvarumärke. |
| [Matchning av profilattribut](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i användarens profil.<br>Använd  [!UICONTROL Profile Attribute Matching] när du vill visa rekommendationer som matchar ett värde som lagras i besökarens profil, till exempel storlek eller favoritmärke. |
| [Parametermatchning](/help/c-recommendations/c-algorithms/parameter-matching.md) | Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).<br>Använd  [!UICONTROL Parameter Matching] för att rekommendera innehåll som matchar sidparametrarna eller besökarens parametrar, till exempel enhetsdimensioner eller geopositionering. |

### Filtrera efter värde

Följande alternativ är tillgängliga för filtrering efter värde:

| Filtrera efter värde, alternativ | Detaljer |
| --- | --- |
| [Statiskt filter](/help/c-recommendations/c-algorithms/static-value.md) | Ange manuellt ett eller flera statiska värden som ska filtreras. |

## Dynamiska kriterier och exempel på kampanjer

Dynamiska kriterier och kampanjer är mycket kraftfullare än statiska kriterier och kampanjer och ger bättre resultat och engagemang.

I följande exempel ges allmänna idéer om hur ni kan använda dynamiska kampanjer i era marknadsföringssatsningar:

| Operator | Exempel |
| --- | --- |
| Lika med | När en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film) kan du använda operatorn lika i dynamiska kampanjer för att marknadsföra andra objekt från:<ul><li>samma varumärke</li><li>samma kategori</li><li>samma kategori OCH från varumärket</li><li>samma butik</li></ul> |
| Är inte lika med | Om du använder operatorn&quot;inte jämför&quot; i dynamiska kampanjer kan du befordra andra saker när en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film):<ul><li>en annan TV-serie</li><li>en annan genre</li><li>en annan produktserie</li><li>ett annat format-ID</li></ul> |
| Är mellan | När en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film) kan du använda operatorn&quot;är mellan&quot; i dynamiska kampanjer för att marknadsföra andra element som är:<ul><li>mer kostsam</li><li>billigare</li><li>kostnad plus eller minus 30 %</li><li>senare avsnitt under samma säsong</li><li>tidigare böcker i en serie</li></ul> |

## Hantera tomma värden vid filtrering efter entitetsattributmatchning, matchning av profilattribut och parametermatchning {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Du kan välja flera alternativ för att hantera tomma värden när du filtrerar med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching] för avslutningskriterier och kampanjer.

Tidigare returnerades inga resultat om ett värde var tomt. I listrutan &quot;If *x* is Empty&quot; kan du välja vilken åtgärd som ska utföras om villkoret har tomma värden, vilket visas på följande bild:

![](assets/empty_value.png)

Om du vill välja önskad åtgärd håller du pekaren över kugghjulsikonen (![](assets/icon_gear.png)) och väljer önskad åtgärd:

| Åtgärd | Finns för | Detaljer |
|--- |--- |--- |
| [!UICONTROL Ignore this filtering rule] | [!UICONTROL Profile Attribute Matching] och[!UICONTROL Parameter Matching] | Det här är standardåtgärden för [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching].<br>Det här alternativet anger att regeln ignoreras. Om det till exempel finns tre filtreringsregler och den tredje regeln inte skickar några värden, i stället för att inte returnera några resultat, kan du helt enkelt ignorera den tredje regeln med de tomma värdena. |
| [!UICONTROL Do not show any results for this criteria]<br>(Endast villkor) | [!UICONTROL Entity Attribute Matching],  [!UICONTROL Profile Attribute Matching]och  [!UICONTROL Parameter Matching] | Detta är standardåtgärden för [!UICONTROL Entity Attribute Matching].<br>Detta gör att tomma värden  [!DNL Target] hanteras innan det här alternativet läggs till: inga resultat kommer att visas för dessa kriterier. |
| [!UICONTROL Do not promote any items<br>(Endast erbjudanden)] | [!UICONTROL Entity Attribute Matching],  [!UICONTROL Profile Attribute Matching]och  [!UICONTROL Parameter Matching] | Detta är standardåtgärden för [!UICONTROL Entity Attribute Matching].<br>Detta gör att tomma värden  [!DNL Target] hanteras innan det här alternativet läggs till: inga resultat kommer att visas för dessa kriterier. |
| [!UICONTROL Use a static value] | [!UICONTROL Entity Attribute Matching],  [!UICONTROL Profile Attribute Matching]och  [!UICONTROL Parameter Matching] | Om ett värde är tomt kan du välja att använda ett statiskt värde. |

## Caveats {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>Olika datatypsattribut kanske inte är kompatibla med operatorerna &quot;equals&quot; och &quot;does not equal&quot; under körning. Du bör använda värdena [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory] och [!UICONTROL Environment] till höger om den vänstra sidan har fördefinierade attribut eller anpassade attribut.

![](assets/left_right.png)

I följande tabell visas gällande regler och regler som kanske inte är kompatibla under körning:

| Kompatibla regler | Regler som kan vara inkompatibla |
|--- |--- |
| värde - är mellan - 90 % och 110 % av aktuell artikels - salesValue | salesValue - är mellan - 90 % och 110 % av aktuell artikels - värde |
| värde - är mellan - 90 % och 110 % av det aktuella objektets - värde | clearancePrice - är mellan - 90 % och 110 % av aktuell artikels - marginal |
| marginal - är mellan - 90 % och 110 % av aktuell artikels - marginal | storeInventory - lika med - aktuell artikel - lager |
| lager - är lika med - aktuell artikel - lager |  |
