---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: df00a36ea3440ebd959351fcfc6a24f6bd9fe8b8
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 6 januari 2022**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

>[!IMPORTANT]
>
>**mbox.js end-of-life**: 31 mars 2021 [!DNL Adobe Target] stöder inte längre mbox.js-biblioteket. Efter den 31 mars 2021 misslyckas alla anrop från mbox.js på ett bra sätt och påverkar de sidor som har [!DNL Target] aktiviteter som körs genom att visa standardinnehåll.
>
>Om du vill undvika eventuella problem med dina webbplatser migrerar du till den senaste versionen av den nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 22.1.1 (6 januari 2022)

Den här versionen innehåller följande nya funktion:

| Funktion | Detaljer |
| --- | --- |
| Använd offertbeslut i målaktiviteter | Du kan nu använda [!DNL Adobe Journey Optimizer] erbjudandebeslut i [!DNL Adobe Target] A/B Test and Experience Targeting (XT) för att fastställa och leverera nästa bästa erbjudande för era besökare på webben och i mobilen.<br>Mer information finns i Använda offertbeslut.<br>**Anteckning**: Den här funktionen är tillgänglig för [!DNL Target] som också har tillgång till Offer decisioning och [!DNL Target] implementering baserad på Adobe Experience Platform Web SDK. |

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

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
