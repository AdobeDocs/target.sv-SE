---
keywords: mobile;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: I det här avsnittet beskrivs hur du skickar aktivitetsinformation för Adobe Target-mobilappar till Adobe Analytics för postAhoc-segmentering.
title: Skicka Adobe Target aktivitetsinformation till Adobe Analytics
feature: mobile implementation
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---


# Skicka aktivitetsinformation till Adobe Analytics{#send-activity-information-to-adobe-analytics}

I det här avsnittet beskrivs hur du skickar aktivitetsinformation för [!DNL Target] mobilappar till Adobe [!DNL Analytics] för segmentering efter behov.

**Förutsättningar**

* Den här integreringen kräver att [!DNL Analytics] och [!DNL Target] implementeras med mobil-SDK.
* Se till att rapportsviten är aktiverad för att ta emot aktivitetsinformation från [!DNL Target].

   Detta görs vanligtvis genom att lägga till [!DNL Target] klientkoden i [!DNL Analytics] rapportsviten. Detta kan redan vara aktiverat om du använder integreringen SiteCatalyst-Test&amp;Target för webbaktiviteter. Kontakta Adobe kundtjänst om du har några frågor om det här steget.

1. Hämta aktivitetsinformationen.

   Om du inkluderar en sträng som följande i ditt upplevelseinnehåll, [!DNL Target] returnerar aktivitetsinformationen som du kan skicka till [!DNL Analytics]:

   ```
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   Ersätt texten i upplevelsejsonkoden med något av följande exempel:

   ```
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   I det här exemplet läggs en nod med variabeln till för att hämta aktivitetsinformationen. `tntVal` Lägg till liknande kod för de andra upplevelserna, med rätt titel och budskap.

   Den här strängen levererar ett tal (till exempel 115110:0:0) i svaret från [!DNL Target]. Detta anger aktivitets-ID, upplevelse-ID och trafiktyp. Här följer ett exempelsvar från [!DNL Target]:

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Tolka JSON-objektet.

   Tolka svaret som kom tillbaka [!DNL Target] i återanropet. Du kan använda `NSJSONSerialization` för att tolka det här svaret och lagra det i en ordlista eller matris.

   Mer information finns i [NSJSONSerialization-dokumentationen](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) .

1. Skicka data till [!DNL Analytics].

   Lägg till den tolkade aktivitetsinformationen (till exempel i svaret ovan) till kontextdataobjektet i ett `tntVal` [!DNL Analytics] anrop. Det här [!DNL Analytics] anropet som innehåller kontextdata kan utlösas omedelbart eller vänta tills nästa [!DNL Analytics] anrop utlöses.

   Det här anropet kan till exempel utlösas i callback-funktionen för `targetLoadRequest` anropet:

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`är en reserverad händelsenyckel i mobil-SDK. Efterklassificeringen av variabeln `tntVal` i fungerar [!DNL Analytics] på samma sätt i mobil-SDK som i webben (JavaScript). När informationen har bearbetats i [!DNL Analytics]bör du se aktivitets- och upplevelsenamnen i [!DNL Analytics] gränssnittet.

