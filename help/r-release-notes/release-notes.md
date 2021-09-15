---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vilka nya funktioner ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '712'
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

## [!DNL Target Standard/Premium] 21.9.1 (14 september 2021)

Den här underhållsversionen innehåller följande förbättringar, korrigeringar och ändringar.

* Problem som medförde att kunder inte kunde logga in på [!UICONTROL Visual Experience Composer] (VEC) på grund av nya säkerhetsprofiler för cookies från tredje part i vissa webbläsare har åtgärdats. Problemet diskuterades i&quot;Sidor som inte läses in i Visual Experience Composer (VEC) eller Enhanced Experience Composer (EEC) när Google Chrome version 80+ används&quot; i [Felsökningsproblem relaterade till Visual Experience Composer och Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).
* Ett problem som gjorde att erbjudandenamn i VEC visades i stället för erbjudandets egna namn har åtgärdats. (TGT-41300)
* Upplevelsnamnen visas nu i [!DNL Analysis Workspace] för A4T-aktiviteter (TGT-38674)
* Korrigerade ett problem i [!DNL Recommendations] som felaktigt tillämpade ändringar av enhets-ID i en befordran av en dubblerad aktivitet till den ursprungliga aktiviteten. (TGT-41482)
* Ett problem som gjorde att knappen Redigera villkor inte kunde visas korrekt på [!UICONTROL Experiences]-sidan för [!DNL Recommendations]-aktiviteter i VEC har åtgärdats. (TGT-39512)
* Korrigerade ett problem som förhindrade synkronisering av aktiviteter när de duplicerades och kopierades till en testarbetsyta. (TGT-40686)
* Ett problem som förhindrade ändringar i en väljare med [upplevelsefragment](/help/c-experiences/c-manage-content/aem-experience-fragments.md) när [!UICONTROL Insert After] användes i VEC har åtgärdats. (TGT-41802)
* Korrigerade ett problem som förhindrade att tomt JSON-innehåll i ett erbjudande skickades till serverdelen. [!DNL Target] skickar nu JSON-objektet trots att det är tomt. (TGT-41555)
* Korrigerade ett problem som gjorde att äldre [!DNL Analytics]-rapportering öppnades i stället för [!DNL Analysis Workspace] när kunderna klickade på [!UICONTROL View in Analytics] när de visade en rapport. (TGT-41867)
* Ytterligare klargöranden lades till i det visade gränssnittsmeddelandet när en kund försöker välja [!DNL Analytics] som rapportkälla (A4T) för en [!UICONTROL Automated Personalization]-aktivitet. Meddelandet anger att &quot;[!DNL Target] är den enda källan som stöds för [!UICONTROL Automated Personalization]-aktiviteter.&quot; (TGT-41954)
* Ytterligare förtydliganden har lagts till i felmeddelandet när kunderna försöker att separera värdar med&quot;newline&quot; i stället för kommatecken. (TGT-40671)
* Korrigerade ett problem som orsakade att vissa aktiviteters [!UICONTROL Last Updated]-datum skilde sig från det engelska användargränssnittet för spanska och japanska kunder (när användargränssnittet visades på spanska och japanska). (TGT-38980)

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
