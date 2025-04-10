---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8af56181ea0ed74eb41d799908ce50f0436d330c
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 10 april 2025**

>[!NOTE]
>
>Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## Uppdatering av målbehörigheter (22 april 2025)

Den här framtida uppdateringen förbättrar organisationskontrollen över [!DNL Target] instanskonfigurationer och förhindrar oavsiktliga uppdateringar som kan påverka aktivitetsleveransen i olika testnings- och personaliseringsteam.

Från och med den 22 april 2025 kan bara [!UICONTROL Product]- och [!UICONTROL Solutions]-administratörer uppdatera inställningarna i [!UICONTROL Administration] -avsnitten, oavsett vilka roller de har i [!DNL Target] -arbetsytorna. Användare utan den här behörigheten har skrivskyddad åtkomst till [!UICONTROL Administration]-avsnitten.

Mer information finns i [Administrera mål](/help/main/administrating-target/start-target.md).

## [!DNL Target Standard/Premium] 25.4.3 (10 april 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Ett fel som gjorde att kunderna inte kunde öppna popup-fönstret för målgruppsinformation för vissa [!UICONTROL Experience Targeting] (XT)-aktiviteter har åtgärdats. (TGT-52049)
* Ett problem som gjorde att kunder inte kunde infoga [!UICONTROL Experience Fragment] i standardarbetsytan har korrigerats. (TGT-52073)
* Korrigerade ett problem där ett erbjudande visades som &quot;Innehåll hittades inte&quot; och inte visades på sidan [!UICONTROL Offers] för en [!UICONTROL Automated Personalization]-aktivitet (AP). (TGT-52150)
* Lagt till möjlighet att tillåta duplicerade målgrupper inom en aktivitet. (TGT-51200)
* Ett problem har korrigerats där fel mbox-namn visades på sidan [!UICONTROL Goals & Settings] för en XT-aktivitet efter redigering. (TGT-52026)
* Ett problem har korrigerats där `defaultContent` visades i alternativ trots att `experiences/optionLocations` inte fanns. (TGT-52036)
* Ett problem har korrigerats som säkerställer att tomma strängar inte konverteras till null-värden. (TGT-52037)
* Korrigerade ett problem som krävde att kunderna konfigurerade om [!UICONTROL Optimization Goal] i [!UICONTROL Reporting Settings] på sidan [!UICONTROL Goals & Settings] efter redigeringar. (TGT-52071)
* Ett problem har korrigerats där en aktivitet utan sidleveransregler visade flera regler på sidan [!UICONTROL Overview]. (TGT-52084)
* Ett felmeddelande har lagts till för användare som försöker spara ett erbjudande med tecken utanför det grundläggande flerspråkiga planet, till exempel känslolägesikoner. (TGT-52105)
* Ett problem har korrigerats där öppnandet av en aktivitet utlöste felmeddelandet:&quot;Den här aktiviteten använder en eller flera målgrupper som har tagits bort från källan.&quot; (TGT-52120)
* Ett problem har korrigerats där ClickTrack-mått inte visades i den uppdaterade [!UICONTROL Visual Experience Composer] (VEC) under redigeringen. (TGT-52152)
* Ett problem har korrigerats där en URL med en frågeparameter som aktivitetsplatsen inte visade frågeparametern på aktivitetens [!UICONTROL Overview]-sida. (TGT-51635)
* Korrigerade ett problem som förhindrade att hela upplevelsens URL visades i [!UICONTROL Browse mode] i [!UICONTROL Visual Experience Composer] (VEC). (TGT-52101)
* Korrigerade ett problem där redigering av en aktivitet orsakade att sidans leverans lade till &quot;/&quot; i slutet av URL:en, vilket gjorde den ogiltig. (TGT-52114)
* Ett problem har korrigerats där länken [!UICONTROL Activity QA] i [!UICONTROL Form-Based Experience Composer] felaktigt omdirigerades till hemsidan [!DNL Adobe Experience Cloud]. (TGT-52055)
* Ett felmeddelande har lagts till som hjälp för användarna när de vill lösa dubblettalternativ i en aktivitet. (TGT-51927)
* Ett problem har korrigerats där ytterligare sidor som lagts till i aktiviteten [!UICONTROL A/B Test] inte sparades när de sparades och öppnades igen. (TGT-51994)
* Ett problem som gjorde att kunder inte kunde ta bort format i avsnittet med infogade format har korrigerats. (TGT-52070)
* Åtkomsten till [målgruppsdefinitionskort](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) i dialogrutan [!UICONTROL Activity QA] återställdes, ungefär som det gamla användargränssnittet. (TGT-52056)
* Det uppdaterade användargränssnittet sparade inte sidor eller målgrupper utan ändringar. Om kunderna har lagt till nya sidor eller målgrupper i en aktivitet men inte har gjort några ändringar i dem, ignorerade [!DNL Target] de oförändrade målgrupperna när de sparades. Meddelanden har lagts till på relevanta platser för att informera användarna om detta. (TGT-52104)

## Ytterligare versionsinformation

| Resurs | Information |
|--- |--- |
| [Versionsinformation: Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=en) | Information om ändringarna i respektive version av Platform Web SDK. |
| [versionsinformation för at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Information om ändringar i varje version av JavaScript-biblioteket [!DNL Adobe Target] at.js. |

## Förhandsversionsinformation {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Registrera dig för [!DNL Adobe Priority Product Update] om du vill få förhandsmeddelanden om kommande produktförbättringar för [!DNL Target] och andra [!DNL Adobe Experience Cloud]-lösningar:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
