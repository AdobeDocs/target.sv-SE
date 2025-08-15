---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 1f8fa78c2b88e179f021128a8fd3dac177dfa3dd
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 15 augusti 2025**

>[!NOTE]
>
>* Releasedatum, funktioner och annan information kan ändras utan föregående meddelande. Informationen i den här artikeln uppdateras ofta, särskilt före releaser.
>
>* Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md).
>
>* Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.8.3 (21 augusti 2025)

Den här versionen innehåller följande uppdateringar och korrigeringar:

**Rekommendationer**

+++Se detaljer
* **Korrigerat problem i gränssnittet för Recs där CSV-hämtning med anpassade villkor returnerade 404-fel**: Ett problem där kunderna inte kunde hämta CSV-filen med anpassade villkor i processen för att skapa aktivitet har korrigerats.
* **Inkonsekvent inläsning av bilder i[!UICONTROL Catalog Search]** har korrigerats: Ett problem där miniatyrbilder och bilder i [!UICONTROL &#x200B; Catalog Search] inte lästes in konsekvent i processen där aktiviteten skapades har åtgärdats. Det gick inte att visa bilder om inte kolumnen &quot;Miniatyrbilds-URL&quot; var synlig och vissa produktbilder lästes in delvis eller inte alls efter navigerings- eller sökåtgärder. (TGT-52778)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Se detaljer
* **Korrigerat problem i aktivitetsskapandeprocessen som blockerade progression till [!UICONTROL Targeting] steg i AP-aktiviteter**: Korrigerade ett fel i aktivitetsskapandeprocessen där kunderna inte kunde fortsätta till [!UICONTROL Targeting] step in [!UICONTROL Automated Personalization] -aktiviteterna (AP) om inte två platser lades till. Detta beteende skilde sig från den tidigare upplevelsen, där en enda plats med flera erbjudanden var tillräckligt. Kravet har korrigerats, vilket gör att kunderna kan fortsätta använda inställningar för en plats som en del av sina AP-arbetsflöden. (TGT-53426)

+++

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=sv-SE){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Target] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Adobe Experience Cloud] och andra [!DNL Adobe Priority Product Update]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
