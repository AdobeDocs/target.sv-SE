---
keywords: inkluderingsregler;inkluderingskriterier;rekommendationer;skapa nya kriterier;befordran;kampanjer;dynamisk filtrering;dynamiska;tomma värden;ignorera filtreringsregel;statiskt filter;filter efter värde;entitetsattributmatchning;profilattributmatchning;parametermatchning;filter efter värde;statiskt filter
description: Lär dig hur du skapar inkluderingsregler i Adobe [!DNL Target] Rekommendationer för villkor och kampanjer. För att få bättre resultat lägger du till mer dynamiska eller statiska filtreringsregler.
title: Hur använder jag regler för dynamisk och statisk inkludering i rekommendationerna?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '2013'
ht-degree: 0%

---

# Använd dynamiska och statiska inkluderingsregler

Information om hur du skapar inkluderingsregler för villkor och kampanjer i [!DNL Adobe Target] och lägger till dynamiska eller statiska filtreringsregler för att få bättre resultat för dina rekommendationer.

Processen för att skapa och använda inkluderingsregler för kriterier och kampanjer liknar den för användningsexempel och exempel. Både kriterier och kampanjer och användningen av inkluderingsregler omfattas av detta avsnitt.

## Lägga till filtreringsregler i villkor {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Klicka [&#x200B; under &#x200B;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE) när du **[!UICONTROL Add Filtering Rule]** skapar villkor **[!UICONTROL Inclusion Rules]**.

![include_options_new image](assets/inclusion_options_new.png)

Vilka alternativ som är tillgängliga varierar beroende på vilken bransch- och rekommendationsnyckel som valts.

## Lägga till filtreringsregler i kampanjer {#section_D59AFB62E2EE423086281CF5D18B1076}

När du [skapar en befordran](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14) väljer du **[!UICONTROL Promote by Attribute]** och klickar sedan på **[!UICONTROL Add Filtering Rule]**.

![include_options, bild](assets/inclusion_options.png)

## Filtertyper {#section_0125F1ED10A84C0EB45325122460EBCD}

I följande avsnitt visas olika filtreringsalternativ för [!UICONTROL Dynamic Filtering] och [!UICONTROL Filter by Value] för både villkor och kampanjer:

### Dynamisk filtrering

Dynamiska inkluderingsregler är kraftfullare än statiska inkluderingsregler och ger bättre resultat och engagemang. Tänk på följande:

* Dynamiska inkluderingsregler ger rekommendationer genom att matcha ett attribut i en användares profilparameter eller i ett mbox-anrop.

  Du kan t.ex. skapa en&quot;De mest populära villkoren&quot;-rekommendation. Från de returnerade rekommendationerna kan du filtrera bort alla rekommendationer (i realtid) mot ett attribut som skickas när användaren öppnar en sida där rekommendationerna visas.

* Använd statiska regler för att begränsa vilka objekt som ska tas med i rekommendationen (i stället för att använda samlingar).

* Du kan skapa så många dynamiska inkluderingsregler som behövs. Inkluderingsreglerna kopplas till en AND-operator. Alla regler måste uppfyllas för att ett objekt ska kunna inkluderas i en rekommendation.

Följande alternativ är tillgängliga för dynamisk filtrering:

| Alternativet för dynamisk filtrering | Information |
| --- | --- |
| [Matchande entitetsattribut](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtrera dynamiskt genom att jämföra en pool med potentiella rekommendationsobjekt med ett specifikt objekt som användarna har interagerat med.<br>Använd [!UICONTROL Entity Attribute Matching] när du vill visa rekommendationer som mest lockar besökaren, till exempel besökarens favoritvarumärke. |
| [Matchning av profilattribut](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i användarens profil.<br>Använd [!UICONTROL Profile Attribute Matching] när du vill visa rekommendationer som matchar ett värde som lagras i besökarens profil, till exempel storlek eller favoritmärke. |
| [Parametermatchning](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).<br>Använd [!UICONTROL Parameter Matching] för att rekommendera innehåll som matchar sidparametrarna eller besökarens parametrar, till exempel enhetsdimensioner eller geopositionering. |

### Filtrera efter värde

Följande alternativ är tillgängliga för filtrering efter värde:

| Filtrera efter värde, alternativ | Information |
| --- | --- |
| [Statiskt filter](/help/main/c-recommendations/c-algorithms/static-value.md) | Ange manuellt ett eller flera statiska värden som ska filtreras. |

## Tillgängliga operatorer {#operators}

Dynamiska kriterier och kampanjer är mycket kraftfullare än statiska kriterier och kampanjer och ger bättre resultat och engagemang.

I följande exempel ges allmänna idéer om hur ni kan använda dynamiska kampanjer och undantag i era marknadsföringssatsningar:

| Operator | Exempel |
| --- | --- |
| Lika med <br> (tillgängligt med entitetsattributmatchning, matchning av profilattribut, parametermatchning och statiskt filter.) | När en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film) kan du använda operatorn lika i dynamiska kampanjer för att marknadsföra andra element från:<ul><li>Samma varumärke</li><li>Samma kategori</li><li>Samma kategori OCH från varumärket</li><li>Samma butik</li></ul> |
| Inte lika med <br> (tillgängligt med entitetsattributmatchning, matchning av profilattribut, parametermatchning och statiskt filter.) | Om du använder operatorn&quot;inte jämför&quot; i dynamiska kampanjer kan du befordra andra saker när en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film):<ul><li>En annan TV-serie</li><li>En annan genre</li><li>En annan produktserie</li><li>Ett annat format-ID</li></ul> |
| Innehåller inte delsträngen <br> (tillgänglig med entitetsattributmatchning, matchning av profilattribut, parametermatchning och statiskt filter.) | När en besökare visar ett objekt på webbplatsen (till exempel en produkt) kan du använda operatorn&quot;innehåller inte delsträng&quot; för att marknadsföra andra element som:<ul><li>Titeln innehåller inte ett svingord</li></ul> |
| Börjar med <br> (tillgängligt med entitetsattributmatchning, matchning av profilattribut, parametermatchning och statiskt filter.) | När en besökare visar ett objekt på webbplatsen (till exempel en produkt) kan du använda operatorn&quot;börjar med&quot; för att marknadsföra andra saker som:<ul><li>Produktnamnet börjar med iPhone</li></ul> |
| Slutar med <br> (tillgängligt med matchning av enhetsattribut, matchning av profilattribut, matchning av parametrar och statiskt filter.) | När en besökare visar ett objekt på webbplatsen (till exempel en produkt) kan du använda operatorn&quot;slutar med&quot; för att marknadsföra andra saker som:<ul><li>Innehållet slutar med EN, som anger engelska</li></ul> |
| Är större än eller lika med <br> (tillgängligt med entitetsattributmatchning, matchning av profilattribut, parametermatchning och statiskt filter.) | När en besökare visar ett objekt på din webbplats (till exempel en produkt) kan du använda operatorn&quot;är större än eller lika med&quot; för att marknadsföra andra element som:<ul><li>Samma kostnad eller dyrare</li></ul> |
| Är mindre än eller lika med <br> (tillgängligt med entitetsattributmatchning, matchning av profilattribut, parametermatchning och statiskt filter.) | När en besökare visar ett objekt på din webbplats (till exempel en produkt) kan du använda operatorn&quot;är mindre än eller lika med&quot; för att marknadsföra andra element som:<ul><li>Samma kostnad eller billigare</li><li>Exkludera objekt som är billigare</li></ul> |
| Är mellan <br> (tillgängligt med matchning av enhetsattribut, matchning av profilattribut och parametermatchning.) | När en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film) kan du använda operatorn&quot;är mellan&quot; i dynamiska kampanjer för att marknadsföra andra element som är:<ul><li>Mer kostsam</li><li>Mindre kostsam</li><li>Kostnad plus eller minus 30 %</li><li>Senare avsnitt under samma säsong</li><li>Tidigare böcker i en serie</li></ul> |
| Finns i listan <br> (tillgänglig med matchning av profilattribut och parametermatchning.) | När en besökare visar ett objekt på webbplatsen (till exempel en produkt, artikel eller film) kan du använda operatorn&quot;finns i listan&quot; för profilattributsmatchning för att befordra andra element som:<ul><li>Tillgängligt i besökarens geografi</li></ul>**Exempel**: Du vill bara rekommendera objekt som är tillgängliga i en besökares geografiska område.<br>Filterregeln kan se ut så här:<br>`availableGeographies list contains an item in user.currentGeography`<br>**Obs!** När du använder den här operatorn förväntas en lista på regelns [högra sida](#caveats). |
| Finns inte i listan <br> (tillgänglig med matchning av profilattribut och parametermatchning.) | Om du använder operatorn&quot;finns inte i listan&quot; för att matcha profilattribut kan du utesluta andra objekt som är:<ul><li>I listan med de tio senaste objekten som besökaren har visat</li></ul></ul>**Exempel**: Du vill inte befordra element som besökaren nyligen har visat och inte visat något intresse för.<br>Din filtreringsregel kan se ut så här:<br>`id is not contained in list user.lastViewedItems`<br>**Obs!** När du använder den här operatorn förväntas en lista på regelns [högra sida](#caveats). |
| Listan innehåller ett objekt i <br> (tillgängligt med entitetsattributmatchning, matchning av profilattribut och parametermatchning.) | Om du använder operatorn&quot;list contains an item in&quot; i profilattributsmatchningen kan du befordra andra element som är:<ul><li>Associerad med en av besökarens favoritteam</li></ul>**Exempel**: Du vill rekommendera spel som är associerade med en av besökarens favoritteam.<br>Din filtreringsregel kan se ut så här:<br>` teamsPlaying list contains an item in user.favoriteTeams`<br>**Obs!** När du använder den här operatorn förväntas en lista på [båda sidor](#caveats) av regeln. |
| Listan innehåller inte något objekt i <br> (tillgängligt med entitetsattributmatchning, matchning av profilattribut och parametermatchning.) | Om du använder operatorn&quot;list does not contain an item in&quot; i parameterattributmatchning kan du utesluta andra objekt som är:<ul><li>Finns i en lista över förbjudna typer</li></ul>**Exempel**: Du vill utesluta objekt som är tillgängliga för besökare som är vuxna, till exempel tobak och alkohol.<br>Din filtreringsregel kan se ut så här:<br>`itemType is not contained in list mbox.prohibitedTypes`<br>**Obs!** När du använder den här operatorn förväntas en lista på [båda sidor](#caveats) av regeln. |
| Listan innehåller alla objekt i <br> (tillgänglig med entitetsattributmatchning, matchning av profilattribut och parametermatchning.) | Om du använder operatorn&quot;list contains all items in&quot; i profilattributsmatchning kan du befordra andra element som:<ul><li>Inkludera en uppsättning färdigheter</li><li>Inkludera en uppsättning obligatoriska ingredienser</li></ul>**Exempel 1**: Anta att en besökare har en uppsättning kunskaper (Java, C++ och HTML). Objekten i katalogen är jobb med nödvändiga kunskaper (Java och HTML). Du vill se till att besökarprofilen innehåller alla nödvändiga kunskaper innan du rekommenderar jobbet till besökaren.<br>Din filtreringsregel kan se ut så här:<br>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<br>**Exempel 2**: Anta att en användare har en lista med panelingredienser. Mottagaren har en lista över obligatoriska ingredienser. Du måste se till att besökarens profil innehåller alla nödvändiga ingredienser innan du rekommenderar receptet till besökaren.<br>Din filtreringsregel kan se ut så här:<br>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<br>**Obs!** När du använder den här operatorn förväntas en lista på [båda sidor](#caveats) av regeln. |
| Listan innehåller inte alla objekt i <br> (tillgänglig med entitetsattributmatchning, matchning av profilattribut och parametermatchning.) | Om du använder operatorn&quot;list does not contain all items in&quot; i entitetsattributmatchningen kan du befordra andra element som:<ul><li>Inkludera inte en uppsättning team</li></ul>**Exempel**: Anta att ett idrottsevenemang innehåller två team. Besökarens profil anger att besökaren inte vill visa spel för dessa team. Du bör se till att du inte rekommenderar ett spel om dessa team spelar.<br>Din filtreringsregel kan se ut så här:<br>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<br>**Obs!** När du använder den här operatorn förväntas en lista på [båda sidor](#caveats) av regeln. |

## Hantera tomma värden vid filtrering efter entitetsattributmatchning, matchning av profilattribut och parametermatchning {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Du kan välja flera alternativ för att hantera tomma värden när du filtrerar efter [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching] för avslutningskriterier och kampanjer.

Tidigare returnerades inga resultat om ett värde var tomt. Med listrutan Om *x* är tom kan du välja vilken åtgärd som ska utföras om villkoret har tomma värden, vilket visas på följande bild:

![empty_value image](assets/empty_value.png)

Om du vill välja önskad åtgärd håller du pekaren över kugghjulsikonen (![icon_istället-bilden](assets/icon_gear.png)) och väljer önskad åtgärd:

| Åtgärd | Finns för | Information |
|--- |--- |--- |
| [!UICONTROL Ignore this filtering rule] | [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching] | Den här åtgärden är standard för [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching].<br>Det här alternativet anger att regeln ignoreras. Om det till exempel finns tre filtreringsregler och den tredje regeln inte skickar några värden, i stället för att inte returnera några resultat, kan du helt enkelt ignorera den tredje regeln med de tomma värdena. |
| [!UICONTROL Do not show any results for this criteria]<br>(Endast villkor) | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching] | Den här åtgärden är standard för [!UICONTROL Entity Attribute Matching].<br>Den här åtgärden är hur [!DNL Target] hanterade tomma värden innan det här alternativet lades till: inga resultat visas för det här villkoret. |
| [!UICONTROL Do not promote any items<br>(Endast erbjudanden)] | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching] | Den här åtgärden är standard för [!UICONTROL Entity Attribute Matching].<br>Den här åtgärden är hur [!DNL Target] hanterade tomma värden innan det här alternativet lades till: inga resultat visas för det här villkoret. |
| [!UICONTROL Use a static value] | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching] | Om ett värde är tomt kan du välja att använda ett statiskt värde. |

## Caveats {#caveats}

>[!IMPORTANT]
>
>Olika datatypsattribut kanske inte är kompatibla med operatorerna &quot;equals&quot; och &quot;does not equal&quot; under körning. Använd värdena [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory] och [!UICONTROL Environment] klokt till höger om den vänstra sidan har fördefinierade attribut eller anpassade attribut.

![left_right image](assets/left_right.png)

I följande tabell visas gällande regler och regler som kanske inte är kompatibla under körning:

| Kompatibla regler | Regler som kan vara inkompatibla |
|--- |--- |
| värde - är mellan - 90 % och 110 % av aktuell artikels - salesValue | salesValue - är mellan - 90 % och 110 % av aktuell artikels - värde |
| värde - är mellan - 90 % och 110 % av det aktuella objektets - värde | clearancePrice - är mellan - 90 % och 110 % av aktuell artikels - marginal |
| marginal - är mellan - 90 % och 110 % av aktuell artikels - marginal | storeInventory - lika med - aktuell artikel - lager |
| lager - är lika med - aktuell artikel - lager |  |
