---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den kommande versionen av [!DNL Adobe Target], inklusive SDK, API och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar som ingår i de kommande [!DNL Target] Frisläpp?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: dba58f591b60ccfa1cdcd27d2704ebf28c40ba10
workflow-type: tm+mt
source-wordcount: '823'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (prerelease)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target] releaser, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 29 september 2023**

>[!NOTE]
>
>Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## [!DNL Target] Standard/Premium 23.9.4 (2-4 oktober 2023)

Den här versionen är tillgänglig enligt följande schema:

* **2 oktober**: Europa, Mellanöstern och Afrika (EMEA)
* **3 oktober**: Amerika
* **4 oktober**: Asien-Stillahavsregionen (APAC)

Den här versionen innehåller följande förbättringar och korrigeringar:

| Funktion | Information |
| --- | --- |
| [!UICONTROL Activities] Uppdatering av användargränssnittet<P>och<P>[!UICONTROL Feeds] Uppdatering av användargränssnittet | Som en del av [!DNL Adobe Target] teamets pågående arbete med att förbättra användarupplevelsen för [!DNL Target] användare, den här versionen uppdaterar [!UICONTROL Activities] och [!DNL Recommendations] [!UICONTROL Feeds] sidor på [!DNL Target] Gränssnitt. Uppdateringen förenar och standardiserar designmönster som tidigare varit inkonsekventa, samtidigt som nya förbättringar läggs till.<P>Mer information finns i [Verksamhet](/help/main/c-activities/activities.md) och [Feeds](/help/main/c-recommendations/c-products/feeds.md). |
| [!DNL Recommendations] implementeringsmönster | The *Recommendations implementeringsmönster med at.js* mönstret hjälper dig att förstå och skapa [!DNL Adobe Target Recommendations] implementering när du använder JavaScript-biblioteket at.js.<P>Allmän information om målmönster finns i [Översikt över implementeringsmönster](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/pattern-overview.html){target=_blank} i *Adobe Target Developer Guide*.<P>Det nya implementeringsmönstret för Recommendations består av följande artiklar:<ul><li>[Recommendations implementeringsmönster med översikten at.js](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank}</li><ul><li>[Initiera SDK:er](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/initialize-sdk.html){target=_blank}</li><li>[Konfigurera datainsamling](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/data-collection.html){target=_blank}</li><li>[Återge upplevelser](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/render-experiences.html?lang=en){target=_blank}</li><li>[Meddela [!DNL Target]](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/notify-target.html?lang=en){target=_blank}</li></ul></ul> |

* Tillagd [!UICONTROL Visual Experience Composer] (VEC) förbättringar för dynamiska ramverk. (TGT-44064)
* Ett problem som orsakade det valda datumet i `getViewInAnalyticsId` begäran om att inte uppdatera korrekt. Den här korrigeringen hjälper dig att beräkna om [!DNL Analytics] länk i rapportering när inställningarna för datumintervall och mätvärden ändras. (TGT-46246)

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

## [!DNL Target] Standard/Premium 23.5.2 (datum ska fastställas)

Den här versionen innehåller följande förbättringar och korrigeringar:

* Val av aktiverade optimeringskriterier för [!DNL Adobe Analytics] mätvärden.
* Aktiverad synkronisering av externa målgrupper med sling-jobb.
* Ett problem har korrigerats där SC-rapportsviter som innehåller ett punkttecken i namnet inte stöds.
* Funktioner som gör att kunderna kan ta bort och redigera inbyggda målgrupper.

## [!DNL Target] Standard/Premium 23.5.3 (datum ska fastställas)

Den här versionen innehåller följande förbättringar:

| Funktion | Information |
|--- |--- |
| [!UICONTROL QA mode] for [!UICONTROL Automated Personalization] verksamhet | [!DNL Adobe Target] [!UICONTROL QA mode] är nu tillgängligt för [!UICONTROL Automated Personalization] aktiviteter, ersätta [!UICONTROL Preview links] funktionalitet.<P>Mer information finns i [Aktivitets-QA](/help/main/c-activities/c-activity-qa/activity-qa.md). |

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Om du vill få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar, registrera dig för [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
