---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
short-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 207095a1db483abcc59f7806a67e559ee8694397
workflow-type: tm+mt
source-wordcount: '594'
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

>[!NOTE]
>
>På grund av problem som sedan dess har åtgärdats, &quot;Optimerade A4T-värden för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]&quot; som släpptes den 8 och 9 mars har tillfälligt tagits bort. Efter ytterligare intern testning kommer funktionen att släppas igen inom några veckor.

Den här versionen innehåller följande korrigeringar:

* Uppdateringar för utveckling av anpassade webbkomponenter med [!UICONTROL Visual Experience Composer] (VEC):

   * Skuggans DOM-element har markerats i VEC genom att redigeringsprocessen har förbättrats så att det inte finns något beroende av [!DNL Target] implementeringstyp vid redigering av skuggroten. Nu ska det fungera för alla webbplatser att välja Shadow DOM-element i VEC.
   * Korrigerade ett problem som förhindrade inläsning av HTML-element med #Shadow DOM i VEC. (TGT-35801)
   * Korrigerade VEC-problem med SPA webbplatser som använder ShadowDOM. (TGT-43169)
   * Ett problem med optimeringsmålet har korrigerats: &quot;klickade på ett element&quot; som inte kunde identifiera CSS-väljaren korrekt i ShadowDOM.

>[!NOTE]
>
>För att vara säker på att ändringarna som har skapats i VEC levereras måste du se till att du använder en [!DNL Target] SDK ([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js) med en version som är större än 2.8.

**Känt fel**: Klickspårning på ett skuggrotelement vid användning [!DNL Adobe Experience Platform Web SDK] fungerar inte korrekt. (TNT-47012)

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
