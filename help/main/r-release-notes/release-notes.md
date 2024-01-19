---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API och JavaScript-bibliotek.
landing-page-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
short-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## [!DNL Target] Standard/Premium 23.11.1 (13 och 14 november 2023)

Den här versionen är schemalagd för följande dagar:

* **13 november**: Asien-Stillahavsregionen (APAC)
* **14 november**: Amerika
* **14 november**: Europa, Mellanöstern och Afrika (EMEA)

Den här versionen innehåller följande förbättringar och korrigeringar:

* Förbättrade [Aktivitets-QA](/help/main/c-activities/c-activity-qa/activity-qa.md) funktioner som stöds [inte tillåter dubbla erbjudanden](/help/main/c-activities/t-automated-personalization/managing-exclusions.md) för upplevelser i [!UICONTROL Automated Personalization] verksamhet. (TGT-46627)
* Ett verktygstips har lagts till i [!DNL Target] Användargränssnitt som hjälper kunderna att förstå varför det kanske inte finns data tillgängliga i aktivitetsrapporter om ingen trafik tilldelas till kontrollupplevelsen. En länk till mer information finns i verktygstipset: [Varför finns det inga data tillgängliga för min aktivitetsrapport?](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B). (TGT-46610)
* Korrigerat ett problem som förhindrade aktiviteter från att visas korrekt på [!UICONTROL Activities] sida för några kunder. (TGT-46830)
* Åtgärdade följande problem som påverkade aktiviteter som använder [[!UICONTROL Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) som rapportkälla:
   * Ett problem som gjorde att vissa kunder inte kunde visa rapporteringsdata har korrigerats. (TGT-46557)
   * Korrigerade ett problem som ibland orsakade [!UICONTROL View in Analytics] länkar på aktivitetsrapporteringssidor för att inte fungera som de ska. (TGT-46731)
   * Korrigerade ett problem som förhindrade data för [!UICONTROL Lift] och [!UICONTROL Confidence] för att visas korrekt i [!DNL Target] Gränssnitt. (TGT-46592, TGT-46554 och TGT-46586)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Information |
|--- |--- |
| [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md) | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen. |
| [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium. |
| [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Information |
|--- |--- |
| [Produktuppdatering Adobe Priority](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar. |
| [Versionsinformation för mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
