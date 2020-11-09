---
keywords: offer;prefetch;iOS;android;sdk;mobile;mobile sdk
description: Adobe Target förhämtningsfunktion använder iOS och Android Mobile SDK för att hämta innehåll som kan erbjudas så få gånger som möjligt genom att cachelagra serversvaren.
title: Förhämta erbjudandeinnehåll
feature: mobile implementation
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 0%

---


# Förhämta erbjudandeinnehåll{#prefetch-offer-content}

I förhämtningsfunktionen används iOS- och Android-mobilens SDK:er för att hämta innehåll så få gånger som möjligt genom att serversvaren cachelagras. [!DNL Target]

Den här processen minskar inläsningstiden, förhindrar flera nätverksanrop och gör det möjligt [!DNL Target] att meddela vilken mbox mobilappsanvändaren har besökt. Allt innehåll hämtas och cachelagras under förhämtningsanropet, och det här innehållet hämtas från cachen för alla framtida anrop som innehåller cachelagrat innehåll för det angivna mbox-namnet.

Tänk på följande begränsningar när du använder förhämtningsmetoden med iOS- och Android-mobilens SDK:

* Förhämtningsinnehåll bevaras inte vid start. Innehållet i förhämtningen cachas så länge som programmet finns eller tills metoden anropas `clearPrefetchCache()` .
* Förhämtningsfunktionen stöds inte för [!UICONTROL Auto-Allocate] - och [!UICONTROL Auto-Target] trafikallokeringsmetoder, för [!UICONTROL Automated Personalization] - eller [!UICONTROL Recommendations] aktivitetstyper, eller för [rekommendationer i en A/B- eller XT-aktivitet](/help/c-recommendations/recommendations-as-an-offer.md).

Mer information, inklusive förhämtningsmetoder, publika klasser och kodexempel finns i:

* **iOS:**  [Förhämta erbjudandeinnehåll i iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) i hjälpen *för* Mobile Services iOS SDK.
* **Android:**  [Förhämta erbjudandeinnehåll i Android](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) i hjälpen *för Android SDK för* mobiltjänster.
