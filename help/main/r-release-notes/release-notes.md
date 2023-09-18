---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
short-description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6fa553c7179cd2a6d500bdc53cc77dc01ee906e7
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 8%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## [!DNL Target] Standard/Premium 23.9.3 (18 september 2023)

Den här versionen innehåller följande förbättringar och korrigeringar:

* Förbättrade [!UICONTROL Visual Experience Composer] (VEC) för att stödja Lightning Web Components (Light DOM). (TGT-45422)
* Korrigerade ett problem som gjorde att VEC-åtgärder tillämpades i fel ordning. I vissa fall tillämpade VEC vissa ändringar asynkront och när extra ändringar lades till i ett element uppstod fel om det elementet visas efter ett [!UICONTROL Insert] åtgärd. Korrigerar även den VEC-URL som nu uppdateras när du klickar på ankarlänkar. (TGT-45983)
* Ett problem med VEC har korrigerats [!UICONTROL Overlay] som nu stöder element i skugg-DOM. (TGT-45202 &amp; TGT-45262)
* Ett problem har korrigerats när en SPA öppnades i VEC och sedan [!UICONTROL Browse] läge fick bakåt- och framåtpilarna att inte fungera korrekt. (TGT-45956)
* Ett problem som gjorde att vissa webbsidor inte kunde läsas in i VEC har korrigerats. (TGT-45983)

## [!DNL Target] Standard/Premium 23.9.2 (12-14 september 2023)

Den här versionen är tillgänglig enligt följande schema:

* **12 september**: Amerika
* **13 september**: Asien-Stillahavsregionen (APAC)
* **14 september**: Europa, Mellanöstern och Afrika (EMEA)

Den här versionen innehåller följande förbättringar och korrigeringar:

* Ändrad [!DNL Analytics] API till nya [!DNL Analytics] API version 2.0. (TGT-45345)
* Åtgärdade problem som påverkade [!UICONTROL Automated Personalization] (AP) aktiviteter för vissa kunder, inklusive synkronisering i rätt tid av aktiviteten på [!DNL Target] backend och leverera den förväntade upplevelsen av förhandsgranskningslänkar. (TGT-46202)

## [!DNL Target] Standard/Premium 23.9.1 (6-11 september 2023)

Den här versionen är tillgänglig enligt följande schema:

* **6 september**: Amerika
* **7 september**: Europa, Mellanöstern och Afrika (EMEA)
* **11 september**: Asien-Stillahavsregionen (APAC)

Den här versionen innehåller följande förbättringar och korrigeringar:

* Ett problem som orsakade inkonsekventa rapporteringsdata i [!DNL Target] Användargränssnittet och [!DNL Adobe Analytics] Användargränssnitt för [!UICONTROL Auto-Allocate] aktiviteter som använder [!UICONTROL Analytics for Target] (A4T) som rapportkälla. (TGT-46112)
* Ökade tidsgränsen för PUT-anrop till Target Delivery API till 15 sekunder för att undvika timeoutfel. (TGT-46091)
* Ett problem som gjorde att URL:en inte kunde uppdateras kontinuerligt när du bläddrar genom en webbplats för ett program (SPA) har åtgärdats. (TGT-45417)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Information |
|--- |--- |
| [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md) | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen. |
| [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium. |
| [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Information |
|--- |--- |
| [Produktuppdatering Adobe Priority](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar. |
| [Versionsinformation för mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
