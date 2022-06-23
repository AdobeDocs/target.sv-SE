---
keywords: mobilapp;mobilapp skicka data;målmobilapp;anpassade användardata för mobilapp;anpassade data för mobilapp
description: Lär dig hur du skickar ytterligare information om platsen eller användaren till Adobe [!DNL Target] som namnvärdespar för att hjälpa er att skapa anpassade målgrupper.
title: Hur skickar jag anpassade användardata i en iOS-app?
feature: Implement Mobile
role: Developer
exl-id: c64219ec-8d60-4d05-b2b8-103e8ffcaefc
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# iOS - skicka anpassade användardata

Du kan skicka ytterligare information om platsen eller användaren till Target som namnvärdespar.

Den här informationen kan användas för att skapa anpassade målgrupper (till exempel användare med fler än 2500 mil) och för rapportering.

Det finns två typer av parametrar som du kan skicka med ett Target-anrop:

* mbox-parametrar

   Mbox-parametrar är inte beständiga mellan sessioner.
* Profilparametrar

   Profilparametrar lagras i besökarprofilens arkiv och är beständiga mellan sessioner. Mbox-parametrar finns inte kvar. Vissa nycklar är reserverade, men både profil- och mbox-parametrar kan vara anpassade nyckel/värde-par.

Även om det finns reserverade nycklar kan både profil- och mbox-parametrar innehålla anpassade nyckel/värde-par.

1. Skapa ordlista.

   Skapa först en ordlista med de värden som du skickar till Target. För enkelhetens skull bör du lägga till det här inuti `welcomeMessageCampaign` så att du inte behöver bekymra dig om omfånget.

   Här följer ett exempel på en ordlista. Du kan kopiera och klistra in den här inuti `(void)welcomeMessageCampaign`. Värdena för tangenter som `userLevel` och `userMiles` är hårdkodade i det här exemplet. Vanligtvis skickar du in motsvarande variabler.

   ```
   NSDictionary *targetParams = [[NSDictionary alloc] initWithObjectsAndKeys: 
                                 @"platinum",@"userLevel", 
                                 @26500,@"userMiles", 
                                 @"1067007",@"entity.id", 
                                 @"dealsapp.qa", @"host", 
                                 @"fashion",@"entity.categoryId", 
                                 @"millenial", @"profile.persona", 
                                 @"cohort_5", @"profile.cohort", 
                                 nil];
   ```

   * Tangenter med prefixprofilen (t.ex. `profile.persona`) lagras i användarens profil.

      Dessa profilattribut kan användas för olika aktiviteter och kanaler.

   * Tangenter som inte har något prefix (t.ex. `userMiles`) är mbox-parametrar.

      De här parametrarna är bara tillgängliga under sessionen.

   * Tangenter med prefixentiteten (till exempel `entity.category.id`) används för produktrekommendationer.

1. Verifiera data.
   1. I programmet `didFinishLaunchingWithOptions`, avkommentera eller lägga till `[ADBMobile setDebugLogging:YES];`.

      Detaljerade felsökningsloggar skrivs ut.
   1. Bygg appen.
   1. Kontrollera att parametrarna skickas i målanropet.

      Sök efter målplatsens namn i felsökningskonsolen. Du kommer att se ett samtal till `YOUR-CLIENT-CODE.tt.omtrdc.net`med alla parametrar som du just har skickat.

      ![](assets/mobile-debug.png)
   Du kan skapa målgrupper och begränsa eller rikta in visningen av innehåll med hjälp av de här parametrarna i Target Standard.
