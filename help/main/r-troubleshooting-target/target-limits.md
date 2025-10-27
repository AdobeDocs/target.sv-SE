---
keywords: teckengräns;mbox-parametrar;batchleverans api;profilparametrar;begränsningar;inbyggda profiler;maximum;limit;begränsning;character;best practice;orderTotal;mbox3rdPartyID;category;categoryID;troubleshooting
description: Visa en lista med teckenbegränsningar och andra begränsningar som påverkar aktiviteter och andra element i  [!DNL Adobe Target].
title: Vilka är de olika tecknen, storleken och andra gränserna i  [!DNL Adobe Target]?
feature: Troubleshooting
mini-toc-levels: 3
exl-id: b318ab16-1382-4f3a-8764-064adf384d6b
source-git-commit: 720f70a97c5c9457f134085696dd79196c7869bc
workflow-type: tm+mt
source-wordcount: '1734'
ht-degree: 0%

---

# Gränser

Teckengränser och andra begränsningar (erbjudandestorlek, målgrupper, profiler, värden, parametrar osv.) som påverkar aktiviteter och andra element i [!DNL Adobe Target].

>[!NOTE]
>
>De gränsvärden som anges nedan skall betraktas som &quot;hårda&quot;, såvida inte annat anges som &quot;rekommenderat&quot;.
>
>När de gränser som anges som&quot;rekommenderas&quot; närmar sig eller överskrids kan prestandan bli långsam. Långsamma inläsningstider för gränssnittet kan också orsakas av en mycket komplex aktivitet, som många målgrupper, mål och upplevelser, allt i en och samma aktivitet.
>
>Mycket komplexa aktiviteter bör granskas med [!DNL Adobe] konsulting och testas i en begränsad miljö innan de släpps till produktion.

## Verksamhet

### Aktivitetsnamn

* **Gräns**: 250 tecken.

### Antal aktiviteter per konto

* **Rekommenderad gräns**: 10 000 aktiva aktiva aktiviteter.

* **Rekommenderad gräns**: 10 000 aktiva sparade (och inte avslutade) aktiviteter.

## Mål-API-anrop

* **Gräns**: 50 anrop per minut för API:er för Admin-, Reporting- och bulkprofiluppdatering. Den här gränsen gäller inte för API:er för leverans- och enprofilsuppdatering.

  Om du gör fler än 50 API-anrop per minut returnerar [!DNL Target] felmeddelandet &quot;503 HTTP-status&quot;.

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

  Om en kund överskrider 100 samtidiga [!DNL Target] innehållsleveransbegäranden för en given användarsession, blockeras alla efterföljande begäranden för den användarsessionen. Två eller flera begäranden anses vara samtidiga om alla skickas till servern [!DNL Target] innan svaret tas emot för någon av dem. [!DNL Target] bearbetar samtidiga begäranden för samma session sekventiellt.

   * **Felbeteende**:

      * Delivery API and Batch Mbox v2:
         * Felkod: HTTP 420 för många begäranden
         * Felmeddelande: &quot;För många begäranden med samma sessions-ID&quot;

      * Äldre mbox-API:
         * Standardinnehåll med kommentaren &quot;För många begäranden med samma sessions-ID&quot;

      * at.js:
         * Standardinnehåll visas

* **Gräns**: 50 mbox per [!DNL Target] batchbegäran om innehållsleverans.

  Om fler än 50 rutor per [!DNL Target] begäran om batchmbox för innehållsleverans returneras felkoden `HTTP 400` med felmeddelandet `size must be between 0 and 50`.

  Batch Mbox-begäranden bearbetas sekventiellt, vilket ökar den totala svarstiden för varje iteration. Ju fler kryssrutor på gruppbegäran, desto fler svarstider kan förväntas, och därför kan timeout-fel uppstå. Om upplevelseåtergivning blockeras på dessa batchbegäranden med hög fördröjning kan fördröjningen leda till en försämrad användarupplevelse när användarna väntar på att upplevelserna ska återges.

* **Limit**: 60 MB HTTP POST body size for [!DNL Target] content delivery requests.

  Om du överskrider 60 MB på HTTP POST-brödtextstorleken för en [!DNL Target]-innehållsleveransbegäran resulterar det i en svarsfelkod `HTTP 413 Request Entity Too Large`.

* **Rekommenderad gräns**: 50 meddelanden per [!DNL Target] batchbegäran om leverans.

  Om fler än 50 meddelanden per [!DNL Target]-leveransbatchbegäran överskrids resulterar detta sannolikt i ökad svarstid och timeout.

  Batchmeddelandebegäranden behandlas sekventiellt, vilket ökar den totala svarstiden för varje upprepning. Ju fler meddelanden om batchbegäran, desto fler svarstider kan förväntas, och därför kan timeout-problem uppstå. Vissa ytterligare latens för batchmeddelandebegäranden kan accepteras av vissa kunder, men tänk på att timeout och efterföljande försök kan orsaka ännu mer fördröjning.

## Kundattribut

### Namn på kundattribut

* **Gräns**: 250 tecken genom feed eller API.

### ID för kundattributalias

* **Max** 50 tecken.

### Kundattribut, överföra

* **Maximal filstorlek för varje överföring med HTTP-metoden**: 100 MB.
* **maximal filstorlek för varje överföring med FTP-metoden**: 4 GB.
* **Antal attribut som tillåts prenumerera**: 5 för [!DNL Target Standard] och 200 för [!DNL Target Premium].

## Enheter

### Antal enheter

* Det högsta antalet enheter som kan refereras i en design, antingen hårdkodade eller via slingor, är 99.
* Den rekommenderade gränsen för bästa prestanda är att hålla katalogen under en miljon artiklar per miljö och under tio miljoner objekt i alla miljöer.
* Den maximala gränsen är tio miljoner objekt per miljö och 100 miljoner objekt i alla miljöer. Om du har mellan en miljon och tio miljoner objekt per miljö påverkas prestandan för användargränssnittet för [!UICONTROL Catalog Search]. [!DNL Target Recommendations] fortsätter dock att producera och leverera rekommendationer.

### Anpassade attribut för entitet

* **Anpassade entitetsattribut**: 100.

* **Teckengräns**: Den maximala teckenlängden beror på språket.

   * 15 000 tecken (språk med ett värde, en och två byte)
   * 500 värden, 100 tecken per värde (flervärde)

  Den maximala längden för anpassade attribut för en entitet med ett värde är 15 000 tecken (för UTF-8-kodade språk med en byte och två byte, som engelska och andra latinska skriftspråk) eller 10 000 tecken (för UTF-8-kodade språk med tre byte som kinesiska, japanska och koreanska).

  Anpassade attribut för entiteter med flera värden får inte innehålla fler än 500 värden. Varje enskilt värde är begränsat till 100 tecken. Det totala antalet tecken i alla värden måste uppfylla begränsningarna för den maximala längden för anpassade entitetsattribut med ett värde (se ovan).

### entity.id

* **Gräns för implementeringar som kräver att inköpsinformation hämtas**: 50 tecken.

  Den här gränsen gäller eftersom mbox-parametern `productPurchasedId` hämtar entity.ids, vilket begränsar antalet tecken till 50.

* **Begränsning för implementeringar som endast kräver vybaserade algoritmer:**: 1 000 tecken.

  Vybaserade algoritmer omfattar vy/vy, de senast visade, nyligen visade och så vidare.

## excludeIds {#excludedid}

* **Gräns**: 5 kB för POST-begäranden. 2 083 tecken minus längden på URL:en för GET-begäranden.

  För GET-begäranden gäller att även om gränsen på backend är 5 kB, eftersom Microsoft Internet Explorer begränsar URL:en till 2 083 tecken, är den realistiska gränsen 2 083 tecken minus URL:ens aktuella längd.

## Erfarenheter

### Experience names

* **Max**: 50 tecken.

### Erfarenheter per aktivitet

* **Begränsa**: 2 000 upplevelser per [!UICONTROL Experience Targeting] (XT), [!UICONTROL A/B Test], [!UICONTROL Multivariate Test] (MVT) och [!UICONTROL Auto-Target] aktivitet.

  30 000 upplevelser per Automated Personalization-aktivitet.

### Ändringar per upplevelse

* **Gräns**: 50 per upplevelse för alla aktiviteter

## mboxes

### Attributvärde för profil i rutan {#in-mbox}

* **Gräns**: 256 tecken.

  Värden med fler än 256 tecken trunkeras när at.js 1 används.*x*. Du får ett felmeddelande när du skickar värden med fler än 256 tecken när du använder at.js 2.*x* eller [!DNL Adobe Experience Platform Web SDK]. Värden trunkeras inte automatiskt.

### Profilnamn i mbox

* **Gräns**: 128 tecken.

### mbox names {#mbox-names}

* **Gräns**: 250 tecken.

  För [!DNL Delivery API] (at.js 2.*x*), gruppruta V2 och [!DNL Adobe Experience Platform Web SDK] (alloy.js)-integreringar, mbox-namn *kan* innehålla alfanumeriska tecken (A-Z, a-z, 0-9) och något av följande tecken:

  ```
  - , . _ / = ` : ; & ! @ # $ % ^ & * ( ) _ + | ? ~ [ ] { }
  ```

  För at.js 1.*x*-integreringar, mbox-namn *får inte* innehålla något av följande tecken:

  ```
  ' " %22 %27 < > %3C %3E 
  ```

### mbox-parametrar {#mbox-parameters}

* **Gräns**: Följande begränsningar gäller för mbox-parametrar:

  För vanliga mbox-anrop:

   * mbox-parametrar: 500 parametrar per mbox.
   * Profilparametrar: 500 parameterprofilparametrar per ruta.
   * Andra parametrar (URL, refererande URL, osv.): 50 per mbox för varje annan parametertyp.

  Dessa begränsningar gäller såvida inte begäran förkortas på grund av webbläsarbegränsningar.

  Om du använder API:t för gruppleverans är gränsen 50 mbox per batch-begäran.

  Om du använder API:t för gruppleverans i Mobile Services SDK är gränsen på 50 mbox-parametrar, 50 profilparametrar och 50 för andra parametertyper begränsningar för själva API:t. Det går inte att skicka en begäran som innehåller fler än dessa nummer med API:t för gruppleverans. Om en begäran innehåller fler än dessa begränsningar returnerar API:t följande felmeddelande:

  &quot;Antalet mboxParameters får inte överskrida 50.&quot;

  Begränsningar för slutpunkter:

  **Gruppruta v2**:

   * mbox parameters 100
   * mbox-parameternamn max length 128
   * mbox-parametervärdet får inte vara null
   * mbox-parametervärde 5000
   * profilparametrar 50
   * profilparameternamn max längd 128
   * profilparametervärdet får inte vara null
   * maxlängd för profilparametervärde 256

  **Slutpunkt för leverans-API**:

   * mbox parameters 100
   * mbox-parameternamn max length 128
   * mbox-parametervärdet får inte vara null
   * mbox-parametervärde 5000
   * profilparametrar 50
   * profilparameternamn max längd 128
   * profilparametervärdet får inte vara null
   * maxlängd för profilparametervärde 256

### URL för mbox-begäran

* **Max**: 2 083 tecken.

  Den här gränsen beror på längdbegränsningar i URL:en för Microsoft Internet Explorer.

### parametern mbox3rdPartyId

* **Gräns**: 256 tecken.

## Erbjudanden

### Erbjudandenamn

* **Gräns**: 250 tecken.

### Antal erbjudanden

* **Max**: totalt 150 000 erbjudanden.

  Fel vid synkronisering av aktivitet uppstår om gränsen på 150 000 erbjudanden överskrids.

### Erbjudandestorlek {#offer-size}

Följande storleksbegränsningar gäller för erbjudanden:

* 1 024 kB för HTML.
* 1 024 kB (för varje upplevelse) för visuella erbjudanden från användargränssnittet.
* 1 024 kB från API:t.

  Om du använder en global mbox är gränsen för hela den innehållsuppsättning som returneras för sidan. Genom att begränsa erbjudandestorleken förbättras sidinläsningstiden. Om gränsen överskrids visas följande meddelande:

  &quot;Innehållet i upplevelsen är för stort för att kunna leverera. Ändra upplevelsen så att den påverkar mindre sidkod.&quot;

## orderId-parameter

* **Rekommenderad gräns**: 120 tecken.

## orderTotal-parameter

* **Rekommenderad gräns**: 120 tecken.

## productPurchasedId, parameter

* **Max**: 50 tecken per kommaavgränsat värde och totalt 250 tecken. Enskilda värden som är längre än 50 tecken trunkeras av systemet. Sammanlagda längder på över 250 tecken resulterar i ett 400-fel.

## Profilskript

* **Rekommenderad gräns för aktiva profilskript (de som är aktiverade)**: 300

* **Rekommenderad gräns för totalt antal profilskript per konto**: 2 000

* **Rekommendationer för att begränsa komplexiteten i profilskript**: Profilskript kan köra ett begränsat antal instruktioner. Mer information finns i [God praxis](/help/main/c-target/c-visitor-profile/profile-parameters.md#best) i *Profilattribut*.

## Egenskaper

* **Rekommenderad gräns**: 5 000 egenskaper.

## Rapportera målgrupper/segment

* **Gräns**: 50 rapportmålgrupper/segment per aktivitet.

## sessionID

Sessions-ID kan vara vilken utskrivbar sträng som helst, förutom blanksteg, frågetecken ( ? ), klammerparenteser ( { } ) eller ett snedstreck ( / ). Det ska vara mellan 1 och 128 tecken långt.

## Skriptprofilens indataruta i användargränssnittet för [!DNL Target]

* **Rekommenderad gräns**: 2 000 tecken.

  Beroende på storleken på den kodade strängen, som kan vara mycket längre än Raw-strängen. Om strängen är för stor misslyckas den innan den når [!DNL Adobe Target].

## Skriptprofiler

### Skriptprofilnamn

* **Max**: 50 tecken.

### Värden för skriptprofil

* **Max**: 2 048 tecken.

  Av prestandaskäl rekommenderar vi ett returvärde på högst 256 tecken.

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
* **Rekommenderad gräns**: 50 000 unika värden per målgrupp över målinriktningsregler.
* **Rekommenderad gräns**: 100 000 unika målregelvärden per aktivitet.
