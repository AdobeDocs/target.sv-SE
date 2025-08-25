---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 65bc050a189b65af57b1258afeff497a0dafcfb5
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 21 augusti 2025**

>[!NOTE]
>
>* Releasedatum, funktioner och annan information kan ändras utan föregående meddelande. Informationen i den här artikeln uppdateras ofta, särskilt före releaser.
>
>* Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md).
>
>* Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.8.4 (28 augusti 2025)

Den här versionen innehåller följande uppdateringar och korrigeringar:

**[!DNL Recommendations]**

+++Se detaljer
**Gränssnittet har uppdaterats så att avancerad sökfiltrering i [!UICONTROL Product Catalog Search] är skiftlägeskänslig**: [!UICONTROL Advanced Search]-gränssnittet på [!UICONTROL Product Catalog Search]-sidan har tidigare utfört exakt skiftlägesmatchning på returnerade värden, även om både backend- och GraphQL-frågor inte var skiftlägeskänsliga. Den här inkonsekvensen orsakade förvirring och minskad söknoggrannhet. Filtreringen av [!UICONTROL Advanced Search] är nu inte skiftlägeskänslig, den justeras mot serverdelsbeteendet och förbättrar användbarheten.

+++

**[!UICONTROL Visual Experience Composer (VEC)]**

+++Se detaljer
* **Ett problem har korrigerats där namnändringen av en plats i en [!UICONTROL Automated Personalization] (AP) eller [!UICONTROL Multivariate Test] (MVT) aktivitet inte kvarstod efter att användaren navigerat till [!UICONTROL Targeting]-steget och återvände.**-kunder kan nu redigera och spara platsnamn, och ändringarna är fortfarande synliga under hela aktivitetsskapandeprocessen. (TGT-52367)

+++

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Target] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Adobe Experience Cloud] och andra [!DNL Adobe Priority Product Update]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
