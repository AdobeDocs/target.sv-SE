---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Versionsinformationen innehåller information om funktioner, förbättringar, korrigeringar och kända fel för varje version av Adobe Target Standard och Target Premium.
title: 'Versionsinformation för Adobe Target (aktuell) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 44d9024cb9c1f6a1e28845f9545fed0d56fe176a
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 0%

---


# Versionsinformation om Target (aktuell){#target-release-notes-current}

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje Target Standard och Target Premium-version. Versionsinformation om Target API:er, SDK:er, JavaScript-biblioteket (at.js) och andra plattformsändringar inkluderas också, om tillämpligt.

>[!NOTE]
>
>* **borttagning** av mbox.js: Den 30 augusti 2020 stöder inte Adobe Target längre mbox.js-biblioteket. Efter 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKompetensverktyg: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig av Adobe.
   >
   >
* **Target-meddelanden**: På Target webbplats för information om kommande evenemang, som sessioner med Target SKill Builder, chats för utvecklare, webbinarier och Target Coffee Break. Mer information finns i [Target-meddelanden](/help/r-release-notes/target-announcements.md).


Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

## Target Standard/Premium 20.5.1 (17 juni 2020)

| Funktion/förbättring | Beskrivning |
| --- | --- |
| Stöd för aktiviteter i Analytics for Target (A4T) [!UICONTROL Auto-Allocate] | [!UICONTROL Auto-Allocate] nu stöder [Analytics för Target](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Tack vare den här integreringen kan ni använda den [!UICONTROL Auto-Allocate] flerarmade bankfunktionen för att driva trafik till vinnande upplevelser, samtidigt som ni använder [!UICONTROL Adobe Analytics] målmätvärden och/eller [!UICONTROL Adobe Analytics] rapporterings- och analysfunktioner.<br>Om du redan har [implementerat A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) för användning med A/B Test- och Experience Targeting-aktiviteter är allt klart!<br>Mer information finns i Stöd för [Analytics for Target (A4T) för automatisk fördelning av aktiviteter](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) när *aktiviteter skapas*. |
| [!UICONTROL Publisher] roll | Den nya rollen liknar den aktuella [!UICONTROL Observer] rollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Rollen har dock [!UICONTROL Publisher] ytterligare behörighet att aktivera aktiviteter.<br>Mer information finns i: <ul><li>**Target Standard-användare**: [Ange roller och behörigheter](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) i *Användare*.</li><li>**Användare** av Target Premium: [Steg 6: Ange roller och behörigheter](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) i *Konfigurera företagsbehörigheter*.</li></ul> |
| Stöd för A4T i [!DNL Analysis Workspace]<br>juni 2020 | [!UICONTROL Anaytics for Target] (A4T) stöds nu i [!DNL Analysis Workspace]. Med [!UICONTROL Analytics for Target (A4T) panel] verktyget kan ni analysera era [!DNL Adobe Target] aktiviteter och upplevelser i [!DNL Analysis Workspace].<br>Mer information finns i [Rapporter i Analytics](/help/c-integrating-target-with-mac/a4t/reporting.md) i *A4T-rapportering* och panelen [A4T (](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) Analytics for Target) i *Analytics-handboken*. |

### Förbättringar, korrigeringar och ändringar

* Korrigerade ett problem som gjorde att &quot;besökarmåttet&quot; lagrades i aktivitetens definition i stället för &quot;UniqueVisitors&quot;. (TGT-37098)
* Korrigerade ett fel i [!DNL Target] användargränssnittet som fick den lodräta rullningslisten att inte fungera korrekt på [!UICONTROL Audiences] sidan. (TGT-36968)

## Versioner av typen at.js 1.8.2 och at.js 2.3.1 (15 juni 2020)

Följande förbättringar och korrigeringar har gjorts i biblioteken [!DNL Target] at.js:

| Funktion/förbättring | Beskrivning |
| --- | --- |
| at.js 1.8.2 | Den här versionen av at.js är en underhållsversion och innehåller följande korrigering:<ul><li>Korrigerade ett problem vid användning av CNAME och kantåsidosättning, at.js 1.*x* kan felaktigt skapa serverdomänen, vilket resulterade i att [!DNL Target] begäran misslyckades. (TNT-35064)</li></ul>Mer information finns [i versionsinformationen](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)för at.js. |
| at.js 2.3.1 | Den här versionen av at.js är en underhållsrelease och innehåller följande förbättringar och korrigeringar:<ul><li>Inställningen kan åsidosättas `deviceIdLifetime` via [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). (TNT-36349)</li><li>Korrigerade ett problem vid användning av CNAME och kantåsidosättning, at.js 2.*x* kan felaktigt skapa serverdomänen, vilket resulterade i att [!DNL Target] begäran misslyckades. (TNT-35065)</li><li>Korrigerade ett problem när tillägget v2 och [!DNL Target] tillägget v2 användes och [!DNL Launch][!DNL Adobe Analytics] tillägget [!DNL Launch] fördröjde [!DNL Target][!DNL Analytics] `sendBeacon` anropet. (TNT-36407, TNT-35990, TNT-36000)</li></ul>Mer information finns [i versionsinformationen](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)för at.js. |

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation - Target serversides-API:er](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Versionsinformation om Adobe Target server-side API:er. |
| [Versionsinformation - Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Versionsinformation om Adobe Target Node.js SDK. |
| [Versionsinformation - Target Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Versionsinformation om Adobe Target Java SDK. |
| [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om ändringarna i varje version av JavaScript-biblioteket Adobe Target at.js. |
| [versionsinformation för mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | På den här sidan visas ändringar för varje version av mbox.js.<br>Observera att mbox.js-biblioteket inte längre utvecklas. Alla kunder bör migrera från mbox.js till at.js. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| Dokumentationsändringar | Visa detaljerad information om uppdateringar av den här guiden som kanske inte finns med i versionsinformationen.<br>Mer information finns i [Dokumentationsändringar](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Versionsinformation för tidigare versioner | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium.<br>Mer information finns i [Versionsinformation för tidigare versioner](../r-release-notes/release-notes-for-previous-releases.md). |
| Versionsinformation om Adobe Experience Cloud | Läs den senaste versionsinformationen om Adobe Experience Cloud-lösningarna.<br>Mer information finns i [versionsinformationen](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)för Experience Cloud. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Följande resurser visar vad som kommer i nästa version av Target.

| Resurs | Detaljer |
|--- |--- |
| Produktuppdateringslista för Adobe-prioritet | Om du vill få förhandsmeddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar registrerar du dig för produktuppdateringen Adobe Priority:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Kommande versionsinformation | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation, finns på sidan [Target Release Notes - Förhandsversion](/help/r-release-notes/target-release-notes.md) . |
