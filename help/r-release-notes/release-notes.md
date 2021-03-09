---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av Adobe Target, inklusive SDK, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den aktuella versionen?
feature: Versionsinformation
translation-type: tm+mt
source-git-commit: 801a2717615a1f0ff2ce306cda59f68cc5c4a8f8
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 0%

---


# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-release. Versionsinformation om Target-API:er, SDK:er, JavaScript-biblioteket (at.js) och andra plattformsändringar inkluderas också, i tillämpliga fall.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Migrera till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## Target Standard/Premium 21.2.1 (9 mars 2021)

Den här underhållsversionen innehåller följande förbättringar, korrigeringar och ändringar.

Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

* Ökade den tillåtna erbjudandestorleken (TGT-38304):

   | Typ | Föregående gräns | Ny gräns |
   | --- | --- | --- |
   | HTML | 256 kB | 1024 kB |
   | Visuella erbjudanden från målgränssnittet | 64 kB | 1 024 kB för varje upplevelse |
   | Via API | 512 kB | 1024 kB |

* [!UICONTROL Personalization Insights] rapporter för  [!UICONTROL Auto-Target] (AT) och  [!UICONTROL Automated Personalization] (AP)-aktiviteter produceras nu dagligen. Du kan välja en rapport med [!UICONTROL Automated Segments] eller [!UICONTROL Important Attributes] för de senaste 15, 30 och 60 dagarna. Alternativen för 45 dagar och 90 dagar har tagits bort så att de andra inställningarna för uppslagsfönstret kan köras dagligen. (TGT-39472)
* Korrigerade ett problem som gjorde att det aktuella beroendet inte visades när kunderna klickade på [!UICONTROL Edit Dependency] på en aktivitets [!UICONTROL Goals & Settings]-sida. (TGT-39340)
* Ett problem har korrigerats vid uppdatering av en arbetsytans [!UICONTROL Audience Library]. Före uppdateringen visas målgrupperna för den valda arbetsytan. Efter uppdateringen visas [!UICONTROL Default Workspace] och dess målgrupper. Den aktuella arbetsytan och dess målgrupper finns kvar efter uppdateringen. (TGT-38871)
* Ett problem har korrigerats vid kopiering av en [!UICONTROL Recommendations]-aktivitet och senare redigering av den ursprungliga aktiviteten genom att villkorssekvensen ändrades. Ändringen i villkorssekvensen i den ursprungliga aktiviteten tillämpades också felaktigt på den kopierade aktiviteten. (TGT-39155)
* Korrigerade ett problem som gjorde att fel antal produkter visades för [!UICONTROL Recommendations] undantag. (TGT-39599)

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
