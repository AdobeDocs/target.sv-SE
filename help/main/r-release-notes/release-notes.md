---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
short-description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: a791fbe805735b278f650ff1f087b85898a66a07
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 4%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## [!DNL Target] Standard/Premium 23.3.1 (28-30 mars 2023)

Den här versionen är tillgänglig enligt följande schema:

* **28 mars**: Europa, Mellanöstern och Afrika (EMEA)
* **29 mars**: Asien-Stillahavsområdet (APAC)
* **30 mars**: Amerika

Den här versionen innehåller följande nya funktioner, förbättringar och korrigeringar:

| Funktion | Detaljer |
|--- |--- |
| Optimerade A4T-värden för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]<p>(Releasedatum 30 mars 2023) | [!DNL Target] låter dig välja mätvärden baserat på binomiala händelser eller mätvärden baserade på kontinuerliga händelser när du använder [!UICONTROL A4T] for [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet.<P>Observera följande ändring av mätvärden som stöds:<ul><li>[!DNL Target] har behållit det tidigare beteendet för befintliga aktiviteter till och med 9 september 2023. Efter detta datum kommer aktiviteter som använder mätvärden som inte stöds att avbrytas för att tvinga befintlig aktivitetsmigrering till det nya beteendet.</li></ul>Mer information finns i&quot;Målmått som stöds&quot; i [A4T-stöd för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] verksamhet](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported).<br>Följande självstudiekurser har uppdaterats med den här funktionen:<ul><li>[Konfigurera A4T-rapporter i [!DNL Analysis Workspace] for [!UICONTROL Auto-Allocate] verksamhet](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li><li>[Konfigurera A4T-rapporter i [!DNL Analysis Workspace] for [!UICONTROL Auto-Target] verksamhet](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html){target=_blank}</li></ul> |

* Förbättrad målgrupps- och aktivitetssynkronisering så att objekt som skapats i [!DNL Adobe Experience Platform] och [!DNL Adobe Audience Manager] finns i [!DNL Target] Snabbare gränssnitt. (TGT-44568)
* Förbättrat användargränssnitt som gör att användarna kan ta bort [!UICONTROL Default URL] under [!UICONTROL Administration] > [!UICONTROL Visual Experience Composer] > [!UICONTROL Default URL]. Med den här ändringen kan kunderna ändra standard-URL:en tillbaka till en tom sträng, vilket tidigare inte var möjligt efter den initiala konfigurationen. (TGT-44577)
* Tog bort begränsningar som hindrade kunderna från att redigera eller ta bort körklara målgrupper (målgrupper med reserverade namn). (TGT-44655)
* Inaktiverade &quot;[!UICONTROL Done]&quot; när du laddade mellanrum visades i [!DNL Target] Gränssnitt när du skapar [kombinerade målgrupper](/help/main/c-target/combining-multiple-audiences.md). (TGT-44079)
* Korrigerade [!UICONTROL Language] länken längst ned i [!UICONTROL Audiences] så att den länkar till[!UICONTROL Account communication preferences]&quot;. (TGT-43562)
* Löste ett problem som ibland hindrade kunder från att skapa [!UICONTROL A/B Test] aktiviteter efter att du har valt [!UICONTROL Adobe Analytics] option under [!UICONTROL Administration] > [!UICONTROL Reporting] > [!UICONTROL Reporting Experience Cloud Solution]. (TGT-44844)
* Ett problem som gjorde att kunderna inte kunde visa den senaste upplevelsen i ett [!UICONTROL Multivariate Test] aktivitet med många upplevelser inifrån [!UICONTROL Visual Experience Composer] (VEC). The [DOM-sökväg](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) längst ned på VEC hindrade ibland kunderna från att se den senaste upplevelsen. (TGT-44578)
* Korrigerade ett problem som gjorde att Bläddra-URL:en i VEC inte reflekterade den aktuella sidan som är synlig i en normal webbläsarsession om sidan kräver auktorisering eller anropar omdirigeringar. (TGT-44350)
* Ett problem som hindrade kunderna från att ändra [!UICONTROL Filter Incompatible Criteria] ange [!UICONTROL Recommendations] > [!UICONTROL Settings]. (TGT-44398)
* Korrigerade ett problem som orsakade att POSTEN begärde att få skapa [!DNL Recommendations] feeds som ska misslyckas vid användning [!UICONTROL Analytics Classifications] med rapportsviter med punkter i namnen. (TGT-44598)
* Uppdaterade länkar i [!DNL Target] Gränssnitt som pekar på det nya [Hjälptillägg för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). (TGT-44459)
* Förbättrat skydd för att förhindra SSRF-försök (Server-Side Request Forgery) i [!DNL Recommendations] feeds. (TGT-43769)
* Utför olika lokaliseringsåtgärder i hela [!DNL Target] Gränssnitt.

## at.js version 2.10.2 (7 mars 2023)

* Ett problem som orsakade `trackEvent` funktion som alltid returnerar ett fel.

Mer information om alla at.js-versioner finns i [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md) | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen. |
| [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium. |
| [Versionsinformation om Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Detaljer |
|--- |--- |
| [Produktuppdatering för Adobe Prioritet](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar. |
| [Versionsinformation för mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
