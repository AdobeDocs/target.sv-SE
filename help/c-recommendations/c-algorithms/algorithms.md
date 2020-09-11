---
keywords: recommendations;recommendations activity;criteria;algorithm;recommendation key;custom key;industry vertical;retail;eccommerce;lead generation;b2b;financial services;media;publishing
description: Kriterierna i Adobe Target är regler som avgör vilka produkter eller vilket innehåll som ska rekommenderas baserat på en fördefinierad uppsättning besökarbeteenden.
title: Kriterier i Adobe Target Recommendations
feature: criteria
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
translation-type: tm+mt
source-git-commit: d276693eeab095b7f2f5fad293a03ab10eb1faf6
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) -kriterier

Kriterier i [!DNL Adobe Target] är regler som bestämmer vilka produkter eller innehåll som ska rekommenderas baserat på en fördefinierad uppsättning besökarbeteenden. Kriterierna kan baseras på populära trender, en besökares aktuella och tidigare beteenden eller liknande produkter och innehåll. Du kan testa flera rekommendationstyper mot varandra genom att lägga till flera villkor.

I följande avsnitt beskrivs mer om villkorsnycklar och den rekommendationslogik du kan använda för varje nyckel. Klicka på länkarna för mer detaljerad information.

## Branschvertikal {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

När du skapar villkor väljer du en bransch vertikalt baserad på syftet med dina rekommendationer.

| Branschvertikal | Mål |
|--- |--- |
| Detaljhandel/e-handel | Konvertering som resulterar i inköp |
| Leadgenerering/B2B/Finansiella tjänster | Konvertering utan köp |
| Media/publicering | Engagemang |

Andra kriteriealternativ ändras beroende på vilken vertikal du väljer i branschen. Du kan ställa in branschstandarden vertikalt på **[!UICONTROL Recommendations > Settings]** sidan eller ange branschvertikalt för varje villkor.

## Rekommendationsnyckel {#section_885B3BB1B43048A88A8926F6B76FC482}

Den rekommendationsnyckel du väljer avgör typen av villkor. Det finns flera kriterietyper som visas som kriteriekort när du ställer in en [!DNL Recommendations] aktivitet.

![Kriteriesida](/help/c-recommendations/c-algorithms/assets/criteria-page.png)

I följande tabell förklaras de olika kriterietyperna och tillhörande nycklar. Klicka på länkarna för mer detaljerad information om varje tangent.

| Villkorstyp | Tangenter |
|--- |--- |
| Aktuell sidaktivitet | Rekommendera objekt baserat på vad användarna gör på den aktuella sidan. Besökare som visar en viss artikel kanske vill se andra artiklar i samma kategori.<ul><li>[Aktuellt objekt](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-item)</li><li>[Aktuell kategori](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-category)</li></ul> |
| Egen | Rekommendera objekt baserat på anpassade attribut.<ul><li>[Anpassat attribut](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#custom)</li></ul>När du baserar rekommendationer på anpassade attribut måste du välja det anpassade attributet och sedan välja rekommendationstypen. |
| Tidigare beteende | Rekommendera objekt baserat på hur besökarna tidigare har svarat på ett objekt. Exempelvis har de som köpt ett visst varumärke större chans att köpa ett annat varumärke.<ul><li>[Senast köpta artikel](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-purchased)</li><li>[Senast visade objekt](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-viewed)</li><li>[Mest visade objekt](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed-logic)</li><li>[Favoritkategori](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#favorite-category)</li></ul> |
| Popularitet | Rekommendera de populäraste objekten, till exempel de populäraste videoklippen i en relaterad kategori eller de produkter som har visats oftast på din webbplats.<ul><li>[Popularitet](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#popularity)</li></ul> |
| [Senast visade objekt](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#recently-viewed) | Rekommendera objekt som en besökare har visat senast, t.ex. de objekt en besökare tittade på när han eller hon senast besökte din webbplats, eller de artiklar som är mest aktuella just nu. |

## Använda en anpassad rekommendationsnyckel {#custom-key}

Du kan också basera rekommendationer på värdet för ett anpassat profilattribut.

>[!NOTE]
>
>Egna profilparametrar kan skickas till Target via JavaScript, API eller integreringar. Mer information om anpassade profilattribut finns i [Besökarprofiler](/help/c-target/c-visitor-profile/visitor-profile.md).

Anta till exempel att du vill visa rekommenderade filmer baserat på den film som en användare senast lade till i kön.

1. Välj ditt anpassade profilattribut i [!UICONTROL Recommendation Key] listrutan (till exempel [!UICONTROL Last Show Added to Watchlist]).

1. Välj [!UICONTROL Recommendation Logic] (till exempel [!UICONTROL People Who Viewed This, Viewed That]).

   ![Dialogrutan Skapa nya villkor](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

Om ditt anpassade profilattribut inte direkt matchar ett enda enhets-ID måste du förklara [!DNL Recommendations] hur du vill att matchningen till en entitet ska ske.

Anta till exempel att du vill visa de mest säljande artiklarna från en användares favoritvarumärke.

1. Välj ditt anpassade profilattribut i [!UICONTROL Recommendation Key] listrutan (till exempel [!UICONTROL Favorite Brand]).

1. Markera den [!UICONTROL Recommendation Logic] som du vill använda med den här tangenten (till exempel [!UICONTROL Top Sellers]).

   Alternativet [!UICONTROL Group By Unique Value Of] visas.

1. Välj det entitetsattribut som matchar nyckeln som du har valt. I det här fallet [!UICONTROL Favorite Brand] matchar `entity.brand`.

   [!DNL Recommendations] skapar nu en&quot;Top Sellers&quot;-lista för varje varumärke och visar användaren rätt&quot;Top Sellers&quot;-lista baserat på värdet som lagras i [!UICONTROL Favorite Brand] profilattributet.

   ![Attribut för bästsäljare](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## Kriterier/algoritmer {#criteria-algorithms}

[!DNL Target Recommendations] använder sofistikerade algoritmer för att avgöra när en besökares åtgärder uppfyller kriterierna som anges i din aktivitet. Rekommendationsnyckeln avgör vilka alternativ för rekommendationslogik som är tillgängliga.

| Kriterier | Beskrivning |
|--- |--- |
| [Objekt/media med liknande attribut](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#similar-attributes) | Rekommenderar objekt eller media som liknar objekt eller media baserat på den aktuella sidaktiviteten eller tidigare besökares beteende. |
| [Folk som tittade på det här, såg det](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-viewed) | Rekommenderar objekt som oftast visas i samma session som det angivna objektet visas. |
| [Folk som såg det här, köpte det](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-bought) | Rekommenderar artiklar som oftast köps i samma session som det angivna objektet visas. |
| [Folk som köpte den här, köpte den där](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#bought-bought) | Rekommenderar artiklar som oftast köps av kunder samtidigt som det angivna objektet. |
| [Tillhörighet till webbplats](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#site-affinity) | Rekommenderar objekt baserat på säkerheten för en relation mellan objekt. |
| [De viktigaste säljarna](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#top-sellers) | De artiklar som ingår i de mest slutförda beställningarna. Flera enheter av samma artikel i en enda order räknas som en order. |
| [Mest visade](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed) | De objekt eller medier som visas oftast. |
| [Användarbaserad Recommendations](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#user-based) | Rekommenderar objekt baserat på besökarens webbläsarhistorik, visning och inköp. De här objekten kallas vanligtvis&quot;Rekommenderas för dig&quot;. |

>[!NOTE]
>
>Om du kör en rekommendation och ändrar villkoren för den kommer du att förlora dina rapportdata.

Du kan även använda ytterligare känd information om en besökare för att förbättra dina rekommendationer.

Alla endagskriterier körs två gånger dagligen. Alla kriterier för en vecka och längre körs en gång om dagen. Kriterierna för platstillhörighet körs en gång om dagen. Säkerhetskopieringsvillkor körs två gånger dagligen.

## Visa villkorsinformation {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Du kan visa villkorsinformation på ett snabbkort genom att hålla muspekaren över ett kort och klicka på ikonen Information på ett villkorskort utan att öppna villkoret.

![Villkorskortshovring](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

Klicka på **[!UICONTROL Algorithm Info]** fliken för att visa allmän information om de valda villkoren, inklusive namn, beskrivningar, branschvertikal, sidtyp(er), rekommendationsnyckel, rekommendationslogik och algoritm-ID.

![Fliken Algoritminformation](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

Klicka på **[!UICONTROL Algorithm Usage]** fliken för att visa en lista över aktiviteter som refererar till de valda villkoren. Kortet innehåller aktiva, inaktiva och utkastsaktiviteter. Klicka på listrutan Aktiva aktiviteter/Inaktiva aktiviteter/Utkastaktiviteter för att visa hela listan med aktiviteter som refererar till det villkoret. Du kan klicka på aktivitetslänken för att öppna aktiviteten för redigering.

![Fliken Algoritmanvändning](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>Den här [!UICONTROL Algorithm Usage] funktionen stöds för närvarande endast för Recommendations-aktiviteter. Den här funktionen stöds för närvarande inte för A/B-tester, autoallokering, automål och XT-aktiviteter (Experience Targeting) som innehåller [rekommendationer som ett erbjudande](/help/c-recommendations/recommendations-as-an-offer.md).
