---
keywords: mobil;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: I det här avsnittet beskrivs hur du skickar aktivitetsinformation för Adobe Target-mobilappar till Adobe Analytics för postAhoc-segmentering.
title: Skicka aktivitetsinformation till Adobe Analytics
feature: Implement Mobile
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---


# Skicka aktivitetsinformation till Adobe Analytics{#send-activity-information-to-adobe-analytics}

I det här avsnittet beskrivs hur du skickar [!DNL Target] aktivitetsinformation för mobilappar till Adobe [!DNL Analytics] för segmentering efter behov.

**Förutsättningar**

* Den här integreringen kräver att [!DNL Analytics] och [!DNL Target] implementeras med mobil-SDK.
* Kontrollera att rapportsviten är aktiverad för att ta emot aktivitetsinformation från [!DNL Target].

   Detta görs vanligtvis genom att lägga till [!DNL Target]-klientkoden i [!DNL Analytics]-rapportsviten. Detta kan redan vara aktiverat om du använder integreringen SiteCatalyst-Test&amp;Target för webbaktiviteter. Kontakta Adobe kundtjänst om du har några frågor om det här steget.

1. Hämta aktivitetsinformationen.

   Om du inkluderar en sträng som följande i ditt upplevelseinnehåll returnerar [!DNL Target] aktivitetsinformationen som du kan skicka till [!DNL Analytics]:

   ```javascript
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   Ersätt texten i upplevelsejsonkoden med något av följande exempel:

   ```javascript
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   I det här exemplet läggs en nod med variabeln `tntVal` till för att hämta aktivitetsinformationen. Lägg till liknande kod för de andra upplevelserna, med rätt titel och budskap.

   Strängen levererar ett tal (till exempel 115110:0:0) i svaret från [!DNL Target]. Detta anger aktivitets-ID, upplevelse-ID och trafiktyp. Nedan följer ett exempelsvar från [!DNL Target]:

   ```javascript
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Tolka JSON-objektet.

   Tolka svaret som kom tillbaka från [!DNL Target] i återanropet. Du kan använda `NSJSONSerialization` för att tolka det här svaret och lagra det i en ordlista eller matris.

   Mer information finns i [NSJSONSerialization-dokumentationen](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error).

1. Skicka data till [!DNL Analytics].

   Lägg till den tolkade aktivitetsinformationen (till exempel `tntVal` i ovanstående svar) till kontextdataobjektet i ett [!DNL Analytics]-anrop. Det här [!DNL Analytics]-anropet som innehåller kontextdata kan utlösas omedelbart eller vänta tills nästa [!DNL Analytics]-anrop utlöses.

   Det här anropet kan till exempel utlösas i återanropet för `targetLoadRequest`-anropet:

   ```javascript
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`är en reserverad händelsenyckel i mobil-SDK. Efterklassificeringen av variabeln `tntVal` i [!DNL Analytics] fungerar på samma sätt i den mobila SDK:n som den gör på webben (JavaScript). När informationen har bearbetats i [!DNL Analytics] bör du visa aktivitets- och upplevelsenamnen i [!DNL Analytics]-gränssnittet.

