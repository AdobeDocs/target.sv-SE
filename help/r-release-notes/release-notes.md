---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Versionsinformationen innehåller information om funktioner, förbättringar, korrigeringar och kända fel för varje utgåva av Adobe Target Standard och Target Premium.
title: 'Versionsinformation om Adobe Target (aktuell) '
feature: release notes
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 0%

---


# Versionsinformation för mål (aktuell){#target-release-notes-current}

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje Target Standard- och Target Premium-version. Versionsinformation om Target-API:er, SDK:er, JavaScript-biblioteket (at.js) och andra plattformsändringar inkluderas också, i tillämpliga fall.

>[!IMPORTANT]
>
>* **mbox.js - utgånget**: 18 januari 2021 kommer Adobe Target inte längre att ha stöd för mbox.js-biblioteket. Efter 18 januari 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor som har Target-aktiviteter igång genom att skicka standardinnehåll. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKomplett Builder: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig från Adobe.
   >
   >
* **Målmeddelanden**: På sidan med målmeddelanden hittar du information om kommande evenemang, bland annat om sessioner i Target SKill Builder, chats för utvecklare, webbinarier och sessioner med Target Coffee Break. Mer information finns i [Målmeddelanden](/help/r-release-notes/target-announcements.md).


Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

## Target Standard/Premium 20.10.1 (27 oktober 2020)

Den här versionen innehåller följande nya funktioner:

| Funktion | Detaljer |
| --- | --- |
| [Enhetsbeslut](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) | Med enhetsbaserad beslutsfattande kan både marknadsförare och produktutvecklare leverera experimenterande och maskininlärningsdriven personalisering inifrån en användares enhet, över flera kanaler, med nästan nolltidsfördröjning.<br>Snabbhet och prestanda - kundinsikter och användarnöjdhet.<br>Med beslutsverktyg på enheter kan ni kompilera viktiga instruktioner för personalisering och experimenterande i aktivitetstyperna A/B Test och Experience Targeting (XT) till optimeringsartefakter: JSON-objekt som läses in till kundenheter via CDN. Och eftersom enhetsspecifika beslut kan kopplas till [!DNL Adobe Experience Cloud] produkter får användarna snabb analys och snabbare upplevelseiterationer [!DNL Target] .<br>Mer information finns i *[Introduktion till enhetsbeslut](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning)* i *Adobe Target SDKs Guide*.<br>**Anmäl dig nu till ett live webbinarium.** Följ Adobe Target produktexperter och diskutera hur rörliga beslut om optimering av kritiska upplevelser på enheter som körs lokalt med nolltidsfördröjning kan öppna dörrar för spännande nya användningsfall samtidigt som webbplatsens prestanda förbättras för dina kunder.<ul><li>10 november 2020</li><li>10.00 PT/12.00 CT/1.00 ET</li><li>[Registrera dig här](https://www.adobeeventsonline.com/Target/2020/OnDeviceDecisions/invite.html)</li></ul> |

Den här versionen innehåller följande förbättringar, korrigeringar och ändringar:

* Korrigerade ett problem som förhindrade [!UICONTROL Average Lift Confidence Interval] och [!UICONTROL Confidence] kunde visas i [!DNL Auto-Target] rapporter för [!UICONTROL Total] raden. Mätningar som visas korrekt för alla enskilda upplevelser. (TGT-37301)
* Korrigerade ett problem som påverkade [!DNL Adobe Target Premium] användarnas [!UICONTROL Auto-Target] rapportering från och med 15 september 2:30. (PDT) till 6 oktober kl. 9.25. (PDT). När du visar rapporter om påverkad konverteringsstatistik (konfigurerad med antingen alternativet &quot;[!UICONTROL Viewed a page]&quot; eller &quot;[!UICONTROL Clicked on mbox]&quot;) rapporteras konverteringsgraden felaktigt. Det finns för närvarande inget känt leveransproblem. Information om hur du synkroniserar om och korrigerar din rapportering finns i [Automatisk målrapportering](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) under *Lösta problem* i *Kända problem och lösta problem*.
* En valbar [!UICONTROL Last Updated At] kolumn i [!UICONTROL Catalog Search] tabellen och ett [!UICONTROL Last Updated At] filter har lagts till. Den här förbättringen sparar tid och arbete eftersom du inte behöver öppna varje enskilt objekt för att se när det uppdaterades senast och du kan filtrera efter det datum då objekten uppdaterades senast.

   ![Senast uppdaterad vid illustration av kolumner och filter](/help/r-release-notes/assets/column-and-filter.png)

* Uppdateringar gjordes för att göra målgränssnittet kompatibelt med [Web Content Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/) 2.0 Level A och AA Success Criteria (WCAG 2.0 AA). (TGT-34384 &amp; TGT-24679)
* Förbättrad CSP (Content Security Policy). (TGT-37035)
* Introducerade ett sätt att ange klientkoden som en parameter för kunder som använder CNAME. (TNT-38571)
* [!DNL Adobe Experience Cloud] går nu till [!DNL Experience League]. Under oktober kommer alla versionsinformation, artiklar, videoklipp och självstudiekurser att flyttas från sin nuvarande plats `docs.adobe.com` till [!DNL Experience League]. Detta säkerställer att allt utbildningsmaterial, självhjälp, hjälpmedel och communityinnehåll hanteras från ett och samma ställe. När den här ändringen inträffar behöver du inte göra något eftersom alla länkar kommer att omdirigeras till [!DNL Experience League]. Vi uppdaterar versionsinformationen när hämtningen börjar.

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| Dokumentationsändringar | Visa detaljerad information om uppdateringar av den här guiden som kanske inte finns med i versionsinformationen.<br>Mer information finns i [Dokumentationsändringar](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Versionsinformation för tidigare versioner | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium.<br>Mer information finns i [Versionsinformation för tidigare versioner](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Versionsinformation för Adobe Experience Cloud | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar.<br>Mer information finns i [versionsinformationen](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)för Experience Cloud. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Detaljer |
|--- |--- |
| Produktuppdateringslista för Adobe Prioritet | Om du vill få förhandsmeddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar registrerar du dig för produktuppdateringen Adobe Priority:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Kommande versionsinformation | Information om målversionerna för den aktuella månaden, inklusive förhandsversionsinformation, finns på sidan [Viktigt om](/help/r-release-notes/target-release-notes.md) mål - Förhandsversion. |
