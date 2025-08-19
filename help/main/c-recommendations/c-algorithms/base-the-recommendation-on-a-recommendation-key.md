---
keywords: rekommendationsnyckel;rekommendationslogik;aktuell kategori;anpassat attribut;senast inköpt objekt;senast visade objekt;senast visade objekt;senast visade objekt;senast visade objekt;favoritkategori;popularitet;senast visade objekt;senast visade;senast visade;senast visade;favoriter;senast visade
description: Lär dig hur du använder rekommendationer baserade på nycklar som använder besökarbeteendekontext för att visa relevanta resultat i [!UICONTROL Recommendations]-aktiviteter.
title: Hur baserar jag [!UICONTROL Recommendation] på en [!UICONTROL Recommendation Key]?
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '3463'
ht-degree: 0%

---

# Basera rekommendationen på en rekommendationsnyckel

Rekommendationer baserade på algoritmer använder besökarbeteendekontext för att visa relevanta resultat i [!DNL Adobe Target] [!DNL Recommendations]-aktiviteter.

Varje algoritmtyp innehåller olika algoritmer som passar för dess typ, vilket visas i följande tabell:

| Algoritmtyp | Använd/Tillgängliga algoritmer |
| --- | --- |
| [!UICONTROL Cart-Based] | Utför rekommendationer baserat på användarens kundvagnsinnehåll.<ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul> |
| [!UICONTROL Popularity-Based] | Utför rekommendationer baserat på hur populärt ett objekt på webbplatsen är eller utifrån hur populärt det är att ha objekt inom en användares favoritkategori, varumärke, genre osv. <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | Rekommendationer baserade på sökning efter liknande objekt för ett objekt som användaren för närvarande visar eller nyligen har visat. <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | Utför rekommendationer baserat på användarens beteende. <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
| [!UICONTROL Custom Criteria] | Utför rekommendationer baserat på en anpassad fil som du överför. <ul><li>Anpassad algoritm</li></ul> |

Varje villkor definieras på en egen flik. Trafiken fördelas jämnt mellan olika kriterietester. Med andra ord, om du har två kriterier, delas trafiken lika mellan dem. Om du har två kriterier och två designer, delas trafiken jämnt mellan de fyra kombinationerna. Du kan också ange en procentandel besökare som ser standardinnehållet för jämförelse. I så fall ser den angivna procentandelen besökare standardinnehållet och resten delas mellan dina kriterier och designkombinationer.

Mer information om hur du skapar villkor och definierar dess algoritmtyper och algoritmer finns i [Skapa villkor](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

Olika rekommendationsalgoritmer passar in på olika typer av sidor. Mer information om varje algoritmtyp och dess tillgängliga algoritmer finns i följande avsnitt.

## Cart-baserad {#cart-based}

Algoritmtypen [!UICONTROL Cart-Based] gör att du kan rekommendera objekt baserat på innehållet i besökarens aktuella kundvagn. Rekommendationstangenterna anges med [mbox-parametern `cartIds`](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=sv-SE){target=_blank} i kommaavgränsade värden. Endast de första 10 värdena beaktas.

Den kundbaserade rekommendationslogiken liknar den användarbaserade algoritmen [!UICONTROL Recommended For You] och de objektbaserade algoritmerna [!UICONTROL People Who Viewed These, Bought Those] och [!UICONTROL People Who Bought These, Bought Those].

I [!DNL Target] används tekniker för att tillsammans filtrera för att fastställa likheter för varje objekt i besökarens kundvagn. Sedan kombineras dessa beteendelikheter för varje objekt för att skapa en sammanfogad lista.

[!DNL Target] ger även marknadsförare möjlighet att se besökarnas beteende i en eller flera sessioner:

* **[!UICONTROL Single Session]**: Baserat på vad andra besökare gjorde under en enda session.

  Om du tittar på beteenden under en session kan det verka klokt om du tycker att produkter &quot;passar ihop&quot; baserat på användning, tillfälle eller händelse. En besökare köper till exempel en skrivare och kan även behöva bläck och papper. Eller så köper besökaren jordnötssmör och behöver bröd och gelé.

* **[!UICONTROL Across Sessions]**: Baserat på vad andra besökare gjorde under flera sessioner.

  Om du tittar på beteenden i flera sessioner kan det vara bra om det finns en känsla av att produkterna&quot;följer med&quot; varandra baserat på besökarens önskemål eller smak. En besökare gillar till exempel Star Wars och kan också gilla Indiana Jones, även om besökaren inte nödvändigtvis vill se båda filmerna på samma plats. Eller så tycker en besökare om styrelsemötet&quot;Codenames&quot; och kanske också om styrelsemötet&quot;Avalon&quot;, även om besökaren inte kan spela båda spelen samtidigt.

[!DNL Target] gör rekommendationer för varje besökare baserat på artiklarna i den aktuella kundvagnen, oavsett om du tittar på besökarbeteendet i en session eller i flera sessioner.

Följande algoritmer är tillgängliga med algoritmtypen [!UICONTROL Cart-Based]:

### [!UICONTROL People Who Viewed This, Also Viewed]

Rekommenderar objekt som oftast visas i samma session som det angivna objektet visas.

Den här logiken returnerar andra produkter som visas när du har tittat på den här. Den angivna produkten ingår inte i resultatuppsättningen.

Med den här logiken kan du skapa ytterligare konverteringsmöjligheter genom att rekommendera objekt som andra besökare som tittade på ett objekt också kan se. Besökare som tittar på cyklar på er webbplats kan till exempel också titta på cykelhjälmar, cykelkit, lås osv. Du kan skapa en rekommendation med hjälp av den här logiken som föreslår att andra produkter hjälper dig att öka intäkterna.

Om du väljer den här algoritmen kan du välja följande rekommendationer:

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Viewed This, Also Bought]

Rekommenderar artiklar som oftast köps i samma session som det angivna objektet visas.

Den här logiken returnerar andra produkter som köpts efter att ha tittat på den här. Den angivna produkten ingår inte i resultatuppsättningen.

Med den här logiken kan du öka möjligheterna till korsförsäljning genom att visa en rekommendation på en produktsida, som till exempel visar objekt som andra besökare som visade det köpta objektet. Om besökaren till exempel tittar på en fiskepunkt kan rekommendationen visa ytterligare saker som andra besökare har köpt, som t.ex. kryssrutor för taggar, skölder och fiskekurser. När besökarna besöker er webbplats kan ni ge dem ytterligare inköpsrekommendationer.

Om du väljer den här algoritmen kan du välja följande rekommendationer:

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Bought This, Also Bought]

Rekommenderar artiklar som oftast köps av kunder samtidigt som det angivna objektet.

Den här logiken returnerar andra produkter som köpts efter att ha köpt den här. Den angivna produkten ingår inte i resultatuppsättningen.

Med den här logiken kan du öka möjligheterna till korsförsäljning genom att visa en rekommendation på en kundvagnssammanfattning, som t.ex. visar artiklar som andra köpare också har köpt. Om besökaren till exempel köper en kostym kan rekommendationen visa ytterligare objekt som andra besökare har köpt tillsammans med kostymen, som slipsar, klädskor och kufflänkar. När besökarna granskar sina inköp ger ni dem ytterligare rekommendationer.

Om du väljer den här algoritmen kan du välja följande rekommendationer:

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

## [!UICONTROL Popularity-Based]

Algoritmtypen [!UICONTROL Popularity-Based] gör att du kan göra rekommendationer baserat på den övergripande populariteten för ett objekt på webbplatsen eller baserat på populariteten för objekt i en användares favoritkategori eller mest visade kategori, märke, genre o.s.v.

Följande algoritmer är tillgängliga med algoritmtypen [!UICONTROL Popularity-Based]:

### [!UICONTROL Most Viewed Across the Site] {#most-viewed}

Rekommendationen avgörs av det objekt som har visats oftast. Detta bestäms av de kriterier för senaste frekvens/frekvens som fungerar enligt följande:

* 10 poäng för den första produktvyn
* 5 poäng för varje efterföljande vy
* I slutet av sessionen divideras alla värden med 2

Om du till exempel visar surfbräda A och sedan surfbräda B i en session blir resultatet A: 10, B: 5. När sessionen avslutas har du A: 5, B: 2.5. Om du visar samma objekt i nästa session ändras värdena till A: 15 B: 7.5.

Använd den här algoritmen på allmänna sidor, som startsidor, landningssidor och annonser utanför webbplatsen.

### [!UICONTROL Most Viewed by Category] {#most-viewed-category}

Rekommendationen avgörs av den kategori som har fått mest aktivitet, med samma metod som används för&quot;mest visade objekt&quot; förutom att kategorier räknas i stället för produkter.

Detta bestäms av de kriterier för senaste frekvens/frekvens som fungerar enligt följande:

* 10 poäng för den första kategorivyn
* 5 poäng för varje efterföljande vy

De kategorier som besöktes för första gången får 10 poäng. Fem poäng ges för efterföljande besök i samma kategori. Vid varje besök minskas inaktuella kategorier som har visats tidigare med 1.

Om du till exempel visar kategori A och sedan kategori B i en session får du resultatet A: 9, B: 10. Om du visar samma objekt i nästa session ändras värdena till A: 20 B: 9.

Använd den här algoritmen på allmänna sidor, som startsidor, landningssidor och annonser utanför webbplatsen.

Om du väljer algoritmen Mest visade av kategori kan du välja följande rekommendationer:

* [!UICONTROL Current Category]
* [!UICONTROL Favorite Category]

### [!UICONTROL Most Viewed by Item Attribute]

Rekommenderar objekt eller media som liknar de mest visade objekten eller medierna på din webbplats.

Med den här algoritmen kan du välja vilket objektattribut du vill basera rekommendationen på, till exempel &quot;Namn&quot; eller &quot;Varumärke&quot;.

Sedan väljer du vilka profilattribut som ska matchas i besökarens profil, till exempel &quot;Favorit Brand&quot;, &quot;Last Item Added to Cart&quot; eller &quot;Most Viewed Show.&quot;

### [!UICONTROL Top Sellers Across the Site] {#top-sellers}

Visar de artiklar som ingår i de mest slutförda beställningarna från hela webbplatsen. Flera enheter av samma artikel i en enda order räknas som en order.

Med den här algoritmen kan du skapa rekommendationer för toppförsäljningsartiklar på webbplatsen för att öka konverteringen och intäkterna. Den här logiken passar särskilt bra för förstagångsbesökare på er webbplats.

### [!UICONTROL Top Sellers by Category]

Visar de artiklar som ingår i de mest slutförda beställningarna per kategori. Flera enheter av samma artikel i en enda order räknas som en order.

Med den här algoritmen kan du skapa rekommendationer för toppförsäljningsartiklar på din webbplats baserat på kategori för att öka konverteringen och intäkterna. Den här logiken passar särskilt bra för förstagångsbesökare på er webbplats.

Om du väljer algoritmen [!UICONTROL Most Viewed by Category] kan du välja följande [!UICONTROL Recommendations Keys]:

* [!UICONTROL Current Category]
* [!UICONTROL Favorite Category]

### [!UICONTROL Top Sellers by Item Attribute]

Rekommenderar objekt eller media som liknar de mest köpta objekten eller medierna på din webbplats.

Med den här algoritmen kan du välja vilket objektattribut du vill basera rekommendationen på, till exempel &quot;Namn&quot; eller &quot;Varumärke&quot;.

Sedan väljer du vilka profilattribut som ska matchas i besökarens profil, till exempel &quot;Favorit Brand&quot;, &quot;Last Item Added to Cart&quot; eller &quot;Most Viewed Show.&quot;

### [!UICONTROL Top by Analytics Metric]

Visar &quot;Övre x&quot; där *x* är ett godtyckligt [!DNL Analytics]-mått. När du använder beteendedata från rutor kan du använda [!UICONTROL Top Sold] eller [!UICONTROL Top Viewed] (x = &quot;Sold&quot; eller x = &quot;Viewed&quot;). Om du använder beteendedata från [!DNL Adobe Analytics] kan du använda x = &quot;kundvagnstillägg&quot; eller något annat [!DNL Analytics]-mått.

## [!UICONTROL Item-Based]

Rekommendationstypen [!UICONTROL Item-Based] gör att du kan göra rekommendationer baserat på om du vill hitta liknande objekt som ett objekt som användaren visar eller nyligen har visat.

Följande algoritmer är tillgängliga med algoritmtypen [!UICONTROL Item-Based]:

### [!UICONTROL People Who Viewed This, Viewed That] {#viewed-viewed}

Rekommenderar objekt som oftast visas i samma session som det angivna objektet visas.

Den här logiken returnerar andra produkter som visas när du har tittat på den här. Den angivna produkten ingår inte i resultatuppsättningen.

Med den här logiken kan du skapa ytterligare konverteringsmöjligheter genom att rekommendera objekt som andra besökare som tittade på ett objekt också kan se. Besökare som tittar på cyklar på er webbplats kan till exempel också titta på cykelhjälmar, cykelkit, lås osv. Du kan skapa en rekommendation med hjälp av den här logiken som föreslår att andra produkter hjälper dig att öka intäkterna.

Om du väljer den här algoritmen kan du välja följande [!UICONTROL Recommendations Keys]:

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Viewed This, Bought That] {#viewed-bought}

Rekommenderar artiklar som oftast köps i samma session som det angivna objektet visas. Detta villkor returnerar andra produkter som köpts efter att ha tittat på den här produkten. Den angivna produkten ingår inte i resultatmängden.

Den här logiken returnerar andra produkter som köpts efter att ha tittat på den här. Den angivna produkten ingår inte i resultatuppsättningen.

Med den här logiken kan du öka möjligheterna till korsförsäljning genom att visa en rekommendation på en produktsida, som till exempel visar objekt som andra besökare som visade det köpta objektet. Om besökaren till exempel tittar på en fiskepunkt kan rekommendationen visa ytterligare saker som andra besökare har köpt, som t.ex. kryssrutor för taggar, skölder och fiskekurser. När besökarna besöker er webbplats kan ni ge dem ytterligare inköpsrekommendationer.

Om du väljer den här algoritmen kan du välja följande [!UICONTROL Recommendations Keys]:

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL People Who Bought This, Bought That] {#bought-bought}

Rekommenderar artiklar som oftast köps av kunder samtidigt som det angivna objektet.

Den här logiken returnerar andra produkter som köpts efter att ha köpt den här. Den angivna produkten ingår inte i resultatuppsättningen.

Med den här logiken kan du öka möjligheterna till korsförsäljning genom att visa en rekommendation på en kundvagnssammanfattning, som t.ex. visar artiklar som andra köpare också har köpt. Om besökaren till exempel köper en kostym kan rekommendationen visa ytterligare objekt som andra besökare har köpt tillsammans med kostymen, som slipsar, klädskor och kufflänkar. När besökarna granskar sina inköp ger ni dem ytterligare rekommendationer.

Om du väljer den här algoritmen kan du välja följande [!UICONTROL Recommendations Keys]:

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

### [!UICONTROL Items with Similar Attributes] {#similar-attributes}

Rekommenderar objekt eller media som liknar objekt eller media baserat på den aktuella sidaktiviteten eller tidigare besökares beteende.

Om du väljer [!UICONTROL Items with Similar Attributes] eller [!UICONTROL Media with Similar Attributes] kan du ange likhetsregler för innehåll.

Att använda innehållets likhet för att generera rekommendationer är särskilt effektivt för nya objekt, som troligen inte visas i rekommendationer med [!UICONTROL People Who Viewed This], [!UICONTROL Viewed That] och annan logik som baseras på tidigare beteende. Ni kan också använda innehållets likhet för att generera användbara rekommendationer för nya besökare som inte har några tidigare inköp eller andra historiska data.

Om du väljer den här algoritmen kan du välja följande [!UICONTROL Recommendations Keys]:

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

Mer information finns i [Likhet för innehåll](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

## [!UICONTROL User-Based]

Algoritmtypen [!UICONTROL User-Based] gör att du kan göra rekommendationer baserat på användarens beteende.

Följande algoritmer är tillgängliga med algoritmtypen [!UICONTROL User-Based]:

### [!UICONTROL Recently Viewed Items] {#recently-viewed}

Använder besökarens historik (spridningssessioner) för att presentera de *x* senaste objekten som besökaren har visat, baserat på antalet platser i designen.

Algoritmen [!UICONTROL Recently Viewed Items] returnerar resultat som är specifika för en given [miljö](/help/main/administrating-target/hosts.md). Om två platser tillhör olika miljöer och en besökare växlar mellan de två platserna, visar varje plats endast nyligen visade objekt från rätt plats. Om två platser finns i samma miljö och en besökare växlar mellan de två platserna, ser besökaren samma nyligen visade objekt för båda platserna.

>[!NOTE]
>
>Du kan inte använda kriterierna [!UICONTROL Recently Viewed Items] för rekommendationer för säkerhetskopiering.

[!UICONTROL Recently Viewed Items] eller [!UICONTROL Recently Viewed Media] kan filtreras så att endast objekt med ett visst attribut visas.

* [!UICONTROL Recently Viewed]-villkor kan konfigureras, precis som andra villkor i rekommendationer.
* Du kan använda [samlingar](/help/main/c-recommendations/c-products/collections.md), [exkluderingar](/help/main/c-recommendations/c-products/exclusions.md) och [inkluderingar](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (inklusive de särskilda reglerna för Pris och Lager) på samma sätt som andra villkor.

Möjliga användningsfall kan vara att ett flernationellt företag med flera företag kan ha besökarvyobjekt över flera digitala resurser. I det här fallet kan du begränsa antalet senast visade objekt så att de bara visas för respektive egenskap som de visades i. Detta förhindrar att nyligen visade objekt visas på en annan digital egenskaps webbplats.

Använd den här algoritmen på allmänna sidor, som startsidor, landningssidor och annonser utanför webbplatsen.

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] respekterar både globala inställningar för undantag och den valda samlingsinställningen för aktiviteten. Om ett objekt utesluts av ett globalt undantag, eller inte ingår i den valda samlingen, visas det inte. När du använder ett [!UICONTROL Recently Viewed Items]-villkor bör därför inställningen &quot;Alla samlingar&quot; användas i allmänhet.

### [!UICONTROL Recommended for You] {#recommended-for-you}

Rekommenderar objekt baserat på besökarens webbsurfning, visning och köphistorik.

Med den här algoritmen kan ni leverera personaliserat innehåll och personaliserade upplevelser till både nya och återkommande besökare. Listan med rekommendationer vägs mot besökarens senaste aktivitet och uppdateras under sessionen och anpassas mer när användaren bläddrar på webbplatsen.

Både vyer och inköp används för att avgöra vilka objekt som rekommenderas. Den angivna rekommendationsnyckeln (till exempel [!UICONTROL Current Item]) används för att tillämpa eventuella inkluderingsregelfilter som du väljer.

Du kan till exempel:

* Uteslut objekt som inte uppfyller vissa kriterier (produkter ur lager, artiklar som publicerats för mer än 30 dagar sedan, filmer med klassificering R och så vidare).
* Begränsa inkluderade objekt till en enda kategori eller till den aktuella kategorin.

Om du väljer den här algoritmen kan du välja följande filtreringsnycklar:

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]

## Anpassade villkor {#custom}

Algoritmtypen [!UICONTROL Custom Criteria] gör att du kan göra rekommendationer baserat på en anpassad fil som du överför.

Rekommendationen bestäms av ett objekt som lagras i en besökarprofil, med hjälp av någon av användarna.*x* eller profil.*x*-attribut.

När det här alternativet är markerat måste värdet `entity.id` finnas i profilattributet.

När du baserar rekommendationer på anpassade attribut måste du välja det anpassade attributet och sedan välja rekommendationstypen.

Du kan filtrera i realtid ovanpå dina egna villkor. Du kan t.ex. begränsa dina rekommenderade objekt till endast de som finns i en besökares favoritkategori eller varumärke. Detta ger dig möjlighet att kombinera offlineberäkningar med realtidsfiltrering.

Den här funktionen innebär att du kan använda [!DNL Target] för att lägga till personalisering ovanpå dina offlineberäknade rekommendationer eller anpassade kuraterade listor. Detta kombinerar styrkan hos era datavetare och er datavetare med Adobe beprövade leverans, filtrering vid körning, A/B-testning, målgruppsanpassning, rapportering, integreringar med mera.

Med tillägg av inkluderingsregler på [!UICONTROL Custom Criteria] förvandlas annars statiska rekommendationer till dynamiska rekommendationer baserade på en besökares intressen.

* Anpassade villkor kan konfigureras, precis som andra villkor i rekommendationer.
* Du kan använda [samlingar](/help/main/c-recommendations/c-products/collections.md), [exkluderingar](/help/main/c-recommendations/c-products/exclusions.md) och [inkluderingar](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (inklusive de särskilda reglerna för Pris och Lager) på samma sätt som andra villkor.

Möjliga användningsområden:

* Du vill rekommendera filmer från en anpassad lista, men bara om besökaren inte redan har tittat på dem.
* Du vill köra en offlinealgoritm och använda resultaten för att ge bättre rekommendationer, men du måste se till att objekt som inte finns i lager aldrig rekommenderas.
* Du vill bara ta med objekt från besökarens favoritkategori.

## Rekommendationsnycklar {#keys}

Följande rekommendationsnycklar är tillgängliga i listrutan [!UICONTROL Recommendation Key]:

### [!UICONTROL Current Item] {#current-item}

Rekommendationen avgörs av det objekt som besökaren för närvarande visar.

Rekommendationer visar andra objekt som kan intressera besökare som är intresserade av det angivna objektet.

När det här alternativet är markerat måste värdet `entity.id` skickas som en parameter i visningsrutan.

Kan användas med följande algoritmer:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Använd rekommendationsnyckeln [!UICONTROL Current Item] på din webbplats:

* Sidor med en artikel, t.ex. produktsidor.
* Använd INTE på null-sökresultatsidor.

### [!UICONTROL Last Purchased Item] {#last-purchased}

Rekommendationen avgörs av den sista artikeln som köptes av varje unik besökare. Detta hämtas automatiskt, så inga värden måste skickas till sidan.

Kan användas med följande algoritmer:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Använd rekommendationsnyckeln [!UICONTROL Last Purchased Item] på din webbplats:

* Startsida, Min kontosida, annonser på annan plats.
* Använd INTE på produktsidor eller sidor som är relevanta för inköp.

#### Anpassad rekommendationsnyckel

Du kan basera rekommendationer på värdet för ett anpassat profilattribut. Anta till exempel att du vill visa rekommenderade filmer baserat på den film som en besökare senast lade till i kön.

1. Välj ditt anpassade profilattribut i listrutan **[!UICONTROL Recommendation Key]** (till exempel [!UICONTROL Last Show Added to Watchlist]).
1. Välj sedan din **[!UICONTROL Recommendation Logic]** (till exempel [!UICONTROL People Who Viewed This, Viewed That]).

Om ditt anpassade profilattribut inte direkt matchar ett enda enhets-ID måste du förklara för [!DNL Recommendations] hur du vill att matchningen till en entitet ska ske. Anta till exempel att du vill visa de främsta säljartiklarna från en besökares favoritvarumärke.

1. Välj ditt anpassade profilattribut i listrutan **[!UICONTROL Recommendation Key]** (till exempel &quot;Favorit Brand&quot;).

1. Välj sedan den **[!UICONTROL Recommendation Logic]** som du vill använda med den här nyckeln (till exempel [!UICONTROL Top Sellers]).

   Alternativet [!UICONTROL Group By Unique Value Of] visas.

1. Välj det entitetsattribut som matchar nyckeln som du har valt. I det här fallet matchar [!UICONTROL Favorite Brand] `entity.brand`.

   [!DNL Recommendations] skapar nu en [!UICONTROL Top Sellers]-lista för varje varumärke och visar besökaren rätt [!UICONTROL Top Sellers]-lista baserat på värdet som lagras i besökarens [!UICONTROL Favorite Brand]-profilattribut.

### [!UICONTROL Last Viewed Item] {#last-viewed}

Rekommendationen avgörs av det sista objektet som visades av varje unik besökare. Detta hämtas automatiskt, så inga värden måste skickas till sidan.

Kan användas med följande algoritmer:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Använd rekommendationsnyckeln [!UICONTROL Last Viewed Item] på din webbplats:

* Startsida, Min kontosida, annonser på annan plats.
* Använd INTE på produktsidor eller sidor som är relevanta för inköp.

### [!UICONTROL Most Viewed Item] {#most-viewed-logic}

Visar de objekt eller medier som visas oftast på platsen.

Med den här logiken kan du visa rekommendationer baserat på de mest visade objekten på webbplatsen för att öka konverteringsgraden för andra objekt. En mediewebbplats kan till exempel visa rekommendationer på sin hemsida för sina mest visade videor för att uppmuntra besökarna att titta på ytterligare videor.

Den här rekommendationsnyckeln kan användas med följande algoritmer:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

### [!UICONTROL Current Category] {#current-category}

Rekommendationen avgörs av den produktkategori som besökaren för närvarande visar.

Rekommendationer visar objekt i den angivna produktkategorin.

När det här alternativet är markerat måste värdet `entity.categoryId` skickas som en parameter till visningsrutan.

Den här rekommendationsnyckeln kan användas med följande algoritmer:

* [!UICONTROL Top Sellers]
* [!UICONTROL Most Viewed]

Använd rekommendationsnyckeln [!UICONTROL Current Category] på din webbplats:

* Sidor i en kategori.
* Använd INTE på null-sökresultatsidor.

### [!UICONTROL Favorite Category] {#favorite-category}

Rekommendationen avgörs av besökarens favoritproduktkategori.

Rekommendationer visar objekt i den angivna produktkategorin.

När det här alternativet är markerat måste värdet `entity.categoryId` skickas som en parameter till visningsrutan.

Den här rekommendationsnyckeln kan användas med följande algoritmer:

* [!UICONTROL Top Sellers]
* [!UICONTROL Most Viewed]

Använd rekommendationsnyckeln [!UICONTROL Current Category] på din webbplats:

* Sidor i en kategori.
* Använd INTE på null-sökresultatsidor.

### [!UICONTROL Site Affinity] {#site-affinity}

Rekommenderar objekt baserat på säkerheten för en relation mellan objekt. Du kan konfigurera det här villkoret för att avgöra hur mycket data som krävs innan en rekommendation presenteras med skjutreglaget [!UICONTROL Inclusion Rules]. Om du t.ex. väljer väldigt stark så rekommenderas de produkter som ger störst säkerhet för en matchning.

Om du till exempel anger en mycket stark tillhörighet och din design innehåller fem objekt, varav tre uppfyller tröskelvärdet för anslutningsstyrkan, visas inte de två objekten som inte uppfyller kraven på minsta styrka i dina rekommendationer och ersätts av dina definierade säkerhetskopieringsobjekt. Objekt med den starkaste tillhörigheten visas först.

En webbutik kan t.ex. rekommendera artiklar i efterföljande besök som en besökare har visat intresse för under tidigare sessioner. Aktivitet för varje besökares session hämtas för att beräkna en tillhörighet baserat på en nyhet och frekvensmodell. När den här besökaren återgår till din webbplats används tillhörighet för att visa rekommendationer baserat på tidigare åtgärder på din webbplats.

Vissa kunder med olika produktsamlingar och olika webbplatsbeteenden kan få det bästa resultatet om de ställer in en svag webbplatstillhörighet.

Den här logiken kan användas med följande rekommendationsnycklar:

* [!UICONTROL Current Item]
* [!UICONTROL Last Purchased Item]
* [!UICONTROL Last Viewed Item]
* [!UICONTROL Most Viewed Item]
