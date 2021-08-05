---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den aktuella versionen?
feature: Versionsinformation
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 42d9d7ed422bd5334a7f5e6467b0257f7ff4ab50
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-release. Versionsinformation om Target-API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar inkluderas också, i tillämpliga fall.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Migrera till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## [!DNL Target Standard/Premium] 21.8.1 (Datum som ska fastställas)

>[!NOTE]
>
>[!DNL Target Standard/Premium] 21.8.1-versionen har fördröjts. Istället för att släppas den 4 augusti 2021 kommer version 21.8.1 att släppas inom de närmaste dagarna. Mer information om det finns.

Den här underhållsversionen innehåller många backend-förbättringar, bland annat följande kundtillvända ändring:

* Korrigerade ett problem som orsakade att rapporter för [!UICONTROL Auto Personalization]-aktiviteter som skapats i [!UICONTROL Form-Based Experience Composer] refererade till borttagna erbjudanden i rapporter. Det här meddelandet orsakade att följande felmeddelande visades:&quot;Det går inte att hämta data för den här rapporten. Kontakta Adobe Client Care om problemet kvarstår.&quot; (TGT-41028)

## [!DNL Target Delivery API] (3 augusti 2021)

Den här versionen innehåller följande förbättringar:

* Gränsen för mbox-parametrar har ökats till 100 parametrar. Den tidigare gränsen var 50 parametrar. (TNT-41717)
* Gränsen för `categoryId` har ökats till 256 tecken. Den tidigare gränsen var 128 tecken.
* Följande [!DNL Adobe Audience Manager] (AAM) information har lagts till i leverans-API:

   * AAM UUID: Det interna AAM-ID som används för att unikt identifiera en användare.
   * dataPartnerId: ID för en datapartner.
   * dataPartnerUserId: Det användar-ID som anges av en datapartner.

   Tidigare ingick endast leverans-API:t `dcsLocationHint` och `blob`. (TNT-41644)

## at.js 2.6.0 (27 juli 2021)

* Ett säkert attribut har lagts till i cookies när inställningarna `secureOnly` för at.js är inställda på `true`.
* Svarstoken är nu tillgängliga när du använder `triggerView()`.
* Korrigerade ett problem som var relaterat till `CONTENT_RENDERING_NO_OFFERS`-händelsen. Den här händelsen utlöses korrekt när inget innehåll returneras från [!DNL Target].
* [!DNL Anlytics for Target] (A4T) klickmätningsinformation returneras korrekt när  `prefetch` begäranden används.
* UUID-genereringen använder inte längre `Math.random()`, men är beroende av `window.crypto`.
* Utgångsdatumet för cookien `sessionId` har utökats korrekt för varje nätverksanrop.
* Cacheinitieringen för vyn [!UICONTROL Single Page Application] (SPA) hanteras nu korrekt och inställningarna för `viewsEnable` följs.

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
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
