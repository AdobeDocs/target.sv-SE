---
keywords: teckengräns;mbox-parametrar;batchleverans api;profilparametrar;begränsningar;inbyggda profiler;maximum;limit;begränsning;character;best practice;orderTotal;mbox3rdPartyID;category;categoryID;troubleshooting
description: Visa en lista över teckenbegränsningar och andra begränsningar som påverkar aktiviteter och andra element i [!DNL Adobe Target].
title: Vilka är de olika tecknen, storleken och andra gränserna i [!DNL Adobe Target]?
feature: Troubleshooting
mini-toc-levels: 3
exl-id: b318ab16-1382-4f3a-8764-064adf384d6b
source-git-commit: 0a8842f0c29b61ee8cd362edf3e4e4afecbe847a
workflow-type: tm+mt
source-wordcount: '1572'
ht-degree: 0%

---

# Gränser

Teckengränser och andra begränsningar (erbjudandestorlek, målgrupper, profiler, värden, parametrar etc.) som påverkar aktiviteter och andra element i [!DNL Adobe Target].

>[!NOTE]
>
>De gränsvärden som anges nedan skall betraktas som &quot;hårda&quot;, såvida inte annat anges som &quot;rekommenderat&quot;.
>
>När de gränser som anges som&quot;rekommenderas&quot; närmar sig eller överskrids kan prestandan bli långsam. Långsamma inläsningstider för gränssnittet kan också orsakas av en mycket komplex aktivitet, som många målgrupper, mål och upplevelser, allt i en och samma aktivitet.
>
>Mycket komplexa aktiviteter bör granskas med [!DNL Adobe] Rådgivning och testning i begränsad miljö innan produkten släpps för produktion.

## Verksamhet

### Aktivitetsnamn

* **Gräns**: 250 tecken.

### Antal aktiviteter per konto

* **Rekommenderad gräns**: 10 000 aktiva aktiviteter.

* **Rekommenderad gräns**: 10 000 aktiva sparade (och inte avslutade) aktiviteter.

## Mål-API-anrop

* **Gräns**: 50 anrop per minut för API:er för Admin-, Reporting- och bulkprofilsuppdatering. Denna gräns gäller inte för API:er för leverans- och enprofilsuppdatering.

   Om du gör fler än 50 API-anrop per minut, [!DNL Target] returnerar felmeddelandet &quot;503 HTTP-status&quot;.

## Målgrupper

### Målgruppsnamn

* **Gräns**: 255 tecken.

### Målgrupper, återanvändbara per konto

* **Rekommenderad gräns**: 20 000 målgrupper.

### Antal målgrupper per mbox, metrisk eller upplevelse

* **Gräns**: 50 målgrupper

## categoryId-parameter

* **Gräns**: 256 tecken.

## Innehållsleverans {#content-delivery}

* **Gräns**: 100 samtidiga [!DNL Target] innehållsleveransbegäranden per användarsession.

   Om en kund överstiger 100 samtidiga [!DNL Target] innehållsleveransbegäranden för en viss användarsession blockeras alla efterföljande begäranden för den användarsessionen. Två eller flera begäranden anses vara samtidiga om alla skickas till [!DNL Target] servern innan svaret tas emot för någon av dem. [!DNL Target] bearbetar samtidiga begäranden för samma session sekventiellt.

   * **Felbeteende**:

      * Delivery API and Batch Mbox v2:
         * Felkod: HTTP 420 För många begäranden
         * Felmeddelande: &quot;För många begäranden med samma sessions-ID&quot;
      * Äldre mbox-API:
         * Standardinnehåll med kommentaren &quot;För många begäranden med samma sessions-ID&quot;
      * at.js:
         * Standardinnehåll visas



* **Gräns**: 50 lådor per [!DNL Target] batchförfrågan om innehållsleverans.

   Mer än 50 lådor per [!DNL Target] batchbegäran om innehållsleverans resulterar i en svarsfelkod `HTTP 400` med felmeddelande `size must be between 0 and 50`.

   Batch Mbox-begäranden bearbetas sekventiellt, vilket ökar den totala svarstiden för varje iteration. Ju fler kryssrutor på gruppbegäran, desto fler svarstider kan förväntas, och därför kan timeout-fel uppstå. Om upplevelseåtergivning blockeras på dessa batchbegäranden med hög fördröjning kan fördröjningen leda till en försämrad användarupplevelse när användarna väntar på att upplevelserna ska återges.

* **Gräns**: 60 MB HTTP POST body size for [!DNL Target] förfrågningar om innehållsleverans.

   Mer än 60 MB på HTTP-POSTENS brödstorlek för en [!DNL Target] innehållsleveransbegäran resulterar i en svarsfelkod `HTTP 413 Request Entity Too Large`.

* **Rekommenderad gräns**: 50 meddelanden per [!DNL Target] batchförfrågan för leverans.

   Mer än 50 meddelanden per [!DNL Target] batchbegäran om leverans resulterar troligen i ökad svarstid och tidsgränser.

   Batchmeddelandebegäranden behandlas sekventiellt, vilket ökar den totala svarstiden för varje upprepning. Ju fler meddelanden om batchbegäran, desto fler svarstider kan förväntas, och därför kan timeout-problem uppstå. Vissa ytterligare latens för batchmeddelandebegäranden kan accepteras av vissa kunder, men tänk på att timeout och efterföljande försök kan orsaka ännu mer fördröjning.

## Kundattribut

### Namn på kundattribut

* **Gräns**: 250 tecken genom feed eller API.

### ID för kundattributalias

* **Gräns** 50 tecken.

### Kundattribut, överföra

* **Maximal filstorlek för varje överföring med HTTP-metoden**: 100 MB.
* **maximal filstorlek för varje överföring med FTP-metoden**: 4 GB.
* **Antal attribut som tillåts prenumerera**: 5 för [!DNL Target Standard] och 200 för [!DNL Target Premium].

## Enheter

### Antal enheter

* Det högsta antalet enheter som kan refereras i en design, antingen hårdkodade eller via slingor, är 99.
* Den rekommenderade gränsen för bästa prestanda är att hålla katalogen under en miljon artiklar per miljö och under tio miljoner objekt i alla miljöer.
* Den maximala gränsen är tio miljoner objekt per miljö och 100 miljoner objekt i alla miljöer. Om du har mellan en miljon och tio miljoner artiklar per miljö, prestanda för [!UICONTROL Catalog Search] Gränssnittet påverkas. [!DNL Target Recommendations]fortsätter dock att producera och leverera rekommendationer.

### Anpassade attribut för entitet

* **Anpassade entitetsattribut**: 100.

* **Teckengräns**: Den maximala teckenlängden beror på språket.

   * 15 000 tecken (språk med ett värde, en och två byte)
   * 500 värden, 100 tecken per värde (flervärde)

   Den maximala längden för anpassade attribut för en entitet med ett värde är 15 000 tecken (för UTF-8-kodade språk med en byte och två byte, som engelska och andra latinska skriftspråk) eller 10 000 tecken (för UTF-8-kodade språk med tre byte som kinesiska, japanska och koreanska).

   Anpassade attribut för entiteter med flera värden får inte innehålla fler än 500 värden. Varje enskilt värde är begränsat till 100 tecken. Det totala antalet tecken i alla värden måste uppfylla begränsningarna för den maximala längden för anpassade entitetsattribut med ett värde (se ovan).

### entity.id

* **Begränsning för implementeringar som kräver att man hämtar inköpsinformation**: 50 tecken.

   Den här begränsningen används eftersom `productPurchasedId` mbox-parametern fångar entity.ids, vilket begränsar teckenantalet till 50.

* **Begränsning för implementeringar som endast kräver vybaserade algoritmer:**: 1 000 tecken.

   Vybaserade algoritmer omfattar vy/vy, de senast visade, nyligen visade och så vidare.

## excludeIds {#excludedid}

* **Gräns**: 5 kB för förfrågningar om POST. 2 083 tecken minus längden på URL:en för GET-begäranden.

   För GET-förfrågningar gäller att även om gränsen för backend är 5 kB så är den realistiska gränsen 2 083 tecken minus den aktuella URL-längden eftersom Microsoft Internet Explorer begränsar URL:en till 2 083 tecken.

## Erfarenheter

### Experience names

* **Gräns**: 50 tecken.

### Erfarenheter per aktivitet

* **Gräns**: 2 000 upplevelser per [!UICONTROL Experience Targeting] (XT), [!UICONTROL A/B Test], [!UICONTROL Multivariate Test] (MVT), och [!UICONTROL Auto-Target] aktivitet.

   30 000 upplevelser per Automated Personalization-aktivitet (AP).

### Ändringar per upplevelse

* **Gräns**: 50 per upplevelse av alla aktiviteter

## mboxes

### Attributvärde för profil i rutan

* **Gräns**: 256 tecken.

   Värden som är längre än detta trunkeras.

### Profilnamn i mbox

* **Gräns**: 128 tecken.

### mbox names {#mbox-names}

* **Gräns**: 250 tecken.

   För leverans-API (at.js 2.*x*), integrering av Batch Mbox V2 och AEP Web SDK (alloy.js), mbox-namn *kan* innehåller alfanumeriska tecken (A-Z, a-z, 0-9) och något av följande tecken:

   ```
   - , . _ / = ` : ; & ! @ # $ % ^ & * ( ) _ + | ? ~ [ ] { }
   ```

   För at.js 1.*x* integreringar, mbox-namn *inte* innehåller något av följande tecken:

   ```
   ' " %22 %27 < > %3C %3E 
   ```

### mbox-parametrar {#mbox-parameters}

* **Gräns**: Följande begränsningar gäller för mbox-parametrar:

   För vanliga mbox-anrop:

   * mbox-parametrar: 500 parametrar per mbox.
   * Profilparametrar: 500 parameterprofilparametrar per mbox.
   * Andra parametrar (URL, refererande URL, osv.): 50 per mbox för varannan parametertyp.

   Dessa begränsningar gäller såvida inte begäran förkortas på grund av webbläsarbegränsningar.

   Om du använder API:t för gruppleverans är gränsen 50 mbox per batch-begäran.

   Om du använder API:t för gruppleverans i SDK för mobila tjänster är begränsningen 50 mbox-parametrar, 50 profilparametrar och 50 för andra parametertyper begränsningar för själva API:t. Det går inte att skicka en begäran som innehåller fler än dessa nummer med API:t för gruppleverans. Om en begäran innehåller fler än dessa begränsningar returnerar API:t följande felmeddelande:

   &quot;Antalet mboxParameters får inte överskrida 50.&quot;

   Begränsningar för slutpunkter:

   **Batchruta v2**:

   * mbox parameters 100
   * mbox-parameternamn max length 128
   * mbox-parametervärdet får inte vara null
   * mbox-parametervärde 5000
   * profilparametrar 50
   * profilparameternamn max längd 128
   * profilparametervärdet får inte vara null
   * maxlängd för profilparametervärde 5000

   **Slutpunkt för leverans-API**:

   * mbox parameters 100
   * mbox-parameternamn max length 128
   * mbox-parametervärdet får inte vara null
   * mbox-parametervärde 5000
   * profilparametrar 50
   * profilparameternamn max längd 128
   * profilparametervärdet får inte vara null
   * maxlängd för profilparametervärde 5000



### URL för mbox-begäran

* **Gräns**: 2 083 tecken.

   Den här gränsen beror på längdbegränsningar i URL:en för Microsoft Internet Explorer.

### parametern mbox3rdPartyId

* **Gräns**: 256 tecken.

## Erbjudanden

### Erbjudandenamn

* **Gräns**: 250 tecken.

### Antal erbjudanden

* **Rekommenderad gräns**: Totalt 50 000 erbjudanden.

### Erbjudandestorlek {#offer-size}

Följande storleksbegränsningar gäller för erbjudanden:

* 1024 kB för erbjudanden från HTML.
* 1 024 kB (för varje upplevelse) för visuella erbjudanden från användargränssnittet.
* 1 024 kB från API:t.

   Om du använder en global mbox är gränsen för hela den innehållsuppsättning som returneras för sidan. Genom att begränsa erbjudandestorleken förbättras sidinläsningstiden. Om gränsen överskrids visas följande meddelande:

   &quot;Innehållet i upplevelsen är för stort för att kunna leverera. Ändra upplevelsen så att den påverkar mindre sidkod.&quot;

## orderId-parameter

* **Rekommenderad gräns**: 120 tecken.

## orderTotal-parameter

* **Rekommenderad gräns**: 120 tecken.

## productPurchasedId, parameter

* **Gräns**: 50 tecken per kommaavgränsat värde och totalt 250 tecken. Enskilda värden som är längre än 50 tecken trunkeras av systemet. Sammanlagda längder på över 250 tecken resulterar i ett 400-fel.

## Profilskript

* **Rekommenderad gräns för aktiva profilskript (de som är aktiverade)**: 300

* **Rekommenderad gräns för totalt antal profilskript per konto**: 2 000

* **Recommendations för att begränsa komplexiteten i profilskript**: Profilskript kan köra ett begränsat antal instruktioner. Mer information finns i [God praxis](/help/main/c-target/c-visitor-profile/profile-parameters.md#best) in *Profilattribut*.

## Egenskaper

* **Rekommenderad gräns**: 5 000 egenskaper.

## Rapportera målgrupper/segment

* **Gräns**: 50 rapportmålgrupper/segment per verksamhet.

## Skriptprofilens inmatningsruta i [!DNL Target] UI

* **Rekommenderad gräns**: 2 000 tecken.

   Beroende på storleken på den kodade strängen, som kan vara mycket längre än Raw-strängen. Om strängen är för stor misslyckas den innan den når [!DNL Adobe Target].

## Skriptprofiler

### Skriptprofilnamn

* **Gräns**: 50 tecken.

### Värden för skriptprofil

* **Gräns**: 2 048 tecken.

   Av prestandaskäl rekommenderar vi ett returvärde som inte är längre än 256 tecken.

   Om returvärdet för ett String-returvärde är större än 2 048 tecken inaktiveras skriptet av systemet.

   Om storleken på de sammanfogade värdena i arrayen överstiger 2 048 tecken inaktiveras skriptet av systemet för ett arrayreturvärde.

## Framgångsmått

* **Gräns**: 200 per aktivitet.

## Målinriktning

### Målförhållanden

* **Rekommenderad gräns**: 1 000 värden.

   Det här refererar till antalet radavgränsade värden i måltextområdet. Du kan till exempel ange 1 000 postkoder i ett postnummermål.

### Riktningsregler {#targeting-rules}

* **Rekommenderad gräns**: 2 500 tecken per målregelvärde.
* **Rekommenderad gräns**: 50 000 unika värden per målgrupp över målinriktningsreglerna.
* **Rekommenderad gräns**: 100 000 unika målregelvärden per aktivitet.
