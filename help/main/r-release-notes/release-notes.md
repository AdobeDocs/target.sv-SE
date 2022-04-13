---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: a03975f8f14db3cb8be0850130aab8d34c4c7fc0
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 0%

---

# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## Target Platform-release (13 april 2022)

Den här versionen innehåller följande uppdatering:

* Ett problem har korrigerats som säkerställer att den sista oktetten med IP-adresser döljs korrekt när de hämtas med profilskript. (TNT-44076)

## [!DNL Target Standard/Premium] 22.3.1 (stegvis frisättning, datum som ska fastställas)

Den här versionen innehåller följande ändringar och förbättringar:

* Korrigerade ett problem som fick redigeringar av profilskript att återgå till det ursprungliga oredigerade skriptet efter att skriptet redigerats, aktiverats och sedan inaktiverats. Profilskriptet förblir nu redigerat. (TGT-43249)
* Ett problem som orsakade följande felmeddelande i [!DNL Target] Gränssnitt när en målgrupp som används i en aktivitet med statusen&quot;utkast&quot; flyttas: &quot;Vi kan inte slutföra din begäran. Kontakta Adobe kundtjänst om problemet kvarstår.&quot; (TGT-43212)
* Ett problem som orsakade [!UICONTROL Include] och [!UICONTROL Exclude] alternativ som ska inaktiveras för kombinerade målgrupper när en aktivitet redigeras. (TGT-43422)
* Ett problem som gjorde att vissa kunder inte kunde se listan över tillgängliga målgrupper när en aktivitet redigerades har åtgärdats. (TGT-43404)
* Ett problem som gjorde att vissa kunder inte kunde ta bort en IP-adress från mappen har åtgärdats[!UICONTROL IPs to exclude from [!DNL Target] reporting data]&quot; i [!UICONTROL Administration] > [!UICONTROL Reporting]. (TGT-43384)
* Korrigerade ett problem som förhindrade användning av negativa tal i målgruppskriteriet som kontrollerar att variabeln är &quot;större än&quot;, &quot;större än eller lika med&quot;, &quot;mindre än&quot; eller &quot;mindre än eller lika med&quot;. (TGT-43367)
* Ett problem som gjorde att kunderna inte kunde se [!UICONTROL Audience Details] när ni skapar kombinerade målgrupper. (TGT-43303)
* Ett problem som orsakade [!DNL Target] Gränssnitt eller nytt [!UICONTROL Audiences] för vissa kunder. (TGT-42590 &amp; TGT-43273)

## [!DNL Target] Plattformsrelease (30 mars)

Den här versionen innehåller följande förbättringar:

* Klickspårsmått inkluderar analysnyttolast i förfrågningar från leverans-API för aktiviteter som använder Analytics som rapportkälla (A4T) och processhändelser på klientsidan. (TNT-43073)

## [!DNL Target Standard] Målgrupper uppdateras (28 mars)

Den här versionen innehåller följande uppdatering:

* Den nya [!UICONTROL Audiences] Gränssnittet aktiveras för alla [!DNL Target Standard] kunder.

## Programfix för kundkonstruktion för Standard/Premium (22 mars 2022)

Den här underhållsversionen innehåller följande förbättringar:

* Tillagda funktioner som ska returneras [!DNL Analytics] nyttolastdata för `prefetch` vyer och `pageLoad` klicka på mätvärden när du använder [!UICONTROL Delivery API] med aktiviteter som använder [!UICONTROL Analytics as the reporting source] (A4T). (TNT-43198)
* Robotfiltreringslistan för användaragenter har uppdaterats så att en webbläsartyp som används ofta i Japan tillåts. (TNT-43867)

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

Förutom anteckningarna för varje release finns det ytterligare information i följande resurser:

| Resurs | Detaljer |
|--- |--- |
| Dokumentationsändringar | Visa detaljerad information om uppdateringar av den här guiden som inte ingår i versionsinformationen.<br>Mer information finns i [Dokumentationsändringar](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Versionsinformation för tidigare versioner | Visa information om nya funktioner och förbättringar i tidigare versioner av Target Standard och Target Premium.<br>Mer information finns i [Versionsinformation för tidigare versioner](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Versionsinformation för Adobe Experience Cloud | Läs den senaste versionsinformationen om Adobe Experience Cloud lösningar.<br>Mer information finns i [Versionsinformation för Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html). |

## Förhandsversionsinformation {#section_5D588F0415A2435B851A4D0113ACA3A0}

Med följande resurser kan du se vad som kommer i nästa Target-version.

| Resurs | Detaljer |
|--- |--- |
| Produktuppdatering för Adobe Prioritet | Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Kommande versionsinformation | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation, finns i [Versionsinformation för mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md) sida. |
