---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: Information om hur du skapar inkluderingsregler i Adobe Target Recommendations för villkor och kampanjer och lägger till ytterligare dynamiska eller statiska filtreringsregler för att få bättre resultat.
title: Använd dynamiska och statiska inkluderingsregler i Adobe Target Recommendations
uuid: f0ee2086-1126-44a4-9379-aa897dc0e06b
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) Använd dynamiska och statiska inkluderingsregler{#use-dynamic-and-static-inclusion-rules}

Information om hur du skapar inkluderingsregler för villkor och kampanjer och lägger till ytterligare dynamiska eller statiska filtreringsregler för att få bättre resultat.

Processen för att skapa och använda inkluderingsregler för kriterier och kampanjer liknar den för användningsexempel och exempel. Både kriterier och kampanjer och användningen av inkluderingsregler omfattas av detta ämne.

## Lägga till filtreringsregler i villkor {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

När du [skapar villkor](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE)klickar du **[!UICONTROL Add Filtering Rule]** under **[!UICONTROL Inclusion Rules]**.

![](assets/inclusion_options.png)

Vilka alternativ som är tillgängliga varierar beroende på vilken bransch- och rekommendationsnyckel som valts.

## Lägga till filtreringsregler i kampanjer {#section_D59AFB62E2EE423086281CF5D18B1076}

När du [skapar en befordran](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14)väljer du **[!UICONTROL Promote by Attribute]** och klickar sedan på **[!UICONTROL Add Filtering Rule]**.

![](assets/inclusion_options_promotion.png)

## Filtertyper {#section_0125F1ED10A84C0EB45325122460EBCD}

I följande tabell visas olika filtreringsalternativ för både villkor och kampanjer:

| Typ | Alternativ | Tillgängliga operatorer |
|--- |--- |--- |
| **Dynamisk filtrering** | **Matchning av enhetsattribut:** Filtrera dynamiskt genom att jämföra en pool med potentiella rekommendationsobjekt med ett specifikt objekt som användarna har interagerat med.<br>Rekommendera t.ex. endast objekt som matchar det aktuella objektets varumärke. | är<br>lika med inte<br>lika med<br><br>mellan behållare,<br>innehåller inte<br>avslutningar<br>med värdet<br>presenterar värdet inte<br>som är större än eller lika<br>med mindre än eller lika med |
|  | **Matchning av profilattribut:** Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i användarens profil.<br>Rekommendera t.ex. endast objekt som matchar besökarens favoritvarumärke. | är lika med<br> inte<br><br>lika med, innehåller inte<br>innehåll<br>som<br>är större än eller lika med<br>tois mindre än eller lika med<br>tois mellan |
|  | **Parametermatchning:** Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).<br>Rekommendera t.ex. endast innehåll som matchar sidparametern&quot;branschsida&quot;.<br>**Viktigt:**Om aktiviteten skapades före 31 oktober 2016 misslyckas leveransen om det använder filtret Parametermatchning. Så här undviker du problemet:<ul><li>Skapa en ny aktivitet och lägg till dina villkor i den.</li><li>Använd ett villkor som inte innehåller filtret Parametermatchning.</li><li>Ta bort filtret &quot;Parametermatchning&quot; från villkoren.</li></ul> | är<br>lika med inte<br><br>lika med-behållare<br>innehåller inte<br>sammandragningar<br>med värdet större än eller lika med<br>för mindre än eller lika med<br>foton mellan |
| **Filtrera efter värde** | **Statiskt filter:** Ange manuellt ett eller flera statiska värden som ska filtreras.<br>Rekommendera t.ex. endast innehåll med MPAA-klassificeringen &quot;G&quot; eller &quot;PG&quot;. | är<br>lika med inte<br><br>lika med-behållare,<br>innehåller inte<br>avslutningar<br>med värdet är<br>presentationsvärdet inte<br>större än eller lika med<br>foton mindre än eller lika med |

>[!NOTE]
>
>Om du känner till hur inkluderingsregler konfigurerades före Target 17.6.1-versionen (juni 2017) kommer du att märka att vissa alternativ och operatorer har ändrats. Endast de operatorer som kan användas för den valda alternativvisningen och vissa operatorer har bytt namn (&quot;match&quot; är nu lika med) för att vara mer konsekventa och intuitiva. Alla befintliga undantagsregler som skapades före den här versionen migrerades automatiskt till den nya strukturen. Ni behöver inte göra någon omstrukturering.

Du kan skapa så många inkluderingsregler som behövs. Inkluderingsreglerna kopplas till en AND-operator. Alla regler måste uppfyllas för att ett objekt ska kunna inkluderas i en rekommendation.

Dynamiska kriterier och kampanjer är mycket kraftfullare än statiska kriterier och kampanjer, och ger bättre resultat och engagemang. I följande exempel får du idéer om hur du kan använda dynamiska kampanjer i dina marknadsföringssatsningar:

**Lika med:** När en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film) kan du använda operatorn lika i dynamiska kampanjer för att marknadsföra andra objekt från:

* samma varumärke
* samma kategori
* samma kategori OCH från varumärket
* samma butik

**Är inte lika med:** Om du använder operatorn&quot;inte jämför&quot; i dynamiska kampanjer kan du befordra andra saker när en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film):

* en annan TV-serie
* en annan genre
* en annan produktserie
* ett annat format-ID

**Är mellan:** När en besökare visar ett objekt på din webbplats (till exempel en produkt, artikel eller film) kan du använda operatorn&quot;är mellan&quot; i dynamiska kampanjer för att marknadsföra andra element som är:

* mer kostsam
* billigare
* kostnad plus eller minus 30 %
* senare avsnitt under samma säsong
* tidigare böcker i en serie

## Hantera tomma värden vid filtrering efter entitetsattributmatchning, matchning av profilattribut och parametermatchning {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Du kan välja flera alternativ för att hantera tomma värden när du filtrerar efter entitetsattributmatchning, Matchning av profilattribut och Parametermatchning för avslutningskriterier och kampanjer.

Tidigare returnerades inga resultat om ett värde var tomt. Med listrutan&quot;Om *x* är tom&quot; kan du välja vilken åtgärd som ska utföras om villkoret har tomma värden, vilket visas på följande bild:

![](assets/empty_value.png)

Om du vill välja önskad åtgärd håller du pekaren över kugghjulsikonen (![](assets/icon_gear.png)) och väljer önskad åtgärd:

| Åtgärd | Finns för | Detaljer |
|--- |--- |--- |
| Ignorera den här filtreringsregeln | Matchning<br>av profilattribut för MatchingParameter | Detta är standardåtgärden för Matchning av profilattribut och Parametermatchning.<br>Det här alternativet anger att regeln ignoreras. Om det till exempel finns tre filtreringsregler och den tredje regeln inte skickar några värden, i stället för att inte returnera några resultat, kan du helt enkelt ignorera den tredje regeln med de tomma värdena. |
| Visa inga resultat för det här villkoret | Matchning av<br>matchningsprofilattribut<br>för entitetsattribut | Det här är standardåtgärden för entitetsattributmatchning.<br>Den här åtgärden är hur Target hanterade tomma värden innan det här alternativet lades till: inga resultat kommer att visas för dessa kriterier. |
| Använd ett statiskt värde | Matchning av<br>matchningsprofilattribut<br>för entitetsattribut | Om ett värde är tomt kan du välja att använda ett statiskt värde. |

## Exempel på matchning av profilattribut {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Profile Attribute Matching] I kan du bara rekommendera de objekt som matchar ett attribut från besökarens profil, som i exemplen nedan.

**Exempel 1: Rekommendera objekt från användarens favoritvarumärke** Du kan till exempel använda alternativet [!UICONTROL Profile Attribute Matching] för att skapa en regel som bara rekommenderar objekt där varumärket är lika med värdet eller texten som lagras i `profile.favoritebrand`. Om en besökare tittar på kortkommandon från ett visst varumärke är det bara rekommendationer som motsvarar användarens favoritvarumärke (värdet som lagras i `profile.favoritebrand` besökarens profil) som visas.

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

**Exempel 2: Matchande jobb till arbetssökande** Anta att du försöker matcha jobb till arbetssökande. Du vill bara rekommendera jobb som finns i samma stad som jobbsökaren.

Du kan använda inkluderingsregler för att matcha en jobbsökares plats från besökarens profil till en jobblista, som i följande exempel:

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

## Exempel på matchning av enhetsattribut

[!UICONTROL Entity Attribute Matching] I kan du endast rekommendera de objekt som matchar ett attribut från det objekt som användaren för närvarande visar, det objekt som användaren senast visade, det objekt som användaren senast köpte, det objekt som användaren oftast visade eller från ett objekt som sparats i ett anpassat attribut i besökarens profil, som i exemplen nedan.

**Exempel 3: Merförsäljning till en dyrare produkt** Anta att du är en klädhandlare och vill uppmuntra användarna att överväga högre priser och därmed mer lönsamma artiklar. Du kan använda operatorerna &quot;equals&quot; och &quot;is between&quot; för att marknadsföra dyrare objekt från samma kategori och samma varumärke. En besökare som ser ett löpande företag kan till exempel marknadsföra dyrare skor i ett försök att sälja in en besökare som tittar på skor.

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

**Exempel 4: Sälja privata etikettprodukter** Du kan blanda dynamiska och statiska filter för att marknadsföra privata etikettprodukter. Ett kontorsföretag kan till exempel marknadsföra tonerkassetter för företagets varumärke för att få en mer lönsam försäljning för en besökare som tittar på toner - och marknadsföra pennor från företagets varumärke för att få en mer lönsam försäljning för en besökare som tittar på pennor.

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
>Olika datatypsattribut kanske inte är kompatibla med operatorerna &quot;equals&quot; och &quot;does not equal&quot; under körning. Du bör använda värdena Värde, Marginal, Lager och Miljö till höger om den vänstra sidan har fördefinierade attribut eller anpassade attribut.

![](assets/left_right.png)

I följande tabell visas gällande regler och regler som kanske inte är kompatibla under körning:

| Kompatibla regler | Regler som kan vara inkompatibla |
|--- |--- |
| värde - är mellan - 90 % och 110 % av aktuell artikels - salesValue | salesValue - är mellan - 90 % och 110 % av aktuell artikels - värde |
| värde - är mellan - 90 % och 110 % av det aktuella objektets - värde | clearancePrice - är mellan - 90 % och 110 % av aktuell artikels - marginal |
| marginal - är mellan - 90 % och 110 % av aktuell artikels - marginal | storeInventory - lika med - aktuell artikel - lager |
| lager - är lika med - aktuell artikel - lager |  |
