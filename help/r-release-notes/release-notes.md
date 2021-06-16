---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den aktuella versionen?
feature: Versionsinformation
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: bdf8fdc0c7d92cb59270518861693ec22eb596f2
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 0%

---

# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-release. Versionsinformation om Target-API:er, SDK:er, JavaScript-biblioteket (at.js) och andra plattformsändringar inkluderas också, i tillämpliga fall.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Migrera till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## Python SDK 1.0.0 (16 juni 2021)

Det nya [!DNL Adobe Target] Python SDK med beslutsfunktioner på enheter är nu tillgängligt. Det senaste tillägget stöder [!DNL Target]-sviten med SDK:er på serversidan. Dessa SDKS hjälper dig att integrera med [!DNL Target] och hjälper dig att få mer tid till värde på det språk du föredrar. Integrationer på serversidan blir ett populärt val eftersom marknaden nu övergår till en cookie-fri värld där förstapartsdata är värdefulla. SDK-målgrupper finns i de populäraste programmeringsspråken på marknaden (Python, Java, JavaScript, C# / .Net).

Mer information finns i [dokumentationen för Python SDK](https://adobetarget-sdks.gitbook.io/docs/sdk-reference-guides/python-sdk) i [handboken för Adobe Target SDK](https://adobetarget-sdks.gitbook.io/docs/).

## Target Standard/Premium 21.5.1 (7 juni 2021)

Den här versionen innehåller följande förbättringar:

| Funktion | Detaljer |
| --- | --- |
| ![Premium ](/help/assets/premium.png) [!DNL Recommendations] [!UICONTROL Catalog Search] badgeAPI | Sök i din [!DNL Recommendations]-produkt och innehållskatalog programmatiskt via API för att identifiera objekt som matchar ett sökvillkor och förenkla katalogadministrationen.<br>**Begränsningar och anteckningar**:<ul><li>Katalogsökning via API stöds inte i miljöer med fler än 2 000 000 objekt.</li><li>Katalogsökresultat via API uppdateras snabbare än katalogsökresultat via användargränssnittet i [!DNL Target]. Katalogsökningen i gränssnittet [!DNL Target] kan ta ytterligare tid att återspegla de senaste resultaten.</li></ul>Mer information finns i [Söka efter entiteter](http://developers.adobetarget.com/api/recommendations/#tag/Searching-Entities) i *[!DNL Adobe Target]API*-handboken.[!DNL Recommendations] |

Den här versionen innehåller följande korrigeringar.

* Ett problem som gjorde att standardarbetsytan ändrades till en annan arbetsyta när sidan [!UICONTROL Audiences] uppdaterades har åtgärdats. (TGT-38871)
* Korrigerade ett fel i [!UICONTROL Administration] > [!UICONTROL Implementation] som ibland orsakade ett felmeddelande med texten &quot;Din globala mbox kanske inte är synkroniserad. Försök spara om den.&quot;

## ![Adobe Experience Platform Web SDK ](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] badgeversion 2.5.0 (1 juni 2021)

Den här versionen av [!DNL Platform Web SDK] har stöd för följande:

| Funktion | Detaljer |
| --- | --- |
| Omdirigeringsstöd med [!UICONTROL Analytics for Target] (A4T) | Platform Web SDK har nu stöd för [!DNL Target]-omdirigeringar när [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md) används.<br>Mer information finns i  [Analytics  [!DNL Target] for implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## at.js version 2.5.0 (13 maj 2021)

Den här versionen av at.js innehåller följande förbättringar och ändringar:

* [Enhetsspecifikt ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) beslutsstöd för at.js.
* [Förhandsgranska ](/help/c-activities/c-activity-qa/activity-qa.md) länkarstöd för Automated Personalization-aktiviteter

Den här versionen tar också bort stöd för Microsoft Internet Explorer 10, Internet Explorer 11 och alla äldre versioner. Microsoft Edge stöds fortfarande i at.js 2.5.0 och senare.

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
