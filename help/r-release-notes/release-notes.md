---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 8d252255499dd8ece5e1de1220a97723659a4bf8
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 0%

---

# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om mål-API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## [!DNL Target Standard/Premium] 22.1.2 (26 januari 2022)

| Funktion | Detaljer |
| --- | --- |
| [!DNL Adobe Experience Platform] målgrupper i [!DNL Target] | Nu kan du använda [!DNL Adobe Experience Platform] målgrupper i [!DNL Target]. The [!DNL Target] team, [!DNL Experience Platform] [!DNL Destinations] team och [!DNL Unified Profile Service] Vi är glada över att kunna meddela att det finns en allmän tillgänglighet för användningsexemplen&quot;Anpassa samma sida/nästa sida&quot;.<br>Använda målgrupper skapade i [!DNL Adobe Experience Platform] ge mer omfattande kunddata som leder till mer slagkraftig personalisering. The [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html){target=_blank} (RTCP), inbyggt [!DNL Adobe Experience Platform] hjälper företag att samla in kända och anonyma data från flera olika företagskällor för att skapa kundprofiler som kan användas för att leverera personaliserade kundupplevelser över alla kanaler och enheter i realtid.<br>Mer information finns i [Använda målgrupper från Adobe Experience Platform](/help/c-target/c-audiences/audiences.md#aep) in *Skapa målgrupper*. |
| [!UICONTROL Audiences] Uppdatering av användargränssnittet | Som en del av [!DNL Adobe Target] teamets pågående arbete med att förbättra användarupplevelsen för [!DNL Target] användare, den här versionen uppdaterar [!UICONTROL Audiences] och [!UICONTROL Profile Scripts] sidor på [!DNL Target] Gränssnitt. Uppdateringen förenar och standardiserar designmönster som tidigare varit inkonsekventa, samtidigt som nya förbättringar läggs till, till exempel:<ul><li>Möjlighet att markera och ta bort flera målgrupper samtidigt</li><li>En uppdaterad [målgruppsbyggare](/help/c-target/c-audiences/create-audience.md)</li><li>Stöd för undantagsregel i [!UICONTROL Audience] biblioteksregelbyggaren</li><li>Ett nytt &quot;Audience Source&quot;-filter som ger snabbare målgruppsidentifiering</li><li>Alternativ för beständig sökning och filtrering av sessioner</li><li>Möjlighet att flytta målgrupper mellan arbetsytor för [!DNL Target Premium] kunder.</li></ul>Mer information finns i [Målgrupper](/help/c-target/target.md).<br>**ANMÄRKNING**: Den här funktionen kommer att lanseras för kunder i olika regioner under de kommande sex veckorna. |
| [!UICONTROL Profile Scripts] Uppdatering av användargränssnittet | The [!UICONTROL Profile Scripts] biblioteket uppdaterades också och innehåller ett uppdaterat gränssnitt samt flera produktivitetsuppdateringar:<ul><li>Möjlighet att markera och ta bort flera profilskript samtidigt</li><li>En ny kodredigerare för profilskript</li><li>Syntaxmarkering och felkontroll inuti kodredigeraren</li><li>Fyll i tokens-parametrar automatiskt (mbox eller profile) via kortkommandon</li></ul>Mer information finns i [Besökarprofiler](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**ANMÄRKNING**: Den här funktionen kommer att lanseras för kunder i olika regioner under de kommande sex veckorna. |

## [!DNL Target Standard/Premium] 22.1.1 (12 januari 2022)

Den här versionen innehåller felkorrigeringar och nödvändiga funktioner för framtida integreringar.

## at.js version 2.8.0 (7 januari 2022)

The [!DNL Target] at.js JavaScript-biblioteket samlar nu in telemetridata för funktionsanvändning och prestanda. Personuppgifter samlas inte in. Du kan välja bort den här funktionen genom att ange `telemetryEnabled` till false in `targetGlobalSettings`. Mer information finns i [telemetryEnabled in targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#telemetry).

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| Dokumentationsändringar | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen.<br>Mer information finns i [Dokumentationsändringar](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Versionsinformation för tidigare versioner | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium.<br>Mer information finns i [Versionsinformation för tidigare versioner](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Versionsinformation för Adobe Experience Cloud | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar.<br>Mer information finns i [Versionsinformation för Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html). |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Detaljer |
|--- |--- |
| Produktuppdatering för Adobe Prioritet | Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Kommande versionsinformation | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation, finns i [Versionsinformation för mål - förhandsversion](/help/r-release-notes/target-release-notes.md) sida. |
