---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den kommande versionen?
feature: Versionsinformation
translation-type: tm+mt
source-git-commit: 453106f7534f83c205722421bbf00044fde7da67
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---


# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 17 februari 2021**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Adobe rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.2.1 (9 mars och 10 mars 2021)

Den här underhållsversionen innehåller följande förbättringar, korrigeringar och ändringar.

Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

* Ökade den tillåtna erbjudandestorleken:

   | Typ | Föregående gräns | Ny gräns |
   | --- | --- | --- |
   | HTML | 256 kB | 1024 kB |
   | Visuella erbjudanden från målgränssnittet | 64 kB | 1 024 kB för varje upplevelse |
   | Via API | 512 kB | 1024 kB |

* Korrigerade ett problem som gjorde att det aktuella beroendet inte visades när kunderna klickade på [!UICONTROL Edit Dependency] på en aktivitets [!UICONTROL Goals & Settings]-sida. (TGT-39340)
* Ett problem har korrigerats vid uppdatering av en arbetsytans [!UICONTROL Audience Library]. Före uppdateringen visas målgrupperna för den valda arbetsytan. Efter uppdateringen visas [!UICONTROL Default Workspace] och dess målgrupper. Den aktuella arbetsytan och dess målgrupper finns kvar efter uppdateringen. (TGT-38871)
* Ett problem har korrigerats vid kopiering av en [!UICONTROL Recommendations]-aktivitet och senare redigering av den ursprungliga aktiviteten genom att villkorssekvensen ändrades. Ändringen i villkorssekvensen i den ursprungliga aktiviteten tillämpades också felaktigt på den kopierade aktiviteten. (TGT-39155)

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
