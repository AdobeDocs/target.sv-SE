---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 71f88ad173599b3a582a1d2c261ba8a562cf734a
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 20 juni 2025**

>[!NOTE]
>
>* Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>* Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md).
>
>* Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.6.3 (20 juni 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Alternativet [!UICONTROL Rearrange] har lagts till i det uppdaterade användargränssnittet för [!UICONTROL Visual Experience Composer] (VEC) för att anpassas till funktioner som är tillgängliga i det äldre VEC. (TGT-46957)
* Ett problem har korrigerats där kopiering av en aktivitet från en arbetsyta till en annan arbetsyta utlöste fel som &quot;får inte vara null&quot; eller &quot;något gick fel&quot;. (TGT-52474)
* Ett problem har korrigerats där [!UICONTROL Automated Segments] och [!UICONTROL Important Attributes] rapporter inte genererades för vissa aktiviteter. (TGT-52904)
* Ett problem har korrigerats i den uppdaterade VEC där standardinnehållshanteringen i [!UICONTROL Automated Personalization] (AP)-aktiviteter inte matchade det gamla användargränssnittet. Systemet lägger nu automatiskt till standardinnehållet `optionGroup` med namnet&quot;Standardinnehåll&quot; med `optionGroupLocalId = 0` när ingen grupp läggs till. Den här gruppen innehåller standardalternativet (till exempel `optionLocalId: 0`). Om standardinnehållet tas bort tas även motsvarande alternativgrupp bort. (TGT-52651)
* Korrigerade ett problem i [!UICONTROL Multivariate Test] (MVT)-aktiviteter där återanvändning av en `experienceLocalId` från tidigare borttagna upplevelser inte tillåts korrekt. (TGT-52672)
* Ett problem har korrigerats där URL:er på aktivitetsplatser inte kunde visa frågeparametrar på grund av ogiltiga tecken, till exempel snedstreck (/). (TNT52845)
* Förbättrade valideringsfelmeddelandet för [!DNL A/B Test] aktivitetsuppdateringar via backend-API:t. När det finns duplicerade platsnamn anges nu tydligt: &quot;Dubblettnamn tillåts inte&quot; för `locations.selectors`. (TGT-52589)
* Korrigerade ett fel som uppstod när en aktiv [!UICONTROL Recommendations]-aktivitet uppdaterades på grund av en okänd egenskap i nyttolasten för begäran. Systemet hanterar nu &quot;Ogiltig JSON&quot; korrekt. Okänt egenskapsnamn. (TGT-52723)
* Ett problem som gjorde att en [!DNL Recommendations]-design inte kunde skapas har åtgärdats. Om du klickar på [!UICONTROL Create] utlöstes meddelandet: &quot;Det ska finnas minst 1 entitetsvariabel i skriptet.&quot; (TGT-52395 &amp; TGT-52899)
* Ett problem har korrigerats där en [!DNL Recommendations]-design utan ändringar blockerades. (TGT-52879)
* Korrigerade ett fel för backend-validering som orsakade felet&quot;400 - felaktig begäran&quot; när en [!UICONTROL Recommendations]-aktivitet sparades. (TGT-52716)
* Korrigerade ett problem i [!UICONTROL Form-Based Experience Composer] där hovring över en mbox med specialtecken i listrutan [!UICONTROL Location] gjorde att redigeraren blev tom och utlöste ett&quot;Failed to execute &#39;querySelector&#39; on &#39;Element&#39;.&quot; fel. (TGT-52717)
* Förbättrad exakthet i feed-status med en ny &quot;PARTIALLY_IMPORTED&quot;-indikator. Tidigare markerades feeds som&quot;lyckade&quot; även om inte alla rader i en fil importerades, vilket var vilseledande. (TGT-52892)
* Korrigerade ett fel där vissa API-anrop till `/admin/rest/ui/v1/campaigns` returnerade klientfel (HTTP 4xx) efter migrering till AP V2. (TGT-52721)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=sv-SE){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Adobe Priority Product Update] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
