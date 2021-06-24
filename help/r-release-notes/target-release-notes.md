---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den kommande versionen?
feature: Versionsinformation
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b897829595ef1cdda28a995481fa1d2d5d1616f4
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 24 juni 2021**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 misslyckas alla anrop från mbox.js på ett säkert sätt och påverkar de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Om du vill undvika eventuella problem med dina platser migrerar du till den senaste versionen av det nya [!DNL Adobe Experience Platform Web SDK]- eller at.js-JavaScript-biblioteket. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.6.1 (30 juni 2021)

Den här versionen innehåller följande nya funktioner och förbättringar. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

| Funktion | Detaljer |
| --- | --- |
| [!UICONTROL Analytics for Target] (A4T) | Om du klickar på länken [!UICONTROL View in Analytics] på sidan [!UICONTROL Reports] från en aktivitet som använder [!DNL Analytics] som rapportkälla (A4T), öppnas [!DNL Analysis Workspace] nu. Tidigare öppnade länken [!DNL Analytics]-rapportering. (TGT-36959) |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | Följande förbättringar gäller för popularitetsalgoritmer i [!DNL Recommendations]:<ul><li>Ett nytt sextimmars &quot;uppslagsfönster&quot; (dataområde) är tillgängligt för alla popularitetsalgoritmer (Mest visade/populära säljare) när [!DNL Target] är den beteendebaserade datakällan. (Det här uppslagsfönstret är *inte* tillgängligt när [!DNL Adobe Analytics] är datakällan för beteendet.)</li><li>När du väljer det här alternativet körs följande algoritmer ungefär var tredje timme (i stället för var tolfte timme).<ul><li>Mest visade</li><li>Mest köpta</li><li>Visas mest per kategori</li><li>Mest köpta per kategori</li><li>Visas mest av ett anpassat attribut (med funktionen groupBy)</li><li>Mest köpta av anpassat attribut (med funktionen groupBy)</li></ul></ul>Releasedatum som ska tillkännages. (TOP-1086) |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
