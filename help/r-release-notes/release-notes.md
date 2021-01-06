---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Versionsinformationen innehåller information om funktioner, förbättringar, korrigeringar och kända fel för varje utgåva av Adobe Target Standard och Target Premium.
title: 'Versionsinformation om Adobe Target (aktuell) '
feature: Release Notes
translation-type: tm+mt
source-git-commit: 531e147d99bbc73414f790d66a3633bd1de8f50f
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 0%

---


# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje Target Standard- och Target Premium-version. Versionsinformation om Target-API:er, SDK:er, JavaScript-biblioteket (at.js) och andra plattformsändringar inkluderas också, i tillämpliga fall.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används. Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser.
>
>* **Adobe Experience Platform Web SDK**: Med  [!UICONTROL Adobe Experience Platform Web SDK] kan du interagera med de olika tjänsterna i  [!DNL Experience Cloud] (inklusive  [!DNL Target]) via Adobe Experience Edge Network. Om du väljer att migrera till [!DNL Adobe Experience Platform Web SDK] läser du [What is Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) i *Web SDK Guide*. Se [Målöversikt](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html) för [!DNL Target]-specifik information.
   >
   >
* **at.js**: JavaScript-biblioteket at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiden för webblöplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program. Om du väljer att migrera till at.js, se [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKompetensverktyg: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Även om det finns stöd för mbox.js (fram till 31 mars 2021) har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Genom att flytta alla kunder till [!UICONTROL Adobe Experience Platform Web SDK] eller at.js kan våra tekniker och vår supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig från Adobe.

Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## kl. 2.3.3 (13 november 2020)

Den här versionen av at.js är en underhållsversion och innehåller följande korrigering:

* Korrigerade ett problem relaterat till lådklicksspårning och A4T.

## Target Standard/Premium 20.10.1 (27 oktober 2020)

Den här versionen innehåller följande nya funktioner:

| Funktion | Detaljer |
| --- | --- |
| [Enhetsbeslut](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) | Med enhetsbaserad beslutsfattande kan både marknadsförare och produktutvecklare leverera experimenterande och maskininlärningsdriven personalisering inifrån en användares enhet, över flera kanaler, med nästan nolltidsfördröjning.<br>Snabbhet och prestanda - kundinsikter och användarnöjdhet.<br>Med beslutsverktyg på enheter kan ni kompilera viktiga instruktioner för personalisering och experimenterande i aktivitetstyperna A/B Test och Experience Targeting (XT) till optimeringsartefakter: JSON-objekt som läses in till kundenheter via CDN. Och eftersom enhetsbeslut kan kopplas till [!DNL Adobe Experience Cloud]-produkter får [!DNL Target]-användare snabb analys och snabbare upplevelseiterationer.<br>Mer information finns i *[Enhetsbeslut](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md). |

Den här versionen innehåller följande förbättringar, korrigeringar och ändringar:

* Korrigerade ett fel som gjorde att [!UICONTROL Average Lift Confidence Interval] och [!UICONTROL Confidence] inte kunde visas i [!DNL Auto-Target]-rapportering för raden [!UICONTROL Total]. Mätningar som visas korrekt för alla enskilda upplevelser. (TGT-37301)
* Korrigerade ett problem som påverkade [!DNL Adobe Target Premium]-användares [!UICONTROL Auto-Target]-rapportering från och med 15 september 2:30. (PDT) till 6 oktober kl. 9.25. (PDT). När du visar rapporter för påverkad konverteringsstatistik (konfigurerad med antingen alternativet [!UICONTROL Viewed a page] eller [!UICONTROL Clicked on mbox]) rapporteras konverteringsgraden felaktigt. Det finns för närvarande inget känt leveransproblem. Information om hur du synkroniserar om och korrigerar din rapportering finns i [Automatisk målrapportering](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) under *Lösta problem* i *Kända fel och lösta problem*.
* En valbar [!UICONTROL Last Updated At]-kolumn i tabellen [!UICONTROL Catalog Search] och ett [!UICONTROL Last Updated At]-filter har lagts till. Den här förbättringen sparar tid och arbete eftersom du inte behöver öppna varje enskilt objekt för att se när det uppdaterades senast och du kan filtrera efter det datum då objekten uppdaterades senast.

   ![Senast uppdaterad vid illustration av kolumner och filter](/help/r-release-notes/assets/column-and-filter.png)

* Uppdateringar gjordes för att göra målgränssnittet kompatibelt med [riktlinjerna för tillgängligt webbinnehåll](https://www.w3.org/WAI/standards-guidelines/wcag/) 2.0 nivå A och AA (AA). (TGT-34384 &amp; TGT-24679)
* Förbättrad CSP (Content Security Policy). (TGT-37035)
* Introducerade ett sätt att ange klientkoden som en parameter för kunder som använder CNAME. (TNT-38571)
* [!DNL Adobe Experience Cloud] går nu till  [!DNL Experience League]. Under oktober kommer alla versionsinformation, artiklar, videoklipp och självstudiekurser att flyttas från sin nuvarande plats på `docs.adobe.com` till [!DNL Experience League]. Detta säkerställer att allt utbildningsmaterial, självhjälp, hjälpmedel och communityinnehåll hanteras från ett och samma ställe. När den här ändringen inträffar behöver du inte göra något eftersom alla länkar kommer att omdirigeras till [!DNL Experience League]. Vi uppdaterar versionsinformationen när hämtningen börjar.

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| Dokumentationsändringar | Visa detaljerad information om uppdateringar av den här guiden som kanske inte finns med i versionsinformationen.<br>Mer information finns i  [Dokumentationsändringar](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Versionsinformation för tidigare versioner | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium.<br>Mer information finns i  [Versionsinformation för tidigare versioner](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Versionsinformation för Adobe Experience Cloud | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar.<br>Mer information finns i  [versionsinformationen](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html) för Experience Cloud. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Detaljer |
|--- |--- |
| Produktuppdateringslista för Adobe Prioritet | Anmäl dig till produktuppdateringen Adobe Priority:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) om du vill få förhandsmeddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar. |
| Kommande versionsinformation | Mer information om målversionerna för den aktuella månaden, inklusive förhandsversionsinformation, finns på sidan [Versionsinformation för mål - Förhandsversion](/help/r-release-notes/target-release-notes.md). |
