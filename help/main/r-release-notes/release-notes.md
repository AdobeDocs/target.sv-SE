---
keywords: Versionsinformation;nya funktioner;utgåvor;uppdateringar;uppdatering;release;förbättring;förbättringar;korrigeringar;felkorrigeringar;uppdateringar
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target], inklusive SDK, API:er och JavaScript-bibliotek.
landing-page-description: Lär dig om de nya funktionerna, förbättringarna och korrigeringarna i den aktuella versionen av [!DNL Adobe Target].
title: Vad ingår i den aktuella versionen?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 894f0d70c3f6575b21026d326562e108dc8670c8
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 1%

---

# [!DNL Target] versionsinformation (aktuell)

Versionsinformationen innehåller information om funktioner, förbättringar och korrigeringar för varje [!DNL Adobe Target Standard] och [!DNL Target Premium] release. Versionsinformation om [!DNL Target] API:er, SDK:er, [!DNL Adobe Experience Platform Web SDK], at.js och andra plattformsändringar ingår också, i tillämpliga fall.

(Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.)

## at.js version 2.10.1 (2 februari 2023)

* Korrigerade ett fel där aktiviteter som innehåller målgruppsregler som innehåller parametrar med punkter i namnen inte returnerade den förväntade upplevelsen för enhetsbeslut.
* Korrigerade ett fel i at.js 2.6.0 där at.js utlöste ett leveransanrop, även när `mboxDisable` har aktiverats.

Mer information om alla at.js-versioner finns i [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## [!DNL Target] Standard/Premium 22.13.3 (25-26 januari 2023)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **25 januari**: Europa, Mellanöstern och Afrika (EMEA)
* **25 januari**: Asien-Stillahavsområdet (APAC)
* **26 januari**: Amerika

Den här versionen innehåller följande nya funktioner, förbättringar och korrigeringar:

| Funktion | Detaljer |
| --- | --- |
| [JSON-erbjudande](/help/main/c-experiences/c-manage-content/create-json-offer.md) stöd i Automated Personalization (AP) | Utökat stöd för JSON-erbjudanden i [!UICONTROL Automated Personalization] (AP) med formulärbaserad Experience Composer. (TGT-41460) |
| [AEM upplevelsefragment](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | Lagt till möjlighet att skilja mellan [!DNL Adobe Experience Manager] fragmenttyper (AEM XF) som exporteras till [!DNL Target]. I stället för alternativet Experience Fragment [!DNL Target] kan du nu filtrera och söka efter &quot;HTML XF&quot; och &quot;JSON XF&quot;. (TGT-44132) |

* Ett problem som orsakade felet 500 i [!UICONTROL A/B Test] och [!UICONTROL Experience Targeting] (XT) aktiviteter som innehåller rekommendationer. Problemet uppstod när [!DNL Target] det gick inte att ta bort villkorsobjekt från [!DNL Target] Användargränssnitt och [!DNL Recommendations] som inte längre används. (TGT-44383)
* Platsen har tagits bort från erbjudandets namn i [!UICONTROL Offer Level] rapport för [!UICONTROL Automated Personalization] verksamhet. Den här ändringen gör rapporten mer läsbar. (TGT-44294)
* Alternativen för 45-dagars och 90-dagars kalender har tagits bort från åtkomstpunkten och [!UICONTROL Auto-Target] [!UICONTROL Personalization Insights] och [!UICONTROL Important Attributes] rapporter i [!DNL Target] Gränssnitt. På grund av användningsmönster och för att förbättra prestanda har datumintervallen tagits bort. Gränssnittet har uppdaterats för att återspegla de aktuella tillåtna intervallen: 15, 30 och 60 dagar. (TGT-39357)
* Otillåten möjlighet att ändra [!UICONTROL Same as Optimization Goal] på [!UICONTROL Goals & Settings] sida efter att aktiviteten är aktiv. (TGT-43923)
* Ett problem som orsakade problem med standardarbetsytan i [!DNL Target] backend när du uppgraderar från [!DNL Target Standard] till [!DNL Target Premium]. (TGT-44081 &amp; TGT-44306)
* Har gjort en ändring som tillåter [!DNL Analytics] rapportsviter som innehåller ett punkttecken &quot;.&quot; i de namn som ska användas i [!DNL Target] Gränssnitt att skapa [!DNL Analytics] klassificeringsfeeds.
* Länken på [!UICONTROL Implementation] sida ([!UICONTROL Administration] > [!UICONTROL Implementation]) för&quot;Implementeringsmetoder med On-Device Decisioning&quot; så att de pekar på sidan som förklarar hur du använder enhetsbeslut för alla SDK:er som stöds: Node.js, Java, .NET och Python. Mer information finns i [Komma igång med mål-SDK:er](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* Ett problem som orsakade filöverföringsproblem vid användning har korrigerats [!DNL Scene7] och [!DNL Target].
* Förbättrad tillgänglighet för [!DNL Target] Användargränssnitt för personer med funktionshinder genom att använda resultat från en intern användarvänlighetsrevision. Dessa tillgänglighetsförbättringar inkluderar åtkomst till funktioner som tidigare inte var tillgängliga via tangentbordet, alt-text-förbättringar, möjlighet att zooma delar av användargränssnittet så att de blir mer användbara, förbättrat tangentbordsfokus med mera.   (TGT-42759)
* Utför olika lokaliseringsåtgärder i hela [!DNL Target] Gränssnitt.

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
