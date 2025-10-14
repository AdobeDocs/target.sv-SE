---
keywords: inkluderingsregler;inkluderingskriterier;rekommendationer;skapa nya kriterier;befordran;kampanjer;dynamisk filtrering;dynamiska;tomma värden;ignorera filtreringsregel;statiskt filter;filter efter värde;entitetsattributmatchning;profilattributmatchning;parametermatchning;filter efter värde;statiskt filter
description: Lär dig hur du skapar inkluderingsregler i  [!DNL Target] Rekommendationer för villkor och kampanjer.
title: Hur använder jag regler för dynamisk och statisk inkludering i rekommendationerna?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
source-git-commit: 51e484d54f4d318ea59fdfdb16d1ed7014abdfdb
workflow-type: tm+mt
source-wordcount: '1846'
ht-degree: 0%

---

# Använd dynamiska och statiska inkluderingsregler

Skapa inkluderingsregler för villkor och kampanjer i [!DNL Adobe Target] och lägg till dynamiska eller statiska filtreringsregler för att få bättre resultat för dina rekommendationer.

Processen för att skapa och använda inkluderingsregler för kriterier och kampanjer liknar den för användningsexempel och exempel. Både kriterier och kampanjer och användningen av inkluderingsregler omfattas av detta avsnitt.

## Lägg till filtreringsregler i villkor och kampanjer {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Följande avsnitt innehåller mer information:

### Lägg till filtreringsregler i villkor

1. Klicka [&#x200B; under &#x200B;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE) när **[!UICONTROL Recommendations]skapar villkor[!UICONTROL Criteria] ([!UICONTROL Create Criteria] >[!UICONTROL Create Criteria]** > **[!UICONTROL Add Filtering Rule]** > **[!UICONTROL Inclusion Rules]**).

   ![Lägg till filtreringsregel](/help/main/c-recommendations/c-algorithms/assets/add-fitering-rule.png)

1. Klicka på listrutan **Statiskt filter** i rutan &quot;Vilka andra regler bör rekommendationen följa&quot; och välj sedan önskat alternativ i listrutan [!UICONTROL Static Filter] .

   ![Listrutan Statiskt filter](/help/main/c-recommendations/c-algorithms/assets/dynamic-and-static.png)

   Vilka alternativ som är tillgängliga varierar beroende på vilken bransch- och rekommendationsnyckel som valts.

### Lägg till filtreringsregler i kampanjer

1. När du [skapar en befordran](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14) väljer du **[!UICONTROL Promote by Attribute]** och klickar sedan på **[!UICONTROL Add Filtering Rule]**.

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
| [[!UICONTROL Entity Attribute Matching]](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtrera dynamiskt genom att jämföra en pool med potentiella rekommendationsobjekt med ett specifikt objekt som användarna har interagerat med.<P>Använd [!UICONTROL Entity Attribute Matching] när du vill visa rekommendationer som mest troligt tilltalar besökaren, till exempel besökarens favoritvarumärke. |
| [[!UICONTROL Profile Attribute Matching]](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i användarens profil.<P>Använd [!UICONTROL Profile Attribute Matching] när du vill visa rekommendationer som matchar ett värde som lagras i besökarens profil, till exempel storlek eller favoritmärke. |
| [[!UICONTROL Parameter Matching]](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).<P>Använd [!UICONTROL Parameter Matching] för att rekommendera innehåll som matchar sidparametrarna eller besökarens parametrar, till exempel enhetsdimensioner eller geopositionering. |

### Filtrera efter värde

Följande alternativ är tillgängliga för filtrering efter värde:

| Filtrera efter värde, alternativ | Information |
| --- | --- |
| [[!UICONTROL Static Filter]](/help/main/c-recommendations/c-algorithms/static-value.md) | Ange manuellt ett eller flera statiska värden som ska filtreras. |

## Tillgängliga operatorer {#operators}

Dynamiska kriterier och kampanjer är mycket kraftfullare än statiska kriterier och kampanjer och ger bättre resultat och engagemang.

I följande exempel ges allmänna idéer om hur ni kan använda dynamiska kampanjer och undantag i era marknadsföringssatsningar:

>[!NOTE]
>
>&quot;List&quot; kräver att både entiteter och profilattribut måste lagras som arrayer. En kommaavgränsad lista fungerar inte.

| Operator | Exempel |
| --- | --- |
| [!UICONTROL equals any of]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] och [!UICONTROL Static Filter].) | När en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film) kan du använda operatorn lika i dynamiska kampanjer för att marknadsföra andra element från:<ul><li>Samma varumärke</li><li>Samma kategori</li><li>Samma kategori OCH från varumärket</li><li>Samma butik</li></ul> |
| [!UICONTROL does not equal any of]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] och [!UICONTROL Static Filter].) | Om du använder operatorn [!UICONTROL does not equal any of] i dynamiska kampanjer och en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film) kan du befordra andra objekt från:<ul><li>En annan TV-serie</li><li>En annan genre</li><li>En annan produktserie</li><li>Ett annat format-ID</li></ul> |
| [!UICONTROL is greater than or equal to any of]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] och [!UICONTROL Static Filter].) | När en besökare visar ett objekt på webbplatsen (till exempel en produkt) med operatorn [!UICONTROL is greater than or equal to any of] kan du befordra andra element som:<ul><li>Samma kostnad eller dyrare</li></ul> |
| [!UICONTROL is less than or equal to any of]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] och [!UICONTROL Static Filter].) | När en besökare visar ett objekt på webbplatsen (till exempel en produkt) med operatorn [!UICONTROL is less than or equal to an of] kan du befordra andra element som:<ul><li>Samma kostnad eller billigare</li><li>Exkludera objekt som är billigare</li></ul> |
| [!UICONTROL contains any of] (Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] och [!UICONTROL Static Filter].) | När en besökare visar ett objekt på webbplatsen (till exempel en produkt) med operatorn [!UICONTROL contains any of] kan du befordra andra element som:<ul><li>Titeln innehåller samma varumärke</li></ul> |
| [!UICONTROL does not contain any of]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] och [!UICONTROL Static Filter].) | När en besökare visar ett objekt på din webbplats (till exempel en produkt) kan du använda operatorn&quot;innehåller inte någon av&quot; för att marknadsföra andra element som:<ul><li>Titeln innehåller inte ett svingord</li></ul> |
| [!UICONTROL starts with any of]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] och [!UICONTROL Static Filter].) | När en besökare visar ett objekt på webbplatsen (till exempel en produkt) med operatorn [!UICONTROL starts with an of] kan du befordra andra element som:<ul><li>Produktnamnet börjar med iPhone</li></ul> |
| [!UICONTROL ends with any of]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], [!UICONTROL Parameter Matching] och [!UICONTROL Static Filter].) | När en besökare visar ett objekt på webbplatsen (till exempel en produkt) med operatorn [!UICONTROL ends with an of] kan du befordra andra element som:<ul><li>Innehållet slutar med EN, som anger engelska</li></ul> |
| [!UICONTROL is between]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching].) | När en besökare visar ett objekt på webbplatsen (till exempel en produkt, artikel eller film) kan du använda operatorn&quot;i[!UICONTROL s between]&quot; i dynamiska kampanjer för att marknadsföra andra objekt som är:<ul><li>Mer kostsam</li><li>Mindre kostsam</li><li>Kostnad plus eller minus 30 %</li><li>Senare avsnitt under samma säsong</li><li>Tidigare böcker i en serie</li></ul> |
| [!UICONTROL list contains an item in]<P>(Tillgängligt med [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching].) | Om du använder operatorn [!UICONTROL list contains an item in] i profilattributsmatchning kan du befordra andra element som är:<ul><li>Tillgängligt i besökarens geografi</li></ul>**Exempel**: Du vill rekommendera objekt som bara är tillgängliga i en besökares geografiska område.<P>Filterregeln kan se ut så här:<P>`availableGeographies list contains an item in user.currentGeography`<P>**Obs!** När du använder den här operatorn förväntas en lista på regelns [högra sida](#caveats). |
| [!UICONTROL list does not contain an item in]<P>(Tillgängligt med [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching].) | Om du använder operatorn [!UICONTROL list does not contain an item in] i profilattributsmatchningen kan du utesluta andra objekt som är:<ul><li>I listan med de tio senaste objekten som besökaren har visat</li></ul></ul>**Exempel**: Du vill inte befordra element som besökaren nyligen har visat och inte visat något intresse för.<P>Filtreringsregeln kan se ut så här:<P>`id is not contained in list user.lastViewedItems`<P>**Obs!** När du använder den här operatorn förväntas en lista på regelns [högra sida](#caveats). |
| [!UICONTROL list contains an item in]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching].) | Om du använder operatorn [!UICONTROL list contains an item in] i profilattributsmatchning kan du befordra andra element som är:<ul><li>Associerad med en av besökarens favoritteam</li></ul>**Exempel**: Du vill rekommendera spel som är associerade med en av besökarens favoritteam.<P>Filtreringsregeln kan se ut så här:<P>` teamsPlaying list contains an item in user.favoriteTeams`<P>**Obs!** När du använder den här operatorn förväntas en lista i [båda sidor](#caveats) av regeln. |
| [!UICONTROL list does not contain an item in]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching].) | Om du använder operatorn [!UICONTROL list does not contain an item in] i parameterattributmatchning kan du utesluta andra objekt som är:<ul><li>Finns i en lista över förbjudna typer</li></ul>**Exempel**: Du vill utesluta objekt som är tillgängliga för besökare som är vuxna, till exempel tobak och alkohol.<P>Filtreringsregeln kan se ut så här:<P>`itemType is not contained in list mbox.prohibitedTypes`<P>**Obs!** När du använder den här operatorn förväntas en lista i [båda sidor](#caveats) av regeln. |
| [!UICONTROL list contains all items in]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching].) | Om du använder operatorn [!UICONTROL list does not contain an item in] i profilattributsmatchning kan du befordra andra element som:<ul><li>Inkludera en uppsättning färdigheter</li><li>Inkludera en uppsättning obligatoriska ingredienser</li></ul>**Exempel 1**: Anta att en besökare har en uppsättning kunskaper (Java, C++ och HTML). Objekten i katalogen är jobb med nödvändiga kunskaper (Java och HTML). Du vill se till att besökarprofilen innehåller alla nödvändiga kunskaper innan du rekommenderar jobbet till besökaren.<P>Filtreringsregeln kan se ut så här:<P>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<P>**Exempel 2**: Anta att en användare har en lista med panelingredienser. Mottagaren har en lista över obligatoriska ingredienser. Du måste se till att besökarens profil innehåller alla nödvändiga ingredienser innan du rekommenderar receptet till besökaren.<P>Filtreringsregeln kan se ut så här:<P>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<P>**Obs!** När du använder den här operatorn förväntas en lista i [båda sidor](#caveats) av regeln. |
| [!UICONTROL list does not contain all items in]<P>(Tillgängligt med [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching].) | Om du använder operatorn [!UICONTROL list does not contain all items in] i entitetsattributmatchningen kan du befordra andra element som:<ul><li>Inkludera inte en uppsättning team</li></ul>**Exempel**: Anta att ett idrottsevenemang innehåller två team. Besökarens profil anger att besökaren inte vill visa spel för dessa team. Du bör se till att du inte rekommenderar ett spel om dessa team spelar.<P>Filtreringsregeln kan se ut så här:<P>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<P>**Obs!** När du använder den här operatorn förväntas en lista i [båda sidor](#caveats) av regeln. |

## Hantera tomma värden vid filtrering av [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching] {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Du kan välja flera alternativ för att hantera tomma värden när du filtrerar efter [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching] för avslutningskriterier och kampanjer.

Tidigare returnerades inga resultat om ett värde var tomt. Med listrutan Om *x* är tom kan du välja vilken åtgärd som ska utföras om villkoret har tomma värden, vilket visas på följande bild:

![empty_value image](assets/empty_value.png)

Om du vill välja önskad åtgärd håller du pekaren över kugghjulsikonen (![icon_istället-bilden](assets/icon_gear.png)) och väljer önskad åtgärd:

| Åtgärd | Finns för | Information |
|--- |--- |--- |
| [!UICONTROL Ignore this filtering rule] | [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching] | Den här åtgärden är standard för [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching].<P>Det här alternativet anger att regeln ignoreras. Om det till exempel finns tre filtreringsregler och den tredje regeln inte skickar några värden, i stället för att inte returnera några resultat, kan du helt enkelt ignorera den tredje regeln med de tomma värdena. |
| [!UICONTROL Do not show any results for this criteria]<P>(Endast villkor) | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching] | Den här åtgärden är standard för [!UICONTROL Entity Attribute Matching].<P>Den här åtgärden är hur [!DNL Target] hanterade tomma värden innan det här alternativet lades till: inga resultat visas för det här villkoret. |
| [!UICONTROL Befordra inga objekt<P>(Endast erbjudanden)] | [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching] och [!UICONTROL Parameter Matching] | Den här åtgärden är standard för [!UICONTROL Entity Attribute Matching].<P>Den här åtgärden är hur [!DNL Target] hanterade tomma värden innan det här alternativet lades till: inga resultat visas för det här villkoret. |
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
