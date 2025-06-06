---
keywords: Målinriktning
description: Läs om hur Adobe [!DNL Target] visar och beräknar konverteringsgraden, ökningen, förtroendet och konfidensintervallet för varje upplevelse.
title: Hur visar jag konverteringsgraden, avbrottsnivån och konfidensnivån?
feature: Reports
exl-id: b4cfe926-eb36-4ce1-b56c-7378150b0b09
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '2113'
ht-degree: 0%

---

# Konverteringsgrad

Konverteringsfrekvens, lyft, konfidensintervall och konfidensintervall rapporteras för varje upplevelse.

Följande bild visar diagramrubriken för en exempelaktivitet med rubrikerna [!UICONTROL Conversion Rate], [!UICONTROL Lift] och [!UICONTROL Confidence] markerade.

![bild med konverteringsgrad](assets/conversion-rate.jpg)

>[!NOTE]
>
>I alla data ignoreras dubblettorder om en `orderID` skickas. Revideringsrapporten innehåller en lista över ignorerade dubblettorder.

## Konverteringsgrad {#section_07A36846C4E84D0881906809B9CE5A74}

Visar mediankonverteringsfrekvens, konfidensintervall och antal konverteringar.

Titta till exempel i följande rapportkolumn för konverteringsgrad:

![bild med konverteringsgrad och detaljskärpa](assets/conversion-rate-detail.jpg)

Den första raden är kontrollupplevelsen. Den visar en konverteringsgrad på 15 %, med tre konverteringar. Den andra raden, Experience B, visar en konverteringsgrad på 15 %, med ett konfidensintervall på plus eller minus 15,65 % och tre konverteringar.

>[!NOTE]
>
>För närvarande beräknas konfidensintervallet bara för binära värden.

## Lyft {#section_0F409572C720433D9378092ABC999982}

Jämför konverteringsgraden för varje upplevelse med kontrollupplevelsen.

Lyft = (Experience CR - Control CR) / Ctrl CR

Om kontrollen är 0, finns ingen procentuell lyft.


## Butiksdata {#section_30A674731BA6440E9BB93C421BE990EE}

AOV-, RPV- och Sales-data visas för varje upplevelse om du infogade en monteringsorder (`orderConfirmPage`) och valde den som konverteringsruta.

## Konfidensnivå och konfidensintervall {#concept_0D0002A1EBDF420E9C50E2A46F36629B}

För varje upplevelse visas konfidensintervallet och konfidensintervallet.

Du kan utföra offlineberäkningar för Analytics för Target (A4T), men det krävs ett steg med dataexporter i [!DNL Analytics]. Mer information finns i&quot;Utföra offlineberäkningar för analys av mål (A4T)&quot; nedan.

### Förtroende {#section_26FE5E44BDD5478792A65FCFD83DCCDC}

Förtroendet hos en upplevelse eller ett erbjudande som visas är en sannolikhet (uttryckt i procent) att få ett resultat som är mindre extrem än det som faktiskt observeras, om nollhypotesen är sann (i praktiken om det inte finns någon skillnad i konverteringsgraden mellan upplevelsen eller erbjudandet och kontrollupplevelsen/erbjudandet). När det gäller p-värden är den här tillförlitligheten 1 - p-värde. Enklare uttryckt innebär ett högre förtroende att data inte är förenliga med antagandet att kontrollerbjudandet och upplevelsen utan kontroll har samma konverteringsgrad.

Konfidensen avrundar till upp till 100,00 % när förtroendet är större än eller lika med 99,995 %.

![conf_report image](assets/conf_report.png) ![conf_report_detail image](assets/conf_report_detail.png)

Innan du fattar några affärsbeslut ska du försöka vänta tills exempelstorleken är tillräckligt stor och att de fyra konfidensintervallen för en eller flera upplevelser är konsekventa hela tiden för att säkerställa att resultaten är stabila.


### Konfidensintervall {#section_F582738DFE1648C78B93D81EBC6CACF7}

>[!NOTE]
>
>För närvarande beräknas konfidensintervallet bara för binära värden.

*konfidensintervallet* är ett intervall med uppskattningar inom vilka det sanna värdet för måttet kan hittas på en given konfidensnivå. Target har alltid 95% konfidensintervall. Konfidensintervallet visas som ett ljusgrått +/- procentvärde i kolumnen Konverteringsfrekvens. I exemplet nedan är konfidensintervallet för Experience B plus eller minus 15,65 %.

![conversion_rate, bild](assets/conversion_rate.png)

**Exempel:** En upplevelseobserverad RPV är $10, och dess 95% **konfidensintervall** är $5 till $15. Okänd för oss är dess verkliga RPV 12 dollar. Om vi sedan kör testet flera gånger kommer 95 % av tiden som vi beräknar att innehålla värdet _true_ för RPV på 12 USD.

**Vad påverkar konfidensintervallet?** Formeln följer statistiska standardmetoder för beräkning av konfidensintervall.

* **Samplingsstorlek:** I takt med att samplingsintervallet växer krymper eller förminskas intervallet. Detta är att föredra eftersom det innebär att dina rapporter närmar sig det verkliga värdet av framgångsmåttet.
* **Standardavvikelsen är mindre:** Mer likartade resultat, som liknande AOV:er eller liknande nummer eller besökare som konverterar varje dag, minskar standardavvikelsen.

## Konfidenskalering och hur den utförs offline {#section_86F7C231943043A5B8B6BFE67B706E3B}

Den [hämtade CSV-rapporten](/help/main/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) innehåller endast rådata och innehåller inte beräknade värden, t.ex. intäkter per besökare, lyft eller förtroende som används för A/B-tester.

Om du vill beräkna de beräknade måtten hämtar du målets [Complete Confidence Calculator](/help/main/assets/complete_confidence_calculator.xlsx) -Excel-fil för att ange aktivitetens värde, eller granskar [statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

>[!NOTE]
>
>Den här räknaren används för målbaserad rapportering och inte för A4T-rapportering.

## Utföra offlineberäkningar för analys för Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Du kan utföra offlineberäkningar för A4T, men det krävs ett steg med dataexporter i [!DNL Analytics].

För A4T använder vi en [Welchs t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank}-beräkning för kontinuerliga variabler (i stället för binära värden). I Analytics spåras alltid en besökare, och alla åtgärder som vidtas räknas. Om besökaren köper flera gånger eller besöker ett framgångsmått flera gånger räknas de ytterligare träffarna. Detta gör mätvärdet till en kontinuerlig variabel. För att utföra Welchs t-test-beräkning krävs ’summan av kvadrater’ för att beräkna variansen, som används i t-statistikens nämnare. [Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md) förklarar detaljerna för de matematiska formler som används. Summan av fyrkanter kan hämtas från [!DNL Analytics]. Om du vill få summan av kvadratdata måste du utföra en export på besökarnivå för det mätresultat som du optimerar för, under en provtidsperiod.

Om du till exempel optimerar till sidvisningar per besökare, kan du exportera ett exempel på det totala antalet sidvisningar per besökare för en viss tidsperiod, kanske några dagar (ett par tusen datapunkter är allt du behöver). Därefter fyrkantiga varje värde och summerar summan (operationsordningen är viktig här). Värdet&quot;summan av kvadrater&quot; används sedan i Complete Confidence Calculator. Använd avsnittet &quot;intäkt&quot; i kalkylbladet för dessa värden.

**Så här använder du dataexportfunktionen [!DNL Analytics]:**

1. Logga in på [!DNL Adobe Analytics].
1. Klicka på **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]**.
1. Fyll i fälten på fliken **[!UICONTROL Data Warehouse Request]**.

   Mer information om de olika fälten finns i Data Warehouse Descriptions i [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=sv-SE).

   | Fält | Instruktioner |
   |--- |--- |
   | Namn på begäran | Ange ett namn för din begäran. |
   | Rapportdatum | Ange en tidsperiod och granularitet.<br>Som bästa praxis bör du välja högst en timme eller en dag med data för din första begäran.  Datan Warehouse tar längre tid att bearbeta längre tid än vad som begärts, så det är alltid en god vana att först begära data om en liten tidsperiod för att vara säker på att filen returnerar det förväntade resultatet. Gå sedan till Request Manager, duplicera din begäran och be om fler data vid andra gången. Om du växlar granularitet till något annat än &quot;Inget&quot; ökar filstorleken drastiskt.<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | Tillgängliga segment | Använd ett segment efter behov. |
   | Uppdelningar | Välj önskade mått: Standard är förberett (OTB), medan Custom innehåller eVars &amp; Props. Vi rekommenderar att du använder&quot;besökar-ID&quot; om information på besökar-ID-nivå behövs, i stället för&quot;Experience Cloud Visitor-ID&quot;.<ul><li>Besökar-ID är det sista ID som används av Analytics. Det blir antingen ett ID (om kunden är äldre) eller ett MID (om kunden är ny eller rensad på cookies sedan besökar-ID-tjänsten för MC startades).</li><li>Experience Cloud Visitor-ID kommer endast att anges för kunder som är nya eller rensade cookies sedan besöks-ID-tjänsten startades.</li></ul> |
   | Mått | Välj önskade mätvärden. Standard är OTB, medan Anpassad innehåller anpassade händelser. |
   | Förhandsgranska rapport | Granska inställningarna innan du schemalägger rapporten.<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | Schemalägg leverans | Ange en e-postadress som filen ska skickas till, ge filen ett namn och välj sedan [!UICONTROL Send Immediately].<br>Obs! Filen kan levereras via FTP under [!UICONTROL Advanced Delivery Options]<br>![Schemalägg leverans](/help/main/c-reports/assets/datawarehouse3.png). |

1. Klicka på **[!UICONTROL Request this Report]**.

   Filleveransen kan ta upp till 72 timmar, beroende på mängden data som begärs. Du kan när som helst kontrollera förloppet för din begäran genom att klicka på [!UICONTROL Tools] > [!UICONTROL Data Warehouse] > [!UICONTROL Request Manager].

   Om du vill begära om data som du har begärt tidigare kan du duplicera en gammal begäran från [!UICONTROL Request Manager] efter behov.

Mer information om [!DNL Data Warehouse] finns i följande länkar i hjälpdokumentationen för [!DNL Analytics]:

* [Skapa en begäran om Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html?lang=sv-SE)
* [Bästa praxis för Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html?lang=sv-SE)

## Räkningsmetod {#concept_EC19BC897D66411BABAF2FA27BCE89AA}

Du kan välja att visa rapporter med olika beräkningsmetoder för att förstå hur dina aktiviteter påverkar dina användare under deras livstid eller under en enda session.

Räkningsmetod stöds för följande aktivitetstyper:

* A/B-test

  Ett undantag är att A/B-aktiviteter med Automatiskt mål endast stöder standardmetoden för Besök.

* Experience Targeting (XT)
* Multivariata tester (MVT)

  För MVT-elementets bidragsrapport stöder inte Target aktivitetsexponeringar för intäktsmätningstyper.

* Recommendations

Endast standardmetoden för antal besök (Besök) stöds för närvarande för Automated Personalization-aktiviteter (AP).

Du kan visa rapporter med följande beräkningsmetoder:

* **Besökare:** En unik deltagare i aktiviteten under aktivitetens livstid.

  En person räknas som ny deltagare om han eller hon besöker webbplatsen från en ny dator eller en ny webbläsare, tar bort cookien eller konverterar och återgår till aktiviteten med samma cookie. En deltagare identifieras av PCID i besökarens mbox-cookie. Om PCID ändras betraktas personen som en ny besökare.

* **Besök:** En unik deltagare i en upplevelse under en enstaka 30-minuters webbläsarsession.

  Om en besökare konverteras eller återkommer till webbplatsen efter att ha varit borta i minst 30 minuter räknas en återkommande besökare som ett nytt besök. Ett besök identifieras av `sessionID` i besökarens mbox-cookie. När `sessionID` ändras betraktas besöket som nytt.

* **Impression/sidvy:** Räknas varje gång en besökare läser in en sida i aktiviteten.

  Ett enda besök kan innehålla flera visningar av till exempel din hemsida.

>[!NOTE]
>
>Antalet bestäms vanligtvis av cookies och sessionsaktivitet. Om du når den sista konverteringspunkten för en aktivitet och sedan anger aktiviteten igen, betraktas du som en ny deltagare och ett nytt besök i aktiviteten. Detta gäller även om dina PCID- och `sessionID`-värden inte ändras.

## Varför rekommenderar [!DNL Target] att du använder Welchs t-test? {#t-test}

A/B-tester är experiment för att jämföra medelvärdet av vissa företagsvärden i en kontrollvariant (kallas även upplevelse) med medelvärdet av samma mätvärden i en eller flera alternativa upplevelser.

[!DNL Target] rekommenderar att du använder [Welchs t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test) eftersom dessa kräver färre antaganden än alternativ som z-test, och är det lämpliga statistiska testet för att utföra parvisa jämförelser av (kvantitativa) affärsvärden mellan en kontrollupplevelse och alternativa upplevelser.

### Mer information

När A/B-tester körs online tilldelas varje användare/besökare slumpmässigt till en enskild variant. Därefter gör vi mätningar av de affärsmått som är av intresse (t.ex. konverteringar, order, intäkter osv.) för besökare i varje variant. Det statistiska testet vi använder testar sedan hypotesen att det genomsnittliga affärsvärdet (t.ex. konverteringsgrad, order per användare, intäkter per användare osv.) är lika för kontrollen och en given alternativ variant.

Även om själva affärsmätningen kan fördelas enligt viss godtycklig fördelning, bör fördelningen av medelvärdet för detta mätvärde (inom varje variant) konvergera till en normal fördelning via [kärnbegränsningsteorem](https://en.wikipedia.org/wiki/Central_limit_theorem). Observera att även om det inte finns någon garanti för hur snabbt denna provdistribution av medelvärdet kommer att konvergera till normal, är detta normalt med tanke på besökarnas omfattning vid onlinetestning.

Med hänsyn till detta medelvärde kan den teststatistik som ska användas visa att den följer en t-fördelning, eftersom den är förhållandet mellan ett normalt fördelat värde (skillnaden i företagsmetervärdet) och ett skalningsvillkor baserat på en uppskattning av data (standardfelet för skillnaden i medelvärde). **t-test** är sedan det lämpliga hypotestestet, eftersom testvärdet följer en t-fördelning.

### Varför andra tester inte används

Ett **z-test** är tekniskt olämpligt eftersom i det typiska A/B-testscenariot är nämnaren för testvärdet inte härledd från en känd varians, utan måste beräknas från data. För stora provstorlekar är z-testet och t-testet dock identiska.

**Kvadrerade tester** används inte eftersom de är lämpliga för att avgöra om det finns ett kvalitativt förhållande mellan två varianter (dvs. en nollhypotes om att det inte finns någon skillnad mellan varianter). T-test är lämpligare för scenariot _kvantitativt_ där mätvärden jämförs.

**Mann-Whitney U-testet** är ett icke-parametriskt test, vilket är lämpligt när provfördelningen av medelvärdet för affärsmätningen (för varje variant) normalt inte fördelas. Som tidigare nämnts gäller dock centralbegränsningsteorem vanligtvis, med tanke på den stora trafik som är involverad i onlinetestning, och t-testet kan därför tillämpas på ett säkert sätt.

Mer komplexa metoder som **ANOVA** (som genererar t-test till mer än två varianter) kan användas när ett test har fler än två upplevelser (&quot;A/Bn-tester&quot;). ANOVA besvarar emellertid frågan om&quot;alla varianter har samma medelvärde&quot;, medan vi i det typiska A/Bn-testet är mer intresserade av _vilken specifik variant_ som är bäst. I [!DNL Target] använder vi därför regelbundna t-tester där varje variant jämförs med en kontroll, med en Bonferroni-korrigering som tar hänsyn till flera jämförelser.