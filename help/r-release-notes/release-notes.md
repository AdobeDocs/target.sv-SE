---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vilka nya funktioner ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 89b995f20491fe0a51c91f8a1fe7e6b1ccc7f974
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 0%

---

# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om mål-API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: 31 mars 2021 [!DNL Adobe Target] stöder inte längre mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor som har [!DNL Target] aktiviteter som körs genom att visa standardinnehåll.
>
>Migrera till den senaste versionen av den nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## at.js version 2.7.0 (28 oktober 2021)

Den här versionen innehåller följande förbättringar:

* Stöd för [Webbkomponenter](https://developer.mozilla.org/en-US/docs/Web/Web_Components). Den här versionen av at.js krävs för att skapa och testa personaliserade upplevelser och erbjudanden på anpassade element och på element inuti anpassade element. Den här funktionen ingår i [!DNL Target Standard/Premium] 21.10.5-utgåvan.

## [!DNL Target Standard/Premium] 21.10.5 (28 oktober 2021)

Den här underhållsversionen innehåller följande förbättringar:

| Funktion | Detaljer |
| --- | --- |
| [!UICONTROL Visual Experience Composer] (VEC) | Stöd för [Webbkomponenter](https://developer.mozilla.org/en-US/docs/Web/Web_Components). Personaliserade upplevelser och erbjudanden kan skapas och testas utifrån anpassade element och på element inuti anpassade element.<br>Mer information finns i [Alternativ för Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#custom). |

## [!DNL Target Standard/Premium] 21.10.4 (21 oktober 2021)

Den här underhållsversionen innehåller följande förbättringar:

| Funktion | Detaljer |
| --- | --- |
| Cart-baserad Recommendations | En ny familj algoritmer har lagts till för att leverera rekommendationer baserat på innehållet i besökarens kundvagn.<br>Mer information finns i &quot;Cart-Based&quot; (Kundvagnsbaserad) i [Skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md) och&quot;Vysidor för kundvagn/utcheckning&quot; och&quot;Uteslut artiklar som redan finns i kundvagnen&quot; i [Planera och implementera Recommendations](/help/c-recommendations/plan-implement.md). |

## [!DNL Target Standard/Premium] 21.10.3 (19 oktober 2021)

Den här underhållsversionen innehåller följande förbättringar, korrigeringar och ändringar:

* Korrigerade problem som hindrade kunderna från att öppna [!UICONTROL A4T] panel i [!DNL Analysis Workspace] genom att klicka på [!UICONTROL View in Analytics] knapp in [!DNL Target] aktivitetsrapportering. (TGT-42099, TGT-42100)
* Ett problem som orsakade [!UICONTROL Edit Design] knapp som inte visas vid redigering [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] (XT) med [!UICONTROL Form-Based Experience Composer]. (TGT-41980)
* Ett problem som förhindrade [!UICONTROL Compatible] kryssruta från visa i villkorsval när du skapar en ny [!UICONTROL Recommendations] aktivitet. (TGT-42053)
* Korrigerade ett felaktigt felmeddelande som visades när det inte gick att markera [!DNL Analytics] som rapportkälla (A4T) på grund av brist på [!DNL Analytics] behörigheter. (TGT-41954)
* Flera tillgänglighetskorrigeringar har implementerats för att förbättra tangentbordsnavigeringen i [!DNL Target] Gränssnitt.

## [!DNL Target Standard/Premium] 21.10.2 (13 oktober 2021)

Följande förbättringar har lagts till när du använder [!DNL Target] [!UICONTROL Audiences] med [!DNL Adobe Experience Platform Web SDK]:

* Lagt till varningsikoner, poseringar och meddelanden på olika platser i [!DNL Target] Gränssnitt som anger att målgruppen togs bort vid källan och inte längre är tillgänglig för användning i [!DNL Target] verksamhet.

   Följande bilder visar några av de platser där ikonerna, poseringarna och meddelandena visas:

   * [!UICONTROL Activity] listsida

      ![Målgruppen togs bort vid källmeddelandet på sidan med aktivitetslistan](assets/deleted-at-source-audiences-list.png)

   * Aktivitet [!UICONTROL Overview] sidor:

      ![Målgruppen togs bort vid källmeddelandet på översiktssidan](assets/deleted-at-source-overview.png)

   * [!UICONTROL Experiences] steg i arbetsflödet för att skapa aktiviteter:

      ![Målgruppen togs bort i källmeddelandet den [!UICONTROL Experiences] page](assets/deleted-at-source-experiences.png)

   * [!UICONTROL Targeting] steg i arbetsflödet för att skapa aktiviteter:

      ![Målgruppen togs bort i källmeddelandet den [!UICONTROL Targeting] page](assets/deleted-at-source-targeting.png)

   * [!UICONTROL Goals & Settings] steg i arbetsflödet för att skapa aktiviteter:

      ![Målgruppen togs bort vid källmeddelandet på [!UICONTROL Goals & Settings] page](assets/deleted-at-source-goals-settings.png)

   * Målgruppsförbättringar ([!UICONTROL Replace Audience] på [!UICONTROL Targeting] steg i arbetsflödet för att skapa aktivitet):

* Om du försöker använda funktionen Kombinera målgrupper och en av målgrupperna togs bort vid källan, [!UICONTROL Save] är inaktiverat.

## [!DNL Target Standard/Premium] 21.10.1 (6 oktober 2021)

Den här versionen innehåller följande nya funktioner:

| Funktion | Detaljer |
| --- | --- |
| [!UICONTROL Audiences] Uppdatering av användargränssnittet | Som en del av [!DNL Adobe Target] teamets pågående arbete med att förbättra användarupplevelsen för [!DNL Target] användare, den här versionen uppdaterar [!UICONTROL Audiences] och [!UICONTROL Profile Scripts] sidor på [!DNL Target] Gränssnitt. Uppdateringen förenar och standardiserar designmönster som tidigare varit inkonsekventa, samtidigt som nya förbättringar läggs till, till exempel:<ul><li>Möjlighet att markera och ta bort flera målgrupper samtidigt</li><li>En uppdaterad [målgruppsbyggare](/help/c-target/c-audiences/create-audience.md)</li><li>Stöd för undantagsregel i [!UICONTROL Audience] biblioteksregelbyggaren</li><li>Ett nytt &quot;Audience Source&quot;-filter som ger snabbare målgruppsidentifiering</li><li>Alternativ för beständig sökning och filtrering av sessioner</li></ul>Mer information finns i [Målgrupper](/help/c-target/target.md).<br>**ANMÄRKNING**: Den nya [!UICONTROL Audiences] Gränssnittet är endast tillgängligt för utvalda kunder. Uppdateringen kommer gradvis att lanseras för alla kunder från och med januari 2022. |
| [!UICONTROL Profile Scripts] Uppdatering av användargränssnittet | The [!UICONTROL Profile Scripts] biblioteket uppdaterades också och innehåller ett uppdaterat gränssnitt samt flera produktivitetsuppdateringar:<ul><li>Möjlighet att markera och ta bort flera profilskript samtidigt</li><li>En ny kodredigerare för profilskript</li><li>Syntaxmarkering och felkontroll inuti kodredigeraren</li><li>Fyll i tokens-parametrar automatiskt (mbox eller profile) via kortkommandon</li></ul>Mer information finns i [Besökarprofiler](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**ANMÄRKNING**: Den nya [!UICONTROL Profile Scripts] Gränssnittet är endast tillgängligt för utvalda kunder. Uppdateringen kommer gradvis att lanseras för alla kunder från och med januari 2022. |
| ![Premium-märke](/help/assets/premium.png) Skapa och redigera Recommendations-kriterier | The [!UICONTROL Recommendations Criteria] arbetsflödet för att skapa och redigera har effektiviserats för att förenkla valet av rätt rekommendationsalgoritm och inställningar för att uppnå dina mål.<br>Mer information finns i [Skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md). |
| ![Premium-märke](/help/assets/premium.png) Förbättrad uppdateringsfrekvens för Recommendations-fönster och algoritm | Nu kan du köra algoritmerna&quot;Mest visade&quot; och&quot;Mest visade&quot; säljare&quot; med ett sextimmars uppslagsfönster för att fånga det innehåll som är mest aktuellt. När du har valt ett sextimmars uppslag uppdateras dina rekommendationer var 3:e till 6:e timme under dagen.<br>Mer information finns i [Datakälla](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) in *Skapa villkor*. |

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
