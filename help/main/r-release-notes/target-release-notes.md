---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: cd25bda52b7a1b916a73ca5e531a7134ba8cef4e
workflow-type: tm+mt
source-wordcount: '416'
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

## [!DNL Target Standard/Premium] 25.4.4 (17 april 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett felmeddelande har lagts till som hjälp för användarna när de vill lösa dubblettalternativ i en aktivitet. (TGT-51927)
* Ett problem har korrigerats där `ClickTrack` väljare inte togs bort när sidor eller upplevelser med omdirigeringserbjudanden togs bort. (TGT-51952)
* Ett problem som orsakats av att tomma `ClickTrack` väljare tillåts har korrigerats. [!DNL Target] kräver nu att väljarfältet inte får vara tomt. (TGT-52107)
* Korrigerade ett problem som felaktigt tillät mätvärden med dubblettnamn. Mätvärden kräver nu unika namn. (TGT-52201)
* Ett problem har korrigerats där målgruppsdefinitioner inte var synliga vid redigering av målgruppsanpassning på erbjudandenivå i [!UICONTROL Automated Personalization] (AP)-aktiviteter. (TGT-52148)
* Ett problem som gjorde att kunder med [!UICONTROL Editor] rättigheter inte kunde spara aktiviteter har korrigerats. (TGT-5227)
* `OptionLocalIDs` ökar inte längre felaktigt när alternativet inte ändras. (TGT-52139)
* Korrigerade ett problem som orsakade ett ogiltigt `optionLocalIds`-meddelande när en aktivitet skulle skapas. (TGT-52154)
* Skillnader mellan `OptionLocalIDs` som har definierats för en aktivitet och de som används för att definiera upplevelser har korrigerats. (TGT-52215)
* Korrigerade ett problem som orsakade ett valideringsfel som inträffade när en A/B-aktivitet skulle skapas. (TGT-51923)

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
