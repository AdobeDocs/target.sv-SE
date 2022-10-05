---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: c5445903e7bbab210d0e72200c54ab07975c21c5
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 0%

---

# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## [!DNL Target] Standard/Premium 22.10.1 (version 5-7 oktober 2022)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **5 oktober**: Asien-Stillahavsområdet (APAC)
* **6 oktober**: Amerika
* **7 oktober**: Europa, Mellanöstern och Afrika (EMEA)

Den här versionen innehåller följande nya funktioner, förbättringar och korrigeringar:

| Funktion | Detaljer |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) upplevelsefragment | Uppdateringar av funktionen AEM Experience fragments innehåller följande:<ul><li>Lagt till möjlighet att filtrera AEM upplevelsefragment efter typ (HTML eller JSON) i [!UICONTROL Offers] lista. (TGT-43121)</li><li>Ett problem som gjorde att kunder kunde infoga JSON har korrigerats [!UICONTROL Experience Fragment] erbjudanden när VEC används, vilket inte stöds. JSON-erbjudanden kan bara infogas när du använder [!UICONTROL Form-Based Experience] disposition. (TGT-43846)</li></ul>Mer information finns i AEM [upplevelsefragment](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| Nytt [!UICONTROL Visual Experience Composer] tillägg för Google Chrome | En ny [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)-tillägget för Chrome finns i Chrome Web Store.<br>Från och med januari 2023 är den nuvarande [!DNL Target] Tillägget VEC Helper slutar fungera i Google Chrome eftersom Google inte tillåter tillägg med Manifest V2. Ladda ned det nya tillägget för att fortsätta att visuellt utveckla dina webbplatser i [!DNL Target] från och med det nya året.<br>Följande länkar visar de två tilläggen i Chrome Web Store:<ul><li>[Nytt tillägg](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Gammalt tillägg](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>Mer information finns i [Hjälptillägg för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| Optimerade A4T-värden för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]<br>(Exakt utgivningsdatum ska fastställas.) | Tänk på följande ändringar:<ul><li>Stöd för binära värden och maximeringsvärden i [!UICONTROL Analytics for Target] A4T-rapportering för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet</li><li>Bevarar befintliga aktiviteter fram till 20 februari 2023. Efter detta datum kommer aktiviteterna att avbrytas för att tvinga befintlig aktivitetsmigrering till nytt beteende</li><li>Från 20 februari 2023, stöd för `averagetimespentonsite`, `bouncerate`och `entries` mätvärden i [!DNL Target] aktiviteter kommer att bli inaktuella.</li></ul> |

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
