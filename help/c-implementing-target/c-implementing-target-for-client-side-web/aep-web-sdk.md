---
keywords: Adobe Experience Platform Web SDK;aep web sdk;web sdk;sdk;adobe experience cloud;platform edge network;adobe experience platform edge network;edge network;aep edge network
description: Lär dig hur du använder Adobe Experience Platform Web SDK för att interagera med de olika tjänsterna i Adobe Experience Cloud via AEP Edge Network.
title: Hur implementerar jag Experience Platform Web SDK?
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: 0cfab8d09b74b3eb0ead33a0c37f9dab68a88305
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Adobe Experience Platform Web SDK

[!DNL Adobe Experience Platform Web SDK] (AEP Web SDK) är ett JavaScript-bibliotek på klientsidan som gör  [!DNL Adobe Experience Cloud] att kunder kan interagera med de olika tjänsterna i Experience Cloud (inklusive  [!DNL Target]) via  [!UICONTROL Adobe Experience Platform Edge Network]. Förutom JavaScript-biblioteket finns det ett [!DNL Experience Platform Launch]-tillägg som kan hjälpa dig med dina Web SDK-konfigurationer.

Mer information finns i följande länkar i *Adobe Experience Platform Web SDK*-hjälpen:

* För utförlig information: [Vad är Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* För information som är specifik för [!DNL Target]: [Målöversikt](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## Rekommenderad dokumentation i den här handboken

Förutom den [!DNL Platform Web SKD]-dokumentation som nämns ovan innehåller avsnitten i den här handboken även information som är specifik för [!DNL Platform Web SDK] vad gäller [!DNL Target]-funktioner.

| Funktion | Beskrivning/länk |
| --- | --- |
| [Aktivitets-QA](/help/c-activities/c-activity-qa/activity-qa.md) | Använd QA-URL:er i [!DNL Adobe Target] för att utföra enkel QA för hela aktiviteten med förhandsgranskningslänkar som aldrig ändras, målgruppsanpassning som tillval och QA-rapportering som förblir segmenterad från live-aktivitetsdata. [!UICONTROL Activity QA] gör att du kan testa dina  [!DNL Target] aktiviteter innan du startar dem live.<br>Se  [Mål-JavaScript-bibliotekets QA-](/help/c-activities/c-activity-qa/activity-qa.md#compatibility) lägeskompatibilitet och  [Förhandsvisa URL:er](/help/c-activities/c-activity-qa/activity-qa.md#preview). |
| [[!UICONTROL Analytics for Target] (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T) är en integrerad lösning som gör att ni kan skapa aktiviteter baserat på  [!DNL Analytics] konverteringsstatistik och målgruppssegment. Med A4T-integreringen kan du använda [!DNL Analytics]-rapporter för att undersöka dina resultat.<br>Se  [Aktivitetstyper ](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) som stöds och  [Implementeringssteg för en Adobe Experience Platform Web SDK-implementering](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform). |
| [Målgrupper](/help/c-target/target.md) | Publiken i [!DNL Adobe Target] avgör vem som ser innehåll och upplevelser i en riktad aktivitet.<br>Se  [Använda ](/help/c-target/c-audiences/audiences.md#use-list) listan Publiker och  [Kombinera flera målgrupper](/help/c-target/combining-multiple-audiences.md). |
| [Omdirigeringserbjudanden - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Omdirigeringserbjudanden gör att besökarnas webbläsare dirigerar om till en ny sida.<br>Se  [Omdirigerar  [!DNL Adobe Experience Platform Web SDK] supporten erbjudanden för A4T?](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [Svarstoken](/help/administrating-target/response-tokens.md) | Med svarstoken kan du skicka Target-data till Google Analytics och andra tredjepartsintegreringar.<br>Se  [Skicka data till Google Analytics via Platform Web ](/help/administrating-target/response-tokens.md#platform-web-sdk) SDKom du vill se ett kodexempel på hur du kan utföra den här uppgiften. |
| [TLS-krypteringsändringar (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | TLS (Transport Layer Security) hjälper er att upprätthålla högsta säkerhetsstandard och främja säkerheten för kunddata. |
