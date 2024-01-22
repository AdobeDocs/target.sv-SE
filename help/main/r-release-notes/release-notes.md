---
keywords: versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API och JavaScript-bibliotek.
landing-page-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
short-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 99152f66217f66174e8b6a5a7319f11b22c74b8e
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## Borttagning av iPad och iPhone från Browser-målgruppsattribut (30 april 2024)

| Föråldring | Information |
|--- |--- |
| [!DNL iPad] och [!DNL iPhone] tas bort från [Webbläsarattribut](/help/main/c-target/c-audiences/c-target-rules/browser.md) används när målgrupper skapas.<p>Föråldringsdatum:<P>30 april 2024 | [!DNL Adobe Target] låter dig [mål för någon av flera kategoriattribut](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), inklusive användare som använder en viss [webbläsare](/help/main/c-target/c-audiences/c-target-rules/browser.md) när de besöker din sida.<P><B>Från och med 30 april 2024 tas iPad och iPhone bort från tillgängliga [!UICONTROL Browser] listrutan type när du skapar kategorier för målgrupper.</b><P>Om du har målgrupper som använder iPad eller iPhone med [!UICONTROL Browser] måste du ändra dessa inställningar före 30 april 2024 för att säkerställa att dessa målgrupper fortsätter att fungera som förväntat.<p>Exempel på alternativa inställningar finns i [Borttagning av iPad och iPhone från Browser-målgruppsattribut (30 april 2024)](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation). |

## [!DNL Target] Standard/Premium 24.1.1 (22 januari, 23 och 25 januari 2024)

Den här versionen är schemalagd för följande dagar:

* **22 januari**: Europa, Mellanöstern och Afrika (EMEA)
* **23 januari**: Asien-Stillahavsregionen (APAC)
* **25 januari**: Amerika

Den här versionen innehåller följande förbättringar och korrigeringar:

* [!UICONTROL Analytics for Target] (A4T) aktiviteter med intäktsmålmått visade inte &quot;Intäkt&quot; eftersom kolumnnamnet och intäktsmåttet inte visades i ($)-format vid rapportering. Detta var en kosmetisk fråga som har åtgärdats. (TGT-46995)
* Korrigerade ett problem som gjorde att rapportdatumintervaller inte fungerade korrekt. (TGT-47396)
* Ett problem som orsakade att felaktig status visades på [!UICONTROL All Activities] sidan efter att kunderna aktiverat eller inaktiverat en aktivitet med [!UICONTROL More Actions] -ikon. (TGT-47367)
* Ett problem som orsakade [!UICONTROL Important Attributes] som inte visas för en enskild kund. (TGT-47272)
* Korrigerade ett problem som orsakade att ett meddelande om ogiltig nyttolast visades när en enskild kund försökte aktivera&quot;Kräv autentisering&quot;. (TGT-47195)
* Uppdaterat flera lokaliserade strängar i [!DNL Target] Gränssnitt.

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

## Dokumentationsändringar, versionsinformation för senaste utgåvan och Experience Cloud

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
| [Produktuppdatering Adobe Priority](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar. |
| [Versionsinformation för mål - förhandsversion](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Information om den aktuella månadens Target-utgåvor, inklusive förhandsversionsinformation. |
