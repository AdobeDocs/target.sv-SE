---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar,aktuella uppdateringar
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
short-description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av  [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: b1fb49d78b3a159c16e8ebb855ff175c26681da6
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard]- och [!DNL Target Premium]-version. Versionsinformation för [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar inkluderas också, om tillämpligt.

(Numren inom parentes är avsedda för intern [!DNL Adobe]-användning.)

## [!DNL Target Standard/Premium] 25.5.2 (8 maj 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* [!DNL Target] användare med [!UICONTROL Product Administrator]- och [!UICONTROL System Administrator]-behörighet kan nu redigera alla inställningar på [!UICONTROL Administration]-sidorna, oavsett deras roll i [!DNL Target]. Användare utan dessa behörigheter har skrivskyddad åtkomst till de här inställningarna. Den här uppdateringen ger striktare åtkomstkontroll över [administrationsinställningarna](/help/main/administrating-target/administrating-target.md). (TGT-48179)
* Korrigerade ett cachelagringsproblem som förhindrade att aktiviteten [Webbplatsinställningar](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings) sparades. (TGT-52213)
* Ett problem har korrigerats där kunderna inte kunde aktivera val efter ID och klass i avsnittet [!UICONTROL Site Preferences] efter att webbplatsen lästs in i VEC. Inställningen [!UICONTROL Site Preferences] återställs automatiskt till inaktiverad även efter att den har aktiverats. (TGT-52207)
* Ett problem har korrigerats där [!UICONTROL Visual Experience Composer] (VEC) inte kunde visa rätt sida när [URL:er för sidleverans](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings) avslutades med ett snedstreck (/). (TGT-52237)
* Ett problem som förhindrade borttagning av anpassade kodändringar när upplevelser ändrades har åtgärdats. (TGT-52240)
* Ett problem har korrigerats där HTML ändringar i VEC överlappade befintliga sidelement. (TGT-52265)
* Ett problem har korrigerats som gjorde att det inte gick att redigera anpassad kod i den uppdaterade VEC-koden eftersom den befintliga anpassade koden inte var synlig i redigeraren. (TGT-52272)
* Korrigerade ett problem som orsakade felmeddelandet&quot;Duplicerade namn är inte tillåtna&quot; när en rekommendationsaktivitet sparades. (TGT-52318)
* Ett problem i den uppdaterade VEC som gjorde att kunderna inte kunde redigera textelement eller ta bort behållarobjekt har åtgärdats. (TGT-52348)
* Ett problem som gjorde att [!DNL Customer Journey Analytics] inte kunde visas korrekt på en aktivitetssida för [!UICONTROL Overview] har korrigerats. (TGT-52359)
* Korrigerade ett problem som förhindrade rapportgrupper från att finnas kvar i [!UICONTROL Automated Personalization] (AP) aktiviteter. (TGT-52368)
* Korrigerade ett problem som förhindrade att aktiviteter som innehöll offertsbeslut sparades. (TGT-52390)
* Ett problem har korrigerats där standarderbjudandet valdes, men annat erbjudandeinnehåll visades i [!UICONTROL Automated Personalization] (AP)- och [!UICONTROL Multivariate Test] (MVT)-aktiviteter. (TGT-52372)
* GET-behörighetslogik för kontroll med OR har korrigerats mellan fullständig organisationsåtkomst och specifik åtkomst för organisation + användare. (TGT-52374)
* Korrigerade ett problem där målgruppsnamn inte visades efter att en målgrupp har valts för [!UICONTROL Managed Content] och [!UICONTROL Reporting Audiences], trots att [!UICONTROL Show Only Selected] var aktiverat. (TGT-52393)

## [!DNL Target Standard/Premium] 25.5.1 (5 maj 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Korrigerade ett problem som hindrade målgruppsförbättringar från att visas för vissa aktiviteter i det uppdaterade användargränssnittet. (TGT-52057)
* Ett problem som förhindrade användning av kombinerade målgrupper i aktiviteter har korrigerats. (TGT-52346)
* Ett problem som gjorde att det inte gick att skapa en ny aktivitet på en arbetsyta som inte är standard med en målgrupp som bara har aktiviteten från samma arbetsyta har åtgärdats. (TGE-52349)
* Korrigerade ett problem som gjorde att målgrupper med endast aktivitet försvann från det uppdaterade användargränssnittet efter att ha skapat och valt en ny målgrupp. (TGT=52091)
* Ett problem som förhindrade användning av dubblettmålgrupper i aktiviteter har korrigerats. (TGT-51200 &amp; TGT-52057)
* Korrigerade ett problem som medförde att målgruppsförbättringar och aktivitetspubliker hämtades i det uppdaterade användargränssnittet. (TGT-52158)
* Korrigerade ett problem som förhindrade att en ny aktivitet skapades på grund av användarindatafel: &quot;icke-standardarbetsyta tillåts inte för den här användaren.&quot; (TGT-52267)
* Korrigerade ett problem som förhindrade att erbjudanden visas i det uppdaterade användargränssnittet för både standardarbetsytor och icke-standardarbetsytor. [!DNL Target] visar nu erbjudanden från båda arbetsytorna. (TGT-52339)
* Ett problem har korrigerats där [!DNL Target] inte varnade kunderna när de redigerade en aktivitet och ändrade ett ändrat webbplatselement. (TGT-52100)
* Ett problem har korrigerats där ett erbjudande med ad hoc-erbjudanden skapade ett nytt erbjudande i stället för att uppdatera det befintliga. (TGT-52135)
* Korrigerat ett problem som orsakade ett ogiltigt nyttolastfel när erbjudanden flyttades till mappar. (TGT-52325)
* Korrigerat ett problem som orsakade ett användarindatafel när erbjudanden flyttades till mappar. (TGT-52296)
* Ett `audienceMetadata`-fält har lagts till för varje aktivitet och det har lästs och uppdaterats när aktiviteten redigeras. (TGT-51004)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Dokumentationsändringar, Versionsinformation om tidigare versioner och Experience Cloud Versionsinformation

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Information |
|--- |--- |
| [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md) | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen. |
| [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium. |
| [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html){target=_blank} | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar. |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Information |
|--- |--- |
| [Adobe Priority-produktuppdatering](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar. |
| [Versionsinformation om mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
