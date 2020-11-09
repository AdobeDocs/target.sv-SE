---
keywords: mobile app;mobile app location;target mobile app;mobile target locations;mobile app success metrics
description: Om du vill använda Target i din mobilapp skapar du en plats och ett framgångsmått.
title: iOS - skapa en målplats och ett framgångsmått
feature: mobile implementation
topic: Target
uuid: dc39260c-8222-42b3-9f6b-f83be30e3210
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 0%

---


# iOS - skapa en målplats och ett framgångsmått{#ios-create-a-target-location-and-success-metric}

Om du vill använda Target i din mobilapp skapar du en plats och ett framgångsmått.

Det här avsnittet innehåller exempelkod som kan användas som mall för ditt program. Exemplen i det här avsnittet innehåller kod för iOS. Samma mönster gäller för Android. Android-specifik syntax finns i [Android SDK 4.x for Experience Cloud Solutions](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/target-main.html) guide.

>[!NOTE]
>
>En lista med alla tillgängliga Target-metoder finns i dokumentationen [för](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-target-methods.html) Mobile.

Det finns två primära metoder för att skapa en målplats i din app och göra en begäran:

* `targetCreateRequestWithName`
* `targetLoadRequest`

1. Skapa en målplats.

   Här följer ett exempel på ett anrop för att skapa en begäran:

   ```
   // make your request 
   ADBTargetLocationRequest *myRequest = [ADBMobile targetCreateRequestWithName:@"heroBanner" 
                                                    defaultContent:@"default.png" 
                                                    parameters:nil];
   ```

   | Parameter | Beskrivning |
   |---|---|
   | `ADBTargetLocationRequest *myRequest` | Ersätt `myRequest` med namnet på din `targetLocation` i appen. |
   | `targetCreateRequestWithName:@"heroBanner"` | Ersätt `heroBanner` med namnet på din `targetLocation` i Target. Detta är samma som mbox-namnet. Den här hjältebanderollen visas i Target-gränssnittet. |
   | `defaultContent:@"default.png"` | Ersätt `default.png` med det värde som appen använder om Target inte svarar. |
   | `parameters:nil` | Ange profil- eller mbox-parametrar. Mer information finns i avsnittet&quot;Skicka anpassade data&quot;. |

   Här följer ett exempel på ett anrop för att läsa in begäran:

   ```
   // load your request 
   [ADBMobile targetLoadRequest:myRequest callback:^(NSString *content) { 
                                        // do something with content 
                                        heroImage.image = [UIImage imageNamed:content]; 
   }];
   ```

   | Parameter | Beskrivning |
   |---|---|
   | `targetLoadRequest:myRequest` | Ersätt `myRequest` med namnet på din `targetLocation` i appen. |
   | `NSString *content` | Ersätt innehåll med det faktiska innehåll som kommer tillbaka från Adobe. Strängen kan vara XML, JSON eller en oformaterad sträng. Använd det här avsnittet av koden för att definiera variabler, ange bildsökvägar, visa styrenhetsflöden, transaktionspunkter eller annat som du vill göra. Målet returnerar innehållet som anges i användargränssnittet i exakt samma format. |
   | `heroImage.image = [UIImage imageNamed:content];` | Till exempel: Ta innehåll och ange vägen till en hjältebild. |

1. Skapa ett framgångsmått.

   Metoden `targetCreateOrderConfirmRequestWithName` kan användas för att spåra ett konverterings-/framgångsmått i din app.

   ```
   ADBTargetLocationRequest *req = [ADBMobile targetCreateOrderConfirmRequestWithName: "orderConfirm" 
                                              orderId: orderId 
                                              orderTotal: @"39.95" 
                                              productPurchasedId: _galleryItem.title 
                                              parameters: nil]; 
   [ADBMobile targetLoadRequest: req callback: nil];
   ```

   | Parameter | Beskrivning |
   |---|---|
   | `orderId` | Ersätt med en dynamisk variabel som representerar ett unikt order-ID. |
   | `@"39.95"` | Ersätt med en dynamisk variabel som representerar en unik ordersumma. |
   | `_galleryItem.title` | Ersätt med en dynamisk variabel som representerar en kommaavgränsad lista över köpta produkter. |
   | `parameters: nil` | Valfri ordlista med ytterligare parametrar. |

1. Bygg appen.

   Stegresultat Skapa ett A/B-test när du har skapat en målplats och taggat ett framgångsmått. Aktiviteten kan skapas med den formulärbaserade upplevelsedispositionen.
