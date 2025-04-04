---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c6799d43ee2f5ebe568f7199ae4ec1deaa164c06
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 3 april 2025**

>[!NOTE]
>
>Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.4.1 (2 april 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Korrigerade ett problem som gjorde att upplevelsemålgrupperna försvann från aktiviteter. (TGT-52003)
* Korrigerade ett problem som orsakade oväntade element under leveransen. (TGT-52011)
* Korrigerade ett problem som hindrade kunder från att visa målgruppen i måldiagrammet på Ove[!UICONTROL r]view-sidan och under aktivitetsredigering. (TGT-52050)
* Ett problem som gjorde att kunderna inte kunde ändra ordning på upplevelserna har korrigerats i prioritetsordning i [!UICONTROL Experience Targeting] (XT)-aktiviteter har åtgärdats. (TGT-52054)
* Korrigerade ett problem som orsakade felaktig återgivning när textstilen ändrades. (TGT-51876)
* Ett problem har korrigerats som innebär att när ett omdirigeringserbjudande ändras tas även alla [!UICONTROL ClickTrack]-väljare som är associerade med det erbjudandet bort av [!DNL Target]. (TGT-51936)
* Korrigerade ett problem som gjorde att [!DNL Target] felaktigt sparade väljaren när [!UICONTROL ClickTrack] avbröts. (TGT-51937)
* Korrigerade ett problem som utlöste ett ogiltigt namnfel efter att mbox-väljaren öppnats och stängts på sidan [!UICONTROL Goals & Settings] utan att några ändringar gjorts. (TGT-51983)
* Korrigerade ett problem som blockerade redigering av ad hoc-erbjudanden som skapades i det gamla [!DNL Target]-gränssnittet. (TGT-51984)
* Ett problem som blockerade redigeringsaktiviteter med ad hoc-erbjudanden som innehåller anpassad kod har korrigerats. (TGT-51995)
* Korrigerade ett problem som gjorde att undantagsregler visades som inkluderingsregler när kombinerade målgruppsdefinitioner redigerades. (TGT-51999)
* Ett problem som gjorde att anpassad kod inte kunde visas korrekt vid redigering av upplevelser har åtgärdats. (TGT-52005)
* Ett problem som gjorde att alternativet [!UICONTROL Insert Before] inte var tillgängligt för infogning av innehåll före navigeringsfältet har korrigerats. (TGT-52031)
* Korrigerade ett problem som förhindrade att standardupplevelsen markerades korrekt vid rapportering. (TGT-51716)
* Korrigerade ett problem som utlöste ett `default message [Invalid optionLocalIds: xx]]`-meddelande när en aktivitet skapades. (TGT-52038)

<!-- 
## [!DNL Target Standard/Premium] 24.10.2 (October 21, 2024)

This release contains the following fixes:

* Fixed an issue that prevented [!UICONTROL Recommendations] activities from loading in [!UICONTROL Compose] and [!UICONTROL Browse] modes. (TGT-50709)
* Fixed an issue with the new [[!DNL Google Chrome] [!UICONTROL Visual Editing Helper] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) that caused a redirect from the [!UICONTROL Visual Experience Composer] (VEC) to the [!UICONTROL Activities Library] after clicking Cancel. Before this fix, customers needed to refresh the [!UICONTROL Activities Library] before being able to create new activities. (TGT-49980)-->

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Adobe Priority Product Update] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
