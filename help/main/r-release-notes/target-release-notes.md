---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 4baa78ac1119e86002c415f09b9481ad351fdcfc
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 4 oktober 2022**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

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
| Dokumentationsuppdateringar | Viktiga dokumentationsuppdateringar är bland annat följande:<ul><li>Nytt och uppdaterat [Dokumentation för Adobe Target Admin och Reporting API](https://developer.adobe.com/target/administer/admin-api/){target=_blank} innehåller omfattande täckning av Admin- och Reporting API-slutpunkter, inklusive egenskaper, erbjudanden, värdar, miljöer, klienter, målgrupper, aktiviteter med mera.<br>Se det här och mer utvecklarinnehåll i [[!DNL Adobe Target] [!UICONTROL Developer Guide]](https://developer.adobe.com/target/){target=_blank}.</li><li>[Statistiska beräkningar i A/Bn-tester](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>I den här artikeln beskrivs de detaljerade statistiska beräkningar som används vid manuella A/Bn-tester i [!DNL Adobe Target].<br>Informationen i den här artikeln ersätter *Adobe Target Calculations for A/B Testing* pdf-fil som tidigare fanns tillgänglig för hämtning på den här webbplatsen.</li></ul> |

* Ett problem som gjorde att målgruppsinformation inte kunde visas korrekt i dialogrutan har korrigerats [!UICONTROL Audiences Refinements] informationsfönstret. (TGT-43917)
* Förbättrade prestanda för [!DNL Target] Gränssnitt vid inläsning av målgrupper som närmar sig [rekommenderad gräns för målinriktningsregler](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Ett problem som gjorde att vissa komponenter inte visades korrekt i [!UICONTROL Modifications] på [!UICONTROL Experiences] sida när du skapar eller redigerar aktiviteter i VEC efter byte från [!UICONTROL Compose] till [!UICONTROL Browse] läge. (TGT-43300)
* Ett problem som gjorde att vissa kunder inte kunde arkivera har åtgärdats [!UICONTROL A/B Test] aktiviteter som använder [!UICONTROL Auto-Target]. (TGT-40978)
* Lagt till möjlighet att automatiskt använda ett enda erbjudande på flera platser inom en enda rapporteringsgrupp. (TGT-40689)

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Om du vill få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar, registrera dig för [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
