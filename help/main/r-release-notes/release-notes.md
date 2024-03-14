---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API och JavaScript-bibliotek.
landing-page-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
short-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f9bfe01924660e42b19f922e00ddc6393c5cfdba
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## Uppdateringar för `Browser:iPad` och `Browser:iPhone` in [!UICONTROL Browser] publikattribut (30 april 2024)

| Uppdateringar | Information |
|--- |--- |
| [!UICONTROL Browser:iPad] och [!UICONTROL Browser:iPhone] uppdaterat i [Webbläsarattribut](/help/main/c-target/c-audiences/c-target-rules/browser.md) används när målgrupper skapas. | [!DNL Adobe Target] låter dig [mål för någon av flera kategoriattribut](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), inklusive besökare som använder en viss [webbläsare](/help/main/c-target/c-audiences/c-target-rules/browser.md) när de besöker din sida.<P>Börja med [!DNL Target] Standard/Premium 24.3.1 (4-6 mars 2024), inbyggda målgrupper som skapats med målgränssnittet, som `Browser:iPad` och `Browser:iPhone` kommer att uppdateras för att utföra korrekt målinriktning för [!DNL iPad] och [!DNL iPhone] använda `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` och `profile.mobile.isTablet`.<P>Uppdateringen kräver inga åtgärder från kundens sida.<p><B>Viktigt</b>: För att kunderna ska kunna målinrikta [!DNL iPad] och [!DNL iPhone] i profilskript (och JavaScript-segment) måste kunden göra manuella ändringar av **30 april 2024**. Exempel på alternativa inställningar som måste ändras manuellt finns i [Uppdateringar för [!DNL iPad] och [!DNL iPhone] in [!UICONTROL Browser] publikattribut](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

## [!UICONTROL Visual Editing Helper] förlängning (14 mars 2024)

Den här versionen innehåller följande förbättringar och korrigeringar för [[!DNL Adobe Experience Cloud Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) tillägg för [!DNL Google Chrome]:

* Förbättrade inläsningsfunktionen för iFrame när du redigerar på kundernas webbplatser.
* Ett problem som orsakade att tillägget dubblerade cookies när redigering i dialogrutan utfördes har korrigerats [!UICONTROL Visual Experience Composer] (VEC)
* Tog bort beroendet att hämta at.js för kunder som använder [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

## [!DNL Target] Standard/Premium 24.3.1 (4-6 mars 2024)

Den här versionen är schemalagd för följande dagar:

* **4 mars**: Europa, Mellanöstern och Afrika (EMEA)
* **5 mars**: Asien-Stillahavsregionen (APAC)
* **6 mars**: Amerika

Den här versionen innehåller följande förbättringar och korrigeringar:

* Åtgärdade logiken som beräknar antalet unika väljare i en aktivitet. (TGT-47878)
* Korrigerade ett problem som orsakade [!UICONTROL Multivariate] (MVT) aktiviteter konfigurerade med [!UICONTROL Analytics for Target] (A4T)-rapportering visas inte korrekt. (TGT-47490)
* Förbättrade varningsmeddelandet som visas i rapporter när en upplevelse utan trafik används som kontrollupplevelse. (TGT-47537)
* Flera åtgärder för backend och lokalisering har lagts till.

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
