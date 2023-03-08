---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 2%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## [!DNL Target] Standard/Premium 22.15.1 (8 och 9 mars 2023)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **8 mars**: Amerika
* **9 mars**: Europa, Mellanöstern och Afrika (EMEA)
* **9 mars**: Asien-Stillahavsområdet (APAC)

Den här versionen innehåller följande nya funktioner och förbättringar:

| Funktion | Detaljer |
| --- | --- |
| Optimerade A4T-värden för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] | [!DNL Target] låter dig välja mätvärden baserat på binomiala händelser eller mätvärden baserade på kontinuerliga händelser när du använder [!UICONTROL A4T] for [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet.<P>Observera följande tidskänsliga ändring av mätvärden som stöds:<ul><li>[!DNL Target] har behållit det tidigare beteendet för befintliga aktiviteter till och med 9 september 2023. Efter detta datum kommer aktiviteter som använder mätvärden som inte stöds att avbrytas för att tvinga befintlig aktivitetsmigrering till det nya beteendet.</li></ul>Mer information finns i [Målmått som stöds](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) in *A4T-stöd för Automatisk allokering och Automatiskt mål-aktiviteter*. |
| [!UICONTROL Auto-Allocate] använda [!UICONTROL Analytics for Target] (A4T) | Ny självstudiekurs:<ul><li>[Konfigurera A4T-rapporter i [!DNL Analysis Workspace] for [!UICONTROL Auto-Allocate] verksamhet](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| [!UICONTROL Auto-Target] använda [!UICONTROL Analytics for Target] (A4T) | Ny självstudiekurs:<ul><li>[Konfigurera A4T-rapporter i [!DNL Analysis Workspace] for [!UICONTROL Auto-Target] verksamhet](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

## at.js version 2.10.2 (7 mars 2023)

* Ett problem som orsakade `trackEvent` funktion som alltid returnerar ett fel.

Mer information om alla at.js-versioner finns i [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

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
