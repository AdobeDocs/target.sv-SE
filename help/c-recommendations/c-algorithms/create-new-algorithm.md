---
keywords: villkor;algoritm;branschvertikal;sidtyp;rekommendationsnyckel;rekommendationslogik;logik;dataintervall;uppslagsfönster;beteendedatakälla;partiell design;säkerhetskopieringsrekommendationer;inkluderingsregler;attributvikt;aktuell kategori;anpassat attribut;senast visade objekt;senast visade objekt;senast visade objekt;senast visade objekt;senast visade objekt;senast visade objekt;senast visade;favoriter;senast visade
description: Lär dig hur du skapar villkor som styr innehållet i dina Adobe Recommendations-aktiviteter för att visa de rekommendationer som är mest lämpliga för din aktivitet.
title: Hur skapar jag kriterier i Recommendations?
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
source-git-commit: 3cccd4879133a8d222b970c92ebcef3df7a028a3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# ![PREMIUM](/help/assets/premium.png) Skapa villkor

Kriterier i [!UICONTROL Adobe Target] [!UICONTROL Recommendations] styr innehållet i [!UICONTROL Recommendations] verksamhet. Skapa villkor för att visa de rekommendationer som passar bäst för din aktivitet. Dessa kriterier använder besökarens åtgärder för att avgöra vilket innehåll eller vilka produkter som ska visas.

I följande avsnitt beskrivs hur du skapar nya villkor.

## Öppna skärmen Skapa nya villkor

Det finns flera sätt att nå [!UICONTROL Create New Criteria] skärm. Vissa skärmalternativ varierar beroende på hur du kommer till skärmen.

* På **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** biblioteksskärm, klicka **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Kriterierna som du skapar här blir automatiskt tillgängliga för alla [!DNL Recommendations] verksamhet.
* När du skapar en [!DNL Recommendations] aktivitet med [!UICONTROL Visual Experience Composer] (VEC) kommer du omedelbart till [!UICONTROL Select Criteria] när du har markerat ett element på sidan och klickat [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before], eller [!UICONTROL Insert Recommendations After]. Du kan sedan välja ett tillgängligt villkor eller klicka på **[!UICONTROL Create Criteria]**. Om du skapar ett nytt villkor kan du välja att spara villkoret för användning med andra villkor [!DNL Recommendations] verksamhet. Mer information finns i [Skapa en Recommendations-aktivitet](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* När du redigerar en [!DNL Recommendations] aktivitet, klicka på en [!UICONTROL Recommendations Location] och väljer **[!UICONTROL Change Criteria]**. På [!UICONTROL Select Criteria] skärm, klicka **[!UICONTROL Create Criteria]**. Du kan spara dina nya villkor och använda dem tillsammans med andra [!DNL Recommendations] verksamhet.

Följande steg förutsätter att du har åtkomst till [!UICONTROL Create New Criteria] skärm med den första metoden: den **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** biblioteksskärm.

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Klicka på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**.

   ![Skapa nya villkor](assets/CreateNewCriteria_full-new.png)

1. Konfigurera informationen i följande avsnitt.

## [!UICONTROL Basic Information] {#info}

1. Skriv a **[!UICONTROL Criteria Name]**.

   Detta är det&quot;interna&quot; namnet som används för att beskriva kriterierna. Du kanske vill kalla villkoren för&quot;Produkter med högsta marginal&quot;, men du vill inte att den titeln ska visas offentligt. Se nästa steg för att ange den offentliga titeln.

   ![Avsnittet Grundläggande information](assets/basic-information.png)

1. Ange en offentlig **[!UICONTROL Display Title]** visas på sidan för rekommendationer som använder det här villkoret.

   Du kan till exempel visa&quot;Personer som visade det här&quot; eller&quot;Liknande produkter&quot; när du använder det här villkoret för att visa rekommendationer.

1. Skriv en kort **[!UICONTROL Description]** av kriterierna.

   Beskrivningen bör hjälpa dig att identifiera villkoren och kan innehålla information om syftet med kriterierna.

1. Välj en vertikal bransch baserat på målen för dina rekommendationer.

   | Branschvertikal | Mål |
   |--- |--- |
   | Detaljhandel/e-handel | Konvertering som resulterar i inköp |
   | Leadgenerering/B2B/Finansiella tjänster | Konvertering utan köp |
   | Media/publicering | Engagemang |

   Andra kriteriealternativ ändras beroende på vilken vertikal du väljer.

1. Välj en **[!UICONTROL Page Type]**.

   Du kan välja flera sidtyper.

   Tillsammans används de vertikala metoderna och sidtyperna för att kategorisera de sparade villkoren, vilket gör det enklare att återanvända villkor för andra [!DNL Recommendations] verksamhet.

## [!UICONTROL Recommendations Algorithm] {#rec-algo}

1. Välj en **[!UICONTROL Algorithm Type]** och **[!UICONTROL Algorithm]**:

   ![Rekommenderat algoritmavsnitt](assets/recommended-algorithm.png)

   | Algoritmtyp | När ska användas | Tillgängliga algoritmer |
   | --- | --- | --- |
   | [!UICONTROL Cart-Based] | Utför rekommendationer baserat på användarens kundvagnsinnehåll. | <ul><li>Folk som såg de här, såg dem</li><li>Folk som såg de här, köpte de där</li><li>Folk som köpte de här, köpte de där</li></ul> |
   | [!UICONTROL Popularity-Based] | Utför rekommendationer baserat på hur populärt ett objekt på webbplatsen är eller utifrån hur populärt det är att ha objekt inom en användares favoritkategori, varumärke, genre osv. | <ul><li>Visas bäst på webbplatsen</li><li>Mest visade per kategori</li><li>Mest visad av objektattribut</li><li>De största säljarna på webbplatsen</li><li>De viktigaste säljarna per kategori</li><li>De viktigaste säljarna efter artikelattribut</li><li>Top by Analytics Metric</li></ul> |
   | [!UICONTROL Item-Based] | Rekommendationer baserade på sökning efter liknande objekt för ett objekt som användaren för närvarande visar eller nyligen har visat. | <ul><li>Folk som tittade på det här, såg det</li><li>Folk som såg det här, köpte det</li><li>Folk som köpte den här, köpte den där</li><li>Objekt med liknande attribut</li></ul> |
   | [!UICONTROL User-Based] | Utför rekommendationer baserat på användarens beteende. | <ul><li>Senast visade objekt</li><li>Rekommenderas för dig</li></ul> |
   | [!UICONTROL Custom Criteria] | Utför rekommendationer baserat på en anpassad fil som du överför. | <ul><li>Anpassad algoritm</li></ul> |

   >[!NOTE]
   >
   >Om du väljer **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]** kan du ange att [likhetsregler för innehåll](#similarity).

1. Välj en **Objektattribut** och **Profilattribut att matcha**, a **Rekommendationsnyckel**, **Filtreringsnyckel** och/eller **Analytics-mått** för att konfigurera algoritmen.

De återstående alternativen för algoritmkonfigurationen varierar beroende på den valda algoritmen. Om du vill avsluta konfigurationen av algoritmen väljer du en [!UICONTROL Recommendation Key], [!UICONTROL Filtering Key], [!UICONTROL Co-Occurrence Basis], [!UICONTROL Analytics Metric]och/eller [!UICONTROL Item Attribute] och [!UICONTROL Profile Attribute to Match].

Mer information om hur du väljer en [!UICONTROL Recommendation Key], se [Basera rekommendationen på en rekommendationsnyckel](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## [!UICONTROL Data Source] {#data-source}

1. Markera önskat **[!UICONTROL Behavioral Data Source]**: [!UICONTROL Adobe Target] eller [!UICONTROL Analytics].

   >[!NOTE]
   >
   >The [!UICONTROL Behavioral Data Source] visas bara om implementeringen använder [Analyser för Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Avsnittet Beteendedatakälla](assets/data-source.png)

   Om du valde [!UICONTROL Analytics]väljer du önskad rapportserie.

   Om kriterierna använder [!DNL Adobe Analytics] När den beteendemässiga datakällan har skapats beror tiden för kriteriernas tillgänglighet på om den valda rapportsviten och uppslagsfönstret har använts för andra villkor, vilket förklaras nedan:

   * **Installation av engångsavisering**: Första gången en rapportsvit används med ett visst fönster för dataintervallsökning, [!DNL Target Recommendations] kan ta mellan två och sju dagar att helt hämta beteendedata för den valda rapportsviten från [!DNL Analytics]. Den här tidsramen är beroende av [!DNL Analytics] systembelastning.
   * **Nya eller redigerade villkor med hjälp av ett rapportpaket som redan är tillgängligt**: När du skapar ett nytt villkor eller redigerar ett befintligt villkor, om den valda rapportsviten redan har använts med [!DNL Target Recommendations], med ett dataintervall som är lika med eller mindre än det markerade dataintervallet, är data omedelbart tillgängliga och ingen engångsinställning krävs. I det här fallet, eller om en algoritms inställningar redigeras utan att den valda rapportsviten eller dataintervallet ändras, körs eller körs om inom 12 timmar.
   * **Pågående algoritmkörningar**: Dataflöden från [!DNL Analytics] till [!DNL Target Recommendations] dagligen. För [!UICONTROL Viewed Affinity] när en användare tittar på en produkt skickas ett spårningsanrop till produktvyn till [!DNL Analytics] nära realtid. The [!DNL Analytics] data skickas till [!DNL Target] tidigt nästa dag och [!DNL Target] kör algoritmen på mindre än 12 timmar.

   Mer information finns i [Använd Adobe Analytics med Recommendations som mål](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

1. Ange **[!UICONTROL Lookback Window]** för att fastställa tidsintervallet för tillgängliga historiska användarbeteendedata som ska användas när du fastställer vilka rekommendationer som ska visas. Det här alternativet är tillgängligt för alla algoritmer med undantag för objekt med liknande attribut och anpassade algoritmer.

   ![Fönsterreglage för uppslag](assets/data-range.png)

   Om det finns mycket trafik och beteenden på platsen ändras ofta väljer du ett kortare datafönster. Ett kortare fönster ger [!DNL Recommendations] för att kunna reagera bättre på förändringar på marknaden och i er verksamhet. Ett kortare fönster betyder till exempel att [!DNL Recommendations] kommer att upptäcka förändringar i besökarnas beteende när besökarna börjar handla säsongsinriktat, t.ex. handla på skolstarten eller jul, och rekommendera artiklar som passar för dessa shoppingsäsonger.

   Om du inte har så mycket data eller besökarbeteendet inte ändras så ofta kan du välja ett längre fönster. För många webbplatser ger dock ett kortare fönster bättre rekommendationer.

   De tillgängliga dataintervallen är:

   | Alternativet Fönster för uppläsning | Uppdaterad frekvens (visas vid hovring) | Symboler som stöds |
   | --- | --- | --- |
   | Sex timmar | Algoritmen körs var 3:e till 6:e timme | [!UICONTROL Popularity-Based] algoritmer när det markerade [!UICONTROL Behavioral Data Source] är [!DNL Adobe Target] |
   | En dag | Algoritmen körs var 12-24:e timme | [!UICONTROL Popularity-Based] algoritmer |
   | Två dagar | Algoritmen körs var 12-24:e timme | <ul><li>[!UICONTROL Popularity-Based] algoritmer</li><li>[!UICONTROL Item-Based] algoritmer</li><li>[!UICONTROL User-Based] algoritmer</li><li>[!UICONTROL Cart-Based] algoritmer</li></ul> |
   | En vecka | Algoritmen körs var 24:e till 48:e timme | <ul><li>[!UICONTROL Popularity-Based] algoritmer</li><li>[!UICONTROL Item-Based] algoritmer</li><li>[!UICONTROL User-Based] algoritmer</li><li>[!UICONTROL Cart-Based] algoritmer</li></ul> |
   | Två veckor | Algoritmen körs var 24:e till 48:e timme | <ul><li>[!UICONTROL Popularity-Based] algoritmer</li><li>[!UICONTROL Item-Based] algoritmer</li><li>Alla [!UICONTROL User-Based] algoritmer</li><li>[!UICONTROL Cart-Based] algoritmer</li></ul> |
   | En månad (30 dagar) | Algoritmen körs var 24:e till 48:e timme | <ul><li>[!UICONTROL Popularity-Based] algoritmer</li><li>[!UICONTROL Item-Based] algoritmer</li><li>[!UICONTROL User-Based] algoritmer</li><li>[!UICONTROL Cart-Based] algoritmer</li></ul> |
   | Två månader (61 dagar) | Algoritmen körs var 24:e till 48:e timme | <ul><li>[!UICONTROL Popularity-Based] algoritmer</li><li>[!UICONTROL Item-Based] algoritmer</li><li>[!UICONTROL User-Based] algoritmer</li><li>[!UICONTROL Cart-Based] algoritmer</li></ul> |

## [!UICONTROL Backup Content] {#content}

[!UICONTROL Backup Content] regler avgör vad som händer om antalet rekommenderade objekt inte fyller dina [rekommendationsdesign](/help/c-recommendations/c-design-overview/design-overview.md). Det är möjligt för [!DNL Recommendations] för att returnera färre rekommendationer än vad designen kräver. Om din design till exempel har platser för fyra objekt, men dina villkor bara leder till att två objekt rekommenderas, kan du lämna de återstående platserna tomma, du kan använda rekommendationer för säkerhetskopiering för att fylla de extra platserna, eller så kan du välja att inte visa några rekommendationer.

![Innehållsavsnitt](assets/content.png)

1. (Valfritt) Skjut **[!UICONTROL Partial Design Rendering]** växla till&quot;på&quot;-positionen.

   Så många kortplatser som möjligt kommer att fyllas, men designmallen kan innehålla tomt utrymme för återstående kortplatser. Om det här alternativet är inaktiverat och det inte finns tillräckligt med innehåll för att fylla alla tillgängliga platser, kommer inga rekommendationer att visas och standardinnehåll visas i stället.

   Aktivera det här alternativet om du vill att rekommendationer ska hanteras med tomma platser. Använd rekommendationer för säkerhetskopiering om du vill att rekommendationsplatserna ska fyllas med innehåll baserat på dina kriterier med tomma platser fyllda med liknande eller populärt innehåll från platsen, vilket förklaras i nästa steg.

1. (Valfritt) Skjut **[!UICONTROL Show Backup Content]** växla till&quot;på&quot;-positionen.

   Fyll eventuella återstående tomma platser i designen med ett slumpmässigt urval av de mest visade produkterna från hela webbplatsen.

   Genom att använda rekommendationer för säkerhetskopiering försäkrar du dig om att din rekommendationsdesign fyller alla tillgängliga platser. Anta att du har en design på 4 x 1 enligt nedan:

   ![4 x 1-design](/help/c-recommendations/c-design-overview/assets/velocity_example.png)

   Anta att dina kriterier gör att bara två objekt rekommenderas. Om du aktiverar [!UICONTROL Partial Design Rendering] de första två kortplatserna fylls, men de återstående två kortplatserna förblir tomma. Om du aktiverar [!UICONTROL Show Backup Recommendations] de första två kortplatserna fylls i baserat på dina angivna villkor och de återstående två kortplatserna fylls i baserat på dina rekommendationer för säkerhetskopiering.

   I följande matris visas resultatet som du får se när du använder [!UICONTROL Partial Design Rendering] och [!UICONTROL Backup Content] alternativ:

   | Delvis designåtergivning | Säkerhetskopiera innehåll | Resultat |
   |--- |--- |--- |
   | Handikappade | Handikappade | Om färre rekommendationer returneras än vad designen kräver ersätts rekommendationsdesignen med standardinnehåll och inga rekommendationer visas. |
   | Aktiverad | Handikappade | Designen återges, men kan innehålla tomt utrymme om färre rekommendationer returneras än vad designanropen kräver. |
   | Aktiverad | Aktiverad | Rekommendationer för säkerhetskopiering fyller i tillgängliga designfack och återger designen helt.<br>Om inkluderingsregler tillämpas på rekommendationer för säkerhetskopiering, begränsas antalet kvalificerade rekommendationer för säkerhetskopiering till den punkt där designen inte kan fyllas, återges designen delvis.<br>Om villkoret inte returnerar några rekommendationer, och inkluderingsreglerna begränsar rekommendationerna för säkerhetskopiering till noll, ersätts designen med standardinnehåll. |
   | Handikappade | Aktiverad | Rekommendationer för säkerhetskopiering fyller i tillgängliga designfack och återger designen helt.<br>Om inkluderingsregler tillämpas på rekommendationer för säkerhetskopiering, begränsas antalet kvalificerade rekommendationer för säkerhetskopiering till den punkt där designen inte kan fyllas, ersätts designen med standardinnehåll och inga rekommendationer visas. |

   Mer information finns i [Använd en rekommendation för säkerhetskopiering](/help/c-recommendations/c-algorithms/backup-recs.md).

1. (Villkorligt) Om du har valt **[!UICONTROL Show Backup Content]** i föregående steg kan du aktivera **[!UICONTROL Apply inclusion rules to backup recommendations]**.

   Inkluderingsregler avgör vilka objekt som tas med i dina rekommendationer. Vilka alternativ som är tillgängliga beror på var du arbetar vertikalt.

   Mer information finns i [Ange inkluderingsregler](#inclusion) nedan.

1. (Valfritt) Skjut **[!UICONTROL Recommend Previously Purchased Items]** växla till&quot;på&quot;-positionen.

   Den här inställningen baseras på `productPurchasedId`. Standardbeteendet är att inte rekommendera tidigare inköpta artiklar. I de flesta fall vill du inte marknadsföra artiklar som en kund nyligen har köpt. Det är användbart om du säljer artiklar som normalt bara köps en gång, t.ex. kajaker. Om du säljer artiklar som personer återkommer till att köpa igen upprepade gånger, som schampo eller andra personliga artiklar, bör du aktivera det här alternativet.

## Liknande innehåll {#similarity}

Använd [!UICONTROL Content Similarity] regler som gör rekommendationer baserade på objekt- eller medieattribut.

>[!NOTE]
>
>Om du valde **[!UICONTROL Item-Based]**/ **[!UICONTROL Media with Similar Attributes]** som din algoritmtyp och algoritm kan du ange regler för innehållets likhet.

Innehållslikhet jämför nyckelord för objektattribut och gör rekommendationer baserat på hur många nyckelord olika objekt har gemensamt. Recommendations baserat på innehållets likhet kräver inte tidigare data för att ge ett starkt resultat.

Att använda innehållets likhet för att generera rekommendationer är särskilt effektivt för nya objekt, som troligen inte visas i rekommendationer med hjälp av *Folk som tittade på det här, såg det* och annan logik som bygger på tidigare beteende. Ni kan också använda innehållets likhet för att generera användbara rekommendationer för nya besökare som inte har några tidigare inköp eller andra historiska data.

När du väljer **[!UICONTROL Item-Based]**/ **[!UICONTROL Media with Similar Attributes]** kan du skapa regler för att öka eller minska vikten av specifika objektattribut när du fastställer rekommendationer. För t.ex. böcker kanske du vill öka vikten av attribut som *genre*, *författare*, *serie* och så vidare för att rekommendera liknande böcker.

![](assets/ContentSimilarity.png)

Eftersom innehållets likhet använder nyckelord för att jämföra objekt, kan det finnas attribut, som *message* eller *description*, kan infoga&quot;brus&quot; i jämförelsen. Du kan skapa regler för att ignorera dessa attribut.

Som standard anges alla attribut till *Baslinje*. Du behöver inte skapa en regel om du inte vill ändra den här inställningen.

>[!NOTE]
>
>Algoritmen för innehållets likhet kan använda slumpmässig sampling för att beräkna likhet mellan objekt. Därför kan likhetsgraderingar mellan objekt variera mellan olika algoritmkörningar.

## Inkluderingsregler {#inclusion}

Det finns flera alternativ som du kan använda för att begränsa de objekt som visas i dina rekommendationer. Du kan använda inkluderingsregler när du skapar villkor eller kampanjer.

![Inkluderingsregler](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

Inkluderingsregler är frivilliga. Men om du ställer in dessa uppgifter får du bättre kontroll över vilka objekt som visas i dina rekommendationer. Varje detalj som du konfigurerar förminskar visningsvillkoren ytterligare.

Du kan t.ex. välja att bara visa damskor som har en inventering på mer än 50 och ett pris mellan 25 och 45 dollar. Du kan också väga varje attribut så att de objekt som är viktigast för ditt företag visas med största sannolikhet.

Som ett annat exempel kan du välja att visa nya jobb för besökare som besöker webbplatsen endast från vissa städer och som har rätt högskoleutbildning.

Inkluderingsregelalternativen varierar beroende på bransch-vertikal. Som standard tillämpas inkluderingsregler på rekommendationer för säkerhetskopiering.

>[!IMPORTANT]
>
>Du bör använda inkluderingsregler med försiktighet. De är användbara om er organisation till exempel har regler som kräver att ett varumärke inte rekommenderas medan ett annat varumärke visas. Men den här funktionen kostar en möjlighet. Du kan förlora en procentandel av en ökning genom att begränsa vissa objekt från att inte visas när de normalt visas av aktivitetskriterierna.

Inkluderingsreglerna kombineras med en AND. Alla regler måste uppfyllas för att ett objekt ska kunna inkluderas i en rekommendation.

Så här skapar du en enkel inkluderingsregel, som tidigare nämnts, som endast visar damskor som har en inventering på mer än 50 och ett pris på mellan 25 och 45 dollar:

1. Ange ett prisintervall för de produkter som du vill rekommendera.
1. Ange det minsta lagerbeloppet för de produkter som du vill rekommendera.
1. Konfigurera rekommendationen så att endast objekt visas när de uppfyller vissa villkor.

   ![](assets/Recs_InclusionRules.png)

   Du kan ange att objekt bara ska inkluderas när ett av attributen i listan uppfyller eller inte matchar ett eller flera angivna villkor.

   Vilka utvärderare som är tillgängliga beror på vilket värde du väljer i den första listrutan. Du kan lista flera objekt. Dessa objekt utvärderas med OR.

   Flera regler kombineras med en AND.

   >[!NOTE]
   >
   >Det här alternativet begränsar de objekt som visas i rekommendationen. Det påverkar inte vilka sidor som rekommendationen visas på. Om du vill begränsa var rekommendationen visas markerar du sidorna i upplevelsedispositionen.

Mer information finns i [Använd dynamiska och statiska inkluderingsregler](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Attributviktning {#weighting}

Du kan lägga till flera regler för att&quot;knuffa&quot; algoritmen baserat på viktig information eller metadata om innehållskatalogen så att vissa objekt lättare visas.

Du kan t.ex. använda en högre viktning på artiklar som säljs så att de visas oftare i rekommendationen. Icke-försäljningsposter exkluderas inte helt, men de verkar mindre ofta. Flera viktade attribut kan tillämpas på samma algoritm och de viktade attributen kan testas på delad trafik i rekommendationen.

1. Välj ett värde.

   Värdet avgör vilken typ av objekt som troligen visas, baserat på ett av flera tillgängliga villkor.

1. Välj en utvärderare.

1. Skriv nyckelordet för att slutföra regelattributen.

   Den fullständiga regeln kan till exempel vara &quot;Kategori innehåller delsträngsskor&quot;.

   ![](assets/Recs_AttributeWeighting.png)

1. Välj den vikt som ska tilldelas regeln.

   Alternativen varierar från 0 till 100 i steg om 25.

1. Lägg till ytterligare regler om du vill.

När du är klar klickar du på **[!UICONTROL Save]**.

Om du skapar en ny [!UICONTROL Recommendations] eller redigera en befintlig **[!UICONTROL Save criteria for later]** är markerad som standard. Om du inte vill använda villkoren i andra aktiviteter avmarkerar du kryssrutan innan du sparar.

## Utbildningsvideo: Skapa villkor i Recommendations (12:33) ![Självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa villkor
* Skapa villkorssekvenser
* Överför anpassade villkor

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
