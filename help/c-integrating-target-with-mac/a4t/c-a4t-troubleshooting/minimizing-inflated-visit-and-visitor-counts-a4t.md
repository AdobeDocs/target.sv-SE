---
keywords: partiella data;partiella data;A4T;avvikelser;analys för mål;överblivna;virtuell rapportsvit;fantom;felsökning;icke-sammansatt;inflated;unspecified
description: Lär dig hur du minimerar effekterna av uppblåst besöks- och besökarantal när du använder Analytics for Target (A4t). Lär dig vad"partiella data" är och hur du kan minska den.
title: Hur minimerar jag antalet uppblåsta besök och besökare i A4T?
feature: Analyser för mål (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '1363'
ht-degree: 0%

---


# Minimera antalet uppblåsta besök och besökare i A4T{#minimizing-inflated-visit-and-visitor-counts-in-a-t}

Information som hjälper dig att minimera effekterna av inflaterade besök- och besökarantal när du använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T).

>[!IMPORTANT]
>Den 14 november 2016 ändrade Adobe Analytics hur vissa data bearbetas för kunder med Analytics-rapportering för Target (A4T). Dessa ändringar gör att Adobe Target data bättre överensstämmer med Adobe Analytics datamodell. De här ändringarna introducerades för alla kunder som använder A4T. Dessa ändringar åtgärdar specifikt ett problem där vissa kunder har upptäckt ett ökat antal besökare när Target-aktiviteter körs.
>
>Den här ändringen är inte retroaktiv. Om dina historiska rapporter visar inflaterade räkningar och du vill utesluta dem från dina rapporter, kan du skapa en virtuell rapportsvit, vilket förklaras nedan.
>
>Dessutom har flera JavaScript-bibliotek uppdaterats för att minimera antalet inflaterade fel. Adobe rekommenderar att du uppgraderar till följande biblioteksversioner (eller nyare):
>
>* Experience Cloud Visitor ID-tjänst: visitorAPI.js version 2.3.0 eller senare.
>* Adobe Analytics: appMeasurement.js version 2.1.
>* Adobe Target: at.js version 0.9.6 eller senare (utom version 1.1.0 om du använder omdirigeringserbjudanden med A4T).

>
>  
Biblioteket mbox.js stöder inte omdirigeringserbjudanden med A4T. Implementeringen måste använda at.js.

## Vad har ändrats? {#section_9CCF45F5D66D48EBA88F3A178B27D986}

När [!DNL Adobe Analytics] används för att mäta [!DNL Target]-aktiviteter (kallas A4T), samlar [!DNL Analytics] in extra data som inte är tillgängliga när det inte finns någon [!DNL Target]-aktivitet på sidan. Aktiviteten [!DNL Target] utlöser ett anrop längst upp på sidan, men [!DNL Analytics] utlöser vanligtvis sina datainsamlingsanrop längst ned på sidan. I implementeringen av A4T hittills inkluderar Adobe dessa ytterligare data när en [!DNL Target]-aktivitet var aktiv. Framöver inkluderar Adobe endast dessa ytterligare data när både [!DNL Target]- och [!DNL Analytics]-taggarna har utlösts.

## Varför gjorde Adobe den här ändringen? {#section_92380A4BD69E4B8886692DD27540C92A}

Adobe sätter sig vid datakvalitet och -kvalitet. När taggen [!DNL Target] utlöses, men inte taggen [!DNL Analytics], spelas &quot;partiella data&quot; in i Analytics (Analytics) (kallas ibland för &quot;osydda träffar&quot;). Dessa osydda träffar fångas inte av [!DNL Analytics] om det inte fanns någon [!DNL Target]-aktivitet. Även om denna del av data i [!DNL Analytics]-rapporter ger ytterligare information skapar den också inkonsekvens med historiska data från perioder när det inte fanns några [!DNL Target]-aktiviteter som kördes. Den här situationen kan orsaka problem för [!DNL Analytics]-användare som analyserar trender över tid. För att säkerställa datakonsekvens i [!DNL Analytics] utesluter Adobe alla partiella data.

## Vad bidrar till delar av data? {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Adobe har upptäckt en del kunder med hög andel partiella data i [!DNL Analytics]. Ett stort antal partiella data kan vara resultatet av felaktig implementering, men det finns också legitima orsaker.

De identifierade orsakerna till partiella data är bland annat följande:

* **Felanpassade rapportsvit-ID:n (implementering):** Rapportsviten som angavs under aktivitetsinställningarna matchar inte rapportsviten på sidan där testet levereras. Data kan inte förenas på [!DNL Analytics]-servrar, så det ser ut som partiella data.
* **Långsamma sidor:** [!DNL Target] anrop finns längst upp på sidan och  [!DNL Analytics] anrop sker vanligtvis längst ned på sidan. Om sidan läses in långsamt ökar det sannolikheten för att en besökare lämnar sidan efter att anropet [!DNL Target] utlösts, men före anropet [!DNL Analytics]. Långsamma sidor kan vara särskilt problematiska på mobilwebbplatser där anslutningarna ofta är långsammare.
* **Sidfel:** Om det finns JavaScript-fel eller andra scenarier där alla kontaktytor inte utlöses (Experience Cloud ID-tjänsten, Target och Analytics), partiella dataresultat.
* **Omdirigeringserbjudanden i  [!DNL Target] aktivitet:** För omdirigeringserbjudanden i aktiviteter som använder A4T måste implementeringen uppfylla vissa minimikrav. Dessutom finns det viktig information som du måste känna till. Mer information finns i [Omdirigeringserbjudanden - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58).
* **Gamla versioner av biblioteken:** Under det senaste året har Adobe förbättrat JavaScript-biblioteken (,  [!DNL appMeasurement.js]och  `at.js/mbox.js`  `visitorAPI.js`) för att säkerställa att data skickas så effektivt som möjligt. Mer information om implementeringskrav finns i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543).

## Vilka är de bästa sätten att minska partiella data? {#section_065C38501527451C8058278054A1818D}

Granska följande steg för att minska partiell datainsamling:

| Steg | Uppgift |
| --- | --- |
| ![Steg 1](assets/step1_icon.png) | Se till att rapportsviten som valts i [!DNL Target] är densamma som på de sidor där aktiviteten presenteras. |
| ![Steg 2](assets/step2_icon.png) | Kontrollera att biblioteken visitorAPI.js, appMeasurement.js, at.js / mbox.js finns i A4T-kompatibla versioner. Mer information om implementeringskrav finns i [Innan du implementerar](/help/c-integrating-target-with-mac/a4t/before-implement.md). |
| ![Steg 3](assets/step3_icon.png) | Kontrollera att SDID anges för alla [!DNL Target]- och [!DNL Analytics]-anrop som lämnar sidan och att de matchar.<br/>Använd en nätverksanalyserare eller ett felsökningsverktyg för att säkerställa att  `mboxMCSDID` parametern för  [!DNL Target] anrop matchar SDID-parametern i  [!DNL Analytics] anropet. |
| ![Steg 4](assets/step4_icon.png) | Bekräfta att implementeringsbiblioteken läses in i rätt ordning på dina webbplatser. Mer information finns i [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## Hur kan jag se hur mycket partiella data jag har? {#section_89B663E2824A4805AB934153508A0F4B}

Även om den här informationen inte är tillgänglig direkt i [!DNL Analytics] kan du kontakta Adobe kundtjänst för att hämta en rapport om partiella data. Denna rapport är avsedd att underlätta felsökningen.

## Hur kan jag se historiska trender utan partiella data? {#section_4C9DED560FAD4428B362DDA2064897C3}

Bearbetningsändringen påverkar endast data efter releasedatum (14 november 2016). Om du vill justera historisk statistik så att den matchar rekommenderar Adobe att du skapar ett segment där partiella data ska exkluderas.

Följande information om den här ändringen innehåller anvisningar om hur du definierar segmentet och använder det på en virtuell rapportserie så att det här segmentet alltid används på dina [!DNL Analytics]-vyer.

I de flesta fall sammanfogas en [!DNL Target]-träff med en [!DNL Analytics]-träff på varje webbsida. Den här sammanfogningen sker om det finns ett konsekvent SDID i både [!DNL Target]- och [!DNL Analytics]-anropet och ett [!DNL Experience Cloud ID] (MCID) i [!DNL Analytics]-anropet på samma sida. [!DNL Target] har oftast även MCID, men om anropet  [!DNL Target] sker innan besökar-ID:t returneras, sammanfogas träffen fortfarande på grund av SDID:t. Användaren måste också vara kvar på sidan tillräckligt länge för att utlösa ett [!DNL Analytics]-anrop efter att ett [!DNL Target]-anrop har utlösts. Det här scenariot är idealiskt.

**Deldataträffar:** Användare finns ibland inte kvar på en sida tillräckligt länge för att skicka ett  [!DNL Analytics] samtal, men  [!DNL Target] har ett korrekt MCID. Detta scenario resulterar i träffar med delar av data (träffar utan sidvy [!DNL Analytics]). Om de här användarna kommer tillbaka till webbplatsen och visar en sida som innehåller [!DNL Analytics]-kod räknas de som återkommande besökare. Träffarna hade gått förlorade om du bara hade [!DNL Analytics] kod på sidan. Vissa kunder vill inte ha data för de här träffarna eftersom de fyller upp vissa mätvärden (besök) och tömmer andra mätvärden (sidvisningar per besök, tid per besök och så vidare). Du kan även se besök utan sidvisningar. Det finns dock fortfarande giltiga skäl att behålla dessa data.

Om du vill minimera träffar med delar av data kan du få sidan att läsas in snabbare, uppdatera till de senaste versionerna av biblioteken eller skapa en [virtuell rapportsvit](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) som utesluter dessa träffar. Stegvisa instruktioner finns i [Skapa virtuella rapportsviter](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) i *handboken för analyskomponenter*.

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

**Överblivna träffar:** I färre situationer finns användarna inte kvar på sidan tillräckligt länge för ett Analytics-anrop och Target fick inget korrekt MCID. Det här är vad Adobe definierar som &quot;föräldralösa&quot; träffar. Dessa träffar representerar kunder som sällan återvänder och som får besökarna att öka antalet besökare på ett felaktigt sätt.

Om du vill minimera dessa &quot;överblivna&quot; träffar kan du skapa en [virtuell rapportsvit](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) som utesluter dessa träffar, vilket förklaras ovan.

## Vad innebär detta för min [!DNL Target]-rapportering? {#section_AAD354C722BE46D4875507F0FCBA5E36}

När den här ändringen har gjorts kan det hända att antalet nya besökare och besök i direkttest minskar eftersom [!DNL Adobe] inte bearbetar inkommande partiella data. Konverteringar och träffar i andra [!DNL Analytics]-mått ändras inte.
