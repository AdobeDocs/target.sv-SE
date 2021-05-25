---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av Adobe Target, inklusive SDK, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den aktuella versionen?
feature: Versionsinformation
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d102e3b93e258199bad40de089443eda3a07d7fe
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 0%

---

# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-release. Versionsinformation om Target-API:er, SDK:er, JavaScript-biblioteket (at.js) och andra plattformsändringar inkluderas också, i tillämpliga fall.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Migrera till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## at.js version 2.5.0 (13 maj 2021)

Den här versionen av at.js innehåller följande förbättringar och ändringar:

* [Enhetsspecifikt ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) beslutsstöd för at.js.
* [Förhandsgranska ](/help/c-activities/c-activity-qa/activity-qa.md) länkarstöd för Automated Personalization-aktiviteter

Den här versionen tar också bort stöd för Microsoft Internet Explorer 10, Internet Explorer 11 och alla äldre versioner. Microsoft Edge stöds fortfarande i at.js 2.5.0 och senare.

## Target Standard/Premium 21.4.1 (19 april 2021)

Den här versionen innehåller följande nya funktioner och förbättringar. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

| Funktion | Detaljer |
| --- | --- |
| Beslutsstöd på enheten för at.js<br>(datum ska tillkännages) | Med enhetsbaserad beslutsfattande kan marknadsförare och utvecklare leverera experiment och personalisering i en användares webbläsare med nästan nolltidsfördröjning.<br>Mer information finns i  [Enhetsbeslut för at.js.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) |
| ![PremiumList-](/help/assets/premium.png) baserade operatorer för entitetsfiltreringsregler | [!DNL Target Recommendations] stöder nya listbaserade operatorer för entitetsfiltreringsregler. (TGT-39234)<br>Operatorer som lagts till nyligen är:<br><ul><li>Finns i listan</li><li>Finns inte i listan</li><li>Listan innehåller ett objekt i</li><li>Listan innehåller inget objekt i</li><li>Listan innehåller alla objekt i</li><li>Listan innehåller inte alla objekt i</li></ul>Mer information finns i&quot;Tillgängliga operatorer&quot; i [Använd dynamiska och statiska inkluderingsregler](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators). |

Den här versionen innehåller följande korrigeringar.

* Korrigerade ett problem som förhindrade en aktivitet från att synkroniseras efter att målgruppen ändrats till [!UICONTROL All Visitors]. (TGT-40259)
* Korrigerade ett problem som förhindrade att erbjudanden duplicerades när de användes på olika platser i [!UICONTROL Automated Personalization]-aktiviteter trots att alternativet [!UICONTROL Disallow Duplicates] är aktiverat. (TGT-39567)
* Ett problem som gjorde att sidan [!UICONTROL Administration] > [!UICONTROL Scene7 configuration] inte kunde läsas in korrekt har åtgärdats. (TGT-39918)
* Korrigerade ett problem som gjorde att egenskaper mappades till fel arbetsyta. (TGT-39869)
* Korrigerade ett problem som orsakade oändlig inläsning om begäran misslyckas efter att miljön ändrats och ett rekommendationsundantag skapades. (TGT-39948)

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| Dokumentationsändringar | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen.<br>Mer information finns i  [Dokumentationsändringar](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Versionsinformation för tidigare versioner | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium.<br>Mer information finns i  [Versionsinformation för tidigare versioner](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Versionsinformation för Adobe Experience Cloud | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar.<br>Mer information finns i  [versionsinformationen](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html) för Experience Cloud. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Detaljer |
|--- |--- |
| Produktuppdatering för Adobe Prioritet | Anmäl dig till produktuppdateringen Adobe Priority:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) om du vill få förhandsmeddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar. |
| Kommande versionsinformation | Mer information om målversionerna för den aktuella månaden, inklusive förhandsversionsinformation, finns på sidan [Versionsinformation för mål - Förhandsversion](/help/r-release-notes/target-release-notes.md). |
