---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar,aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 0f96fb2a74a0716542308037d183847c91b1dc04
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-version. Versionsinformation för [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar inkluderas också, om tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## [!DNL Target Standard/Premium] 25.5.1 (5 maj 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Korrigerade ett problem som hindrade målgruppsförbättringar från att visas för vissa aktiviteter i det uppdaterade användargränssnittet. (TGT-52057)
* Ett problem som förhindrade användning av kombinerade målgrupper i aktiviteter har korrigerats. (TGT-52346)
* Ett problem som gjorde att det inte gick att skapa en ny aktivitet på en arbetsyta som inte är standard med en målgrupp som bara har aktiviteten från samma arbetsyta har åtgärdats. (TGE-52349)
* Korrigerade ett problem som gjorde att målgrupper med endast aktivitet försvann från det uppdaterade användargränssnittet efter att ha skapat och valt en ny målgrupp. (TGT=52091)
* Ett problem som förhindrade användning av dubblettmålgrupper i aktiviteter har korrigerats. (TGT-51200 &amp; TGT-52057)
* Korrigerade ett problem som medförde att målgruppsförbättringar och aktivitetspubliker hämtades i det uppdaterade användargränssnittet. (TGT-52158)
* Korrigerade ett problem som förhindrade att en ny aktivitet skapades på grund av användarindatafel: &quot;icke-standardarbetsyta tillåts inte för den här användaren.&quot; (TGT-52267)
* Korrigerade ett problem som förhindrade att erbjudanden visas i det uppdaterade användargränssnittet för både standardarbetsytor och icke-standardarbetsytor. [!DNL Target] visar nu erbjudanden från båda arbetsytorna. (TGT-52339)
* Ett problem har korrigerats där [!DNL Target] inte varnade kunderna när de redigerade en aktivitet och ändrade ett ändrat webbplatselement. (TGT-52100)
* Ett problem har korrigerats där ett erbjudande med ad hoc-erbjudanden skapade ett nytt erbjudande i stället för att uppdatera det befintliga. (TGT-52135)
* Korrigerat ett problem som orsakade ett ogiltigt nyttolastfel när erbjudanden flyttades till mappar. (TGT-52325)
* Korrigerat ett problem som orsakade ett användarindatafel när erbjudanden flyttades till mappar. (TGT-52296)
* Ett `audienceMetadata`-fält har lagts till för varje aktivitet och det har lästs och uppdaterats när aktiviteten redigeras. (TGT-51004)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=sv-SE) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=sv-SE){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, Versionsinformation om tidigare versioner och Experience Cloud Versionsinformation

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Information |
|--- |--- |
| [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md) | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen. |
| [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium. |
| [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv-SE){target=_blank} | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Information |
|--- |--- |
| [Adobe Priority-produktuppdatering](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar. |
| [Versionsinformation om mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
