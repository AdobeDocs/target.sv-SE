---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bdc2f76af2a1f1554556d56a983748aa2c9caf2c
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 14 mars 2025**

>[!NOTE]
>
>Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.3.7 (26 mars 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett problem som blockerade sparande av flersidiga aktiviteter om en sida togs bort efter ändringar har åtgärdats. (TGT-51988)
* Ett fel som uppstod när en aktivitet redigerades: `default message [Invalid optionLocalIds: xx]]` har åtgärdats. (TGT-51985)
* Ett problem där nya ändringar i en aktivitet togs bort när befintliga ändringar lades till har åtgärdats. (TGT-51981)
* Ett problem där felet&quot;Duplicera målgrupper tillåts inte&quot; uppstod när en målgrupp skulle ersättas med [!UICONTROL All visitors]&quot; när aktiviteten skapades eller redigerades. (TGT-51978)
* Ett problem som orsakade ett fel av typen &quot;Ogiltig användarinmatning&quot; när en [!UICONTROL A/B Test]-aktivitet sparades har åtgärdats. (TGT-51976)
* Ett problem som gjorde att beräknade värden inte kunde visas korrekt på sidan [!UICONTROL Goals & Settings] har åtgärdats. (TGT-51975)
* Löste ett problem som förhindrade matchning av `companyName` och `reportSuite` i [!DNL Analytics]-konfigurationen för måttet `pageviews`. (TGT-51965)
* Löste ett problem där växling av upplevelser i en aktivitet tog bort ändringar. (TGT-51945)
* Ett problem har korrigerats där [!UICONTROL ClickTrack] väljare togs bort när en sidpublik togs bort. (TGT-51935)
* Ett problem som gjorde en aktivitet icke-redigerbar efter att sidan [!UICONTROL Overview] öppnades har åtgärdats. (TGT-51931)
* Ett problem som orsakade ett `[Unused optionLocalIds: 0]]`-fel när aktiviteten skapades har åtgärdats. (TGT-51920)
* Ett problem där vissa ändringar inte översattes korrekt efter att textformatsändringar hade tagits bort har åtgärdats. (TGT-51876)
* Ett problem som hindrade målgrupper från att uppdatera korrekt i [!UICONTROL Form-Based Experience Composer] har åtgärdats. (TGT-51845)
* Ett problem har korrigerats där URL:en i [!UICONTROL Visual Experience Composer] inte uppdaterades korrekt under aktivitetsnavigeringen. (TGT-51832)
* Ett problem som gjorde att erbjudanden inte kunde visas i användargränssnittet för [!UICONTROL Offers] har åtgärdats, trots att de visades korrekt när en aktivitet skapades och erbjudanden lades till. (TGT-51805)
* Ett problem där vissa aktiviteter saknade en reservskärm för att visa standardinnehåll när det inte gick att leverera anpassat eller målinriktat innehåll har åtgärdats. (TGT-51638)
* Ett problem som gjorde att direkterbjudanden och vissa mappar inte kunde visas korrekt i användargränssnittet för [!UICONTROL Offers] har åtgärdats. (TGT-51628)
* Ett problem som gjorde att vissa URL-strängar och goURL:er inte kunde lokaliseras korrekt har åtgärdats. (TGT-35741)
* Ett problem som gjorde att roller ([!UICONTROL Approver], [!UICONTROL Editor] och [!UICONTROL Observer]) inte kunde lokaliseras korrekt i användargränssnittet för [!DNL Target] har åtgärdats. (TGT-29925)

## [!DNL Target Standard/Premium] 25.3.6 (14 mars 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Löste ett fel om ogiltig användarinmatning i [!UICONTROL Visual Experience Composer] (VEC)-aktiviteter med [!UICONTROL Click Tracking] aktiverat när samma [!UICONTROL ClickTrack]-väljare används flera gånger. (TGT-51921)
* Felet &quot;Ogiltig användarinmatning&quot; i VEC-aktiviteter med delade platser (till exempel HEAD-väljare) och identiska erbjudanden har åtgärdats. (TGT-51879)
* Ett problem som orsakade att upplevelseändringar delades mellan olika målgrupper har åtgärdats. (TGT-51815)
* Löste valideringsfel när aktiviteter skapades på grund av konflikter mellan segment-ID. Felen uppstod när [!DNL Target] upptäckte befintliga aktiviteter med anonyma segment. (TGT-51784)
* Ett problem som förhindrar [!DNL Target] från att spara aktiviteter med undantagsregler i en målgrupp har åtgärdats. (TGT-51581)
* Ett problem som gjorde att kunder inte kunde skapa, ta bort eller flytta mappar utan åtkomst till standardarbetsytan har åtgärdats. (TGT-51499)
* Ett problem som medförde att GET-begäranden misslyckades när [!DNL Analytics]-mätningslistan hämtades har åtgärdats. (TGT-51106)

## [!DNL Target Standard/Premium] 25.3.5 (11 mars 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett problem som hindrade användare från att ändra erbjudanden på panelen [!UICONTROL Modifications] har åtgärdats. (TGT-51800)
* Ett problem där funktionsmakron visades felaktigt i den vänstra panelen för upplevelser och målgrupper, inklusive i [!UICONTROL ClickTrack]-läge, har åtgärdats. (TGT-51895)
* Ett problem där [!UICONTROL ClickTrack] väljare inte tillämpades på rätt målgruppssida har åtgärdats. (TGT-51871)

## [!DNL Target Standard/Premium] 25.3.4 (7 mars 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett problem har korrigerats där målgrupper som bara har aktiviteten inte var synliga på panelen [!UICONTROL Audiences], vilket förhindrar redigering eller återanvändning. (TGT-51860)
* Ett problem som blockerade [!DNL Target Standard]-kunder från att skapa aktiviteter med hjälp av [!UICONTROL Analytics for Target] (A4T)-rapportering har åtgärdats. (TGT-51854)
* Korrigerade ett problem som uteslöt lokala ID-räknare från nyttolasten under gruppskapnings- och redigeringsåtgärder. (TGT-51867)

## [!DNL Target Standard/Premium] 25.3.2 (6 mars 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett problem har korrigerats där kopiering av en aktivitet med en målgrupp som endast är aktiv inte kunde skapa en ny aktivitet. Den ursprungliga aktivitetens målgrupp användes av misstag. (TGT-51855)
* Korrigerade ett problem som förhindrade redigering av [!UICONTROL Experience Targeting] (XT)-aktiviteter med enbart aktivitet. (TGT-51846)
* Ett problem har korrigerats där [!UICONTROL Visual Experience Composer] (VEC) inte kunde använda ändringar på en upplevelse korrekt vid den första redigeringen. (TGT-51843)
* Ett problem som utlöste ett ID-fel när du klickade på vissa element i VEC har korrigerats. (TGT-51814)
* Felhanteringen i VEC uppdaterades när aktiviteten skapades. (TGT-51759)
* Korrigerade ett problem där en vy som saknas på panelen [!UICONTROL Modifications] orsakade ett fel av typen ogiltig användarinmatning när aktiviteten sparades. (TGT-51827)
* Ett problem som gjorde att rekommendationskriterier inte kunde skapas har korrigerats. (TGT-51834)
* Ett bekräftelsemeddelande lades till innan omdirigering till en annan URL. (TGT-51703)
* Problem med GraphQL integrationstester i erbjudanden och mappar har åtgärdats. (TGT-51839)

## [!DNL Target Standard/Premium] 25.3.1 (3 mars 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* En kombinerad målgrupp kan innehålla undergrupper, där var och en innehåller flera målgrupper. Den här versionen åtgärdade ett problem som förhindrade att undergrupper kunde visas i dialogrutan [!UICONTROL Rules]. (TGT-51813)
* Ett problem där vissa upplevelsemålgrupper ersattes med [!UICONTROL All Visitors] när äldre aktiviteter öppnades har åtgärdats. (TGT-51812)
* Löste ett problem som förhindrade redigering av aktiviteter med enbart aktivitetsgrupper. (TGT-51807)
* Ett problem som förhindrade redigering av sidhuvudets ändringar i det uppdaterade [!DNL Target]-gränssnittet har åtgärdats. (TGT-51797)
* Ett null-fel som uppstod när en upplevelse skulle dupliceras, en annan upplevelse tas bort och sedan försöker spara aktiviteten har åtgärdats. (TGT-51796)
* Ett problem som förhindrade att regler för målgruppsundantag visades i målgruppens informationspanel under [!UICONTROL Targeting]-steget för att skapa aktiviteter har åtgärdats. (TGT-51579)
* Uppdaterade felmeddelanden på koreanska. (TGT-51701 &amp; TGT-51699)

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Adobe Priority Product Update] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
