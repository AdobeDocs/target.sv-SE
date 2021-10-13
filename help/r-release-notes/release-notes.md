---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vilka nya funktioner ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 53a7bd5bb258f2f12f68d3b4cfdfc77d5519c913
workflow-type: tm+mt
source-wordcount: '790'
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

## [!DNL Target Standard/Premium] 21.10.2 (13 oktober 2021)

Följande förbättringar har lagts till när du använder [!DNL Target] [!UICONTROL Audiences] med [!DNL Adobe Experience Platform Web SDK]:

* Varningsikoner, poseringar och meddelanden på olika platser i [!DNL Target]-gränssnittet har lagts till för att ange att målgruppen togs bort från källan och inte längre är tillgänglig för användning i [!DNL Target]-aktiviteter.

   Följande bilder visar några av de platser där ikonerna, poseringarna och meddelandena visas:

   * [!UICONTROL Activity] listsida

      ![Målgruppen togs bort vid källmeddelandet på sidan med aktivitetslistan](assets/deleted-at-source-audiences-list.png)

   * Aktivitet [!UICONTROL Overview] sidor:

      ![Målgruppen togs bort vid källmeddelandet på översiktssidan](assets/deleted-at-source-overview.png)

   * [!UICONTROL Experiences] steg i arbetsflödet för att skapa aktiviteter:

      ![Målgruppen togs bort vid källmeddelandet på  [!UICONTROL Experiences] sidan](assets/deleted-at-source-experiences.png)

   * [!UICONTROL Targeting] steg i arbetsflödet för att skapa aktiviteter:

      ![Målgruppen togs bort vid källmeddelandet på  [!UICONTROL Targeting] sidan](assets/deleted-at-source-targeting.png)

   * [!UICONTROL Goals & Settings] steg i arbetsflödet för att skapa aktiviteter:

      ![Målgruppen togs bort vid källmeddelandet på  [!UICONTROL Goals & Settings] sidan](assets/deleted-at-source-goals-settings.png)

   * Målgruppsförbättringar ([!UICONTROL Replace Audience] i [!UICONTROL Targeting]-steget i arbetsflödet för att skapa aktivitet):

* Om du försöker använda funktionen Kombinera målgrupper och en av målgrupperna togs bort från källan, är [!UICONTROL Save] inaktiverat.

## [!DNL Target Standard/Premium] 21.10.1 (6 oktober 2021)

Den här versionen innehåller följande nya funktioner:

| Funktion | Detaljer |
| --- | --- |
| [!UICONTROL Audiences] Uppdatering av användargränssnittet | Som en del av [!DNL Adobe Target]-teamets pågående arbete med att förbättra användarupplevelsen för [!DNL Target]-användare uppdaterar den här versionen sidorna [!UICONTROL Audiences] och [!UICONTROL Profile Scripts] i [!DNL Target]-gränssnittet. Uppdateringen förenar och standardiserar designmönster som tidigare varit inkonsekventa, samtidigt som nya förbättringar läggs till, till exempel:<ul><li>Möjlighet att markera och ta bort flera målgrupper samtidigt</li><li>En uppdaterad [målgruppsbyggare](/help/c-target/c-audiences/create-audience.md)</li><li>Stöd för uteslutningsregel i [!UICONTROL Audience]-biblioteksregelverktyget</li><li>Ett nytt &quot;Audience Source&quot;-filter som ger snabbare målgruppsidentifiering</li><li>Alternativ för beständig sökning och filtrering av sessioner</li></ul>Mer information finns i [Publiker](/help/c-target/target.md). |
| [!UICONTROL Profile Scripts] Uppdatering av användargränssnittet | Biblioteket [!UICONTROL Profile Scripts] uppdaterades också och innehåller ett uppdaterat gränssnitt samt flera produktivitetsuppdateringar:<ul><li>Möjlighet att markera och ta bort flera profilskript samtidigt</li><li>En ny kodredigerare för profilskript</li><li>Syntaxmarkering och felkontroll inuti kodredigeraren</li><li>Fyll i tokens-parametrar automatiskt (mbox eller profile) via kortkommandon</li></ul>Mer information finns i [Besökarprofiler](/help/c-target/c-visitor-profile/visitor-profile.md). |
| ![Premium ](/help/assets/premium.png) badgeRecommendations Criteria create and edit | Arbetsflödet för att skapa och redigera [!UICONTROL Recommendations Criteria] har förenklats så att det är enklare att välja rätt rekommendationsalgoritm och inställningar för att uppnå dina mål.<br>Mer information finns i  [Skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md). |
| ![Förbättrad Premium ](/help/assets/premium.png) badgeRecommendations lookback window och algorithm refresh rate | Nu kan du köra algoritmerna&quot;Mest visade&quot; och&quot;Mest visade&quot; säljare&quot; med ett sextimmars uppslagsfönster för att fånga det innehåll som är mest aktuellt. När du har valt ett sextimmars uppslag uppdateras dina rekommendationer var 3:e till 6:e timme under dagen.<br>Mer information finns i  [Datakälla ](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) i  *Skapa villkor*. |

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
