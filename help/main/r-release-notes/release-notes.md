---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
short-description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e130c68c838e799228956c598c583038a2f68ecf
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 11%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## [!DNL Adobe Target] Uppgradering av planerad infrastruktur {#edge}

Den planerade uppgraderingen av Edge-infrastrukturen kräver att ytterligare IP-domäner eller domäner är tillåtna. Granska och tillåt-lista NAT och IP/domäner för edge-distributioner 41-48. Uppgraderingar av infrastrukturen börjar 9 augusti 2023.

Mer information finns i [Tillåtelselista: Hörnkantsnoder](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html){target=_blank} i *Adobe Target Developer Guide*.

## [!DNL Target] Standard/Premium 23.8.1 (9 augusti 2023)

Den här versionen innehåller följande förbättringar och korrigeringar:

* Korrigerade ett problem som ibland förhindrade aktiviteter från att synkroniseras korrekt, vilket visas i[!UICONTROL Status]&quot; -kolumnen på [!UICONTROL Activity] listsida. (TGT-46010 &amp; TGT-44831)
* Ett problem som ibland förhindrade felet har korrigerats[!UICONTROL View in Analytics]&quot; länk från att visas på [!UICONTROL Reports] sida med aktiviteter som använder [!UICONTROL Analytics for Target] (A4T) som rapportkälla. (TGT-45808)
* Justerade presentationen av värden i tabeller så att de visas som procenttal i stället för siffror med decimaler. Till exempel 8 % i stället för 0,08. (TGT-45548)
* Ett problem som hindrade kunder från att använda tangentbordsfokus för att gå till nästa element i [!UICONTROL Goals & Settings] sida för [!UICONTROL Experience Targeting] (XT) aktiviteter. (TGT-44526)
* Ett problem som orsakade att tangentbordsfokus gick förlorat när du öppnade[!UICONTROL Add audiences]när du skapar en aktivitet. (TGT-44525)

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
