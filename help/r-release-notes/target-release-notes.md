---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
translation-type: tm+mt
source-git-commit: dba3044c94502ea9e25b21a3034dc581de10f431
workflow-type: tm+mt
source-wordcount: '456'
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

Den här versionen innehåller följande nya funktioner och förbättringar. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

| Funktion | Detaljer |
| --- | --- |
| Beslutsstöd på enheten för at.js | Med enhetsbaserad beslutsfattande kan marknadsförare och utvecklare leverera experiment och personalisering i en användares webbläsare med nästan nolltidsfördröjning.<br>Mer information finns i  [Enhetsbeslut för at.js.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)<br>(Datum som ska tillkännages) |
| ![PremiumList-](/help/assets/premium.png) baserade operatorer för entitetsfiltreringsregler | [!DNL Target Recommendations] stöder nya listbaserade operatorer för entitetsfiltreringsregler. (TGT-39234)<br>Operatorer som lagts till nyligen är:<br><ul><li>Finns i listan</li><li>Finns inte i listan</li><li>Listan innehåller ett objekt i</li><li>Listan innehåller inget objekt i</li><li>Listan innehåller alla objekt i</li><li>Listan innehåller inte alla objekt i</li></ul>Mer information finns i&quot;Tillgängliga operatorer&quot; i [Använd dynamiska och statiska inkluderingsregler](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators). |

Den här versionen innehåller följande korrigeringar.

* Korrigerade ett problem som förhindrade en aktivitet från att synkroniseras efter att målgruppen ändrats till [!UICONTROL All Visitors]. (TGT-40259)
* Korrigerade ett problem som förhindrade att erbjudanden duplicerades när de användes på olika platser i [!UICONTROL Automated Personalization]-aktiviteter trots att alternativet [!UICONTROL Disallow Duplicates] är aktiverat. (TGT-39567)
* Ett problem som gjorde att sidan [!UICONTROL Administration] > [!UICONTROL Scene7 configuration] inte kunde läsas in korrekt har åtgärdats. (TGT-39918)
* Korrigerade ett problem som gjorde att egenskaper mappades till fel arbetsyta. (TGT-39869)
* Korrigerade ett problem som orsakade oändlig inläsning om begäran misslyckas efter att miljön ändrats och ett rekommendationsundantag skapades. (TGT-39948)

## at.js version 2.5.0 (datum ska tillkännages)

Den här versionen av at.js innehåller följande förbättringar och ändringar:

* [Enhetsspecifikt ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) beslutsstöd för at.js.
* [Förhandsgranska ](/help/c-activities/c-activity-qa/activity-qa.md) länkarstöd för Automated Personalization-aktiviteter

Den här versionen tar också bort stöd för Microsoft Internet Explorer 10 och senare versioner.

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
