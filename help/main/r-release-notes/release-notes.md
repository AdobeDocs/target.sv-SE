---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 44445f269a69a3ac3e3bc88bab8abf9fc4d51663
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-version. Versionsinformation för [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar inkluderas också, om tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## [!DNL Target] rapporterar i [!DNL Adobe Customer Journey Analytics] (8 maj 2024)

Integrationen mellan [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} och [!DNL Target] ger kraftfulla analys- och tidsbesparande verktyg för optimeringsprogrammet.

De främsta fördelarna med att använda [!DNL Customer Journey Analytics] som rapportkälla för [!DNL Target] är:

* Marknadsförarna kan när som helst dynamiskt tillämpa [!DNL Customer Journey Analytics]-framgångsmått på [!DNL Target]-aktivitetsrapporter. Du behöver inte ange allt innan du kör aktiviteten.
* Marknadsförarna kan utnyttja [!DNL Customer Journey Analytics] funktioner, som [panelen Experimentation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}, för att ytterligare analysera webbplatspersonaliseringen.
* Marknadsförare kan ha en enda rapportkälla för [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/cja-ajo){target=_blank} och [!DNL Target]. Båda personaliseringsprodukterna kan anslutas till [!DNL Customer Journey Analytics] för en mer helhetsbild av din webbpersonalisering.

Mer information finns i [Målrapportering i Adobe Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

## [!UICONTROL Visual Experience Composer] hjälptillägg (23 april 2024)

Det gamla hjälptillägget [!DNL Target] för Visual Experience Composer skapades med Manifest V2. [!DNL Google] meddelade att tillägg som skapats med Manifest V2 inte längre tillåts från och med juni 2024. Mer information finns i [[!UICONTROL Visual Experience Composer] hjälptillägg](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

[!DNL Adobe] rekommenderar att kunderna går över till det nyare [hjälptillägget för visuell redigering](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) så snart som möjligt.

## Uppdateringar för `Browser:iPad` och `Browser:iPhone` i [!UICONTROL Browser] målgruppsattribut (30 april 2024)

| Uppdateringar | Information |
|--- |--- |
| [!UICONTROL Browser:iPad] och [!UICONTROL Browser:iPhone] har uppdaterats i [Webbläsarattribut](/help/main/c-target/c-audiences/c-target-rules/browser.md) som används när målgrupper skapas. | Med [!DNL Adobe Target] kan du [ange mål för ett av flera kategoriattribut](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), inklusive besökare som använder en viss [webbläsare eller webbläsaralternativ](/help/main/c-target/c-audiences/c-target-rules/browser.md) när de besöker din sida.<P>Från och med [!DNL Target] Standard/Premium 24.3.1 (4-6 mars 2024) kommer inbyggda målgrupper som skapats med målgränssnittet, som `Browser:iPad` och `Browser:iPhone`, att uppdateras för att kunna utföra korrekt målinriktning för [!DNL iPad] och [!DNL iPhone] med `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` och `profile.mobile.isTablet`.<P>Uppdateringen kräver inga åtgärder från kundens sida.<p><B>Viktigt</b>: För att kunder ska kunna utföra korrekt målinriktning för [!DNL iPad] och [!DNL iPhone] i profilskript (och JavaScript-segment) måste kunden göra manuella ändringar senast den **30 april 2024**. Exempel på alternativa inställningar som måste ändras manuellt finns i [Uppdateringar för  [!DNL iPad]  och  [!DNL iPhone]  i [!UICONTROL Browser] målgruppsattribut](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

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
| [Produktuppdatering för Adobe Prioritet](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar. |
| [Versionsinformation om mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
