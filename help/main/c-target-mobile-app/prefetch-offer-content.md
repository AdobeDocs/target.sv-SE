---
keywords: erbjudande;prefetch;iOS;android;sdk;mobile;mobile sdk
description: Använd Adobe [!DNL Target] förhämtningsfunktionen i iOS och Android Mobile SDK:er för att hämta erbjudandeinnehåll så få gånger som möjligt genom att cachelagra serversvaren.
title: Kan jag förhämta erbjuda innehåll för mobilappar?
feature: Implement Mobile
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%

---

# Förhämta erbjudandeinnehåll

The [!DNL Target] förhämtningsfunktionen använder iOS och Android Mobile SDK:er för att hämta erbjudandeinnehåll så få gånger som möjligt genom att cachelagra serversvaren.

Den här processen minskar inläsningstiden, förhindrar flera nätverksanrop och tillåter [!DNL Target] för att få ett meddelande om vilken mbox som mobilappsanvändaren har besökt. Allt innehåll hämtas och cachelagras under förhämtningsanropet, och det här innehållet hämtas från cachen för alla framtida anrop som innehåller cachelagrat innehåll för det angivna mbox-namnet.

Tänk på följande begränsningar när du använder förhämtningsmetoden med iOS och Android Mobile SDK:

* Förhämtningsinnehåll bevaras inte vid start. Det förhämtade innehållet cachelagras så länge som programmet finns eller tills `clearPrefetchCache()` -metoden anropas.
* Förhämtningsfunktionen stöds inte för [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] trafiktilldelningsmetoder, för [!UICONTROL Automated Personalization] eller [!UICONTROL Recommendations] aktivitetstyper, eller för [rekommendationer i A/B- eller XT-aktivitet](/help/main/c-recommendations/recommendations-as-an-offer.md).

Mer information, inklusive förhämtningsmetoder, publika klasser och kodexempel finns i:

* **iOS:**  [Förhämta erbjudandeinnehåll i iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) i *Mobile Services iOS SDK - hjälp*.
* **Android:**  [Förhämta erbjudandeinnehåll i Android](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) i *Hjälp för Mobile Services Android SDK*.
