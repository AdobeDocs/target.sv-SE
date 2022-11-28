---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5566393192b131b837fece1bb2a6781e2f953190
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## Models API-version (23 november 2022)

Den nya [!DNL Adobe Target] Med API:t för modeller, som även kallas API för Blockeringslista, kan användare visa och hantera listan med funktioner som används i maskininlärningsmodeller för [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Auto-Target] (AT) verksamhet.

Mer information finns i [API-översikt för modeller](https://developer.adobe.com/target/before-administer/models-api/){target=_blank} i *Adobe Target Developer Guide*.

## [!DNL Target] Standard/Premium 22.10.3 (version 25-27 oktober 2022)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **25 oktober**: Europa, Mellanöstern och Afrika (EMEA)
* **26 oktober**: Asien-Stillahavsområdet (APAC)
* **27 oktober**: Amerika

Den här versionen innehåller följande nya funktioner, förbättringar och korrigeringar:

| Funktion | Detaljer |
| --- | --- |
| Optimerade A4T-värden för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]<br>(Tillgängligt för utvalda kunder för testning. Kommer att vara tillgänglig för alla kunder i en framtida version.) | Tänk på följande ändringar:<ul><li>Stöd för icke-binära och maximeringsvärden har lagts till i [!UICONTROL Analytics for Target] A4T-rapportering för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet</li><li>Bevarat beteende för befintliga aktiviteter fram till februari 2023. Efter detta datum kommer aktiviteterna att avbrytas för att tvinga befintlig aktivitetsmigrering till nytt beteende</li><li>Från 20 februari 2023, stöd för `averagetimespentonsite`, `bouncerate`och `entries` mätvärden i [!DNL Target] aktiviteter kommer att bli inaktuella.</li></ul> |

* Fler verktygstips i [!DNL Target] Användargränssnitt som hjälper kunderna att navigera effektivare i målgruppsbyggaren och för att lära sig hur de använder funktioner som kanske inte är kända. (TGT-44139)
* Funktioner som förhindrar kunderna från att redigera en aktivitet som inaktiverats av [!DNL Target] eftersom det använder mätvärden som inte stöds. Ett meddelande i användargränssnittet uppmanar kunderna att duplicera aktiviteten och sedan uppdatera konverteringsmåttet.

   Med den här versionen `averagetimespentonsite`, `bouncerate`och `entries` mätvärden i [!DNL Target] aktiviteter kommer att bli inaktuella för nya aktiviteter. Befintliga aktiviteter kan fortsätta att använda dessa mått fram till maj 2023.

* Ett verktygstips har lagts till i [!DNL Target] Användargränssnitt som hjälper kunderna att välja ett optimeringsvillkor när de skapar eller redigerar ett [!UICONTROL Auto-Target] aktivitet som använder A4T.

## [!DNL Target] Standard/Premium 22.10.1 (version 10-13 oktober 2022)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **10 oktober**: Asien-Stillahavsområdet (APAC)
* **12 oktober**: Amerika
* **13 oktober**: Europa, Mellanöstern och Afrika (EMEA)

Den här versionen innehåller följande nya funktioner, förbättringar och korrigeringar:

| Funktion | Detaljer |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) upplevelsefragment | Uppdateringar av funktionen AEM Experience fragments innehåller följande:<ul><li>Lagt till möjlighet att filtrera AEM upplevelsefragment efter typ (HTML eller JSON) i [!UICONTROL Offers] lista. (TGT-43121)</li><li>Ett problem som gjorde att kunder kunde infoga JSON har korrigerats [!UICONTROL Experience Fragment] erbjudanden när VEC används, vilket inte stöds. JSON-erbjudanden kan bara infogas när du använder [!UICONTROL Form-Based Experience] disposition. (TGT-43846)</li></ul>Mer information finns i AEM [upplevelsefragment](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| Nytt [!UICONTROL Visual Experience Composer] tillägg för Google Chrome | En ny [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)-tillägget för Chrome finns i Chrome Web Store.<br>Från och med januari 2023 är den nuvarande [!DNL Target] Tillägget VEC Helper slutar fungera i Google Chrome eftersom Google inte tillåter tillägg med Manifest V2. Ladda ned det nya tillägget för att fortsätta att visuellt utveckla dina webbplatser i [!DNL Target] från och med det nya året.<br>Följande länkar visar de två tilläggen i Chrome Web Store:<ul><li>[Nytt tillägg](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Gammalt tillägg](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>Mer information finns i [Hjälptillägg för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| Dokumentationsuppdateringar | Viktiga dokumentationsuppdateringar är bland annat följande:<ul><li>Nytt och uppdaterat [Dokumentation för Adobe Target Admin och Reporting API](https://developer.adobe.com/target/administer/admin-api/){target=_blank} innehåller omfattande täckning av Admin- och Reporting API-slutpunkter, inklusive egenskaper, erbjudanden, värdar, miljöer, klienter, målgrupper, aktiviteter med mera.<br>Se det här och mer utvecklarinnehåll i [[!DNL Adobe Target] [!UICONTROL Developer Guide]](https://developer.adobe.com/target/){target=_blank}.</li><li>[Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>I den här artikeln beskrivs de detaljerade statistiska beräkningar som används vid manuella A/Bn-tester i [!DNL Adobe Target].<br>Informationen i den här artikeln ersätter *Adobe Target Calculations for A/B Testing* pdf-fil som tidigare fanns tillgänglig för hämtning på den här webbplatsen.</li></ul> |

* Ett problem som gjorde att målgruppsinformation inte kunde visas korrekt i dialogrutan har korrigerats [!UICONTROL Audiences Refinements] informationsfönstret. (TGT-43917)
* Förbättrade prestanda för [!DNL Target] Gränssnitt vid inläsning av målgrupper som närmar sig [rekommenderad gräns för målinriktningsregler](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Ett problem som gjorde att vissa komponenter inte visades korrekt i [!UICONTROL Modifications] på [!UICONTROL Experiences] sida när du skapar eller redigerar aktiviteter i VEC efter byte från [!UICONTROL Compose] till [!UICONTROL Browse] läge. (TGT-43300)
* Ett problem som gjorde att vissa kunder inte kunde arkivera har åtgärdats [!UICONTROL A/B Test] aktiviteter som använder [!UICONTROL Auto-Target]. (TGT-40978)
* Lagt till möjlighet att automatiskt använda ett enda erbjudande på flera platser inom en enda rapporteringsgrupp. (TGT-40689)

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| Dokumentationsändringar | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen.<br>Mer information finns i [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Versionsinformation för tidigare versioner | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium.<br>Mer information finns i [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Versionsinformation för Adobe Experience Cloud | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar.<br>Mer information finns i [Versionsinformation för Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html). |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Detaljer |
|--- |--- |
| Produktuppdatering för Adobe Prioritet | Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Kommande versionsinformation | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation, finns i [Versionsinformation för mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md) sida. |
