---
keywords: Adobe Experience Platform Web SDK;aep web sdk;web sdk;sdk;adobe experience cloud;platform edge network;adobe experience platform edge network;edge network;aep edge network
description: Lär dig hur du använder Adobe Experience Platform Web SDK för att interagera med de olika tjänsterna i Adobe Experience Cloud via AEP Edge Network.
title: Hur implementerar jag Experience Platform Web SDK?
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# Adobe Experience Platform Web SDK

[!DNL Adobe Experience Platform Web SDK] (AEP Web SDK) är ett JavaScript-bibliotek på klientsidan som tillåter kunder som [!DNL Adobe Experience Cloud] interagera med de olika tjänsterna i Experience Cloud (inklusive [!DNL Target]) via [!UICONTROL Adobe Experience Platform Edge Network]. Förutom JavaScript-biblioteket finns det en [!DNL Adobe Experience Platform] för att hjälpa dig med dina Web SDK-konfigurationer.

Mer information finns i följande länkar i *Adobe Experience Platform Web SDK* hjälp:

* För utförlig information: [Vad är Adobe Experience Platform Web SDK?](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* För information som är specifik för [!DNL Target]: [Målöversikt](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## Självstudiekurs: Implementera Adobe Experience Cloud med Platform Web SDK

Lär dig hur [implementera Experience Cloud-program med Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target=_blank}. Mer information om Target finns i [Konfigurera Target med Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-target.html){target=_blank} i självstudiekursen.

## Rekommenderad dokumentation

Förutom [!DNL Platform Web SDK] dokumentationen ovan innehåller även avsnitt i den här handboken specifik information om [!DNL Platform Web SDK] som det relaterar till [!DNL Target] funktioner.

| Funktion | Beskrivning/länk |
| --- | --- |
| [Aktivitets-QA](/help/main/c-activities/c-activity-qa/activity-qa.md) | Använd QA-URL:er i [!DNL Adobe Target] att utföra enkel QA för hela verksamheten med förhandsgranskningslänkar som aldrig ändras, målgruppsanpassning som tillval och QA-rapportering som förblir segmenterad från liveaktivitetsdata. [!UICONTROL Activity QA] låter dig testa [!DNL Target] aktiviteter innan de lanseras live.<br>Se [Kompatibilitet med mållayoutbibliotek i JavaScript - QA-läge](/help/main/c-activities/c-activity-qa/activity-qa.md#compatibility) och [Förhandsgranska URL:er](/help/main/c-activities/c-activity-qa/activity-qa.md#preview). |
| [[!UICONTROL Analytics for Target] (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T) är en integrering med flera lösningar som gör att du kan skapa aktiviteter baserade på [!DNL Analytics] konverteringsstatistik och målgruppssegment. Med A4T-integreringen kan du använda [!DNL Analytics] rapporter för att undersöka resultaten.<br>Se [Aktivitetstyper som stöds](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) och [Implementeringssteg för en Adobe Experience Platform Web SDK-implementering](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#platform). |
| [Målgrupper](/help/main/c-target/target.md) | Målgrupper i [!DNL Adobe Target] avgöra vilka som ser innehåll och upplevelser i en målinriktad aktivitet.<br>Se [Använda publiklistan](/help/main/c-target/c-audiences/audiences.md#use-list) och [Kombinera flera målgrupper](/help/main/c-target/combining-multiple-audiences.md). |
| [Skapa målgrupper](/help/main/c-target/c-audiences/audiences.md) | Använda målgrupper skapade i [!DNL Adobe Experience Platform] ge mer omfattande kunddata som leder till mer slagkraftig personalisering.<ul>Se [Använd målgrupper från [!DNL Adobe Experience Platform]](/help/main/c-target/c-audiences/audiences.md#aep). |
| [Erbjudandebeslut](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) | Lägg till offertbeslut som skapats i Adobe Journey Optimizer i Target-aktiviteter (manuellt A/B-test eller Experience Targeting) för att fastställa och leverera nästa bästa erbjudande för era besökare på webben och i mobilen. |
| [Omdirigeringserbjudanden - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Omdirigeringserbjudanden gör att besökarnas webbläsare dirigerar om till en ny sida.<br>Se [Gör [!DNL Adobe Experience Platform Web SDK] stöder omdirigeringserbjudanden för A4T?](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [Svarstoken](/help/main/administrating-target/response-tokens.md) | Med svarstoken kan du skicka Target-data till Google Analytics och andra tredjepartsintegreringar.<br>Se [Skicka data till Google Analytics via Platform Web SDK](/help/main/administrating-target/response-tokens.md#platform-web-sdk) om du vill se ett kodexempel på hur du utför den här uppgiften. |
| [Programimplementering på en sida](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/spa-implementation.html?lang=en) i *SDK för plattform* guide. | [!UICONTROL Adobe Experience Platform Web SDK] innehåller omfattande funktioner som gör det möjligt för ditt företag att utföra personalisering på nästa generations klienttekniker, som single page-applikationer (SPA). |
| [TLS-krypteringsändringar (Transport Layer Security)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/) | TLS (Transport Layer Security){target=_blank} hjälper dig att upprätthålla högsta säkerhetsstandard och främja säkerheten för kunddata. |
