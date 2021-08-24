---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den kommande versionen?
feature: Versionsinformation
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: afa370a38921ab76babf5e49edc1e4b23ee807b0
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 24 augusti 2021**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 misslyckas alla anrop från mbox.js på ett säkert sätt och påverkar de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Om du vill undvika eventuella problem med dina platser migrerar du till den senaste versionen av det nya [!DNL Adobe Experience Platform Web SDK]- eller at.js-JavaScript-biblioteket. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.8.1 (10 augusti 2021)

Den här underhållsversionen innehåller många backend-förbättringar, bland annat följande kundtillvända ändring:

* Korrigerade ett problem som orsakade att rapporter för [!UICONTROL Auto Personalization]-aktiviteter som skapats i [!UICONTROL Form-Based Experience Composer] refererade till borttagna erbjudanden i rapporter. Det här meddelandet orsakade att följande felmeddelande visades:&quot;Det går inte att hämta data för den här rapporten. Kontakta Adobe Client Care om problemet kvarstår.&quot; (TGT-41028)

## Target Delivery API (3 augusti 2021)

Den här versionen innehåller följande förbättringar:

* Gränsen för mbox-parametrar har ökats till 100 parametrar. Den tidigare gränsen var 50 parametrar. (TNT-41717)
* Gränsen för `categoryId` har ökats till 256 tecken. Den tidigare gränsen var 128 tecken.
* Följande [!DNL Adobe Audience Manager] (AAM) information har lagts till i leverans-API:

   * AAM UUID: Det interna AAM-ID som används för att unikt identifiera en användare.
   * dataPartnerId: ID för en datapartner.
   * dataPartnerUserId: Det användar-ID som anges av en datapartner.

   Tidigare ingick endast leverans-API:t `dcsLocationHint` och `blob`. (TNT-41644)

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
