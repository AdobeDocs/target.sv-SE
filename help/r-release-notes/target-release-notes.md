---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den kommande versionen?
feature: Versionsinformation
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7bb1f896dd92b41d04eb0dfd39116ff1c132fe50
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 1 juni 2021**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 misslyckas alla anrop från mbox.js på ett säkert sätt och påverkar de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Om du vill undvika eventuella problem med dina platser migrerar du till den senaste versionen av det nya [!DNL Adobe Experience Platform Web SDK]- eller at.js-JavaScript-biblioteket. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.5.1 (8 juni 2021)

| Funktion | Detaljer |
| --- | --- |
| ![Premium ](/help/assets/premium.png) [!DNL Recommendations] [!UICONTROL Catalog Search] badgeAPI | Sök i din [!DNL Recommendations]-produkt och innehållskatalog programmatiskt via API för att identifiera objekt som matchar ett sökvillkor och förenkla katalogadministrationen.<br>**Begränsningar och anteckningar**:<ul><li>Katalogsökning via API stöds inte i miljöer med fler än 2 000 000 objekt.</li><li>Katalogsökresultat via API uppdateras snabbare än katalogsökresultat via användargränssnittet i [!DNL Target]. Katalogsökningen i gränssnittet [!DNL Target] kan ta ytterligare tid att återspegla de senaste resultaten.</li></ul>Mer information finns i [Söka efter entiteter](http://developers.adobetarget.com/api/recommendations/#tag/Searching-Entities) i *[!DNL Adobe Target]API*-handboken.[!DNL Recommendations] |

## [!DNL Target Standard/Premium] 21.5.2 (Datum som ska fastställas)

Den här versionen innehåller följande nya funktioner och förbättringar. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

| Funktion | Detaljer |
| --- | --- |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | Följande förbättringar gäller för popularitetsalgoritmer i [!DNL Recommendations]:<ul><li>Ett nytt sextimmars &quot;uppslagsfönster&quot; (dataområde) kommer att vara tillgängligt för alla popularitetsalgoritmer (Mest visade/populära säljare) när [!DNL Target] är den beteendebaserade datakällan. (Det här uppslagsfönstret är *inte* tillgängligt när [!DNL Adobe Analytics] är datakällan för beteendet.)</li><li>När du väljer det här alternativet körs följande algoritmer ungefär var tredje timme (i stället för var tolfte timme).<ul><li>Mest visade</li><li>Mest köpta</li><li>Visas mest per kategori</li><li>Mest köpta per kategori</li><li>Visas mest av ett anpassat attribut (med funktionen groupBy)</li><li>Mest köpta av anpassat attribut (med funktionen groupBy)</li></ul></ul>(TOP-1086) |

Den här versionen innehåller följande korrigeringar.

* Innehållet läggs till när releasedatum närmar sig.

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
