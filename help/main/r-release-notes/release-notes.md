---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar,aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: cee17e318dedffaadccd2f93ae593e5fdd2bd600
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-version. Versionsinformation för [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar inkluderas också, om tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## [!DNL Target Standard/Premium] 25.3.4 (7 mars 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett problem har korrigerats där målgrupper som bara har aktiviteten inte var synliga på panelen [!UICONTROL Audiences], vilket förhindrar redigering eller återanvändning. (TGT-51860)
* Ett problem som blockerade [!DNL Target Standard]-kunder från att skapa aktiviteter med hjälp av [!UICONTROL Analytics for Target] (A4T)-rapportering har åtgärdats. (TGT-51854)
* Korrigerade ett problem som uteslöt lokala ID-räknare från nyttolasten under gruppskapnings- och redigeringsåtgärder. (TGT-51867)

## [!DNL Target Standard/Premium] 25.3.2 (6 mars 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett problem har korrigerats där kopiering av en aktivitet med en målgrupp som endast är aktiv inte kunde skapa en ny aktivitet. Den ursprungliga aktivitetens målgrupp användes av misstag. (TGT-51855)
* Korrigerade ett problem som förhindrade redigering av [!UICONTROL Experience Targeting] (XT)-aktiviteter med enbart aktivitet. (TGT-51846)
* Ett problem har korrigerats där [!UICONTROL Visual Experience Composer] (VEC) inte kunde använda ändringar på en upplevelse korrekt vid den första redigeringen. (TGT-51843)
* Ett problem som utlöste ett ID-fel när du klickade på vissa element i VEC har korrigerats. (TGT-51814)
* Felhanteringen i VEC uppdaterades när aktiviteten skapades. (TGT-51759)
* Korrigerade ett problem där en vy som saknas på panelen [!UICONTROL Modifications] orsakade ett fel av typen ogiltig användarinmatning när aktiviteten sparades. (TGT-51827)
* Ett problem som gjorde att rekommendationskriterier inte kunde skapas har korrigerats. (TGT-51834)
* Ett bekräftelsemeddelande lades till innan omdirigering till en annan URL. (TGT-51703)
* Problem med GraphQL integrationstester i erbjudanden och mappar har åtgärdats. (TGT-51839)

## [!DNL Target Standard/Premium] 25.3.1 (3 mars 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* En kombinerad målgrupp kan innehålla undergrupper, där var och en innehåller flera målgrupper. Den här versionen åtgärdade ett problem som förhindrade att undergrupper kunde visas i dialogrutan [!UICONTROL Rules]. (TGT-51813)
* Ett problem där vissa upplevelsemålgrupper ersattes med [!UICONTROL All Visitors] när äldre aktiviteter öppnades har åtgärdats. (TGT-51812)
* Löste ett problem som förhindrade redigering av aktiviteter med enbart aktivitetsgrupper. (TGT-51807)
* Ett problem som förhindrade redigering av sidhuvudets ändringar i det uppdaterade [!DNL Target]-gränssnittet har åtgärdats. (TGT-51797)
* Ett null-fel som uppstod när en upplevelse skulle dupliceras, en annan upplevelse tas bort och sedan försöker spara aktiviteten har åtgärdats. (TGT-51796)
* Ett problem som förhindrade att regler för målgruppsundantag visades i målgruppens informationspanel under [!UICONTROL Targeting]-steget för att skapa aktiviteter har åtgärdats. (TGT-51579)
* Uppdaterade felmeddelanden på koreanska. (TGT-51701 &amp; TGT-51699)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, Versionsinformation om tidigare versioner och Experience Cloud Versionsinformation

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
| [Adobe Priority-produktuppdatering](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar. |
| [Versionsinformation om mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
