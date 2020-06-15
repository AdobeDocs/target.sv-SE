---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Versionsinformation som innehåller information om funktioner, förbättringar och korrigeringar för de senaste eller kommande DNL-versionerna av Adobe Target.
title: Adobe Target prerelease notes
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 8ef5b9c09cc016aad08c75d62f361b22630a7a56
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 0%

---


# Versionsinformation för mål (prerelease){#target-release-notes-prerelease}

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 15 juni 2020**

Information om den aktuella versionen finns i [Versionsinformation](release-notes.md)för mål. Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Numren inom parentes är avsedda för intern [!DNL Adobe] användning.

>[!NOTE]
>
>* **borttagning** av mbox.js: 30 augusti 2020 kommer Adobe Target inte längre att ha stöd för mbox.js-biblioteket. Efter 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKompetensverktyg: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
   >
   >   
   Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig av Adobe.
   >
   >
* **Målmeddelanden**: På sidan med målmeddelanden hittar du information om kommande evenemang, bland annat om sessioner i Target SKill Builder, chats för utvecklare, webbinarier och sessioner med Target Coffee Break. Mer information finns i [Målmeddelanden](/help/r-release-notes/target-announcements.md).


## Versioner av typen at.js 1.8.2 och at.js 2.3.1 (15 juni 2020)

Följande förbättringar och korrigeringar har gjorts i biblioteken [!DNL Target] at.js:

### at.js 1.8.2

* Korrigerade ett problem vid användning av CNAME och kantåsidosättning, at.js 1.*x* kan felaktigt skapa serverdomänen, vilket resulterade i att [!DNL Target] begäran misslyckades. (TNT-35064)

### at.js 2.3.1

* Inställningen kan åsidosättas `deviceIdLifetime` via [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). (TNT-36349)
* Korrigerade ett problem vid användning av CNAME och kantåsidosättning, at.js 2.*x* kan felaktigt skapa serverdomänen, vilket resulterade i att [!DNL Target] begäran misslyckades. (TNT-35065)
* Korrigerade ett problem när tillägget v2 och [!DNL Target] tillägget v2 användes och [!DNL Launch][!DNL Adobe Analytics] tillägget [!DNL Launch] fördröjde [!DNL Target][!DNL Analytics] `sendBeacon` anropet. (TNT-36407, TNT-35990, TNT-36000)

## Target Standard/Premium 20.5.1 (17 juni 2020)

| Funktion/förbättring | Beskrivning |
| --- | --- |
| Analyser för målstöd (A4T) för automatisk allokering av aktiviteter | I juniversionen har autofördelningstester stöd för [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md). Tack vare den här integreringen kan ni använda Auto-Allocates multiväpnade bandit-funktion för att dirigera trafik till vinnande upplevelser, samtidigt som ni använder Adobe Analytics-målstatistik och/eller Adobe Analytics-rapporter och analysfunktioner. Om du redan har [implementerat A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) för användning med A/B Test- och Experience Targeting-aktiviteter är allt klart! |
| Utgivarroll | Den nya rollen liknar den nuvarande observationsrollen (kan visa aktiviteter, men kan inte skapa eller redigera dem). Utgivarrollen har dock ytterligare behörighet att aktivera aktiviteter. |
| Stöd för A4T i [!DNL Analysis Workspace]<br>juni 2020 | [!UICONTROL Anaytics for Target] (A4T) stöds nu i [!DNL Analysis Workspace]. Med [!UICONTROL Analytics for Target (A4T) panel] verktyget kan ni analysera era [!DNL Adobe Target] aktiviteter och upplevelser i [!DNL Analysis Workspace].<br>Mer information finns i [Analytics for Target (A4T)-panelen](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) i *Analytics Tools Guide*. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få förhandsmeddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
