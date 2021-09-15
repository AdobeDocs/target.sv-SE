---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 5a5b39db9b9b4ffd95573d643dcff52fe562c0c2
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 14 september 2021**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 misslyckas alla anrop från mbox.js på ett säkert sätt och påverkar de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Om du vill undvika eventuella problem med dina platser migrerar du till den senaste versionen av det nya [!DNL Adobe Experience Platform Web SDK]- eller at.js-JavaScript-biblioteket. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
