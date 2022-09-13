---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 3d8da94a52046e70a89dc24d7923f743bee5c458
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 0%

---

# Versionsinformation för mål (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## [!DNL Target] Standard/Premium 22.9.1 (version 13-15 september 2022)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **13 september**: Europa, Mellanöstern och Afrika (EMEA)
* **14 september**: Amerika
* **15 september**: Asien-Stillahavsområdet (APAC)

Den här versionen innehåller följande förbättringar och korrigeringar:

* Lagt till en [!UICONTROL Cross-Domain] vid nedladdning på .js 2.10.0 (och senare) för att tillåta eller inaktivera inställning av cookies från tredje part. (TGT-43674)
* Uppdaterade meddelanden i [!DNL Target] Gränssnitt för att informera kunder om importen [!DNL Recommendations] feeds misslyckas. (TGT-35811)
* Korrigerade ett problem som orsakade [!UICONTROL Decision Offers] inte fungerar som det ska i [!UICONTROL Visual Experience Composer] (VEC). (TGT-43866)
* Ett problem som orsakade att ett felmeddelande visades när användaren valde [!UICONTROL Clicked an Element] konverteringsmål när ett [!UICONTROL Multivariate Testing] (MVT) aktivitet. (TGT-43842)
* Ett problem som förhindrade [!UICONTROL Impressions] kolumn från visa i den hämtade CSV-rapportfilen för [!UICONTROL Automated Personalization] (AP) aktiviteter. (TGT-43780)
* Ett problem som hindrade kunder från att redigera HTML/JSON-erbjudanden efter att ha duplicerat upplevelser när de använde [!UICONTROL Form-Based Experience Composer]. (TGT-43633)
* Ett problem som hindrade kunder från att kopiera en [!UICONTROL A/B Test] från en icke-standardarbetsyta till en annan icke-standardarbetsyta. (TGT-41910)
* Ett problem har korrigerats för att säkerställa att kunderna kan visa användning av [!DNL Recommendations] objekt (design, villkor, samlingar o.s.v.) i [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] (XT) aktiviteter som innehåller rekommendationer och även tar bort kriterieobjekt som inte längre används från [!DNL Target] Användargränssnitt och [!DNL Recommendations] serverdel. (TGT-42331)
* Ett problem som orsakade att en timeout-varning för nätverk visades i [!DNL Target] Gränssnitt vid hämtning av parametrar. (TGT-43737)
* Uppdaterat gränssnitt som ser till att vissa dra och släpp-åtgärder är tillgängliga via tangentbordet. (TGT-42969)
* Uppdaterat användargränssnitt för att säkerställa att textinställningarna är korrekt lokaliserade.

## at.js version 2.10.0 (13 september 2022)

* Lagt till en [!UICONTROL Cross-Domain] vid nedladdning på .js 2.10.0 (och senare) för att tillåta eller inaktivera inställning av cookies från tredje part. (TGT-43674)

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

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
