---
keywords: partial data;partial-data;A4T;discrepancies;analytics for target;orphaned;virtual report suite;phantom;troubleshooting;unstitched;inflated;unspecified
description: Information som hjälper er att minimera effekterna av inflaterade besök- och besökarantal när ni använder Analytics som rapportkälla.
title: Minimera antalet uppblåsta besök och besökare i A4T
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 1%

---


# Minimera antalet uppblåsta besök och besökare i A4T{#minimizing-inflated-visit-and-visitor-counts-in-a-t}

Information som hjälper er att minimera effekterna av inflaterade besök- och besökarantal när ni använder Analytics som rapportkälla.

>[!IMPORTANT]
>Den 14 november 2016 ändrade Adobe Analytics hur vissa data bearbetas för kunder med Analytics-rapportering för Target (A4T). Dessa ändringar gör att Adobe Target data bättre överensstämmer med Adobe Analytics datamodell. De här ändringarna introducerades för alla kunder som använder A4T. Dessa ändringar åtgärdar specifikt ett problem där vissa kunder har upptäckt ett ökat antal besökare när Target-aktiviteter körs.
>
>Observera att den här ändringen inte är retroaktiv. Om dina historiska rapporter visar inflaterade räkningar och du vill utesluta dem från dina rapporter, kan du skapa en virtuell rapportsvit, vilket förklaras nedan.
>
>Dessutom har flera JavaScript-bibliotek uppdaterats för att minimera antalet inflaterade fel. Vi rekommenderar att du uppgraderar till följande biblioteksversioner (eller nyare):
>
>* Experience Cloud Visitor ID-tjänst: visitorAPI.js version 2.3.0 eller senare.
>* Adobe Analytics: appMeasurement.js version 2.1.
>* Adobe Target: at.js version 0.9.6 eller senare (utom version 1.1.0 om du använder omdirigeringserbjudanden med A4T).

>
>  
Biblioteket mbox.js stöder inte omdirigeringserbjudanden med A4T. Implementeringen måste använda at.js.

## Vad har ändrats? {#section_9CCF45F5D66D48EBA88F3A178B27D986}

När [!DNL Adobe Analytics] används för att mäta [!DNL Target] aktiviteter (kallas A4T), [!DNL Analytics] samlar in ytterligare data som inte är tillgängliga när det inte finns någon [!DNL Target] aktivitet på sidan. Detta beror på att [!DNL Target] aktiviteten utlöser ett anrop längst upp på sidan, men [!DNL Analytics] oftast utlöses anrop till datainsamlingen längst ned på sidan. I implementeringen av A4T hittills har vi tagit med dessa ytterligare data när en [!DNL Target] aktivitet var aktiv. Framöver kommer vi endast att inkludera dessa ytterligare data när både [!DNL Target] - och [!DNL Analytics] -taggarna har utlösts.

## Varför gjorde Adobe den här ändringen? {#section_92380A4BD69E4B8886692DD27540C92A}

Adobe sätter sig vid datakvalitet och -kvalitet. När [!DNL Target] taggen utlöses, men inte taggen [!DNL Analytics] , spelar vi in&quot;partiella data&quot; (kallas ibland för &quot;osökta träffar&quot;) som inte skulle fångas av [!DNL Analytics] om det inte fanns någon [!DNL Target] aktivitet. Även om denna del av uppgifterna i [!DNL Analytics] rapporteringen ger ytterligare information skapar den också inkonsekvens med historiska data från perioder då det inte fanns några [!DNL Target] aktiviteter som kördes. Detta kan orsaka problem för [!DNL Analytics] användare som analyserar trender över tid. För att säkerställa att data är konsekventa i [!DNL Analytics]kommer vi att utesluta alla delar av data.

## Vad bidrar till delar av data? {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Vi har sett en del kunder med mycket hög andel partiella data i [!DNL Analytics]. Detta kan bero på felaktigt genomförande, men det finns också legitima orsaker.

De identifierade orsakerna till partiella data är bland annat följande:

* **Feljusterade ID:n för rapportsviten (implementering):** Rapportsviten som angavs under aktivitetsinställningarna matchar inte rapportsviten på sidan där testet levereras. Detta ser ut som partiella data eftersom data inte kan förenas på [!DNL Analytics] servrar.
* **Långsamma sidor:** Eftersom [!DNL Target] anrop är längst upp på sidan och [!DNL Analytics] anrop vanligtvis är längst ned på sidan ökar sannolikheten för att en besökare lämnar sidan efter att [!DNL Target] anropet utlösts, men före [!DNL Analytics] anropet, om sidan läses in långsamt. Detta kan vara särskilt problematiskt på mobilwebbplatser där anslutningarna ofta är långsammare.
* **Sidfel:** Om det finns JavaScript-fel eller andra scenarier där var och en av kontaktytorna inte utlöses (Experience Cloud ID-tjänsten, Target och Analytics), resulterar partiella data.
* **Omdirigeringserbjudande i [!DNL Target] aktivitet:** För omdirigeringserbjudanden i aktiviteter som använder A4T måste implementeringen uppfylla vissa minimikrav. Dessutom finns det viktig information som du behöver känna till. Mer information finns i [Omdirigeringserbjudanden - A4T Frågor och svar](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58).
* **Gamla versioner av biblioteken:** Under det senaste året har Adobe gjort flera förbättringar av våra JavaScript-bibliotek ( [!DNL appMeasurement.js], `at.js/mbox.js`och `visitorAPI.js`) för att säkerställa att data skickas så effektivt som möjligt. Mer information om implementeringskrav finns i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543).

## Vilka är de bästa sätten att minska partiella data? {#section_065C38501527451C8058278054A1818D}

Granska följande steg för att minska partiell datainsamling:

| Steg | Uppgift |
| --- | --- |
| ![Steg 1](assets/step1_icon.png) | Se till att rapportsviten som är vald i [!DNL Target] är densamma som den på sidan/sidorna där aktiviteten presenteras. |
| ![Steg 2](assets/step2_icon.png) | Kontrollera att biblioteken visitorAPI.js, appMeasurement.js, at.js / mbox.js finns i A4T-kompatibla versioner. Mer information om implementeringskrav finns i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md). |
| ![Steg 3](assets/step3_icon.png) | Kontrollera att SDID anges för alla [!DNL Target] och [!DNL Analytics] anrop som lämnar sidan och att de matchar.<br/>Det gör du genom att använda en nätverksanalyserare eller ett felsökningsverktyg för att säkerställa att `mboxMCSDID` parametern för [!DNL Target] anrop matchar SDID-parametern i [!DNL Analytics] anropet. |
| ![Steg 4](assets/step4_icon.png) | Bekräfta att implementeringsbiblioteken läses in i rätt ordning på dina webbplatser. Mer information finns i [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## Hur kan jag se hur mycket partiella data jag har? {#section_89B663E2824A4805AB934153508A0F4B}

Även om den här informationen inte är tillgänglig direkt i [!DNL Analytics]kan du kontakta Adobe kundtjänst för att få en rapport över delar av data. Denna rapport är avsedd att underlätta felsökningen.

## Hur kan jag se historiska trender utan partiella data? {#section_4C9DED560FAD4428B362DDA2064897C3}

Eftersom den här bearbetningen endast påverkar data efter releasedatum (14 november 2016) rekommenderar vi att du skapar ett segment som inte innehåller vissa data om du vill justera dina historiska värden så att de matchar varandra.

Följande information om den här ändringen innehåller instruktioner som hjälper dig att definiera segmentet och använda det på en virtuell rapportserie så att det här segmentet alltid tillämpas på dina [!DNL Analytics] vyer.

I de flesta fall sammanfogas en [!DNL Target] träff med en [!DNL Analytics] träff på varje webbsida. Den här sammanfogningen sker om det finns ett konsekvent SDID i både [!DNL Target] - och [!DNL Analytics] -anropet och ett [!DNL Experience Cloud ID] (MCID) i [!DNL Analytics] anropet på samma sida. [!DNL Target] har vanligtvis även MCID, men om anropet till [!DNL Target] inträffar innan besökar-ID:t returneras kommer träffen fortfarande att sammanfogas på grund av SDID:t. Användaren måste också vara kvar på sidan tillräckligt länge för att ringa ett [!DNL Analytics] samtal efter att ett [!DNL Target]samtal har utlösts. Detta är det idealiska scenariot.

**Deldataträffar:** Ibland finns användarna inte kvar på en sida tillräckligt länge för att skicka ett [!DNL Analytics] samtal, men [!DNL Target] har ett korrekt MCID. Detta resulterar i träffar med delar av data (träffar utan [!DNL Analytics] sidvy). Om de här användarna kommer tillbaka till webbplatsen och visar en sida med [!DNL Analytics] kod räknas de som återkommande besökare. Det här är träffar som skulle ha gått förlorade om du bara hade [!DNL Analytics] kod på sidan. Vissa kunder vill inte ha data för de här träffarna eftersom de fyller upp vissa mätvärden (besök) och tömmer andra mätvärden (sidvisningar per besök, tid per besök och så vidare). Du kan även se besök utan sidvisningar. Det finns dock fortfarande giltiga skäl att behålla dessa data.

Om du vill minimera träffar med delar av data kan du få sidan att läsas in snabbare, uppdatera till de senaste versionerna av biblioteken eller skapa en [virtuell rapportserie](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) som utesluter sådana träffar. Stegvisa instruktioner finns i [Skapa virtuella rapportsviter](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) i *Analytics Components Guide*.

Följande bild visar segmentdefinitionen för den virtuella rapportsviten:

![](assets/ts_a4t.png)

När du skapar den virtuella rapportsviten anger du följande konfiguration för segmentdefinitionen (som på bilden ovan):

* **Visa träff:**
* Analyser för Target: Finns
* Och
* Sidvyer: Finns inte
* Och
* Anpassade länkinstanser: Finns inte
* Och
* Hämta länkinstanser: Finns inte
* Och
* Avsluta länkinstanser: Finns inte

**Överblivna träffar:** I färre situationer finns användarna inte kvar på sidan tillräckligt länge för ett Analytics-anrop och Target fick inget korrekt MCID. Det här är vad vi definierar som &quot;föräldralösa&quot; träffar. Dessa träffar representerar kunder som sällan återvänder och som får besökarna att öka antalet besökare på ett felaktigt sätt.

Om du vill minimera dessa &quot;överblivna&quot; träffar kan du skapa en [virtuell rapportsvit](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) som utesluter dessa träffar, vilket förklaras ovan.

## Vad betyder det för min [!DNL Target] rapportering? {#section_AAD354C722BE46D4875507F0FCBA5E36}

När den här förändringen inträffar kan det hända att antalet nya besökare och besök på direktsända tester minskar, eftersom [!DNL Adobe] inkommande partiella data inte bearbetas. Konvertering och träffar till andra [!DNL Analytics] mätvärden ändras inte.
