---
keywords: offer;prefetch;iOS;android;sdk;mobile;mobile sdk
description: Adobe Target förhämtningsfunktion använder iOS och Android Mobile SDK för att hämta innehåll som kan erbjudas så få gånger som möjligt genom att cachelagra serversvaren.
title: Förhämta erbjudandeinnehåll
feature: mobile implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 0%

---


# Förhämta innehåll för erbjudande{#prefetch-offer-content}

Funktionen [!DNL Target] för förhämtning använder iOS och Android Mobile SDK:er för att hämta innehåll så få gånger som möjligt genom att cachelagra serversvaren.

Den här processen minskar inläsningstiden, förhindrar flera nätverksanrop och gör att [!DNL Target] kan meddelas vilken mbox som mobilappsanvändaren har besökt. Allt innehåll hämtas och cachelagras under förhämtningsanropet, och det här innehållet hämtas från cachen för alla framtida anrop som innehåller cachelagrat innehåll för det angivna mbox-namnet.

Tänk på följande begränsningar när du använder förhämtningsmetoden med iOS- och Android-mobilens SDK:

* Förhämtningsinnehåll bevaras inte vid start. Förhämtningsinnehållet cachelagras så länge som programmet finns eller tills metoden `clearPrefetchCache()` anropas.
* Förhämtningsfunktionen stöds inte för metoderna [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target] för trafikallokering, för aktivitetstyperna [!UICONTROL Automated Personalization] eller [!UICONTROL Recommendations], eller för [rekommendationer i A/B- eller XT-aktiviteter](/help/c-recommendations/recommendations-as-an-offer.md).

Mer information, inklusive förhämtningsmetoder, publika klasser och kodexempel finns i:

* **iOS:**  [Förhämtning erbjuder innehåll i ](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) iOSi hjälpen *för* Mobile Services iOS SDK.
* **Android:**  [Förhämtning erbjuder innehåll i ](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) Android i hjälpen *för Android på* Mobile Services SDK.
