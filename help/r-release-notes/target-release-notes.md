---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den kommande versionen?
feature: Versionsinformation
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
translation-type: tm+mt
source-git-commit: 2e678fa8a4826f6bfdaef1a04b89b8da7de48d12
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 16 april 2021**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 misslyckas alla anrop från mbox.js på ett säkert sätt och påverkar de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Om du vill undvika eventuella problem med dina platser migrerar du till den senaste versionen av det nya [!DNL Adobe Experience Platform Web SDK]- eller at.js-JavaScript-biblioteket. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.4.1 (19 april 2021)

Den här versionen innehåller följande nya funktioner. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

| Funktion | Detaljer |
| --- | --- |
| Beslutsstöd på enheten för at.js | Med enhetsbaserad beslutsfattande kan marknadsförare och utvecklare leverera experiment och personalisering i en användares webbläsare med nästan nolltidsfördröjning. |

Den här versionen innehåller följande förbättringar, korrigeringar och ändringar.

* Korrigerade ett problem som förhindrade en aktivitet från att synkroniseras efter att målgruppen ändrats till [!UICONTROL All Visitors]. (TGT-40259)
* Korrigerade ett problem som förhindrade att erbjudanden duplicerades när de användes på olika platser i [!UICONTROL Automated Personalization]-aktiviteter trots att alternativet [!UICONTROL Disallow Duplicates] är aktiverat. (TGT-39567)
* Ett problem som gjorde att sidan [!UICONTROL Administration] > [!UICONTROL Scene7 configuration] inte kunde läsas in korrekt har åtgärdats. (TGT-39918)
* Korrigerade ett problem som gjorde att egenskaper mappades till fel arbetsyta. (TGT-39869)
* [!DNL Target Recommendations] stöder nya listbaserade operatorer för entitetsfiltreringsregler. (TGT-39234)

   Nya operatorer:

   * Finns i listan
   * Finns inte i listan
   * Listan innehåller ett objekt i
   * Listan innehåller inget objekt i
   * Listan innehåller alla objekt i
   * Listan innehåller inte alla objekt i

* Korrigerade ett problem som orsakade oändlig inläsning om begäran misslyckas efter att miljön ändrats och ett rekommendationsundantag skapades. (TGT-39948)

## at.js version 2.5.0 (19 april 2021)

Den här versionen av at.js innehåller följande förbättringar:

* Beslutsstöd på enheten för at.js
* Stöd för förhandsgranskningslänkar i Automated Personalization

Den här versionen tar också bort stöd för Microsoft Internet Explorer 10 och senare versioner.

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
