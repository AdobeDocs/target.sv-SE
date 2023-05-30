---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
short-description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 2e6efe777925eb14e280ea38110dc1cb12264d17
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 8%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## [!DNL Target] Standard/Premium 23.5.2 (31 maj 2023)

Den här versionen innehåller följande förbättringar och korrigeringar:

* Korrigerade ett problem som gjorde att en tom sida visades när en auktoriseringstoken för profil-API genererades. (TGT-45387 &amp; TGT-45423)
* Ett problem som gjorde att en bild inte kunde visas i [!UICONTROL Create Design] om bildnamnet innehåller GB 18030-tecken. (TGT-44614)
* Korrigerade ett problem där vissa GB-symboltecken på 18030 felaktigt utelämnades i Text/HTML i upplevelser. (TGT-44600)
* Korrigerade ett problem som orsakade rapporter för [!UICONTROL Auto Personalization] aktiviteter som ska frysas under analysen. (TGT-44820)
* Ett problem som gjorde att det inte gick att söka efter en aktivitet på [!UICONTROL Activity] sida om aktivitetsnamnet innehåller en hakparentes ( [ eller ] ). (TGT-44777)
* Korrigerade ett problem som förhindrade en aktivitet från att synkroniseras om aktivitetens mål innehåller specialtecken. (TGT-44982)
* Korrigerat ett problem som gjorde att inga aktiviteter visades i [!DNL Target] Gränssnitt för standardarbetsytan för vissa kunder. (TGT-45286)
* Beteendet för flaggan&quot;Tillåt inte dubbletter&quot; har uppdaterats. Uteslutna upprepade erbjudandeflaggor uppdateras för att tillåta upprepade erbjudanden om de är standarderbjudandet (för API:er v3, v4) och tillåter dubblettalternativ om alternativen refererar till standarderbjudandet och inte har några definierade mallar. (TNT-46617)
* Ett problem där en frågeparameter lades till i en URL som förhindrade att sidan lästes in i [!UICONTROL Visual Experience Composer] (VEC). (TGT-44873)
* Utför olika lokaliseringsåtgärder i hela [!DNL Target] Gränssnitt.

## [!DNL Target] Standard/Premium 23.5.1 (23-25 maj 2023)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

23 maj: Europa, Mellanöstern och Afrika (EMEA) Asien-Stillahavsområdet (APAC), 25 maj: Amerika

Den här versionen innehåller följande nya förbättringar och korrigeringar:

* Ett problem som hindrade vissa kunder från att skapa målgrupper med besökarprofiler med operatorerna &quot;större än&quot; eller &quot;mindre än&quot; har åtgärdats. (TGT-45271)
* Utför olika lokaliseringsåtgärder i hela [!DNL Target] Gränssnitt.
* Målgränssnittet uppdaterades på olika platser för en kommande gränssnittsuppdatering (ändringarna ligger bakom en funktionsflagga tills uppdateringarna släpps).

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

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
