---
keywords: recommendations;recommendations activity;criteria;algorithm;recommendation key;custom key;industry vertical;retail;eccommerce;lead generation;b2b;financial services;media;publishing
description: Kriterierna i Adobe Target Recommendations är regler som avgör vilka produkter som ska rekommenderas baserat på en fördefinierad uppsättning besökarbeteenden.
title: Kriterier i Adobe Target Recommendations
feature: null
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1593'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) -kriterier{#criteria}

Kriterier är regler som bestämmer vilka produkter som ska rekommenderas utifrån en fördefinierad uppsättning besökarbeteenden.

Kriterierna avgör vilken åtgärd som resulterar i vilken rekommendation. Du kan testa flera rekommendationstyper mot varandra genom att lägga till flera villkor.

## Branschvertikal {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Du väljer en vertikal bransch baserat på målen för dina rekommendationer:

| Branschvertikal | Mål |
|--- |--- |
| Detaljhandel/e-handel | Konvertering som resulterar i inköp |
| Leadgenerering/B2B/Finansiella tjänster | Konvertering utan köp |
| Media/publicering | Engagemang |

## Rekommendationsnyckel {#section_885B3BB1B43048A88A8926F6B76FC482}

Den rekommendationsnyckel du väljer avgör typen av villkor. Det finns flera kriterietyper som visas som kriteriekort när du ställer in en [!DNL Recommendations] aktivitet.

| Villkorstyp | Tangenter |
|--- |--- |
| Aktuell sidaktivitet | Rekommendera objekt baserat på vad användarna gör på den aktuella sidan. Besökare som visar en viss artikel kanske vill se andra artiklar i samma kategori.<ul><li>Aktuellt objekt</li><li>Aktuell kategori</li></ul> |
| Egen | Rekommendera objekt baserat på anpassade attribut.<ul><li>Anpassat attribut</li></ul>När du baserar rekommendationer på anpassade attribut måste du välja det anpassade attributet och sedan välja rekommendationstypen.<br>Du kan filtrera i realtid ovanpå dina egna villkor. Du kan t.ex. begränsa dina rekommenderade objekt till endast de som finns i en besökares favoritkategori eller varumärke. Detta ger dig möjlighet att kombinera offlineberäkningar med realtidsfiltrering.<br>Den här funktionen innebär att du kan använda Target för att lägga till personalisering ovanpå dina offlineberäknade rekommendationer eller anpassade kuraterade listor. Detta kombinerar styrkan hos era datavetare och er forskning med Adobe provad och sann leverans, filtrering vid körning, A/B-testning, målgruppsanpassning, rapportering, integreringar med mera.<br>Med tillägg av inkluderingsregler på anpassade kriterier förvandlas annars statiska rekommendationer till dynamiska rekommendationer baserade på besökarens intressen.<ul><li>Anpassade villkor kan konfigureras, precis som andra villkor i rekommendationer.</li><li>Du kan använda [samlingar](/help/c-recommendations/c-products/collections.md), [uteslutningar](/help/c-recommendations/c-products/exclusions.md)och [inkluderingar](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (inklusive de särskilda reglerna för Pris och Lager) på samma sätt som andra villkor.</li></ul>Möjliga användningsområden:<ul><li>Du vill rekommendera filmer från en anpassad lista, men bara om besökaren inte redan har tittat på dem.</li><li>Du vill köra en offlinealgoritm och använda resultaten för att ge bättre rekommendationer, men du måste se till att objekt som inte finns i lager aldrig rekommenderas.</li><li>Du vill bara ta med objekt från besökarens favoritkategori.</li></ul> |
| Tidigare beteende | Rekommendera objekt baserat på hur besökarna tidigare har svarat på ett objekt. Exempelvis har de som köpt ett visst varumärke större chans att köpa ett annat varumärke.<ul><li>Senast köpta artikel</li><li>Senast visade objekt</li><li>Mest visade objekt</li><li>Favoritkategori</li></ul> |
| Popularitet | Rekommendera de populäraste objekten, till exempel de populäraste videoklippen i en relaterad kategori eller de produkter som har visats oftast på din webbplats.<ul><li>Popularitet</li></ul> |
| Senast visade objekt | Rekommendera de objekt som en besökare senast har tittat på, t.ex. de objekt en besökare tittade på när han eller hon senast besökte din webbplats, eller de artiklar som är mest aktuella just nu.<br>Algoritmen Senast visade objekt returnerar resultat som är specifika för en besökares aktivitet i en [miljö](/help/administrating-target/hosts.md). Om två webbplatser tillhör olika miljöer och en besökare växlar mellan de två platserna, kommer algoritmen endast att returnera nyligen visade objekt från rätt plats.<br>Den här villkorstypen begränsas inte av samlingar.<ul><li>Senast visade objekt</li></ul>**Obs!** Du kan inte använda villkoret Senast visade objekt för att få säkerhetskopieringsrekommendationer.<br>Nyligen visade objekt/media kan filtreras så att endast objekt med ett visst attribut visas.<ul><li>Senast visade villkor kan konfigureras, precis som andra villkor i rekommendationerna.</li><li>Du kan använda [samlingar](/help/c-recommendations/c-products/collections.md), [uteslutningar](/help/c-recommendations/c-products/exclusions.md)och [inkluderingar](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (inklusive de särskilda reglerna för Pris och Lager) på samma sätt som andra villkor.</li></ul>Möjliga användningsområden:<ul><li>Ett flernationellt företag med flera företag kan ha besökarvisningsobjekt över flera digitala resurser. I det här fallet kan du begränsa antalet senast visade objekt så att de bara visas för respektive egenskap som de visades i. Detta förhindrar att nyligen visade objekt visas på en annan digital egenskaps webbplats.</li></ul> |

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
| Objekt/media med liknande attribut | Rekommenderar objekt eller media som liknar objekt eller media baserat på den aktuella sidaktiviteten eller tidigare besökares beteende.<br>**Obs!**Om du väljer Objekt/Media med liknande attribut kan du ange likhetsregler för innehåll. |
| Folk som tittade på det här, såg det | Rekommenderar objekt som oftast visas i samma session som det angivna objektet visas. |
| Folk som såg det här, köpte det | Rekommenderar artiklar som oftast köps i samma session som det angivna objektet visas. Detta villkor returnerar andra produkter som köpts efter att ha tittat på den här produkten. Den angivna produkten ingår inte i resultatmängden. |
| Folk som köpte den här, köpte den där | Rekommenderar artiklar som oftast köps av kunder samtidigt som det angivna objektet. |
| Tillhörighet till webbplats | Rekommenderar objekt baserat på säkerheten för en relation mellan objekt. Du kan konfigurera det här villkoret för att avgöra hur mycket data som krävs innan en rekommendation presenteras med skjutreglaget Inkluderingsregler. Om du t.ex. väljer väldigt stark så rekommenderas de produkter som ger störst säkerhet för en matchning.<br>Om du till exempel anger en mycket stark tillhörighet och din design innehåller fem objekt, varav tre uppfyller tröskelvärdet för anslutningsstyrkan, visas inte de två objekten som inte uppfyller kraven på minsta styrka i dina rekommendationer och ersätts av dina definierade säkerhetskopieringsobjekt. Objekt med den starkaste tillhörigheten visas först.<br>Vissa kunder med olika produktsamlingar och olika webbplatsbeteenden kan få det bästa resultatet om de ställer in en svag webbplatstillhörighet. |
| De viktigaste säljarna | De artiklar som ingår i de mest slutförda beställningarna. Flera enheter av samma artikel i en enda order räknas som en order. |
| Mest visade | De objekt eller medier som visas oftast. |
| Senast visade objekt/media | Objekt som har visats nyligen av besökaren. När du använder det här villkoret bör du uppdatera Target-designen för att hantera fall där tomma rekommendationer visas när det inte finns tillräckligt med tidigare visade objekt att visa. |
| Användarbaserad Recommendations | Rekommenderar objekt baserat på besökarens webbläsarhistorik, visning och inköp. De här objekten kallas vanligtvis&quot;Rekommenderas för dig&quot;.<br>Med dessa kriterier kan ni leverera personaliserat innehåll och personaliserade upplevelser till både nya och återkommande besökare. Listan med rekommendationer vägs mot besökarens senaste aktivitet och uppdateras under sessionen och anpassas mer när användaren bläddrar på webbplatsen.<br>Både vyer och inköp används för att avgöra vilka objekt som rekommenderas. Den angivna rekommendationsnyckeln (t.ex. Aktuellt objekt) används för att tillämpa eventuella inkluderingsregelfilter som du väljer. Du kan till exempel:<ul><li>Uteslut objekt som inte uppfyller vissa kriterier (produkter ur lager, artiklar som publicerats för mer än 30 dagar sedan, filmer med klassificering R o.s.v.)</li><li>Begränsa inkluderade objekt till en enda kategori eller till den aktuella kategorin</li></ul> |

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

Klicka på **[!UICONTROL Algorithm Usage]** fliken för att visa en lista över aktiviteter som refererar till de valda villkoren. Kortet innehåller aktiva och inaktiva aktiviteter. Klicka på listrutan Aktiva aktiviteter eller Inaktiviteter för att visa hela listan med aktiviteter som refererar till det villkoret. Du kan klicka på aktivitetslänken för att öppna aktiviteten för redigering.

![Fliken Algoritmanvändning](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>Den här [!UICONTROL Algorithm Usage] funktionen stöds för närvarande endast för Recommendations-aktiviteter. Den här funktionen stöds för närvarande inte för A/B Test- och Experience Targeting-aktiviteter (XT) som innehåller [rekommendationer som ett erbjudande](/help/c-recommendations/recommendations-as-an-offer.md).
