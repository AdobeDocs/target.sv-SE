---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 872e56662e04e3fabda7ff38233adfea32efbe48
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 17 april 2025**

>[!NOTE]
>
>Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.4.5 (24 april 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Korrigerade ett problem som gjorde att flera upplevelsemålgrupper visades när en aktivitet redigerades eller sparades. (TGT-52134)
* Ett problem har korrigerats där rekommendationer inte visades på kundens webbplats efter att aktiviteten [!DNL Recommendations] aktiverats. (TGT-52164)
* `OptionLocalIDs` ökar inte längre felaktigt när alternativet inte ändras. (TGT-52187)
* Hämtade rapportfiler visar nu korrekt data i det rapporterade användargränssnittet. (TGT-52068)
* Korrigerade ett fel som gjorde att Target inte kunde identifiera tecknet&quot;#&quot; i en webbplats URL. (TGT-52093)
* Gruppåtgärder misslyckas inte längre efter att sidleveransregler har lagts till. (TGT-52097)
* Ett problem som gjorde att [!DNL Target] trimmade alla frågeparametrar från webbplatsens URL har åtgärdats. (TGT-52100)
* Korrigerade ett problem som medförde att målgruppsförbättringar och aktivitetspubliker hämtades i det uppdaterade användargränssnittet. (TGT-52158)

## Uppdatering av målbehörigheter (22 april 2025)

Den här framtida uppdateringen förbättrar organisationskontrollen över [!DNL Target] instanskonfigurationer och förhindrar oavsiktliga uppdateringar som kan påverka aktivitetsleveransen i olika testnings- och personaliseringsteam.

Från och med den 22 april 2025 kan bara [!UICONTROL Product]- och [!UICONTROL Solutions]-administratörer uppdatera inställningarna i [!UICONTROL Administration] -avsnitten, oavsett vilka roller de har i [!DNL Target] -arbetsytorna. Användare utan den här behörigheten har skrivskyddad åtkomst till [!UICONTROL Administration]-avsnitten.

Mer information finns i [Administrera mål](/help/main/administrating-target/start-target.md).

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| Versionsinformation för [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Adobe Priority Product Update] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
