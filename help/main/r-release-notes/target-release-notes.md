---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease
description: Läs om de nya funktionerna, förbättringarna och korrigeringarna i den kommande versionen av [!DNL Adobe Target], inklusive SDK, API och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar som ingår i de kommande [!DNL Target] Frisläpp?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 362fac25f04028dff0fb0233d418ef9ce88e53d6
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---

# [!DNL Target] versionsinformation (prerelease)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target] releaser, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 4 september 2023**

>[!NOTE]
>
>Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Utgivningsnumren inom parentes är för interna [!DNL Adobe] använd.

## [!DNL Target] Standard/Premium 23.9.1 (6-11 september 2023)

Den här versionen är tillgänglig enligt följande schema:

* **6 september**: Amerika
* **7 september**: Europa, Mellanöstern och Afrika (EMEA)
* **11 september**: Asien-Stillahavsregionen (APAC)

Den här versionen innehåller följande förbättringar och korrigeringar:

* Ett problem som orsakade inkonsekventa rapporteringsdata i [!DNL Target] Användargränssnittet och [!DNL Adobe Analytics] Användargränssnitt för [!UICONTROL Auto-Allocate] aktiviteter som använder [!UICONTROL Analytics for Target] (A4T) som rapportkälla. (TGT-46112)
* Ökade tidsgränsen för PUT-anrop till Target Delivery API till 15 sekunder för att undvika timeoutfel. (TGT-46091)
* Ett problem som visade fel rapportnamn vid växling mellan [!UICONTROL Table View] och [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes] rapporter. (TGT-46040)
* Förbättrade [!UICONTROL Visual Experience Composer] (VEC) för att stödja Lightning DOM (webbkomponenter). (TGT-45422)
* Korrigerade ett problem som gjorde att VEC-åtgärder tillämpades i fel ordning. I vissa fall tillämpade VEC vissa ändringar asynkront och när extra ändringar lades till i ett element uppstod fel om det elementet visas efter ett [!UICONTROL Insert] åtgärd. (TGT-45983)
* Lagt till möjlighet att ange en CSS-väljare i VEC. (TGT-45958 och TGT-46017)
* Ett problem som uppstod när en SPA öppnades i VEC-läget och sedan gick till bläddringsläget orsakade att bakåt- och framåtpilarna inte fungerade korrekt. (TGT-45956)
* Ett problem som gjorde att URL:en inte kunde uppdateras kontinuerligt när du bläddrar genom en webbplats för ett program (SPA) har åtgärdats. (TGT-45417)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringarna i varje version av [!DNL Adobe Target] at.js JavaScript-bibliotek. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Om du vill få förhandsmeddelanden om kommande produktförbättringar i [!DNL Target] och andra [!DNL Adobe Experience Cloud] lösningar, registrera dig för [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
