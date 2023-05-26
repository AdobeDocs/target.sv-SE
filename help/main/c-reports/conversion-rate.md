---
keywords: Målinriktning
description: Se hur Adobe [!DNL Target] visar och beräknar konverteringsgraden, ökningen, förtroendet och konfidensintervallet för varje upplevelse.
title: Hur visar jag konverteringsgraden, avbrottsnivån och konfidensnivån?
feature: Reports
exl-id: b4cfe926-eb36-4ce1-b56c-7378150b0b09
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '2137'
ht-degree: 0%

---

# Konverteringsgrad

Konverteringsfrekvens, lyft, konfidensintervall och konfidensintervall rapporteras för varje upplevelse.

Följande bild visar diagramrubriken för en exempelaktivitet med [!UICONTROL Conversion Rate], [!UICONTROL Lift]och [!UICONTROL Confidence] rubriker markerade.

![bild med konverteringsgrad](assets/conversion-rate.jpg)

>[!NOTE]
>
>I alla data ignoreras dubblettorder om en `orderID` har skickats. Revideringsrapporten innehåller en lista över ignorerade dubblettorder.

## Konverteringsgrad {#section_07A36846C4E84D0881906809B9CE5A74}

Visar mediankonverteringsfrekvens, konfidensintervall och antal konverteringar.

Titta till exempel i följande rapportkolumn för konverteringsgrad:

![bild med konverteringsgrad-detalj](assets/conversion-rate-detail.jpg)

Den första raden är kontrollupplevelsen. Den visar en konverteringsgrad på 15 %, med tre konverteringar. Den andra raden, Experience B, visar en konverteringsgrad på 15 %, med ett konfidensintervall på plus eller minus 15,65 % och tre konverteringar.

>[!NOTE]
>
>För närvarande beräknas konfidensintervallet bara för binära värden.

## Lyft {#section_0F409572C720433D9378092ABC999982}

Jämför konverteringsgraden för varje upplevelse med kontrollupplevelsen.

Lyft = (Experience CR - Control CR) / Ctrl CR

Om kontrollen är 0, finns ingen procentuell lyft.


## Butiksdata {#section_30A674731BA6440E9BB93C421BE990EE}

AOV-, RPV- och Sales-data visas för varje upplevelse om du har infogat en platsorder (`orderConfirmPage`) och markerat den som konverteringsruta.

## Konfidensnivå och konfidensintervall {#concept_0D0002A1EBDF420E9C50E2A46F36629B}

För varje upplevelse visas konfidensintervallet och konfidensintervallet.

Du kan utföra offlineberäkningar för Analytics för Target (A4T), men det kräver ett steg med dataexport i [!DNL Analytics]. Mer information finns i&quot;Utföra offlineberäkningar för analys av mål (A4T)&quot; nedan.

### Förtroende {#section_26FE5E44BDD5478792A65FCFD83DCCDC}

Förtroendet hos en upplevelse eller ett erbjudande som visas är en sannolikhet (uttryckt i procent) att få ett resultat som är mindre extrem än det som faktiskt observeras, om nollhypotesen är sann (i praktiken om det inte finns någon skillnad i konverteringsgraden mellan upplevelsen eller erbjudandet och kontrollupplevelsen/erbjudandet). När det gäller p-värden är den här tillförlitligheten 1 - p-värde. Enklare uttryckt innebär ett högre förtroende att data inte är förenliga med antagandet att kontrollerbjudandet och upplevelsen utan kontroll har samma konverteringsgrad.

Konfidensen avrundar till upp till 100,00 % när förtroendet är större än eller lika med 99,995 %.

![conf_report-bild](assets/conf_report.png)  ![conf_report_detail, bild](assets/conf_report_detail.png)

Innan du fattar några affärsbeslut ska du försöka vänta tills exempelstorleken är tillräckligt stor och att de fyra konfidensintervallen för en eller flera upplevelser är konsekventa hela tiden för att säkerställa att resultaten är stabila.


### Konfidensintervall {#section_F582738DFE1648C78B93D81EBC6CACF7}

>[!NOTE]
>
>För närvarande beräknas konfidensintervallet bara för binära värden.

The *konfidensintervall* är en serie uppskattningar inom vilka det verkliga värdet för mätvärdet kan hittas på en given konfidensnivå. Target har alltid 95% konfidensintervall. Konfidensintervallet visas som ett ljusgrått +/- procentvärde i kolumnen Konverteringsfrekvens. I exemplet nedan är konfidensintervallet för Experience B plus eller minus 15,65 %.

![konvertering_rate, bild](assets/conversion_rate.png)

**Exempel:** En upplevelse observerade RPV är $10 och dess 95% **konfidensintervall** är 5 till 15 dollar. Okänd för oss är dess verkliga RPV 12 dollar. Om vi sedan kör testet flera gånger kommer 95 % av tiden som vi beräknar att innehålla _true_ RPV på $12.

**Vad påverkar konfidensintervallet?** Formeln följer statistiska standardmetoder för beräkning av konfidensintervall.

* **Samplingsstorlek:** I takt med att exemplet växer krymper eller förminskas intervallet. Detta är att föredra eftersom det innebär att dina rapporter närmar sig det verkliga värdet av framgångsmåttet.
* **Standardavvikelse mindre:** Mer likartade resultat, som liknande AOV:er eller liknande nummer eller besökare som konverterar varje dag, minskar standardavvikelsen.

## Konfidenskalering och hur den utförs offline {#section_86F7C231943043A5B8B6BFE67B706E3B}

The [hämtad CSV-rapport](/help/main/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) innehåller endast rådata och omfattar inte beräknade värden, t.ex. intäkter per besökare, lyft eller förtroende som används för A/B-tester.

Om du vill beräkna de beräknade måtten hämtar du målets [Slutför konfidensberäkning](/help/main/assets/complete_confidence_calculator.xlsx) Excel-fil för att ange aktivitetens värde eller granska [Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

>[!NOTE]
>
>Den här räknaren används för målbaserad rapportering och inte för A4T-rapportering.

## Utföra offlineberäkningar för analys för Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Du kan utföra offlineberäkningar för A4T, men det kräver ett steg med dataexport i [!DNL Analytics].

För A4T använder vi en [Welch&#39;s t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} för kontinuerliga variabler (i stället för binära värden). I Analytics spåras alltid en besökare, och alla åtgärder som vidtas räknas. Om besökaren köper flera gånger eller besöker ett framgångsmått flera gånger räknas de ytterligare träffarna. Detta gör mätvärdet till en kontinuerlig variabel. För att utföra Welchs t-test-beräkning krävs ’summan av kvadrater’ för att beräkna variansen, som används i t-statistikens nämnare. [Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md) I förklaras detaljerna för de matematiska formler som används. Summan av fyrkanter kan hämtas från [!DNL Analytics]. Om du vill få summan av kvadratdata måste du utföra en export på besökarnivå för det mätresultat som du optimerar för, under en provtidsperiod.

Om du till exempel optimerar till sidvisningar per besökare, kan du exportera ett exempel på det totala antalet sidvisningar per besökare för en viss tidsperiod, kanske några dagar (ett par tusen datapunkter är allt du behöver). Därefter fyrkantiga varje värde och summerar summan (operationsordningen är viktig här). Värdet&quot;summan av kvadrater&quot; används sedan i Complete Confidence Calculator. Använd avsnittet &quot;intäkt&quot; i kalkylbladet för dessa värden.

**Så här använder du [!DNL Analytics] dataexportfunktion för att göra detta:**

1. Logga in på [!DNL Adobe Analytics].
1. Klicka på **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]**.
1. På **[!UICONTROL Data Warehouse Request]** fyller du i fälten.

   Mer information om de olika fälten finns i Data warehouse beskrivningar i [data warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html).

   | Fält | Instruktioner |
   |--- |--- |
   | Namn på begäran | Ange ett namn för din begäran. |
   | Rapportdatum | Ange en tidsperiod och granularitet.<br>Som bästa praxis bör du inte välja mer än en timme eller dag med data för din första förfrågan.  data warehouse-filer tar längre tid att bearbeta längre tid än vad som begärts, så det är alltid en god vana att begära data för en liten tidsperiod först för att vara säker på att filen returnerar det förväntade resultatet. Gå sedan till Request Manager, duplicera din begäran och be om fler data vid andra gången. Om du växlar granularitet till något annat än &quot;Inget&quot; ökar filstorleken drastiskt.<br>![data warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | Tillgängliga segment | Använd ett segment efter behov. |
   | Uppdelningar | Välj önskade mått: Standard är körklar (OTB), medan Custom innehåller eVars &amp; Props. Vi rekommenderar att du använder&quot;besökar-ID&quot; om information på besökar-ID-nivå behövs, i stället för&quot;Experience Cloud Visitor-ID&quot;.<ul><li>Besökar-ID är det sista ID som används av Analytics. Det blir antingen ett ID (om kunden är äldre) eller ett MID (om kunden är ny eller rensad på cookies sedan besökar-ID-tjänsten för MC startades).</li><li>Experience Cloud Visitor-ID kommer endast att anges för kunder som är nya eller rensade cookies sedan besöks-ID-tjänsten startades.</li></ul> |
   | Mått | Välj önskade mätvärden. Standard är OTB, medan Anpassad innehåller anpassade händelser. |
   | Förhandsgranska rapport | Granska inställningarna innan du schemalägger rapporten.<br>![data warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | Schemalägg leverans | Ange en e-postadress som filen ska skickas till, ge filen ett namn och välj sedan [!UICONTROL Send Immediately].<br>Obs! Filen kan levereras via FTP under [!UICONTROL Advanced Delivery Options]<br>![Schemalägg leverans](/help/main/c-reports/assets/datawarehouse3.png). |

1. Klicka på **[!UICONTROL Request this Report]**.

   Filhanteringen kan ta upp till 72 timmar, beroende på mängden data som begärs. Du kan när som helst kontrollera förloppet för din förfrågan genom att klicka på [!UICONTROL Tools] > [!UICONTROL Data Warehouse] > [!UICONTROL Request Manager].

   Om du vill begära om data som du har begärt tidigare kan du duplicera en gammal begäran från [!UICONTROL Request Manager] efter behov.

Mer information om [!DNL Data Warehouse], se följande länkar i [!DNL Analytics] Hjälpdokumentation:

* [Skapa en begäran från Data warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [data warehouse bästa praxis](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)

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

* **Besökare:** En unik deltagare i aktiviteten, under aktivitetens livstid.

   En person räknas som ny deltagare om han eller hon besöker platsen från en ny dator eller en ny webbläsare. tar bort cookien, eller konverterar och återgår till aktiviteten med samma cookie. En deltagare identifieras av PCID i besökarens mbox-cookie. Om PCID ändras betraktas personen som en ny besökare.

* **Besök:** En unik deltagare i en upplevelse under en enstaka 30-minuters webbläsarsession.

   Om en besökare konverteras eller återkommer till webbplatsen efter att ha varit borta i minst 30 minuter räknas en återkommande besökare som ett nytt besök. Ett besök identifieras av `sessionID` i besökarens mbox cookie. När `sessionID` Besöken anses vara ny.

* **Impression/sidvy:** Räknas varje gång en besökare läser in någon sida i aktiviteten.

   Ett enda besök kan innehålla flera visningar av till exempel din hemsida.

>[!NOTE]
>
>Antalet bestäms vanligtvis av cookies och sessionsaktivitet. Om du når den sista konverteringspunkten för en aktivitet och sedan anger aktiviteten igen, betraktas du som en ny deltagare och ett nytt besök i aktiviteten. Detta gäller även om ditt PCID och `sessionID` värdena inte ändras.

## Varför gör det [!DNL Target] rekommenderar du att använda Welchs t-test? {#t-test}

A/B-tester är experiment för att jämföra medelvärdet av vissa företagsvärden i en kontrollvariant (kallas även upplevelse) med medelvärdet av samma mätvärden i en eller flera alternativa upplevelser.

[!DNL Target] rekommenderar [Welch&#39;s t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test), eftersom dessa kräver färre antaganden än alternativ som z-tester, och är det lämpliga statistiska testet för att göra parvisa jämförelser av (kvantitativa) affärsvärden mellan kontrollupplevelser och alternativa upplevelser.

### Mer information

När A/B-tester körs online tilldelas varje användare/besökare slumpmässigt till en enskild variant. Därefter gör vi mätningar av de affärsmått som är av intresse (t.ex. konverteringar, order, intäkter osv.) för besökare i varje variant. Det statistiska testet vi använder testar sedan hypotesen att det genomsnittliga affärsvärdet (t.ex. konverteringsgrad, order per användare, intäkt per användare osv.) är lika för kontrollen och en given alternativ variant.

Även om själva affärsmåttet kan fördelas enligt viss godtycklig fördelning, bör fördelningen av medelvärdet av detta mätvärde (inom varje variant) sammanfalla med en normal fördelning via [Central Limit Theorem](https://en.wikipedia.org/wiki/Central_limit_theorem). Observera att även om det inte finns någon garanti för hur snabbt denna provdistribution av medelvärdet kommer att konvergera till normal, är detta normalt med tanke på besökarnas omfattning vid onlinetestning.

Med hänsyn till detta medelvärde kan den teststatistik som ska användas visa att den följer en t-fördelning, eftersom den är förhållandet mellan ett normalt fördelat värde (skillnaden i företagsmetervärdet) och ett skalningsvillkor baserat på en uppskattning av data (standardfelet för skillnaden i medelvärde). The **t-test** är sedan det lämpliga hypotestestet, eftersom provningsvärdet följer en t-fördelning.

### Varför andra tester inte används

A **z-test** är tekniskt olämpligt eftersom nämnaren för provningsvärdet i det typiska A/B-testscenariot inte härleds från en känd varians, utan i stället måste beräknas från data. För stora provstorlekar är z-testet och t-testet dock identiska.

**Chi-quared-tester** används inte eftersom dessa är lämpliga för att avgöra om det finns ett kvalitativt samband mellan två varianter (dvs. en nollhypotes om att det inte finns någon skillnad mellan varianter). T-tester är lämpligare för scenariot _kvantitativt_ jämföra mätvärden.

The **Mann-Whitney U test** är ett icke-parametriskt test, vilket är lämpligt när provfördelningen av det genomsnittliga affärsmåttet (för varje variant) normalt inte fördelas. Som tidigare nämnts gäller dock centralbegränsningsteorem vanligtvis, med tanke på den stora trafik som är involverad i onlinetestning, och t-testet kan därför tillämpas på ett säkert sätt.

Mer komplexa metoder som **ANOVA** (som generaliserar t-tester till mer än två varianter) kan användas när ett test har mer än två upplevelser (&quot;A/Bn-tester&quot;). ANOVA besvarar dock frågan om&quot;alla varianter har samma medelvärde&quot;, medan vi i det typiska A/Bn-testet är mer intresserade av&quot;om alla varianter har samma medelvärde&quot; _vilken specifik variant_ är bäst. I [!DNL Target]använder vi därför regelbundna t-tester där varje variant jämförs med en kontroll, med en Bonferroni-korrigering som tar hänsyn till flera jämförelser.