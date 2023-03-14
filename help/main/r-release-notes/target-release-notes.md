---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna i den kommande utgåvan av Adobe Target, bland annat SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar som ingår i de kommande [!DNL Target] Frisläpp?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2c4f5666b65bfc36885aad3907639a309e8c69f2
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Versionsinformation för mål (prerelease)

Den här artikeln innehåller förhandsversionsinformation. Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.

**Senast uppdaterad: 14 mars 2023**

Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna släpps. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## [!DNL Target] Standard/Premium 22.15.1 (8 och 9 mars 2023)

Den här versionen kommer att vara tillgänglig enligt följande uppdelade schema:

* **8 mars**: Amerika
* **9 mars**: Europa, Mellanöstern och Afrika (EMEA)
* **9 mars**: Asien-Stillahavsområdet (APAC)

>[!NOTE]
>
>På grund av problem som sedan dess har åtgärdats, &quot;Optimerade A4T-värden för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]&quot; som släpptes den 8 och 9 mars har tillfälligt tagits bort. Efter ytterligare intern testning kommer funktionen att släppas igen inom några veckor.

Den här versionen innehåller följande korrigeringar:

* Uppdateringar för utveckling av anpassade webbkomponenter med [!UICONTROL Visual Experience Composer] (VEC):

   * Skuggans DOM-element har markerats i VEC genom att redigeringsprocessen har förbättrats så att det inte finns något beroende av [!DNL Target] implementeringstyp vid redigering av skuggroten. Nu ska det fungera för alla webbplatser att välja Shadow DOM-element i VEC.
   * Korrigerade ett problem som förhindrade inläsning av HTML-element med #Shadow DOM i VEC. (TGT-35801)
   * Korrigerade VEC-problem med SPA webbplatser som använder ShadowDOM. (TGT-43169)
   * Ett problem med optimeringsmålet har korrigerats: &quot;klickade på ett element&quot; som inte kunde identifiera CSS-väljaren korrekt i ShadowDOM.

>[!NOTE]
>
>För att vara säker på att ändringarna som har skapats i VEC levereras måste du se till att du använder en [!DNL Target] SDK ([at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html){target=_blank} (alloy.js) med en version som är större än 2.8.

**Känt fel**: Klickspårning på ett skuggrotelement vid användning [!DNL Adobe Experience Platform Web SDK] fungerar inte korrekt. (TNT-47012)

## at.js version 2.10.2 (7 mars 2023)

* Ett problem som orsakade `trackEvent` funktion som alltid returnerar ett fel.

Mer information om alla at.js-versioner finns i [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## Ytterligare versionsinformation

| Resurs | Detaljer |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |


## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Om du vill få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar, registrera dig för [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
