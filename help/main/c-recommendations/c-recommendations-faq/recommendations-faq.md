---
keywords: felsökning;vanliga frågor;Vanliga frågor;Vanliga frågor;Vanliga frågor;rekommendationer;specialtecken;attributvikt;innehållets likhet
description: Visa en lista med vanliga frågor och svar om [!DNL Target Recommendations] aktiviteter.
title: Var hittar jag frågor och svar om  [!DNL Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: aaa52923-1c2d-44ae-bd89-671329222077
source-git-commit: 18f6c06aa06e9526ee65bd3cc0f9b552c91c10e7
workflow-type: tm+mt
source-wordcount: '3444'
ht-degree: 0%

---

# Rekommendationer - frågor och svar

Lista med vanliga frågor och svar om [!DNL Adobe Target] [!DNL Recommendations] aktiviteter.

## Skapas [!DNL Recommendations] objekt via API-visning i [!DNL Target]-gränssnittet?

Ja, [!UICONTROL Recommendations] objekt ([!UICONTROL Criteria], [!UICONTROL Designs], [!UICONTROL Collections] och [!UICONTROL Exclusions]) som skapats över API är tillgängliga i användargränssnittet och kan redigeras via API eller [!DNL Target] användargränssnitt.

## Kan jag hantera [!DNL Target] visuella erbjudanden som har skapats i användargränssnittet med API:erna i [!DNL Target]?

Nej. [!DNL Recommendations] aktiviteter med visuella erbjudanden skapade i [!DNL Target]-gränssnittet kan inte hanteras med API:erna för [!DNL Target]. Även om dessa aktiviteter visas i listan [!UICONTROL Activities] kan du inte läsa eller uppdatera dem (med GET/PUT).

## Varför visar [!UICONTROL Catalog Search] inte rätt resultat när jag söker efter ett anpassat attribut med ett numeriskt värde?

När du gör en katalogsökning i ett anpassat attribut med ett numeriskt värde behandlas det anpassade attributet som en strängtyp i stället för ett numeriskt värde.

För närvarande finns det ingen tillgänglig funktion som gör att kunderna kan ändra typen av attribut. Om du vill göra en ändring [öppnar du ett kundproblem](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) som refererar till de attribut som behöver typen ändrad från sträng till numerisk.

## Hur lång tid tar det att uppdatera objekt i min katalog ska återspeglas på min webbplats?

Tidsramen och resultaten varierar beroende på hur objekten uppdateras.

| Source | Information |
| --- | --- |
| Objektattribut uppdaterade via mbox eller API | <ul><li>Rekommendationerna uppdateras inom 15 minuter.</li><li>Befintliga rekommendationer och objektattribut visas tills uppdateringarna är tillgängliga.</li><li>Katalogsökning uppdateras efter katalogindex (3-8 timmar).</li></ul> |
| Objektattribut uppdaterade via feed | <ul><li>Rekommendationerna uppdateras efter foderkonsumtion (2-8 timmar).</li><li>Befintliga rekommendationer och objektattribut visas tills uppdateringarna är tillgängliga.</li><li>Katalogsökningen uppdateras efter feed-importen (2-8 timmar) och efter efterföljande katalogindex (3-8 timmar). Katalogsökning uppdateras inom totalt 5-16 timmar.</li></ul> |
| Objektet togs bort från katalogen via [!DNL Target]-gränssnittet eller API:t | <ul><li>Rekommendationerna uppdateras inom 15 minuter.</li><li>Befintliga rekommendationer och objektattribut visas tills uppdateringarna är tillgängliga.</li><li>Katalogsökning uppdateras efter katalogindex (3-8 timmar).</li></ul> |
| Objekt som lagts till i katalogen via mbox eller API | <ul><li>Rekommendationer uppdateras efter att algoritmen har körts. Algoritmkörningar schemaläggs var tolfte timme för 1-2-dagars algoritmer och varannan timme för 7+-dagars algoritmer.</li><li>Befintliga rekommendationer visas tills det finns uppdateringar om det tillagda objektet inte är en begärd nyckel.</li><li>Rekommendationer för säkerhetskopiering visas tills det finns uppdateringar om det tillagda objektet är en begärd nyckel.</li><li>Katalogsökning uppdateras efter katalogindex (3-8 timmar).</li></ul> |
| Objekt som lagts till i katalogen via feed | <ul><li>Rekommendationerna uppdateras efter att fodret har intagits (2-8 timmar). Efterföljande algoritmkörningar schemaläggs var tolfte timme för 1-2-dagarsalgoritmer och varannan timme för 7+-dagsalgoritmer. Rekommendationer uppdateras inom totalt 2-32 timmar.</li><li>Befintliga rekommendationer visas tills det finns uppdateringar om det tillagda objektet inte är en begärd nyckel.</li><li>Rekommendationer för säkerhetskopiering visas tills det finns uppdateringar om det tillagda objektet är en begärd nyckel.</li><li>Katalogsökningen uppdateras efter feed-importen (2-8 timmar) och efter katalogindexet (3-8 timmar). Katalogsökning uppdateras inom totalt 5-16 timmar.</li></ul> |

När du har importerat en feed-fil eller efter att ha tagit emot entitetsuppdateringar via API eller mbox visas följande ändringar under 60 minuter:

* Om ett objekt tidigare har uteslutits men nu ska inkluderas objektet i nästa algoritmkörning (12-24 timmar).

  Den här situationen inträffar eftersom [!DNL Target] tillämpar undantag både online och offline. När ett objekt nyligen har uteslutits tillämpas detta snabbt. När ett objekt nyligen ingår försvinner undantaget från webben snabbt, men offlineundantaget försvinner inte förrän nästa algoritm körs.

* Om ett objekt tidigare inkluderades men nu ska exkluderas, exkluderas objektet enligt tidsraden&quot;Uppdaterade artikelattribut..&quot; som beskrivs ovan beroende på flödeskälla (15 minuter via mbox/API eller 12-24 timmar via feed).

Följande ändringar återspeglas inte förrän nästa algoritmkörning inträffar (inom 12-24 timmar):

* Objektattribut som används i samlingsreglerna som används för aktiviteten.
* Artikelattribut som används i en kampanj baserat på ett attribut eller en samling som är associerad med aktiviteten.
* Artikelkategori som objektet visas i för en&quot;Aktuell kategori&quot; eller&quot;Favoritkategori&quot; i algoritmen Top Sellers eller Most Viewed.
* Rankning av rekommenderade objekt när attributet ändras är ett anpassat attribut som används som anpassad nyckel för en algoritm.
* Rankning av rekommenderade objekt baserat på ett eller flera ändrade attribut när rekommendationslogiken är&quot;Objekt med liknande attribut&quot; när&quot;Likhetsfaktor för innehåll&quot; används, eller när&quot;Attributviktningsfaktorer&quot; används.

>[!NOTE]
>
>En feed-fil betraktas som importerad när dess status ändras från&quot;Importera objekt&quot; till&quot;Förbereda sökindexuppdateringar&quot;. Uppdateringar kan ta mer än 60 minuter att spegla i användargränssnittet för katalogsökning. Katalogsökningen är uppdaterad när flödets status ändras till Uppdateringar slutförda. Även om katalogsökningen ännu inte är uppdaterad visas uppdateringar för de tidsramar som anges ovan på webbplatsen. Den senaste uppdateringstiden för katalogens sökindex visas på sidan Katalogsökning.

## Hur lång tid tar det att ändra konfigurationen för min [!UICONTROL Recommendations]-aktivitet, mitt erbjudande, mina kampanjer eller villkor så att de återspeglas på min webbplats?

* En ändring av kampanjinställningarna kan ta upp till fem timmar att reflektera på plats.
* En ändring av andra villkorsinställningar kanske inte återspeglas förrän nästa algoritm körs:

   * Vissa villkorsinställningar (till exempel&quot;tillägg av en regel för dynamisk infogning&quot;) visas omedelbart.
   * Andra villkorsinställningar (t.ex. &quot;borttagning av en regel för dynamisk inkludering&quot;, ändring av uppslagsfönster o.s.v.) kan inte införlivas förrän nästa algoritm körs.
   * Algoritmkörningar utlöses av dessa ändringar men kan ta upp till 24 timmar att slutföra. Algoritmer körs också på schemalagd basis var 12:24:e timme.

## Hur lång tid tar det för en användares beteende (till exempel att klicka på produkt A och köpa produkt B) att återspeglas i rekommendationerna *som* -användaren får?

* Den produkt/det innehåll som för närvarande visas/köpts påverkar de rekommendationer som användaren får på samma sidvy/innehållsförfrågan från [!DNL Target].
* Historiskt användarbeteende, t.ex.&quot;senast visade produkt&quot;,&quot;mest visade produkt&quot; och övergripande visnings-/inköpshistorik uppdateras med den begäran och påverkar de rekommendationer som användaren får på nästa sidvy/[!DNL Target]-innehållsbegäran. Algoritmerna&quot;Senast visade objekt&quot; och&quot;Rekommenderas för dig&quot; uppdateras till exempel för varje produktvy/köp och återspeglas i den efterföljande innehållsförfrågan.

## Hur lång tid tar det för en användares beteende (till exempel att klicka på produkt A och köpa produkt B) att återspeglas i rekommendationerna som *andra* -användare får?

Beteendet hos användare i sammanställningen är inbyggt i offlinealgoritmbearbetning där varje algoritm körs var 12-24:e timme.

## Vad ska jag göra om specialtecken bryter min array? {#section_D27214116EE443638A60887C7D1C534E}

Använd escape-värden i JavaScript. Citattecken ( &quot; ) kan bryta arrayen. Följande kodfragment är ett exempel på escape-värden:

```
#set($String='') 
#set($escaper=$String.class.forName('org.apache.commons.lang.StringEscapeUtils')) 
<script type="text/javascript"> 
console.log("$escaper.escapeJavaScript($entity1.name)") 
console.log("$escaper.escapeJavaScript($entity2.name)") 
console.log('$escaper.escapeJavaScript($entity3.name)') 
names.push("$escaper.escapeJavaScript($entity4.name)") 
</script>
```

## Varför är inte alla villkor, inklusive anpassade kriterier, tillgängliga för markering när en rekommendationsaktivitet skapas? {#section_B2265AC8B8A94E0298D495A05C5D817F}

De tillgängliga villkoren baseras på den aktuella kategorin. När du skapar rekommendationer visas villkor baserat på kategori-ID i algoritmväljaren.

Om platsen som du använder det här villkoret på inte innehåller kategori-ID:t är vissa villkor inte tillgängliga i algoritmväljaren.

Om du använder en plats där kategori-ID finns i rutan innehåller kriterieväljaren alla tillämpliga villkor.

[!DNL Target] har en inställning för [Inkompatibla filtervillkor](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=sv-SE){target=_blank} som styr intelligent filtrering av algoritmväljaren.

>[!NOTE]
>
>Den här inställningen gäller endast aktiviteter som skapats i [!UICONTROL Visual Experience Composer] (VEC). Den här inställningen gäller inte för aktiviteter som skapats i den formulärbaserade Experience Composer ([!DNL Target] har ingen platskontext).

Om du vill komma åt inställningen [!UICONTROL Filter Incompatible Criteria] klickar du på [!UICONTROL Recommendations] > [!UICONTROL Settings]:

![recs_settings_filter-bild](assets/recs_settings_filter.png)

Om inställningen [!UICONTROL Filter Incompatible Criteria] INTE är aktiverad filtrerar [!DNL Target] inte algoritmer i algoritmväljaren och alla algoritmer visas.

Om inställningen [!UICONTROL Filter Incompatible Criteria] är aktiverad läser [!DNL Target] entitet-ID och kategori-ID från den valda platsen i VEC-aktiviteter och visar sedan algoritmer baserade på `currentItem|currentCategory` (om det finns respektive värden på den platsen). Därför visas som standard bara kompatibla algoritmer för den valda platsen i algoritmväljaren.

Om inställningen [!UICONTROL Filter Incompatible Criteria] är aktiverad kan du fortfarande visa icke-kompatibla algoritmer genom att avmarkera kryssrutan [!UICONTROL Compatible] när du väljer villkor.

![compatible_checkbox image](assets/compatible_checkbox.png)

Följande lista innehåller specialfall där [!DNL Target] inte visar kryssrutan [!UICONTROL Compatible]:

* Både entityId och category Id finns på platsen och inget filtreras.
* Du använder [!DNL mbox.js] version 55 eller tidigare.
* Inget mbox-anrop aktiveras från sidan (!config.isAutoCreateGlobalMbox &amp;&amp; !config.isRegionalMbox)
* [!DNL Target] parametrar har inte definierats.

## Vad ska jag göra om en samling i Rekommendationer blir noll (0)? {#section_E2DB2FE67CF24EEC81412BFF3FA6385D}

Tänk på följande information om du ser en samling gå till noll som tidigare inte var noll:

* Du kan spara om samlingen och se om den uppdaterar numret. Genom att spara om genereras alla algoritmer som använder samlingen om.
* Tittar du på rätt miljö? Gå till [!DNL /target/products.html#recsSettings] om du vill dubbelkontrollera (se nedan).

  ![product_catalog image](assets/product_catalog.png)

* Är ditt index uppdaterat? Gå till [!DNL /target/products.html#productSearch] och kontrollera hur många timmar som indexet är gammalt (t.ex. &quot;Indexerad för 3 timmar sedan&quot;). Du kan uppdatera indexet efter behov.
* Har du ändrat något i feeden eller datalagret som resulterade i att dina enheter inte längre matchade samlingsreglerna? Se till att CASE-filen överensstämmer (skiftlägeskänslig).
* Kördes din feed korrekt? Ändrade någon FTP-katalog, lösenord och så vidare?
* [!DNL Target] gör sitt bästa för att göra uppdateringar av leveransen (på kundens sida/app) så snabbt som möjligt. Men [!DNL Target] måste även tillhandahålla en viss representation i användargränssnittet för marknadsföraren. [!DNL Target] försenar inte leveransuppdateringar så att de väntar på att gränssnittsuppdateringarna ska vara synkroniserade. Du kan använda [mboxTrace](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md) för att se vad som finns i systemet när en begäran kommer in.

## Vad är skillnaden mellan allmän attributviktning och innehållets likhetsspecifika attributviktning? {#section_FCD96598CBB44B16A4C6C084649928FF}

Attributviktningen finns i två former: &quot;standardattributviktning&quot; och &quot;attributviktning för likhet med innehåll&quot;.

&quot;Standardattributviktning&quot; gäller de flesta, om inte alla, kriterietyper (inte bara innehållets likhet). Den här typen av viktning ger mer vikt åt vissa attributvärden. I följande exempel får Nike-produkter en ojämnhet i utdatarrekommendationerna.

![attribute_weight_example image](assets/attribute_weighting_example.png)

&quot;Attributvikning för innehållets likhet&quot; gäller endast för kriterier för innehållets likhet.

Den här typen av viktning är mer dynamisk och baseras på den aktuella rekommendationsnyckeln (det objekt som visas för närvarande). I följande exempel (varumärke x 16), om en besökare tittade på Nike sneakers, är det mer sannolikt att den besökaren rekommenderas till andra Nike-produkter (inte nödvändigtvis bara sneakers) än konkurrenternas sensorer. Om en besökare tittar på Adidas-sensorer är det troligare att den besökaren rekommenderar Adidas-produkter.

![content_likity_example image](assets/content_similarity_example.png)

## Varför kan [!DNL Target] ibland inte visa rekommendationer? {#section_DB3F40673AED42228E407C05437D99E9}

[!DNL Target] kan ibland inte visa rekommendationer på grund av det låga antalet tillgängliga rekommendationer.

Antalet genererade värden per villkor är tre gånger så många enheter som anges i designen. Körtidsfiltrering (till exempel lagerhantering, mbox-attributmatchning) tillämpas efter att 3x-värdena har genererats, så det är möjligt att få färre än 3x-värden vid leveranstiden. Om du vill minska den här situationen ökar du antalet enheter i designen genom att dölja andra enheter.

Följande JavaScript kan användas i början av designen för att öka antalet begärda enheter. I det här exemplet skulle antalet begärda entiteter vara 30 (3x10).

```
#foreach($entity in $entities) 
 #if( $foreach.count > 10 ) 
  #break 
 #end 
 #set ($foo = $entity.id) 
#end 
```

## Vilken är storleksgränsen för ett API-anrop för infognings-/uppdateringsprodukter? Kan jag uppdatera 50 000 produkter i ett samtal med API:t istället för en feed? {#section_434FE1F187B7436AA39B7C14C7895168}

[!DNL Target] sätter en postgräns på 50 MB på programnivå, men det är bara när du skickar innehållstypsrubriken `application/x-www-form-urlencoded`.

Du kan försöka att skicka 50 000 produkter i ett enda samtal. Om det inte fungerar kan du dela upp det i grupper. Adobe rekommenderar att kunderna bryter sina samtal till 5 000 eller 10 000 produktgrupper för att minska sannolikheten för en timeout på grund av systembelastning.

## Måste jag ange mbox-namnet när jag skapar rekommendationer, kampanjer eller testregler för mallar? {#section_FFA42ABCC5954B48A46526E32A3A88A2}

När du skapar en regel för rekommendationskriterier, kampanjer eller malltestning som baseras på en mbox-parameter, uppmanar `mboxParameter` dig inte längre att ange `mboxName`. Nu är mbox-namnet valfritt. Med den här ändringen kan du använda parametrar från flera rutor eller referera till en parameter som ännu inte har registrerats på kanten.

Så här väljer du önskad parameter:

* Välj ett parameternamn i listan när du skapar ett villkor, en kampanj eller en malltestningsregel. Börja skriva de första tecknen i det önskade parameternamnet eller skriv det fullständiga namnet på det önskade parameternamnet.
* Om du kommer ihåg mbox-namnet, men inte parameternamnet, använder du kryssrutan för att filtrera på en känd mbox som skickar den önskade parametern.

Om du använder någon av metoderna finns det ingen länk mellan mbox och parametern. Regeln för villkor, befordran eller malltestning fungerar baserat på parametern i alla kryssrutor som skickar den parametern.

Om du redigerar ett befintligt villkor, en befordran eller en malltestregel visas filtervillkoren med namnet på mbox som angavs när du skapade.

## Varför kan jag inte spara min tidigare Rekommendationer-aktivitet efter att jag har definierat en ny målgrupp? {#section_1E47C40B1FE7479BAC3EE0F50CE7C2C4}

Se till att målgruppen har ett unikt namn. Om du gav publiken samma namn som en befintlig publik kan du inte spara din tidigare Rekommendationer-aktivitet (en Rekommendationsaktivitet som skapades före oktober 2016).

## Vilken är den maximala storleken för en CSV-fil för en feed-överföring? {#section_20F1AF4839A447B9889B246D6E873538}

Det finns ingen hård gräns för antalet rader eller filstorleken för en feed CSV-filöverföring. Som en god praxis rekommenderar Adobe dock att CSV-filens storlek begränsas till 1 GB för att undvika fel under filöverföringen. Om filens storlek överstiger 1 GB kan den helst delas upp i flera feedsfiler. Det maximala antalet anpassade attributkolumner är 100 och anpassade attribut är begränsade till 4 096 tecken. Andra begränsningar för längden på obligatoriska kolumner är tillgängliga på sidan [[!DNL Target] Begränsningar](/help/main/r-troubleshooting-target/target-limits.md#reference_BEFE60C3AAA442FF94D4EBFB9D3CC9B1).

## Kan jag utesluta en entitet dynamiskt? {#exclude}

I frågesträngen kan du skicka enhets-ID:n för entiteter som du vill utesluta från dina rekommendationer. Du kan t.ex. utesluta artiklar som redan finns i kundvagnen.

Använd parametern `excludedIds` för att aktivera exkluderingsfunktionen. Den här parametern pekar på en lista med kommaavgränsade enhets-ID:n. Exempel: `mboxCreate(..., "excludedIds=1,2,3,4,5")`. Värdet skickas när rekommendationer begärs.

Undantaget utförs endast för det aktuella [!DNL Target]-anropet. Objekt exkluderas inte vid efterföljande [!DNL Target] anrop såvida inte värdet `excludedIds` skickas igen. Om du vill utesluta artiklar i kundvagnen från rekommendationer på varje sida fortsätter du skicka värdet `excludedIds` på varje sida.

>[!NOTE]
>
>Om för många enheter utesluts beter sig rekommendationerna som om det inte finns tillräckligt många enheter för att fylla rekommendationsmallen.

Om du vill exkludera `entityIds` lägger du till `&excludes=${mbox.excludedIds}`-token till erbjudandeinnehållets URL. När innehålls-URL:en extraheras ersätts de obligatoriska parametrarna med aktuella parametrar för mbox-begäran.

Som standard är den här funktionen aktiverad för nya rekommendationer. Befintliga rekommendationer måste sparas för att stödja enheter som utesluts dynamiskt.

## Vad betyder NO_CONTENT-svaret som ibland returneras i innehållspårningen Recommendations?

NO_CONTENT returneras när rekommendationer inte är tillgängliga för den begärda algoritmen och tangentkombinationen. I allmänhet inträffar detta när säkerhetskopieringar inaktiveras för algoritmen och ett eller flera av följande är också sant:

* Resultaten är inte klara än.

  Den här situationen inträffar vanligtvis när en nyskapad aktivitet sparas eller efter att konfigurationsändringar har gjorts i den samling, de kriterier eller kampanjer som används i aktiviteten.

* Resultaten är klara, men har ännu inte cachelagrats på närmaste edge-server, för den begärda algoritm-/tangentkombinationen.

  Begäran initierar en cachelagringsåtgärd, så problemet bör lösas efter att några sidor har lästs in och/eller några minuter framåt.

* Resultaten är klara, men inte tillgängliga för det angivna nyckelvärdet.

  Den här situationen inträffar vanligtvis när du begär rekommendationer för ett objekt som har lagts till i katalogen efter att den senaste algoritmen har körts och kommer att matchas automatiskt efter nästa algoritmkörning.

* Delvis mallåtergivning är inaktiverat och det finns inte tillräckligt med resultat för att fylla mallen.

  Den här situationen inträffar vanligtvis när du har en regel för dynamisk inkludering som tar bort många objekt från möjliga resultat. Du kan undvika en situation genom att aktivera säkerhetskopieringar och inte tillämpa inkluderingsregeln på säkerhetskopieringar, eller använda villkoren i följd med ett mindre aggressivt filtrerat villkor.

## Bevaras rekommendationer baserade på nyligen visade objekt på flera enheter för en enskild besökare? {#persist-across-devices}

När en besökare initierar en session är sessions-ID kopplat till en enda edge-dator och ett temporärt profilcache lagras på den här edge-datorn. Efterföljande begäranden från samma session läser den här profilcachen, inklusive nyligen visade objekt.

När sessionen avslutas (vanligtvis när den går ut efter 30 minuter utan aktivitet), behålls sessionstillståndet, inklusive nyligen visade objekt, till en mer permanent profillagring i samma geografiska kant.

Efterföljande sessioner från olika enheter kan sedan komma åt de senast visade objekten så länge den nya sessionen är länkad till kundprofilen via samma Marketing Cloud ID (MCID), Experience Cloud ID (ECID) eller CustomerID/mbox3rdPartyId.

Om en besökare har två aktiva sessioner samtidigt uppdaterar inte nyligen visade objekt på en enhet de senast visade objekten på den andra enheten, såvida inte enheterna tvingas dela sessions-ID. Det finns en möjlig lösning på problemet, men [!DNL Target] stöder inte direkt delning av ett sessions-ID mellan flera enheter. Kunden måste själva hantera denna ID-delning.

Detta beteende inträffar fortfarande om en besökare är aktiv på en enhet och sedan aktiveras på den andra enheten några minuter senare. Den första enhetens session upphör inte att gälla på 30 minuter och det kan ta upp till fem minuter innan profilläget skrivs till det permanenta läget och bearbetas. Det kan ta 35 minuter innan sessionen upphör att gälla och profilen sparas när du testar det här beteendet.

Om besökaren inte har två aktiva sessioner samtidigt uppdaterar nyligen visade objekt på en enhet de senast visade objekten på den andra enheten så länge sessionen har avslutats. Det kan ta 35 minuter innan sessionen går ut när du testar det här beteendet.

## Kan jag använda en algoritm som har skapats i [!DNL Adobe Recommendations Classic] i [!DNL Recommendations Premium]?

En algoritm som skapats i [!DNL Recommendations Classic] stöds inte i [!DNL Recommendations Premium]. Du kan kanske använda den äldre algoritmen i [!DNL Target Premium], men algoritmen kan skapa synkroniseringsproblem när aktiviteten i [!DNL Target Premium] inaktiveras eller tas bort. Mer information om skillnaderna mellan de två lösningarna finns i [[!DNL Recommendations Classic] kontra [!DNL Recommendations] aktiviteter i [!DNL Target Premium]](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md).

## Hur kan jag rekommendera enbart nya artiklar eller videoklipp? {#recommend-new-articles}

En del kunder inom media och publicering vill se till att rekommenderade objekt endast innehåller de senaste artiklarna eller videofilmerna. En [!DNL Target]-kund använde till exempel följande metod för att rekommendera artiklar som är yngre än 60 dagar:

1. Skicka artikelns publiceringsdatum i YMMDDD-format som ett anpassat entitetsattribut.
1. Skapa ett profilskript som är dagens datum minus 60 dagar, även i formatet YYYMMDD.
1. Använd ett dynamiskt inkluderingsfilter i villkoren så att `publish date > today's date minus 60 days`.

### Skicka publiceringsdatumet som ett anpassat entitetsattribut:

| Entitetsattribut | Exempel |
| --- | --- |
| issueDate | 2021218 |
| lastViewDate | 2021701 |
| parentCategory | kommentar |
| publishDate | 20210113 |
| publishDateDisplay | 13 jan 2021 |

### Konfigurera profilskriptet:

![Exempelprofilskript](/help/main/c-recommendations/c-recommendations-faq/assets/sample-profile-script.png)

### Konfigurera inkluderingsregeln:

![Exempelinkluderingsregel](/help/main/c-recommendations/c-recommendations-faq/assets/sample-inclusion-rule.png)

>[!NOTE]
>
>Det här exemplet kan också utföras med parametermatchning och genom att skicka värdet `priorDate60` som en mbox-parameter.

### Vad är några kända problem när [!DNL Recommendations] aktiviteter används?

Följande är kända problem med [!UICONTROL Recommendations]-aktiviteter:

* När [!DNL Target] returnerar ett JSON-erbjudande med getOffer() returneras det med typen JSON. Om du returnerar en JSON-rekommendation returneras den emellertid med en typ av HTML.
* Enheter som har gått ut har gått ut 60 dagar efter att de inte har fått några uppdateringar via feed eller API. De enheter som har gått ut tas dock inte bort från katalogens sökindex efter att de har gått ut. Enheter som tas bort via feed eller API tas inte heller bort från indexet för katalogsökning. (IRI-857)
* Rekommendationer i A/B- och Experience Targeting-aktiviteter visar ingen visuell förhandsgranskning av rekommendationsfältet (TGT-33426)
* Rekommendationsaktiviteter som skapas via API kan visas i användargränssnittet, men kan bara redigeras via API.
* Den feed-status för anpassade kriterier som visas i kriterielistan (kortvyn) uppdateras var tionde minut och kan i sällsynta fall vara mer än tio minuter gammal. Statusen som visas i redigeringsvyn för anpassade kriterier hämtas i realtid och är alltid uppdaterad. (TGT-35896, TGT-36173)
