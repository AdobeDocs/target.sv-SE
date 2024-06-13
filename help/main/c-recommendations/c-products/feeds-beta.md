---
keywords: rekommendationsfeed;feed;SAINT;ftp;csv;klassificeringar;analysklassificeringar
description: Lär dig hur feeds importerar entiteter till [!DNL Adobe Target] [!DNL Recommendations] med CSV-filer [!DNL Google Product Search] matningsformat, och [!DNL Analytics] produktklassificeringar.
title: Hur jag använder [!UICONTROL Feeds] in [!DNL Target Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: f29f9b5c234dc629d104afaccdf50010dc825ea1
workflow-type: tm+mt
source-wordcount: '2423'
ht-degree: 0%

---

# Feeds

Använd feeds för att importera enheter till [!DNL Adobe Target] [!DNL Recommendations]. Enheter kan skickas med CSV-filer, [!DNL Google Product Search] matningsformat, och [!DNL Adobe Analytics] produktklassificeringar.

## Feeds - översikt {#concept_D1E9C7347C5D4583AA69B02E79607890}

Du kan skicka feeds [Enheter](/help/main/c-recommendations/c-products/products.md) eller utöka dina mbox-data med information som antingen inte är tillgänglig på sidan eller som inte kan skickas direkt från sidan. Exempel: marginal, kostnad för sålda varor (COGS) osv.

Du kan även skicka detaljerad objektinformation till [!DNL Recommendations], till exempel produkt-ID, kategori, namn, meddelande och andra attribut.

Du kan välja vilka kolumner i [!DNL Target] produktklassificeringsfil eller [!DNL Google Product Search] filen som du vill skicka till [!DNL Recommendations] server.

Dessa datadelar för varje objekt kan sedan användas för att:

* Visa värden i design
* Definiera villkor för inkludering
* Sortera objekt i olika samlingar
* Tillämpa undantag för rekommendationer

Artikelbeskrivningar kan skickas till [!DNL Target] med hjälp av feeds eller mbox. If [!DNL Target] samlar in data både med en enhetsfeed och en mbox, vilket innebär att de senaste data vinner. Vanligtvis kommer de senaste data från en mbox, eftersom de visas oftare. I den sällsynta händelse att enhetsmatningsdata och mbox-data träffar samtidigt, används mbox-data.

The [!UICONTROL Feeds] lista ( **[!UICONTROL Recommendations]** > **[!UICONTROL Feeds]**) innehåller information om alla feeds som du har skapat.

![Sidan Feeds](/help/main/c-recommendations/c-products/assets/feeds-page-new.png)

The [!UICONTROL Feeds] sidan innehåller följande kolumner:

* **Namn**: Namnet på den feed som angavs när den skapades. Om du vill redigera namnet på en feed måste du redigera själva feeden. När du sparar feeden med det nya namnet uppdateras feeden.
* **Status**: Aktuell feed [status](/help/main/c-recommendations/c-products/feeds.md#concept_E475986720D1400999868B3DFD14A7A0).
* **Typ**: Typerna innefattar [CSV](/help/main/c-recommendations/c-products/feeds.md#section_65CC1148C7DD448FB213FDF499D35FCA), [[!DNL Google Product Feed]](/help/main/c-recommendations/c-products/feeds.md#section_8EFA98B5BC064140B3F74534AA93AFFF)och [Analysklassificeringar](/help/main/c-recommendations/c-products/feeds.md#section_79E430D2C75443BEBC9AA0916A337E0A).
* **Objekt**: Visar antalet objekt i feeden.
* **Schema**: Visar uppdateringsschemat för feeden: [!UICONTROL Daily], [!UICONTROL Weekly], [!DNL Every 2 Weeks], eller [!UICONTROL Never].
* **Senast uppdaterad**: Visar datum och tid då flödet senast uppdaterades och namnet på den person som uppdaterade flödet.

Klicka på [!UICONTROL Customize Table] ikon ( ![Ikonen Anpassa tabell](/help/main/c-recommendations/c-products/assets/customize-table-icon.png) ) för att markera eller avmarkera kolumner som du vill visa.

Klicka på [!UICONTROL Information] om du vill visa ett kort som visar det senaste överföringsdatumet och feed-URL:en.

Klicka på ellipsikonen för att komma åt följande åtgärder: [!UICONTROL Deactivate], [!DNL Edit], [!UICONTROL Copy]och [!UICONTROL Delete].

>[!IMPORTANT]
>
>Överförda entiteter och entitetsattribut upphör att gälla efter 61 dagar. Detta innebär:
>
>* Din feed bör köras minst en gång i månaden för att säkerställa att kataloginnehållet inte går ut.
>* När du tar bort ett objekt från din feed-fil tas det inte bort från katalogen. Om du vill ta bort ett objekt från katalogen tar du manuellt bort objektet via [!DNL Target] Gränssnitt eller API. Eller ändra artikelattributen (t.ex. lager) för att säkerställa att artikeln utesluts från övervägande.

## Källtyper

Enheter kan skickas med CSV-filer, [!DNL Google Product Search] matningsformat, och [!DNL Adobe Analytics] produktklassificeringar.

### CSV {#section_65CC1148C7DD448FB213FDF499D35FCA}

Du kan skapa en CSV-fil med [!DNL Adobe] tillverkarspecifikt CSV-överföringsformat. Filen innehåller visningsinformation om de reserverade och anpassade attributen för dina produkter. Ersätt om du vill överföra attribut som är specifika för implementeringen `CustomN` i rubrikraden med namnet på det attribut som du vill använda. I exemplet nedan `entity.Custom1` har ersatts med: `entity.availability`. Du kan sedan överföra filen till [!DNL Recommendations] server.

Att använda CSV-formatet har följande fördelar jämfört med [!DNL Google] feed-format:

* CSV-formatet kräver inte fältkopplingar.
* CSV-formatet stöder attribut med flera värden (se exemplet nedan).
* CSV-formatet har stöd för upp till 100 anpassade attribut. Om du behöver fler än 100 anpassade attribut kan du skapa en andra feed-fil med en annan uppsättning anpassade attribut angivna.

Använd metoden för massöverföring för att skicka visningsinformation om du inte har några kryssrutor på sidan, eller om du vill komplettera visningsinformationen med objekt som inte är tillgängliga på webbplatsen. Du kan till exempel skicka lagerinformation som inte är publicerad på din plats.

Alla data som har överförts med CSV-filen, Google produktfeed eller [!DNL Analytics] Produktklassificeringsfeed skriver över det befintliga entitetsattributvärdet i databasen. Om du skickar prisinformation via mbox-begäranden och sedan skickar olika prisvärden i filen, skriver värdena i filen över de värden som angetts med mbox-begäran. Undantaget är `categoryId` entitetsattribut där kategorivärdena läggs till i stället för att skrivas över upp till gränsen på 250 tecken.

>[!IMPORTANT]
>
>Omge inte värden med citattecken ( &quot; ) i CSV-filen om de inte är avsiktliga. Om du omsluter värden med dubbla citattecken måste du undvika dem genom att omsluta dem med en annan uppsättning dubbla citattecken. Dubbla citattecken som inte escape-konverteras förhindrar att rekommendationsfeeden läses in korrekt.

Följande syntax är till exempel felaktig:

```
"Apples "Bananas" Grapes"",
```

Följande syntax är korrekt:

```
"Apples ""Bananas"" Grapes""",
```

>[!NOTE]
>
>Du kan inte skriva över ett befintligt värde med ett tomt värde. Skriv över det befintliga värdet genom att ange ett annat värde. Vid ett försäljningspris är en gemensam lösning att antingen skicka in ett faktiskt&quot;NULL&quot; eller något annat meddelande. Du kan sedan skriva en mallregel för att exkludera objekt med det värdet.

Produkten är tillgänglig i administratörsgränssnittet cirka två timmar efter att enheten har överförts.

Följande är exempelkod för en CSV-fil:

```
## RECSRecommendations Upload File 
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines. 
## RECS 
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left. 
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'. 
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations. 
## RECSentity.id,entity.name,entity.categoryId,entity.message,entity.thumbnailUrl,entity.value,entity.pageUrl,entity.inventory,entity.margin,entity.last_updated_by,entity.multi_english,entity.availability,entity.tax_country,entity.tax_region,entity.tax_rate,entity.product_type,entity.item_group_id,entity.color,entity.size,entity.brand,entity.gtin 
na3456,RipCurl Watch with Titanium Dial,Watches & Sport,Cutting edge titanium with round case,https://example.com/s7/na3456_Viewer,425,https://example.com/shop/en-us/na3456_RipCurl,24,0.25,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Titanium,44mm,RipCurl,"075380 01050 5" 
na3457,RipCurl Watch with Black Dial,Watches & Sport,Cutting edge matte black with round case,https://example.com/s7/na3457_Viewer,275,https://example.com/shop/en-us/na3457_RipCurl,24,0.27,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Black,44mm,RipCurl,"075340 01060 7"
```

### [!DNL Google] {#section_8EFA98B5BC064140B3F74534AA93AFFF}

The [!DNL Google Product Search] matningstypen använder [!DNL Google] format. Detta skiljer sig från [!DNL Adobe] tillverkarspecifikt CSV-överföringsformat.

Om du har en befintlig [!DNL Google Product Feed]kan du använda den som importfil.

>[!NOTE]
>
>Du behöver inte använda [!DNL Google] data. [!DNL Recommendations] använder samma format som [!DNL Google]. Du kan använda den här metoden för att överföra data som du har och använda de tillgängliga schemafunktionerna. Du måste dock behålla [!DNL Google] fördefinierade attributnamn när du konfigurerar filen.

De flesta återförsäljare överför produkter till [!DNL Google], så när en besökare använder [!DNL Google] produktsökning visas. [!DNL Recommendations] följer [!DNL Google] exakt för entitetsflöden. Enhetsfeeds kan skickas till [!DNL Recommendations] via .xml, .txt eller .tsv, och kan använda [attribut som definieras av Google](https://support.google.com/merchants/answer/188494?hl=en&amp;topic=2473824&amp;ctx=topic#US). Resultaten är sökbara på [[!DNL Google] shoppingsidor](https://www.google.com/prdhp).

>[!NOTE]
>
>Metoden POST måste vara tillåten på den server som är värd för [!DNL Google] feed-innehåll.

För [!DNL Recommendations] användare redan har konfigurerat .xml- eller .txt-feeds att skicka till [!DNL Google] antingen via URL eller FTP godkänner entitetsflödena produktdata och använder dem för att skapa rekommendationskatalogen. Ange var denna feed finns och rekommendationsservern hämtar data.

Om du [!DNL Google Product Search] för överföring av enhetsfeed måste du fortfarande ha en produktsidesruta på sidan om du vill visa rekommendationer där eller spåra produktvyer för algoritmleverans baserat på vyer.

[!DNL Google] feeds stöder inte flera värden för ett anpassat attribut.

Flödet körs när du sparar och aktiverar det. Den körs vid den tidpunkt då du sparar flödet, och därefter varje dag i en timme.

Följande är exempelkod för en [!DNL Google Product Search] feed-XML-fil:

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?> 
<feed xmlns="https://www.w3.org/2005/Atom" xmlns:ns2="https://base.google.com/ns/1.0" xmlns:ns3="https://base.google.com/cns/1.0"> 
    <title>Product Feed</title> 
    <link href="https://example.com"/> 
    <updated>2017-12-13T08:45:04.918-08:00</updated> 
    <author> 
        <name>Product Feed Author</name> 
    </author> 
    <id>https://example.com</id> 
    <entry> 
        <title>RipCurl Watch with Titanium Dial</title> 
        <description>Cutting edge Titanium with Round case</description> 
        <ns2:id>na3452</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3452_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 01050 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3452_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3452_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>425</ns2:price> 
        <ns2:product_review_average>5.0</ns2:product_review_average> 
        <ns2:product_review_count>30</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>375</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
    <entry> 
        <title>RipCurl Watch with Black Dial</title> 
        <description>Cutting edge matte black with Round case</description> 
        <ns2:id>na3453</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3453_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 013450 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3453_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3453_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>275</ns2:price> 
        <ns2:product_review_average>4.8</ns2:product_review_average> 
        <ns2:product_review_count>23</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>249</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
</feed> 
```

Följande är exempelkod för en [!DNL Google Product Search] feed.tsv-fil:

```
id    title    description    link    price    condition    availability    image_link    tax    shipping_weight    shipping    google_product_category    product_type    item_group_id    color    size    gender    age_group    pattern    brand    gtin    mpn 
na3454    RipCurl Watch with Titanium Dial    Cutting edge titanium with round case    https://example.com/shop/en-us/na3454_RipCurl    425    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075380 01050 5    DZ1437 
na3455    RipCurl Watch with Black Dial    Cutting edge matte black with round case    https://example.com/shop/en-us/na3455_RipCurl    275    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075340 01060 7    DZ1446
```

### [!DNL Analytics] Produktklassificeringar {#section_79E430D2C75443BEBC9AA0916A337E0A}

The [!DNL Adobe Analytics] Produktklassificering är den enda klassificeringen som är tillgänglig för rekommendationer. Mer information om den här klassificeringsfilen finns i [Om klassificeringar](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html) i *Analyskomponenter* guide. Det är möjligt att inte all information du behöver för rekommendationer finns tillgänglig i den aktuella implementeringen, så följ den här användarhandboken om du vill lägga till i klassificeringsfilen.

>[!IMPORTANT]
>
>Innan du importerar enhetsdata till [!DNL Recommendations] använda [!DNL Analytics] produktklassificeringar bör du vara medveten om att detta inte är den rekommenderade metoden.
>
> Var uppmärksam på följande kavattar:
>
>* Uppdateringar av entitetsattribut medför en ytterligare fördröjning på upp till 24 timmar.
>* [!DNL Target] supports [!UICONTROL Product Classifications] endast. The [!DNL Analytics] produkt-SKU måste mappas till samma nivå som [!DNL Recommendations] `entity.id`. Egen [!DNL Analytics] Klassificeringar kan utformas med [!UICONTROL Adobe Consulting Services]. Kontakta din kontoansvarige med frågor.

## Skapa feed {#steps}

Skapa ett flöde för att infoga information om dina produkter eller tjänster i [!DNL Recommendations].

1. Från [!DNL Target] gränssnitt, klicka **[!UICONTROL Recommendations]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]**.

   ![Dialogrutan Skapa feed](assets/CreateFeed.png)

1. Ange ett beskrivande namn för feeden.
1. Välj en **[!UICONTROL Source Type]**.

   * [!UICONTROL CSV]
   * [!UICONTROL Google Product Feed]
   * [!UICONTROL Analytics Classifications]

   Mer information om [!UICONTROL CSV] och [!UICONTROL Google Product Feed] flödestyper, se [Feeds - översikt](/help/main/c-recommendations/c-products/feeds.md#concept_D1E9C7347C5D4583AA69B02E79607890). Du kan också [hämta en CSV-modellguide](/help/main/c-recommendations/c-products/assets/EntityFileUploadTemplate.csv) för att du ska kunna formatera matningen korrekt.

1. (Villkorligt) Om du har valt **[!UICONTROL CSV]** eller **[!UICONTROL Google Product Feed]** anger du platsen där feeden kan användas.

   * **FTP**: Om du har valt FTP anger du FTP-serverinformationen, inloggningsuppgifterna, filnamnet och FTP-katalogen. Du kan använda FTP med SSL (FTPS) för säkrare överföringar.

     FTP-serverinställningar som stöds:

      * FTP och FTPS måste anges till Passiv FTP.
      * För FTPS ska du konfigurera servern så att den accepterar explicita FTPS-anslutningar.
      * SFTP stöds inte.
      * Du kan ange en port som anslutningen ska initieras på manuellt (till exempel `ftp://ftp.yoursite.com:2121`). Om du inte anger någon port används FTP- eller FTPS-standardporten.

   * **URL**: Om du väljer [!UICONTROL URL]anger du URL-adressen.

1. (Villkorligt) Om du har valt **[!UICONTROL Analytics Classifications]** väljer du rapportsviten i listrutan.

1. Klicka på **[!UICONTROL Next]** pil för att visa [!UICONTROL Schedule] alternativ.

   ![Stegresultat](assets/CreateFeedSchedule.png)

1. Välj ett uppdateringsalternativ:

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 Weeks]
   * [!UICONTROL Never]: Schemalägg inte någon uppdatering. Välj det här alternativet om du inte vill att denna feed ska köras.

1. Ange den tid då du vill att din feed ska köras.

   Det här alternativet baseras på den tidszon som används i webbläsaren. Om du vill använda en tid i en annan tidszon måste du beräkna den tiden enligt din tidszon.

1. Klicka på **[!UICONTROL Next]** pil för att visa [!UICONTROL Mapping] anger du sedan hur du vill mappa dina data till [!DNL Target] definitioner.

   ![Stegresultat](assets/CreatFeedMapping.png)

1. (Valfritt) Om du vill att flödet ska tillhöra en miljö (värdgrupp) väljer du värdgruppen.

   Som standard tillhör feeden alla värdgrupper. Detta garanterar att objekt i denna feed är tillgängliga i alla miljöer. Mer information finns i [Värdar](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

1. Klicka på **[!UICONTROL Save]**.

När du har skapat eller redigerat en feed körs den omedelbart. Flödet uppdateras sedan enligt de parametrar som du anger. Det tar ett tag innan informationen är tillgänglig. Först måste feeden synkroniseras, sedan måste den bearbetas och indexeras innan den kan publiceras och göras tillgänglig. Aktuell status visas under [Feed-status](/help/main/c-recommendations/c-products/feeds.md#status) i [!UICONTROL Feeds] lista. Du kan stänga [!DNL Target] innan processen är klar och processen fortsätter.

När indexering pågår visas produkter och flödeshuvuden innan enskilda värden har indexerats. På så sätt kan du söka efter och visa produkter så att du kan skapa samlingar, uteslutningar, designer och aktiviteter innan indexeringen har slutförts.

När det står&quot;Slutfört&quot; i status betyder det att filen hittades och att den tolkades korrekt. Informationen är inte tillgänglig inom [!DNL Recommendations] tills filen har indexerats, vilket kan ta lite tid, beroende på filens storlek. Om processen misslyckas betyder det att filen inte kunde hittas. Du använde till exempel en felaktig URL eller FTP-informationen var felaktig eller så var det ett tolkningsfel.

## Feedstatus och indikatorer {#concept_E475986720D1400999868B3DFD14A7A0}

Information om möjliga feedstatusar och deras indikatorer.

### Feed-status {#status}

Följande är möjliga statusvärden för en feed:

| Status | Beskrivning |
|--- |--- |
| [!UICONTROL Syncing] | Feedinställningsinformation sparas i [!DNL Target]. |
| [!UICONTROL Sync Failed] | Det gick inte att spara information om matningsinställningar i [!DNL Target]. Försök igen. |
| [!UICONTROL No Feed Run] | Du har skapat en feed men den har inte schemalagts (frekvensen anges till Aldrig). |
| Schemalagd *datum och tid* | Feed har inte körts, men är schemalagd att köras vid angivet datum och angiven tid. |
| [!UICONTROL Waiting for Download] | [!DNL Target] förbereder hämtning av feed-filen. |
| [!UICONTROL Downloading Feed File] | [!DNL Target] hämtar feed-filen. |
| [!UICONTROL Importing Items] | [!DNL Target] importerar objekt från feed-filen. |
| Feed importerades: *tid* | [!DNL Target] har importerat feed-filen till innehållsleveranssystemet. Ändringar av objektattribut har gjorts i innehållsleveranssystemet och kommer snart att återspeglas i levererade rekommendationer. Om du inte ser de förväntade ändringarna kan du försöka igen och uppdatera sidan med rekommendationer.<br>Anteckningar:<ul><li>Om ändringar i ett objekts attribut leder till att ett objekt utesluts från rekommendationerna, återspeglas uteslutningen omedelbart. Om ett objekt läggs till nyligen eller om attributen ändras resulterar det i att ett objekt *inte längre* som inte ingår i rekommendationerna återspeglas inte förrän nästa algoritmuppdatering, som sker inom 24 timmar.</li><li>När den här statusen visas kanske inte uppdateringarna visas i [!UICONTROL Catalog Search] Gränssnitt. En separat status visas i [!UICONTROL Catalog Search] som anger den senaste gången den sökbara katalogen uppdaterades.</li></ul> |
| [!UICONTROL Failed to Index] | Indexåtgärden misslyckades. Försök igen. |
| [!UICONTROL Server Not Found] | FTP- eller URL-platserna är ogiltiga eller går inte att nå på annat sätt. |

Om du vill uppdatera en feed (till exempel för att ändra din flödeskonfiguration eller feed-fil) öppnar du den, gör önskade ändringar och klickar på **[!UICONTROL Save]**.

>[!IMPORTANT]
>
>Överförda enheter upphör att gälla efter 61 dagar. Det innebär att din feed-fil ska laddas upp minst var 60:e dag för att undvika avbrott i dina rekommendationer. Om ett objekt inte ingår i en feed-fil (eller någon annan metod för enhetsuppdatering) minst en gång var 60:e dag, [!DNL Target] infogar objektet som inte längre är relevant och tar bort det från katalogen.

### Indikatorer för matningsstatus {#section_3C8A236C5CB84C769A9E9E36B8BFABA4}

Följande statusindikatorer för feed visas i [!UICONTROL Status] kolumn:

| Statusindikator | Beskrivning |
|--- |--- |
| Grön statusindikator | När en feed har indexerats utan fel anger en grön statuspunkt att feeden är i ett lyckat läge. |
| Gul statusindikator | När ett feed- eller feed-index fördröjs med 25 % av matningsfrekvensen visas en gul statuspunkt. En gul punkt visas till exempel för en feed-uppsättning som körs dagligen om indexet inte har slutförts sex timmar efter den schemalagda tiden. Obs! När matningsstatusen är&quot;Väntar på indexkö&quot; är de nyligen uppdaterade värdena tillgängliga vid leverans och villkorsbearbetning. |
| Indikator för vit status | När en feed inte är schemalagd anger en vit statuspunkt att den inte har körts än. |
| Röd statusindikator | Om feeden inte kan överföra data till servern visas en röd statusindikator. |

Titta på följande exempel:

**Exempel 1:**

* Dag ett: dagliga foderprocesser klockan 9.00 PST.
* Dag två: klockan är 23.30 och maten har inte gått sedan i går klockan 9.00.

Statusen bör vara gul eftersom indexet borde ha körts för cirka 6,5 timmar sedan. 6,5 timmar +24 är 127% av matningsfönstret.

**Exempel 2:**

* 1 januari: månatliga feed-processer klockan 9:00 PST.
* 3 februari: klockan är 10.00 och maten har inte gått på en månad, en dag och en timme sedan.

Statusen ska vara gul eftersom indexet ska ha körts för ungefär en dag och en timme sedan. Även om detta endast är (31+(1/25))/30 = 1,03 % av frekvensinställningen, överskred det maximala antalet endagsfördröjningar.

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Förstå flöden i Recommendations (3:01) ![Märket Översikt](/help/main/assets/overview.png)

Den här videon innehåller följande information:

* Förstå syftet med feeds
* Förstå värdet av flöden

>[!VIDEO](https://video.tv.adobe.com/v/27695)

### Skapa en feed (6:44) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller följande information:

* Konfigurera en feed
* Ha koll på vilken typ av feed som ska användas

>[!VIDEO](https://video.tv.adobe.com/v/27696)