---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL Adobe Target-versionerna.
title: Adobe Target prerelease notes
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a55aeb18e86a4428187faa5ecba6c66d11feda6d
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---


# Versionsinformation för Target (prerelease){#target-release-notes-prerelease}

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 17 juni 2020**

Information om den aktuella versionen finns i [Target Versionsinformation](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

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


## Target Standard/Premium 20.5.1 (17 juni 2020)

| Funktion/förbättring | Beskrivning |
| --- | --- |
| Stöd för aktiviteter i Analytics for Target (A4T) [!UICONTROL Auto-Allocate] | [!UICONTROL Auto-Allocate] nu stöder [Analytics för Target](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Tack vare den här integreringen kan ni använda den [!UICONTROL Auto-Allocate] flerarmade bankfunktionen för att driva trafik till vinnande upplevelser, samtidigt som ni använder [!UICONTROL Adobe Analytics] målmätvärden och/eller [!UICONTROL Adobe Analytics] rapporterings- och analysfunktioner.<br>Om du redan har [implementerat A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) för användning med A/B Test- och Experience Targeting-aktiviteter är allt klart!<br>Mer information finns i Stöd för [Analytics for Target (A4T) för automatisk fördelning av aktiviteter](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) när *aktiviteter skapas*. |
| Svarstoken för trafiktilldelningsmetod för automatiska Target- och automatiserade personaliseringsaktiviteter | Två [svarstokens](/help/administrating-target/response-tokens.md) har lagts till [!UICONTROL Auto-Target] och [!UICONTROL Automated Personalization] aktiviteter för att det ska gå att avgöra om en besökare har fått en viss upplevelse som ett resultat av att han eller hon har tilldelats &quot;kontroll&quot; eller &quot;riktad&quot; trafik.<ul><li>`experience.trafficAllocationId` returnerar 0 om en besökare har fått en upplevelse av att vara i&quot;kontrolltrafik&quot; och 1 om en besökare har fått en upplevelse av den&quot;riktade&quot; trafikfördelningen.</li><li>`experience.trafficAllocationType` returnerar &quot;control&quot; eller &quot;target&quot;.</li></ul>Mer information om kontroll kontra riktad trafik finns i [Välja kontrollen för din automatiska personalisering eller Automatisk Target-aktivitet](/help/c-activities/t-automated-personalization/experience-as-control.md). |
| [!UICONTROL Publisher] roll | Den nya rollen liknar den aktuella [!UICONTROL Observer] rollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Rollen har dock [!UICONTROL Publisher] ytterligare behörighet att aktivera aktiviteter.<br>Mer information finns i: <ul><li>**Target Standard-användare**: [Ange roller och behörigheter](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) i *Användare*.</li><li>**Användare** av Target Premium: [Steg 6: Ange roller och behörigheter](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) i *Konfigurera företagsbehörigheter*.</li></ul> |
| Stöd för A4T i [!DNL Analysis Workspace]<br>juni 2020 | [!UICONTROL Anaytics for Target] (A4T) stöds nu i [!DNL Analysis Workspace]. Med [!UICONTROL Analytics for Target (A4T) panel] verktyget kan ni analysera era [!DNL Adobe Target] aktiviteter och upplevelser i [!DNL Analysis Workspace].<br>Mer information finns i [Rapporter i Analytics](/help/c-integrating-target-with-mac/a4t/reporting.md) i *A4T-rapportering* och panelen [A4T (](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) Analytics for Target) i *Analytics-handboken*. |

### Förbättringar, korrigeringar och ändringar

* Korrigerade ett problem som gjorde att &quot;besökarmåttet&quot; lagrades i aktivitetens definition i stället för &quot;UniqueVisitors&quot;. (TGT-37098)
* Korrigerade ett fel i [!DNL Target] användargränssnittet som fick den lodräta rullningslisten att inte fungera korrekt på [!UICONTROL Audiences] sidan. (TGT-36968)

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
