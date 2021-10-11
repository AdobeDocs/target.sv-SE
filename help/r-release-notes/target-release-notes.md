---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: f6efc1e921535abdd11501979d6f44e84e443a1f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 11 oktober 2021**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 misslyckas alla anrop från mbox.js på ett säkert sätt och påverkar de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Om du vill undvika eventuella problem med dina platser migrerar du till den senaste versionen av det nya [!DNL Adobe Experience Platform Web SDK]- eller at.js-JavaScript-biblioteket. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.10.2 (13 oktober 2021)

Följande förbättringar har lagts till när du använder [!DNL Target] [!UICONTROL Audiences] med [!DNL Adobe Experience Platform Web SDK]:

* Varningsikoner, poseringar och meddelanden på olika platser i [!DNL Target]-gränssnittet har lagts till för att ange att målgruppen togs bort från källan och inte längre är tillgänglig för användning i [!DNL Target]-aktiviteter.

   Följande bilder visar några av de platser där ikonerna, poseringarna och meddelandena visas:

   * [!UICONTROL Activity] listsida

      ![Målgruppen togs bort vid källmeddelandet på sidan med aktivitetslistan](assets/deleted-at-source-audiences-list.png)

   * Aktivitet [!UICONTROL Overview] sidor:

      ![Målgruppen togs bort vid källmeddelandet på översiktssidan](assets/deleted-at-source-overview.png)

   * [!UICONTROL Experiences] steg i arbetsflödet för att skapa aktiviteter:

      ![Målgruppen togs bort vid källmeddelandet på  [!UICONTROL Experiences] sidan](assets/deleted-at-source-experiences.png)

   * [!UICONTROL Targeting] steg i arbetsflödet för att skapa aktiviteter:

      ![Målgruppen togs bort vid källmeddelandet på  [!UICONTROL Targeting] sidan](assets/deleted-at-source-targeting.png)

   * [!UICONTROL Goals & Settings] steg i arbetsflödet för att skapa aktiviteter:

      ![Målgruppen togs bort vid källmeddelandet på  [!UICONTROL Goals & Settings] sidan](assets/deleted-at-source-goals-settings.png)

   * Målgruppsförbättringar ([!UICONTROL Replace Audience] i [!UICONTROL Targeting]-steget i arbetsflödet för att skapa aktivitet):

* Om du försöker använda funktionen Kombinera målgrupper och en av målgrupperna togs bort från källan, är [!UICONTROL Save] inaktiverat.

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
