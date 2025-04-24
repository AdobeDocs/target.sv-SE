---
keywords: versionsinformation;utgåvor;uppdateringar;framtida utgåvor;förbättringar;nya funktioner;korrigeringar;uppdateringar;prerelease;tidig åtkomst
description: Lär dig mer om de nya funktionerna, förbättringarna och korrigeringarna som ingår i den kommande versionen av  [!DNL Adobe Target], inklusive SDK:er, API:er och JavaScript-bibliotek.
title: Vilka nya funktioner och förbättringar ingår i den kommande [!DNL Target] versionen?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b09796cd8464b54dcc1945ae1ec00eb914ba218c
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 0%

---

# Versionsinformation för [!DNL Target] (förhandsversion)

Den här artikeln innehåller förhandsversionsinformation för kommande [!DNL Adobe Target]-versioner, inklusive SDK, API:er och JavaScript-bibliotek.

**Senast uppdaterad: 24 april 2025**

>[!NOTE]
>
>Releasedatum, funktioner och annan information kan ändras utan föregående meddelande.
>
>Information om den aktuella versionen finns i [Versionsinformation för mål](release-notes.md). Informationen på dessa sidor kan vara densamma, beroende på när releaserna ska släppas. Utfärdandenumren inom parentes är avsedda för intern [!DNL Adobe]-användning.

## [!DNL Target Standard/Premium] 25.4.5 (25 april 2025)

Den här versionen innehåller följande korrigeringar och uppdateringar:

* Korrigerade ett problem som orsakade skillnader i målgruppslistor mellan inställningssidan [!UICONTROL Activity] och översiktssidan [!UICONTROL Reporting]. (TGT-52203)
* Korrigerade ett problem som förhindrade att en ny sida lades till i en aktivitet på grund av ett ogiltigt användarinmatningsfel. (TGT-52263)
* Ett problem har korrigerats där rekommendationer inte visades på kundens webbplats efter att aktiviteten [!DNL Recommendations] aktiverats. (TGT-52164)
* Korrigerade ett problem som gjorde att `OptionLocalIDs` ökade felaktigt när alternativet inte ändrades. (TGT-52187)
* Ett problem har korrigerats så att hämtade rapportfiler korrekt visar data i rapportgränssnittet. (TGT-52068)
* Ett problem har korrigerats så att gruppåtgärder inte längre misslyckas efter att sidleveransregler har lagts till. (TGT-52097)
* Ett problem som gjorde att [!DNL Target] trimmade alla frågeparametrar från webbplatsens URL har åtgärdats. (TGT-52100)
* Ett konsolfel som hindrade kunder från att skapa aktiviteter i det gamla och uppdaterade målgränssnittet har åtgärdats. (TGT-52181)
* Korrigerade ett problem som hindrade kunder från att lägga till nya sidor, vilket orsakade ett ogiltigt användarinmatningsfel. (TGT-52258)
* Korrigerade ett problem som gjorde att ändringar försvann efter att du lagt till ytterligare sidor och sedan navigerade tillbaka till fliken [!UICONTROL Experiences]. (TGT-52264)
* Korrigerade ett problem som hindrade kunder från att ändra målgrupp i en [!UICONTROL Experience Targeting] (XT)-aktivitet. (TGT-52191)
* Korrigerade ett fel som förhindrade redigering av en XT-aktivitet på grund av en gränssnittsregel som inte stöds. (TGT-52273)
* Ett problem har korrigerats där aktivitetsändringar inte visades i användargränssnittet för [!DNL Target] trots att de levererades till webbsidan. (TGT-52192)
* Korrigerade ett fel i den uppdaterade [!UICONTROL Visual Experience Composer] (VEC) där vägbeskrivningar inte alltid visades längst ned i redigeraren, vilket medförde problem med att välja element exakt. (TGT-51169)
* Ett problem har korrigerats där listrutan [!UICONTROL Audience] inte kunde visa alla målgrupper på grund av sidnumrering. (TGT-52204)
* Ett problem som orsakade ett ogiltigt användarindatameddelande när nya erbjudanden lades till i [!UICONTROL Automated Personalization] (AP)-aktiviteter har åtgärdats. (TGT-52210)
* Korrigerade ett problem där [!UICONTROL Analytics for Target] (A4T) felaktigt valdes som rapportkälla, trots att kunden inte hade åtkomst till A4T. (TGT-52226)
* Ett problem som gjorde att en aktivitet med URL-måttet [!UICONTROL View a Page] inte kunde sparas har åtgärdats. (TGT-52260)
* Korrigerade ett problem som hindrade kunder från att välja arbetsytor när de skapade erbjudanden i en aktivitet. (TGT-52289)
* Ett problem har korrigerats där ändringar från en upplevelse visades felaktigt när de växlades till en annan upplevelse. (TGT-52184)
* Ett problem har korrigerats där standarderbjudandet felaktigt visades i användargränssnittet för [!DNL Target] när aktiviteten öppnades. (TGT-52198)

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
