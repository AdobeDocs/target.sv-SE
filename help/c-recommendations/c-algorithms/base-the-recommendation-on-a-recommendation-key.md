---
keywords: recommendation key;recommendation logic;current category;custom attribute;last purchased item;last viewed item;most viewed item;most viewed item;favorite category;popularity;recently viewed item;last purchased;last viewed;most viewed;favorite;recently viewed
description: Recommendations baserat på nycklar använder besökarbeteendekontext för att visa relevanta resultat i Adobe Target Recommendations-aktiviteter.
title: Basera rekommendationen på en rekommendationsnyckel
feature: criteria
mini-toc-levels: 2
translation-type: tm+mt
source-git-commit: 21c8e39669925e8fd26d7f64ea7dfe95f28795bf
workflow-type: tm+mt
source-wordcount: '2001'
ht-degree: 0%

---


# Basera rekommendationen på en rekommendationsnyckel

Recommendations baserat på nycklar använder besökarbeteendekontext för att visa relevanta resultat i [!DNL Adobe Target][!DNL Recommendations] aktiviteter.

Det finns två typer av Recommendations:

* **Popularitet:** Visar objekt enligt Mest visade, Mest sålda och Mät upp. Nyckeln är tom för popularitetskriterier.
* **Nyckelbaserad:** Innefattar resten av kriterierna. Recommendations erbjuder en mängd olika alternativ när det gäller nyckeltypen. Alternativen varierar från&quot;aktuellt objekt&quot; till&quot;profilparametrar&quot;, vilket gör att du kan ställa in nyckelvärdena för programmering att rekommendera. Du kan testa flera villkor mot varandra genom att basera varje villkor på en annan nyckel.

Varje villkor definieras på en egen flik. Trafiken fördelas jämnt mellan olika kriterietester. Med andra ord, om du har två kriterier, delas trafiken lika mellan dem. Om du har två kriterier och två designer, delas trafiken jämnt mellan de fyra kombinationerna. Du kan också ange en procentandel besökare som ser standardinnehållet för jämförelse. I så fall ser den angivna procentandelen besökare standardinnehållet och resten delas mellan dina kriterier och designkombinationer.

1. Skapa ett nytt villkor eller välj ett befintligt villkor och klicka på **[!UICONTROL Edit]**.
1. Om du vill ändra rekommendationsnyckeln väljer du den nya nyckeln i [!UICONTROL Recommendation Key] listrutan och klickar sedan på **[!UICONTROL Save]** eller **[!UICONTROL Update]**.

   Eftersom olika logik mappar till olika rekommendationstangenter passar olika rekommendationer in på olika typer av sidor. Mer information om varje rekommendationsnyckel finns i följande avsnitt.

## Rekommendationsnycklar

Följande rekommendationsnycklar är tillgängliga i [!UICONTROL Recommendation Key] listrutan:

### Aktuellt objekt

Rekommendationen avgörs av det objekt som besökaren för närvarande visar.

Recommendations visar andra objekt som kan intressera besökare som är intresserade av det angivna objektet.

När det här alternativet är markerat måste `entity.id` värdet skickas som en parameter i visningsrutan.

#### Logic (villkor)

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]
* [!UICONTROL Site Affinity]

#### Var kan du använda på din webbplats?

* Sidor med en artikel, t.ex. produktsidor.
* Använd INTE på null-sökresultatsidor.

### Aktuell kategori

Rekommendationen avgörs av den produktkategori som besökaren för närvarande visar.

Recommendations visar objekt i den angivna produktkategorin.

När det här alternativet är markerat måste `entity.categoryId` värdet skickas som en parameter till visningsrutan.

#### Logic (villkor)

* De viktigaste säljarna
* Mest visade

#### Var kan du använda på din webbplats?

* Sidor i en kategori.
* Använd INTE på null-sökresultatsidor.

### Anpassat attribut {#custom}

Rekommendationen bestäms av ett objekt som lagras i en besökarprofil, med hjälp av någon av användarna.*x* eller profil.*x* -attribut.

När det här alternativet är markerat måste `entity.id` värdet finnas i profilattributet.

#### Logic (villkor)

* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]
* [!UICONTROL Overall behavior]
* [!UICONTROL Most Viewed]
* [!UICONTROL Top Sellers]

Om nyckeln är ett anpassat profilattribut och algoritmtypen är Most Viewed eller Top Sellers, visas en ny listruta med namnet &quot;Group By Unique Value Of&quot; som har en lista med kända entitetsattribut (förutom ID, kategori, marginal, värde, lager och miljö). Det här fältet är obligatoriskt.

#### Var kan du använda på din webbplats?

* Kan användas på alla sidor.

#### Anpassad rekommendationsnyckel

Du kan basera rekommendationer på värdet för ett anpassat profilattribut. Anta till exempel att du vill visa rekommenderade filmer baserat på den film som en besökare senast lade till i sin kö.

1. Välj det anpassade profilattributet i **[!UICONTROL Recommendation Key]** listrutan (till exempel &quot;Senast visade tillagd i bevakningslista&quot;).
1. Välj sedan din **[!UICONTROL Recommendation Logic]** (till exempel&quot;Personer som har tittat på det här, har sett det&quot;).

   ![Dialogrutan Skapa nytt villkor](/help/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

Om ditt anpassade profilattribut inte direkt matchar ett enda enhets-ID måste du förklara [!DNL Recommendations] hur du vill att matchningen till en entitet ska ske. Anta till exempel att du vill visa de främsta säljartiklarna från en besökares favoritvarumärke.

1. Välj det anpassade profilattributet i **[!UICONTROL Recommendation Key]** listrutan (till exempel &quot;Favoritmärke&quot;).

1. Välj sedan den **[!UICONTROL Recommendation Logic]** du vill använda med den här nyckeln (till exempel&quot;Top Sellers&quot;).

   Alternativet [!UICONTROL Group By Unique Value Of] visas.

1. Välj det entitetsattribut som matchar nyckeln som du har valt. I det här fallet matchar&quot;Favorite Brand&quot; `entity.brand`.

   [!DNL Recommendations] skapar nu en&quot;Top Sellers&quot;-lista för varje varumärke och visar besökaren rätt&quot;Top Sellers&quot;-lista baserat på det värde som lagras i besökarens attribut för favoritprofilen.

   ![Skapa ny villkorsdialogruta 2](/help/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

### Senast köpta artikel

Rekommendationen avgörs av den sista artikeln som köptes av varje unik besökare. Detta hämtas automatiskt, så inga värden behöver skickas till sidan.

#### Logic (villkor)

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]
* [!UICONTROL Site Affinity]

#### Var kan du använda på din webbplats?

* Startsida, Min kontosida, annonser på annan plats.
* Använd INTE på produktsidor eller sidor som är relevanta för inköp.

### Senast visade objekt

Rekommendationen avgörs av det sista objektet som visades av varje unik besökare. Detta hämtas automatiskt, så inga värden behöver skickas till sidan.

#### Logic (villkor)

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]
* [!UICONTROL Site Affinity]

#### Var kan du använda på din webbplats?

* Startsida, Min kontosida, annonser på annan plats.
* Använd INTE på produktsidor eller sidor som är relevanta för inköp.

### Mest visade objekt

Rekommendationen avgörs av det objekt som har visats oftast, med samma metod som används för favoritkategorin.

Detta bestäms av kriterier för aktuell frekvens och frekvens som fungerar enligt följande:

* 10 poäng för den första produktvyn
* 5 poäng för varje efterföljande vy
* I slutet av sessionen divideras alla värden med 2

Om du till exempel visar surfboardA och sedan surfboardB i en session blir resultatet A: 10 B: 5. När sessionen är slut får du ett: 5 B: 2.5. Om du visar samma objekt i nästa session ändras värdena till A: 15 B: 7.5.

#### Logic (villkor)

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]
* [!UICONTROL Site Affinity]

#### Var kan du använda på din webbplats?

* Allmänna sidor, t.ex. hemsidor eller landningssidor och annonser utanför webbplatsen.

### Favoritkategori

Rekommendationen avgörs av den kategori som har fått mest aktivitet, med samma metod som används för&quot;mest visade objekt&quot; förutom att kategorier räknas i stället för produkter.

Detta bestäms av kriterier för aktuell frekvens och frekvens som fungerar enligt följande:

* 10 poäng för den första kategorivyn
* 5 poäng för varje efterföljande vy

De kategorier som besöktes för första gången får 10 poäng. Fem poäng ges för efterföljande besök i samma kategori. Vid varje besök minskas inaktuella kategorier som har visats tidigare med 1.

Om du till exempel visar kategori A och sedan kategori B i en session blir resultatet A: 9 B: 10. Om du visar samma objekt i nästa session ändras värdena till A: 20 B: 9.

#### Logic (villkor)

* [!UICONTROL Top Sellers]
* [!UICONTROL Most Viewed]

#### Var kan du använda på din webbplats?

* Allmänna sidor, t.ex. hemsidor eller landningssidor och annonser utanför webbplatsen.

### Popularitet

Rekommendationen avgörs av hur populära objekten på webbplatsen är. Populariteten omfattar bland annat de främsta säljarna och de mest visade uppgifterna i mbox och, om du använder Adobe Analytics, alla mätvärden som finns i produktrapporten. Objekten rangordnas baserat på den rekommendationslogik du väljer.

#### Logic (villkor)

* [!UICONTROL Top Sellers]
* [!UICONTROL Most Viewed]
* Produktrapportstatistik (om du använder Adobe Analytics)

#### Var kan du använda på din webbplats?

* Allmänna sidor, t.ex. hemsidor eller landningssidor och annonser utanför webbplatsen.

### Senast visade objekt {#recently-viewed}

Använder besökarens historik (spridningssessioner) för att presentera de senaste *x* -objekten som besökaren har visat, baserat på antalet platser i designen.

Kriterierna för nyligen visade objekt returnerar nu resultat som är specifika för en viss [miljö](/help/administrating-target/hosts.md). Om två platser tillhör olika miljöer och en besökare växlar mellan de två platserna, visar varje plats endast nyligen visade objekt från rätt plats. Om två platser finns i samma miljö och en besökare växlar mellan de två platserna, kommer besökaren att se samma nyligen visade objekt för båda platserna.

#### Var kan du använda på din webbplats?

* Allmänna sidor, t.ex. hemsidor eller landningssidor och annonser utanför webbplatsen.

>[!NOTE]
>
>Nyligen visade objekt respekterar både de globala inställningarna Uteslutningar och den valda samlingsinställningen för aktiviteten. Om ett objekt utesluts av ett globalt undantag, eller inte ingår i den valda samlingen, visas det inte. Därför bör inställningen&quot;Alla samlingar&quot; användas i allmänhet när du använder ett villkor för nyligen visade objekt.

## Rekommendationslogik

Följande rekommendationslogik (villkor) finns i den [!UICONTROL Recommendation Logic] nedrullningsbara listan:

### Objekt med liknande attribut

Innehållslikhet jämför nyckelord för objektattribut och gör rekommendationer baserat på hur många nyckelord olika objekt har gemensamt. Recommendations baserat på innehållets likhet kräver inte tidigare data för att ge ett starkt resultat.

Att använda innehållets likhet för att generera rekommendationer är särskilt effektivt för nya objekt, som troligen inte visas i rekommendationer med Personer som har tittat på det här, Visat det och annan logik som baseras på tidigare beteende. Ni kan också använda innehållets likhet för att generera användbara rekommendationer för nya besökare som inte har några tidigare inköp eller andra historiska data.

Mer information finns i [Likhet](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity)för innehåll.

Den här logiken kan användas med följande rekommendationsnycklar:

* Aktuellt objekt
* Senast köpt objekt
* Senast visade objekt
* Mest visade objekt

### Mest visade

Visar de mest visade objekten på webbplatsen.

Med den här logiken kan du visa rekommendationer baserat på de mest visade objekten på webbplatsen för att öka konverteringsgraden för andra objekt. En mediewebbplats kan till exempel visa rekommendationer på sin hemsida för sina populäraste videor för att uppmuntra besökare att titta på ytterligare videor.

Den här logiken kan användas med följande rekommendationsnycklar:

* Aktuell kategori
* Anpassat attribut
* Favoritkategori
* Popularitet

### Folk som köpte den här, köpte den där

Visar objekt som andra besökare även har köpt och som har köpt det valda objektet.

Med den här logiken kan du öka möjligheterna till korsförsäljning genom att visa en rekommendation på en kundvagnssammanfattning, som t.ex. visar artiklar som andra köpare också har köpt. Om besökaren t.ex. köper en kostym kan rekommendationen visa ytterligare objekt som andra besökare har köpt, t.ex. slipsar, klädskor och kufflänkar. När besökarna granskar sina inköp ger ni dem ytterligare inköpsrekommendationer.

Den här logiken kan användas med följande rekommendationsnycklar:

* Aktuellt objekt
* Anpassat attribut
* Senast köpta artikel
* Senast visade objekt
* Mest visade objekt

### Folk som såg det här, köpte det

Visar andra objekt som köpts av besökare som visade det markerade objektet.

Med den här logiken kan du öka möjligheterna till korsförsäljning genom att visa en rekommendation på en produktsida, som till exempel visar objekt som andra besökare som visade det köpta objektet. Om besökaren till exempel tittar på en fiskepunkt kan rekommendationen visa ytterligare objekt som andra besökare tittar på objektet som köpts, som t.ex. kryssrutor, torn och fiskekurser. När besökarna besöker er webbplats kan ni ge dem ytterligare inköpsrekommendationer.

Den här logiken kan användas med följande rekommendationsnycklar:

* Aktuellt objekt
* Anpassat attribut
* Senast köpta artikel
* Senast visade objekt
* Mest visade objekt

### Folk som tittade på det här, såg det

Visar objekt som andra besökare också visade som visade det markerade objektet.

Med den här logiken kan du skapa ytterligare konverteringsmöjligheter genom att rekommendera objekt som andra besökare som tittade på ett objekt också kan se. Besökare som tittar på cyklar på er webbplats kan till exempel också titta på cykelhjälmar, cykelkit, lås osv. Du kan skapa en rekommendation med hjälp av den här logiken som föreslår andra produkter.

Den här logiken kan användas med följande rekommendationsnycklar:

* Aktuellt objekt
* Anpassat attribut
* Senast köpta artikel
* Senast visade objekt
* Mest visade objekt

### Tillhörighet till webbplats

Visar artiklar som använder en Adobe-algoritm för att rekommendera andra artiklar baserat på kriterier som produktsidor, inköp och kundvagnsaktiviteter (lägga till eller ta bort artiklar, visa kundvagnen osv.)

En onlinebutik kan t.ex. rekommendera artiklar som en besökare har visat intresse för under tidigare sessioner i efterföljande besök. Aktivitet för varje besökares session hämtas för att beräkna en affinitetspoäng baserat på en nyhet och frekvensmodell. När den här besökaren återgår till din webbplats används tillhörighet för att visa rekommendationer baserat på tidigare åtgärder på din webbplats.

Den här logiken kan användas med följande rekommendationsnycklar:

* Aktuellt objekt
* Senast köpta artikel
* Senast visade objekt
* Mest visade objekt

### De viktigaste säljarna

Visar de mest säljande objekten på webbplatsen baserat på besökarkonverteringar.

Med den här logiken kan du skapa rekommendationer för populära objekt på din webbplats för att öka konverteringen. Den här logiken passar särskilt bra för förstagångsbesökare på er webbplats.

Den här logiken kan användas med följande rekommendationsnycklar:

* Favoritkategori
* Popularitet
