---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner ingår i den kommande versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bd7032b915bf1b333fa5cc3cb4825eaa7e4f83fb
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 6 oktober 2021**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 misslyckas alla anrop från mbox.js på ett säkert sätt och påverkar de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Om du vill undvika eventuella problem med dina platser migrerar du till den senaste versionen av det nya [!DNL Adobe Experience Platform Web SDK]- eller at.js-JavaScript-biblioteket. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.10.1 (6 oktober 2021)

Den här versionen innehåller följande nya funktioner:

| Funktion | Detaljer |
| --- | --- |
| [!UICONTROL Audiences] Uppdatering av användargränssnittet | Som en del av [!DNL Adobe Target]-teamets pågående arbete med att förbättra användarupplevelsen för [!DNL Target]-användare uppdaterar den här versionen sidorna [!UICONTROL Audiences] och [!UICONTROL Profile Scripts] i [!DNL Target]-gränssnittet. Uppdateringen förenar och standardiserar designmönster som tidigare varit inkonsekventa, samtidigt som nya förbättringar läggs till, till exempel:<ul><li>Möjlighet att markera och ta bort flera målgrupper samtidigt</li><li>En uppdaterad [målgruppsbyggare](/help/c-target/c-audiences/create-audience.md)</li><li>Stöd för uteslutningsregel i [!UICONTROL Audience]-biblioteksregelverktyget</li><li>Ett nytt &quot;Audience Source&quot;-filter som ger snabbare målgruppsidentifiering</li><li>Alternativ för beständig sökning och filtrering av sessioner</li></ul>Mer information finns i [Publiker](/help/c-target/target.md).<br>**Obs**: Det nya  [!UICONTROL Audiences] och  [!UICONTROL Profile Scripts] användargränssnittet kommer att lanseras i alla regioner nästa vecka. |
| [!UICONTROL Profile Scripts] Uppdatering av användargränssnittet | Biblioteket [!UICONTROL Profile Scripts] uppdaterades också och innehåller ett uppdaterat gränssnitt samt flera produktivitetsuppdateringar:<ul><li>Möjlighet att markera och ta bort flera profilskript samtidigt</li><li>En ny kodredigerare för profilskript</li><li>Syntaxmarkering och felkontroll inuti kodredigeraren</li><li>Fyll i tokens-parametrar automatiskt (mbox eller profile) via kortkommandon</li></ul>Mer information finns i [Besökarprofiler](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**Obs**: Det nya  [!UICONTROL Audiences] och  [!UICONTROL Profile Scripts] användargränssnittet kommer att lanseras i alla regioner nästa vecka. |
| ![Premium ](/help/assets/premium.png) badgeRecommendations Criteria create and edit | Arbetsflödet för att skapa och redigera [!UICONTROL Recommendations Criteria] har förenklats så att det är enklare att välja rätt rekommendationsalgoritm och inställningar för att uppnå dina mål.<br>Mer information finns i  [Skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md). |
| ![Förbättrad Premium ](/help/assets/premium.png) badgeRecommendations lookback window och algorithm refresh rate | Nu kan du köra algoritmerna&quot;Mest visade&quot; och&quot;Mest visade&quot; säljare&quot; med ett sextimmars uppslagsfönster för att fånga det innehåll som är mest aktuellt. När du har valt ett sextimmars uppslag uppdateras dina rekommendationer var 3:e till 6:e timme under dagen.<br>Mer information finns i  [Datakälla ](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) i  *Skapa villkor*. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Anmäl dig till produktuppdateringen Adobe Priority om du vill få meddelanden om kommande produktförbättringar för Target och andra Adobe Experience Cloud-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
