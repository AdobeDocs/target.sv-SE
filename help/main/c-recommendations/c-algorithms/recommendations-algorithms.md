---
keywords: rekommendationer, algoritmer;modellutbildning;modellvisning;innehållsleverans;objektbaserad;användarbaserad;popularitetsbaserad;kundbaserad;kundbaserad;anpassade kriterier
description: Läs mer om algoritmerna som används i [!DNL Target Recommendations], inklusive modellutbildning och modellhantering.
title: Var kan jag lära mig om vetenskapen bakom Target's Recommendations Algorithms?
feature: Recommendations
mini-toc-levels: 2
exl-id: c156952b-8eda-491d-a68e-d3d09846f640
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '2763'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Forskningen bakom Target:s rekommendationsalgoritmer

En ingående beskrivning av algoritmerna som används i [!DNL Adobe Target Recommendations], inklusive logik och matematiska detaljer i modellutbildning och modelleringsprocessen.

Modellutbildning är processen för hur rekommendationer genereras av [!DNL Adobe Target] utbildningsalgoritmer. Modelltjänsten är så här [!DNL Target] ger rekommendationer till besökarna på webbplatsen (kallas även innehållsleverans).

[!DNL Target] innehåller följande breda typer av algoritmer i [!DNL Recommendations]:

* **Objektbaserade algoritmer**: Inkludera algoritmer som följer logiken&quot;Personer som visade/köpte det här objektet visade/köpte även dessa objekt.&quot; Dessa algoritmer grupperas under den paraplya termen objektbaserad samarbetsfiltrering samt [!UICONTROL Items with Similar Attributes] algoritmer.

* **Användarbaserade algoritmer**: Inkludera [!UICONTROL Recently Viewed] och [!UICONTROL Recommended for You] algoritmer.

* **Popularitetsbaserade algoritmer**: Inkludera algoritmer som returnerar de mest visade eller mest köpta objekten på webbplatsen, eller toppvisade eller toppköpta efter kategori eller objektattribut.

* **Cart-baserade algoritmer**: Inkludera rekommendationer som baseras på flera objekt med logiken&quot;personer som visade/köpte dessa objekt, även visade/köpte dem&quot;.

* **Anpassade villkor**: Inkludera rekommendationer baserade på anpassade filer som överförts till [!DNL Target].

>[!NOTE]
>
>Mer allmän information om varje algoritmtyp och de enskilda algoritmerna finns i [Basera rekommendationen på en rekommendationsnyckel](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

Många av de algoritmer som anges ovan beror på om det finns en eller flera nycklar. Dessa nycklar används för att hämta liknande objekt vid innehållsleverans (när rekommendationer görs). Kundspecificerade nycklar kan inkludera det objekt som någon visar, det senast visade eller köpta objektet, det översta objektet, den aktuella kategorin eller favoritkategorin för den besökaren. Andra algoritmer, t.ex. kundvagnsbaserade eller användarbaserade rekommendationer, använder implicita nycklar (som inte kan konfigureras av kunden). Mer information finns i *Rekommendationsnycklar*, in [Basera rekommendationen på en rekommendationsnyckel](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys). Observera dock att dessa nycklar endast är relevanta vid modellanvändning (innehållsleverans). Dessa knappar påverkar inte tidslogiken för&quot;offline&quot; eller modellutbildning.

I följande avsnitt grupperas algoritmer på ett något annorlunda sätt än de algoritmtyper som beskrivs ovan. Följande gruppering baseras på likheterna i modellens utbildningslogik.

## Samarbetsfiltrering av objekt

Algoritmer är:

* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Rekommendationsalgoritmer för filtrering av objekt-objekt baseras på tanken att du bör använda beteendemönstren för många användare (och därigenom samarbeta) för att ge användbara rekommendationer för ett visst objekt (t.ex. filtrera katalogen med möjliga objekt att rekommendera). Även om det finns många olika algoritmer som faller under det allmänna paraplyet i [samarbetsfiltrering](https://en.wikipedia.org/wiki/Collaborative_filtering), använder dessa algoritmer generellt beteendedatakällor som indata. I [!DNL Target Recommendations]är de här inmatningarna de unika vyerna och användarnas inköp av artiklar.

För algoritmen&quot;personer som visade/köpte det här objektet även visade/köpte dessa objekt&quot; är målet att beräkna en likhet som (A,B) mellan alla par av objekt. För en given post A ordnas de översta rekommendationerna sedan efter deras likhet som (A,B).

Ett exempel på en sådan likhet är den samförekomst som finns mellan objekten: ett enkelt antal användare som har köpt båda artiklarna. Även om det är intuitivt är en sådan mätmetod naiv eftersom den är partisk med att rekommendera populära objekt. Om till exempel de flesta i en livsmedelsbutik köper bröd, kommer brödet att vara mycket vanligt tillsammans med alla artiklar, men det behöver inte vara en bra rekommendation. [!DNL Target] I används i stället ett mer avancerat likhetsmått som kallas log Sability ratio (LLR). Den här kvantiteten är stor när sannolikheten för att två artiklar, A och B, inträffar samtidigt skiljer sig mycket från sannolikheten för att de inte inträffar samtidigt. Ett exempel på [!UICONTROL People Who Viewed This, Bought That] algoritm. Likheten i LLR är stor när sannolikheten att B köptes är *not* oberoende av om någon visade A.

Om

![Formel för den visade/köpta algoritmen](assets/formula.png)

bör punkt B inte rekommenderas för post A. Fullständig information om den här likhetsberäkningen av loggsannolikhetsgrad finns [i PDF](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf).

Det logiska flödet för den faktiska algoritmimplementeringen visas i följande schematiska diagram:

![Schematiskt diagram över en visad/köpt algoritm](assets/diagram1.png)

Här följer information om de här stegen:

* **Indata**: Beteendedata, i form av visningar och köp av besökare som samlats in när du [implementera mål](https://developer.adobe.com/target/implement/recommendations/){target=_blank} eller från [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **Modellutbildning**:

   * **Rensa och sampla data**: För algoritmer med N-dagars uppslag filtreras beteendedata först så att endast de N-dagars data inkluderas. Samlingsregler och globala undantag tillämpas sedan för att ta bort objekt som inte bör rekommenderas. Alla besökare som interagerade med mer än 1 000 artiklar får dessutom endast 1 000 uppgifter.
   * **Beräkning av likhet i objekt**: Detta är det grundläggande datorsteget: beräkna hur lika sannolikhetsgraden för loggar är mellan alla objektpar i ett kandidatobjekt och rangordna objektspar med detta likhetsresultat.
   * **Offlinefiltrering**: Slutligen tillämpas alla andra tillämpliga dynamiska filter (till exempel undantag för dynamiska kategorier). Efter det här steget cachelagras förberäknade rekommendationer globalt så att de kan användas.

* **Modelltjänst**: Recommendations-material levereras från [!DNL Target]&#39;s [globalt &quot;Edge&quot;-nätverk](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934). När mbox-begäranden görs till [!DNL Target] och det fastställs att rekommendationsinnehållet ska skickas till sidan, begäran om lämplig [objektnyckel](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys) för rekommendationsalgoritmen antingen tolkas från begäran eller slås upp från användarprofilen och används sedan för att hämta de rekommendationer som beräknats i föregående steg. Ytterligare dynamiska filter tillämpas nu, före [design](/help/main/c-recommendations/c-design-overview/create-design.md) återges.

## Likhet i innehåll

Algoritm:

* [!UICONTROL Items with Similar Attributes]

I den här typen av algoritm anses två objekt vara relaterade om deras namn och textbeskrivningar är semantiskt lika. Till skillnad från de flesta rekommendationsalgoritmer där beteendedatakällor måste användas, använder algoritmer för innehållets likhet metadata från produktkataloger för att härleda likheterna mellan objekt. [!DNL Target] kan därför leda till rekommendationer i så kallade&quot;kallstart&quot;-scenarier där inga beteendedata har samlats in (till exempel i början av en [!DNL Target] aktivitet).

Även om modellservning och innehållsleverans är [!DNL Target]Likhetsalgoritmer för innehåll är identiska med andra objektbaserade algoritmer. Modellutbildningsstegen är helt olika och omfattar en serie naturliga språkbehandlings- och förbearbetningssteg enligt bilden nedan. Kärnan i likhetsberäkningen är användningen av den koniska likheten hos modifierade tf-idf-vektorer som representerar varje objekt i katalogen.

![Diagram som visar flödet i likhetsprocessen för innehåll](assets/diagram2.png)

Här följer information om de här stegen:

* **Indata**: Den här algoritmen är som tidigare enbart baserad på katalogdata (hämtas från [!DNL Target] via [Katalogfeed, Entity API eller från siduppdateringar](https://developer.adobe.com/target/implement/recommendations/){target=_blank}.

* **Modellutbildning**:

   * **Attributextrahering**: Efter användning av vanliga statiska filter, katalogregler och globala undantag extraherar den här algoritmen relevanta textfält från entitetsschemat. [!DNL Target] använder namn-, meddelande- och kategorifälten från entitetsattributen och försöker extrahera alla strängfält från anpassade [entitetsattribut](/help/main/c-recommendations/c-products/entity-attributes.md). Detta görs genom att se till att merparten av värdena för det fältet inte kan tolkas som ett tal, datum eller booleskt värde.
   * **Ordstam och ordstopp**: För exaktare matchning av textlikhet är det klokt att ta bort mycket vanliga &quot;stopp&quot;-ord som inte ändrar innebörden av ett objekt i någon större utsträckning (t.ex. &quot;var&quot;, &quot;is&quot;, &quot;och&quot; o.s.v.). På samma sätt hänvisar ordstammen till processen att minska ord med olika suffix till deras rotord, som har en identisk betydelse (till exempel &quot;connect&quot;, &quot;connecting&quot; och &quot;connection&quot;), som alla har samma rotord: &quot;connect&quot;). [!DNL Target] använder Snowball-stammen. [!DNL Target] utför automatisk språkidentifiering först, och kan stoppa ordborttagning för upp till 50 språk och härleda för 18 språk.
   * **Skapa n-gram**: Efter föregående steg behandlas varje ord som en token. Att kombinera sekvenser av variabler i en enda token kallas för att skapa n-gram. [!DNL Target]Algoritmer tar upp till 2 gram.
   * **tf-idf-beräkning**: Nästa steg är att skapa tf-idf-vektorer som återspeglar tokens relativa betydelse i objektbeskrivningen. För varje token/term t i ett objekt i, i en katalog D med |D| objekt, termen frekvens TF(t, i) beräknas först (antalet gånger termen visas i objektet i) samt dokumentfrekvensen DF(t, D). Det vill säga antalet objekt där token finns. Tf-idf-måttet är sedan

      ![Formel som visar tf-idf-mått](assets/formula2.png)

      [!DNL Target] använder Apache Sparks *tf-idf* funktionsimplementering, som under huven hashar varje token till ett utrymme på 218 tokens. I det här steget tillämpas också den kundspecificerade attributförbättringen och nedladdningen genom att termfrekvenserna i varje vektor justeras baserat på inställningarna i [kriterier](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

   * **Beräkning av likhet i objekt**: Den sista likhetsberäkningen för objekt görs med en ungefärlig cosinuslikhet. För två objekt: *A* och *B*, med vektorerna tA och tB, definieras cosinus-likhet som:

      ![Formel som visar beräkning av likhet för objekt](assets/formula3.png)

      För att undvika en betydande komplexitet när det gäller att beräkna likheter mellan alla N x N-poster har *tf-idf* vektorn trunkeras så att den bara innehåller sina största 500 poster och sedan beräknas cosinus-likheter mellan objekten med denna trunkerade vektorrepresentation. Detta tillvägagångssätt visar sig vara mer robust för likhetsberäkningar för gles vektor, jämfört med andra approximativa närliggande (ANN) tekniker, t.ex. lokaliseringskänslig hash.

   * **Modelltjänst**: Den här processen är identisk med samarbetsfiltreringstekniker för objektobjekt som beskrivs i föregående avsnitt.

## Rekommendationer med flera tangenter

Algoritmer är:

* Cart-baserade rekommendationer
* [!UICONTROL Recommended For You]

De senaste tilläggen i [!DNL Target] en serie rekommendationsalgoritmer är [!UICONTROL Recommended For You] och en serie Cart-baserade rekommendationer-algoritmer. Båda typerna av algoritmer använder tekniker för samarbete vid filtrering för att skapa individuella objektbaserade rekommendationer. Sedan kan flera objekt i användarens webbläsarhistorik (för [!UICONTROL Recommended For You]) eller användarens aktuella kundvagn (för kundvagnsbaserade rekommendationer) används för att hämta dessa artikelbaserade rekommendationer, som sedan sammanfogas för att utgöra den slutliga listan med rekommendationer. Observera att det finns många varianter av personaliserade rekommendationsalgoritmer. Valet av en flernyckelalgoritm innebär att rekommendationer är omedelbart tillgängliga efter det att en besökare har en webbläsarhistorik och rekommendationer kan uppdateras för att svara på den senaste besökarfunktionen.

Dessa algoritmer bygger på de grundläggande filtertekniker för samarbete som beskrivs i det objektbaserade rekommendationsavsnittet, men innehåller även hyperparameterjustering för att fastställa det optimala likhetsmåttet mellan objekten. Algoritmen utför en kronologisk delning av beteendedata för varje användare, och utbildar rekommendationsmodeller på tidigare data samtidigt som man försöker förutsäga objekt som en användare tittar på eller köper senare. Likhetsmåttet som ger optimalt resultat [Genomsnittlig precision](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval)#Mean_average_precision) väljs sedan.

Logiken i modellutbildning och poängsättning visas i följande diagram:

![Diagram som visar logiken i modellutbildning och poängsättning](assets/diagram3.png)

Här följer information om de här stegen:

* **Indata**: Detta är identiskt med CF-metoder (item-item collaborative filtering). [!UICONTROL Both Recommended For You] och Cart-baserade algoritmer använder beteendedata, i form av visningar och köp av användare som samlas in när du [implementera mål](https://developer.adobe.com/target/implement/recommendations/){target=_blank} eller från [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **Modellutbildning**:

   * **Rensa och sampla data**: Detta är samma sak som för samarbetsfiltreringsmetoder, där uppslagsfönstret används för att filtrera beteendedata till ett lämpligt datumintervall, följt av katalogregler och globala undantag. Besökare som har interagerat med mer än 1 000 objekt har bara de senaste 1 000 användningarna.
   * **Tågprovsdelning**: Utför en kronologisk delning av användningsområdena för varje användare och allokera de första 80 % av användarens användning till utbildningsdata, och återstående 20 % allokeras till testdata.
   * **Artikellikhet - modellutbildning**: Beräkningen av likhet för huvudobjekt skiljer sig åt för [!UICONTROL Recommended For You] och Cart-baserade algoritmer i det sätt på vilket vektorer för förslagsobjekt skapas. För [!UICONTROL Recommended For You], har artikelvektorerna dimensionerna NUsers, där varje post representerar summan av implicita klassificeringar för den användaren av artikeln - inköp av ett objekt får en vikt på 2x den för artikelns vyer. För Cart-baserade rekommendationer har objektvektorerna binära poster. om beteendet under en session endast ska beaktas, finns det en ny post för varje session. Annars finns det en post i den här objektvektorn för varje besökare.

   Utbildningssteget beräknar flera typer av likheter med vektorer: LLR-likhet ([här](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)), cosinus likhet (definierad tidigare) och en normaliserad L2-likhet, definierad som:

   ![Formel som visar beräkning av utbildning](assets/formula4.png)

   * **Utvärdering av objektlikhetsmodell**: Modellutvärderingen görs genom att rekommendationerna som genererades i det föregående steget följs och att man gör prognoser för testdatauppsättningen. Onlinebedömningsfasen härleds genom att varje användares objektanvändning i testdatauppsättningen ordnas kronologiskt och sedan görs 100 rekommendationer för ordnade deluppsättningar av objekt i ett försök att förutse efterföljande vyer och inköp. En informationshämtning, [Genomsnittlig precision](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval)#Mean_average_precision), används för att utvärdera kvaliteten på dessa rekommendationer. Detta mätresultat tar hänsyn till rekommendationsordningen och prioriterar relevanta poster högre upp i listan över rekommendationer, som är en viktig egenskap för rangordningssystem.
   * **Modellval**: Efter offlineutvärdering väljs den modell som har den högsta genomsnittliga precisionen och alla rekommendationer för enskilda artiklar beräknas för den.
   * **Offlinefiltrering**: Det sista steget i modellutbildningen är att tillämpa eventuella tillämpliga dynamiska filter. Efter det här steget cachelagras förberäknade rekommendationer globalt så att de kan användas.


* **Modelltjänst**: Till skillnad från tidigare algoritmer där rekommendationer ska hanteras måste en enda nyckel för hämtning anges, följt av tillämpning av affärsregler, [!UICONTROL Recommended for You] och Cart-baserade algoritmer använder en mer komplex körningsprocess.

   * **Hämtning och sammanslagning av flera tangenter**: För kundvagnsbaserade rekommendationer räknas upp till tio artiklar som skickas i kundvagnen som nycklar för hämtning och rekommendationer från var och en av dem viktas lika. För [!UICONTROL Recommended for You], upp till de senaste fem unika visade objekten och de senaste fem unika inköpta objekten betraktas som nycklar för hämtning, där rekommendationer från inköpta artiklar viktas dubbelt så mycket som rekommendationer från visade artiklar. När du sammanfogar rekommendationer, om ett objekt visas i flera individuella listor med rekommendationer, läggs dess viktade likhetspoäng till. Den sista listan med rekommendationer från det här steget är sedan den sammanfogade listan med omviktade rekommendationer, rankade i fallande ordning.
   * **Filtrering**: Därefter tillämpas filtreringsregler som borttagning av tidigare visade och/eller köpta objekt samt andra dynamiska affärsregler.

De här processerna illustreras i följande bild, där en besökare har visat objekt A och köpt objekt B. Individuella rekommendationer hämtas med likhetspoängen offline som visas under varje objektetikett. Efter hämtning sammanfogas rekommendationerna med viktade likhetsresultat. I ett scenario där kunden har angett att tidigare visade och köpta artiklar måste filtreras bort, tar filtreringssteget bort A och B från listan med rekommendationer.

![Diagram som visar bearbetning av flernyckelalgoritmer](assets/diagram4.png)

## Popularitetsbaserad

Algoritmer är:

* [!UICONTROL Most Viewed Across the Site]
* [!UICONTROL Most Viewed by Category]
* [!UICONTROL Most Viewed by Item Attribute]
* [!UICONTROL Top Sellers Across the Site]
* [!UICONTROL Top Sellers by Category]
* [!UICONTROL Top Sellers by Item Attribute]

[!DNL Target] innehåller popularitetsbaserade algoritmer för både de mest visade objekten och de främsta säljartiklarna på en webbplats eller uppdelade efter ett objektattribut eller en kategori. Popularitetsbaserade algoritmer rangordnar objekt baserat på det antal sessioner i vilka det objektet visades eller köptes under en given tidsram.

Alla dessa algoritmer kombinerar aggregerade beteendedata där det totala antalet sessioner där objekt visades och köptes registreras med upplösningar både varje timme och varje dag. Enskilda algoritmer hittar sedan de mest visade eller köpta objekten för kundens konfigurerade fönster för sökning.

Enskilda algoritmenheter är följande:

* [!UICONTROL Most Viewed Across the Site] och [!UICONTROL Top Sellers Across the Site] rangordna artiklar efter det sammanlagda antalet sessioner där dessa artiklar visades respektive köptes. Utdata är en enda (nyckellös) lista med rekommenderade objekt.
* De flesta visade/populära säljarna efter kategori/artikelattribut är rekommendationer där artiklar sorteras efter det sammanlagda antalet sessioner där dessa artiklar visades eller köptes, men grupperas efter artikelkategorin eller det specifika artikelattributet. Utdata är listor med rekommenderade objekt, ordnade efter kategorivärden eller värden för objektattribut.

## Senast visade

Algoritmen&quot;nyligen visade&quot; rekommendationer möjliggör anpassning av rekommendationer under sessioner. Den här algoritmen kräver ingen &quot;modellutbildning offline&quot;. Istället [!DNL Target] använder den unika [Besökarprofil](/help/main/c-target/c-visitor-profile/visitor-profile.md) för att upprätthålla en löpande lista över objekt som har visats under en given session och som kan visa dessa objekt i rekommendationer. På så sätt kan du uppdatera rekommendationer i realtid och personalisera nästa sida.

## Egna villkor

Med anpassade kriterier kan kunderna [överför sina egna rekommendationer till [!DNL Target]](/help/main/c-recommendations/c-algorithms/recommendations-csv.md), vilket ger stor flexibilitet och gör det möjligt att&quot;ta fram en egen modell&quot;. Anpassade kriterier ersätter delen&quot;offline-utbildning&quot; i [!UICONTROL Item-Based] rekommendationer, men fungerar på ungefär samma sätt som artikelbaserade rekommendationsalgoritmer under innehållsleveransfasen online, eftersom en enda nyckel används för att hämta rekommendationer och affärsregler/filter sedan tillämpas.
