---
keywords: partiella data;partiella data;A4T;avvikelser;analys för mål;överblivna;virtuell rapportsvit;fantom;felsökning;icke-sammansatt;inflated;unspecified
description: Lär dig hur du minimerar effekterna av uppblåst besöks- och besökarantal när du använder Analytics för [!DNL Target] (A4t). Lär dig vad"partiella data" är och hur du kan minska den.
title: Hur minimerar jag antalet uppblåsta besök och besökare i A4T?
feature: Analytics for Target (A4T)
exl-id: 308711f7-e630-4f6b-8a6d-a1f36ed7902d
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 0%

---

# Minimera antalet uppblåsta besök och besökare i A4T

Information som hjälper dig att minimera effekterna av uppblåst besök och besökarantal när du använder [!DNL Adobe Analytics] som rapportkälla för [!DNL Adobe Target] (A4T).

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


## Vad har ändrats? {#section_9CCF45F5D66D48EBA88F3A178B27D986}

När [!DNL Adobe Analytics] används för att mäta [!DNL Target] aktiviteter (kallas A4T), [!DNL Analytics] samlar in extra data som inte är tillgängliga när det inte finns någon [!DNL Target] på sidan. The [!DNL Target] aktiviteten utlöser ett samtal högst upp på sidan, men [!DNL Analytics] oftast anropas för datainsamling längst ned på sidan. I implementeringen av A4T hittills inkluderar Adobe dessa ytterligare data när [!DNL Target] aktiviteten var aktiv. Framåt inkluderar Adobe endast dessa ytterligare data när båda [!DNL Target] och [!DNL Analytics] -taggar har utlösts.

## Varför gjorde Adobe den här ändringen? {#section_92380A4BD69E4B8886692DD27540C92A}

Adobe sätter sig vid datakvalitet och -kvalitet. När [!DNL Target] -taggen utlöses, men [!DNL Analytics] -taggen gör inte det, analytikerna spelar in&quot;partiella data&quot; (kallas ibland för&quot;osökta träffar&quot;). De här osökta träffarna fångas inte av [!DNL Analytics] om det inte fanns [!DNL Target] aktivitet. Även om deldata inkluderas i [!DNL Analytics] rapportering ger ytterligare information, skapar också inkonsekvens med historiska data från perioder där det inte fanns några [!DNL Target] aktiviteter som körs. Denna situation kan orsaka problem för [!DNL Analytics] användare som analyserar trender över tid. För att säkerställa att data är konsekventa [!DNL Analytics], Adobe exkluderar alla partiella data.

## Vad bidrar till delar av data? {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Adobe har upptäckt en del kunder med hög andel partiella data på [!DNL Analytics]. Ett stort antal partiella data kan vara resultatet av felaktig implementering, men det finns också legitima orsaker.

De identifierade orsakerna till partiella data är bland annat följande:

* **Feljusterade ID:n för rapportsviten (implementering):** Rapportsviten som angavs under aktivitetsinställningarna matchar inte rapportsviten på sidan där testet levereras. Data kan inte förenas på [!DNL Analytics] servrar, så det ser ut som partiella data.
* **Långsamma sidor:** [!DNL Target] samtalen är högst upp på sidan och [!DNL Analytics] oftast längst ned på sidan. Om sidan läses in långsamt ökar sannolikheten för att en besökare lämnar sidan efter [!DNL Target] anropa eld, men före [!DNL Analytics] ring. Långsamma sidor kan vara särskilt problematiska på mobilwebbplatser där anslutningarna ofta är långsammare.
* **Sidfel:** Om det finns JavaScript-fel eller andra scenarier där var och en av kontaktytorna inte utlöses (Experience Cloud ID-tjänsten, Target och Analytics), ger det partiella dataresultatet.
* **Omdirigera erbjudanden i [!DNL Target] aktivitet:** För omdirigeringserbjudanden i aktiviteter som använder A4T måste implementeringen uppfylla vissa minimikrav. Dessutom finns det viktig information som du måste känna till. Mer information finns i [Omdirigeringserbjudanden - Vanliga frågor om A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58).
* **Gamla versioner av biblioteken:** Under det senaste året har Adobe förbättrat JavaScript-biblioteken ( [!DNL appMeasurement.js], `at.js`och `visitorAPI.js`) för att säkerställa att data skickas så effektivt som möjligt. Mer information om implementeringskrav finns i [Innan du implementerar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543).

## Vilka är de bästa sätten att minska partiella data? {#section_065C38501527451C8058278054A1818D}

Granska följande steg för att minska partiell datainsamling:

| Steg | Uppgift |
| --- | --- |
| ![Steg 1](assets/step1_icon.png) | Se till att rapportsviten är vald i [!DNL Target] är densamma som på de sidor där aktiviteten presenteras. |
| ![Steg 2](assets/step2_icon.png) | Kontrollera att biblioteken visitorAPI.js, appMeasurement.js och at.js finns i A4T-kompatibla versioner. Mer information om implementeringskrav finns i [Innan du implementerar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md). |
| ![Steg 3](assets/step3_icon.png) | Se till att SDID anges för alla [!DNL Target] och [!DNL Analytics] samtal lämnar sidan och att de matchar.<br/>Använd en nätverksanalyserare eller ett felsökningsverktyg för att säkerställa att `mboxMCSDID` parameter på [!DNL Target] anrop matchar SDID-parametern i [!DNL Analytics] ring. |
| ![Steg 4](assets/step4_icon.png) | Bekräfta att implementeringsbiblioteken läses in i rätt ordning på dina webbplatser. Mer information finns i [Analyser för målinriktad implementering](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## Hur kan jag se hur mycket partiella data jag har? {#section_89B663E2824A4805AB934153508A0F4B}

Även om denna information inte är tillgänglig direkt i [!DNL Analytics]kan du kontakta Adobe kundtjänst för att få fram en rapport över delar av data. Denna rapport är avsedd att underlätta felsökningen.

## Hur kan jag se historiska trender utan partiella data? {#section_4C9DED560FAD4428B362DDA2064897C3}

Bearbetningsändringen påverkar endast data efter releasedatum (14 november 2016). Om du vill justera historisk statistik så att den matchar rekommenderar Adobe att du skapar ett segment där partiella data ska exkluderas.

Följande information om den här ändringen innehåller instruktioner som hjälper dig att definiera segmentet och använda det på en virtuell rapportsvit så att det här segmentet alltid tillämpas på din [!DNL Analytics] vyer.

I de flesta fall kan en [!DNL Target] träffen sys ihop med en  [!DNL Analytics] tryck på varje webbsida. Den här sammanfogningen sker om det finns ett konsekvent SDID i båda  [!DNL Target] och [!DNL Analytics] ring och [!DNL Experience Cloud ID] (MCID) i  [!DNL Analytics] på samma sida. [!DNL Target] har oftast också MCID, men om [!DNL Target] inträffar innan besökar-ID:t returneras, kommer träffen fortfarande att sammanfogas på grund av SDID:t. Användaren måste också vara kvar på sidan tillräckligt länge för att kunna avskeda en  [!DNL Analytics] ring efter  [!DNL Target] samtalet avlossades. Det här scenariot är idealiskt.

**Deldataträffar:** Ibland finns användarna inte kvar på en sida tillräckligt länge för att skicka en [!DNL Analytics] ring, men [!DNL Target] har ett korrekt MCID. Det här scenariot resulterar i partiella dataträffar (träffar utan [!DNL Analytics] sidvy). Om de här användarna kommer tillbaka till webbplatsen och visar en sida som innehåller [!DNL Analytics] kod räknas de som återkommande besökare. De här träffarna hade gått förlorade om du bara hade [!DNL Analytics] på sidan. Vissa kunder vill inte ha data för de här träffarna eftersom de fyller upp vissa mätvärden (besök) och tömmer andra mätvärden (sidvisningar per besök, tid per besök och så vidare). Du kan även se besök utan sidvisningar. Det finns dock fortfarande giltiga skäl att behålla dessa data.

Om du vill minimera träffar med delar av data kan du få sidan att läsas in snabbare, uppdatera till de senaste versionerna av biblioteken eller skapa en [virtuell rapportsvit](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) som utesluter de där träffarna. Stegvisa instruktioner finns i [Skapa virtuella rapportsviter](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) i *Handbok för analyskomponenter*.

Följande bild visar segmentdefinitionen för den virtuella rapportsviten:

![ts_a4t-bild](assets/ts_a4t.png)

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

**Överblivna träffar: ** I färre situationer finns användarna inte kvar på sidan tillräckligt länge för ett Analytics-anrop och Target fick inte rätt MCID. Det här är vad Adobe definierar som &quot;föräldralösa&quot; träffar. Dessa träffar representerar kunder som sällan återvänder och som får besökarna att öka antalet besökare på ett felaktigt sätt.

Om du vill minimera dessa &quot;överblivna&quot; träffar kan du skapa en [virtuell rapportsvit](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) som utesluter dessa träffar, vilket förklaras ovan.

## Vad betyder det här för [!DNL Target] rapportera? {#section_AAD354C722BE46D4875507F0FCBA5E36}

När den här förändringen inträffar kan det hända att antalet nya besökare och besök på direktsända tester minskar eftersom [!DNL Adobe] bearbetar inte inkommande partiella data. Konverteringar och träffar till andra [!DNL Analytics] mätvärdena ändras inte.
