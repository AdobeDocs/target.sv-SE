---
keywords: recommendations design;create design;copy design
description: En design definierar hur rekommendationer visas på en sida.
title: Skapa en design
uuid: 812258e0-8d28-4ef3-b745-45ed694fcabe
translation-type: tm+mt
source-git-commit: 669160af359972cace9c298aa061fcfa2af69072

---


# ![PREMIUM](/help/assets/premium.png) Skapa en design {#create-a-design}

En design definierar hur rekommendationer visas på en sida.

Du kan skapa en [!UICONTROL Recommendations] design med hjälp av en standarddesign eller genom att skapa en anpassad design. På **[!UICONTROL Recommendations > Designs]** skärmen visas både standarddesignkort och eventuella designer som du har skapat. Det går inte att redigera eller ta bort standarddesigner.

1. På **[!UICONTROL Recommendations > Designs]** skärmen för du musen över kortet för den design du vill skapa.

   ![](assets/Card_CopyDesign.png)

1. Om du vill kopiera och redigera en befintlig symbol klickar du på **[!UICONTROL Copy]** ikonen.

   eller

   Om du vill skapa en egen design klickar du **[!UICONTROL Create Design]** på **[!UICONTROL Recommendations > Designs]** skärmen.

   ![](assets/createDesign.png)

1. Lägg till en **[!UICONTROL Content Name]**.

   När du använder en standarddesign visas designnamnet och &quot;Kopiera&quot; i **[!UICONTROL Content Name]** fältet. Du kan redigera namnet. 1. (Valfritt) Klicka för att välja en bild som ska visas på designkortet.
1. Redigera designen **[!UICONTROL Code]**.

   I rekommendationsdesignen används designspråket Velocity med öppen källkod. Information om hastighet finns på [https://velocity.apache.org](https://velocity.apache.org).

   En design kan vara HTML eller icke-HTML. HTML-design kapslas som standard med en <div> -tagg för klickspårning i en webbmiljö. Icke-HTML-design är avsedd för icke-webbaserade miljöer där klickspårning inte är möjlig.

   >[!NOTE]
   >
   >Det högsta antalet enheter som kan refereras i en design, antingen hårdkodade eller via slingor, är 99.

1. Klicka på **[!UICONTROL Save]**.

## JSON-exempel {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

I följande exempel visas hur JSON-svar kan returneras när en aktivitet konfigureras via den formulärbaserade redigeraren.

1. Skapa en design i designbiblioteket eller i det formulärbaserade arbetsflödet. Om du försöker göra detta i Visual Experience Composer-arbetsflödet (VEC) kan du inte skapa något annat än en HTML-design, som är inkapslad i en `<div>` klickningsspårning.
1. Kontrollera att alternativet &quot;HTML-design&quot; är inaktiverat:

   ![](assets/html_design_toggle.png)

1. Följande kod är ett exempel nedan på vad du kan klistra in i din design:

   ```
       #* 
       * "Return a simple list of recommended entity ids"   
       *#
   
       {   
         "notes":{   
         "purpose": "Return a simple list of recommended entity ids",   
         "use-case": "Use this approach if you prefer to do a real-time lookup of entity attribute details (such as inventory, price, rating) from another system (such as a CMS, PIM or ecommerce platform)",   
         "version": "01"   
         },   
         "recommendedItems": {   
           "key": "$key.id",   
           "slot-01": "$entity1.id",   
           "slot-02": "$entity2.id",   
           "slot-03": "$entity3.id",   
           "slot-04": "$entity4.id",   
           "slot-05": "$entity5.id",   
           "slot-06": "$entity6.id",   
           "slot-07": "$entity7.id",   
           "slot-08": "$entity8.id",   
           "slot-09": "$entity9.id",   
           "slot-10": "$entity10.id"   
         }   
       }  
   ```

1. Ställ in en formulärbaserad rekommendationsaktivitet som använder den här designen.

   1. Navigera till sidan Aktiviteter.
   1. Klicka på **[!UICONTROL Create Activity]**.
   1. Välj **[!UICONTROL Recommendations]**.
   1. Under **[!UICONTROL Choose Experience Composer]** väljer du **[!UICONTROL Form]**.

   1. Ange texten under platsen: &quot;Sample_Recs_response&quot;
   1. Under **[!UICONTROL Default Content]** klickar du på nedpilen och sedan på **[!UICONTROL Add Recommendation]**.
   1. Välj en sidtyp. Detta avgör den inledande filtreringen för nästa skärm.
   1. Välj ett villkorskort och klicka sedan på **[!UICONTROL Next]**.
   1. Markera designen som du skapade i föregående steg och klicka sedan på **[!UICONTROL Save]**.
   1. Slutför installationsprocessen.
   1. Klicka på högerpilen bredvid **[!UICONTROL Inactive]** och välj sedan **[!UICONTROL Activate]**.

1. När din aktivitet har konfigurerats och aktiverats kan du ställa in en exempelbegäran för att få tillbaka det rena JSON-svaret.

   Från den tidpunkt du sparar aktiviteten måste Target skapa en modell som stöder den valda villkorskonfigurationen. Beroende på ett antal faktorer kan detta ta en stund. Resultaten visas när modellen har byggts.

   Exempel:

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   där

| Parameter | Värde |
|--- |--- |
| `[YOUR_CLIENT_CODE]` | Målklientkod (finns på ../target/products.html#recsSettings > Recommendations API Token > Klientkod. |
| `[YOUR_MBOX_NAME]` | Det namn du har valt i avsnittet &quot;locations&quot; i de formulärbaserade rekommendationerna, i det här fallet Sample_Recs_Response. |
| `[ENTITY_ID`] | Objektets namn `entity.id` i katalogen. |
| `[AT_PROPERTY_TOKEN]` | (Valfritt) Lägg till om du har valt en egenskap (ingår i Enterprise Permissions) under aktivitetsinställningarna. |

När algoritmen har körts och du har fått resultat bör svaret se ut ungefär så här:

![](assets/json_recommendation.png){width=&quot;575px&quot;}

## Ytterligare tips och tricks för JSON-objekt {#section_C305673C68944749969DB239E3221DC2}

Du kan också skicka tillbaka en enkel kommaavgränsad lista med objekt genom att konfigurera en design med följande syntax:

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

Du kan också skicka ytterligare information i svaret. Följande kodfil är ett mer komplext exempel som returnerar mycket mer än enhets-ID:n med associerade platser (ordning). Det här designexemplet returnerar även aktivitetsinformation, målprofilinformation (om det är tillämpligt) och andra `entity.attributes` associerade med de returnerade objekten.

```
    {   
     "adobeRecommendations": {   
      "notes": {   
       "purpose": "Return a list of entity ids with their associated entity.attributes",   
       "use-case": "Use this approach to avoid looking up attribute details after receiving a response from Target",   
       "version": "01"   
      },   
      "recommendedItems": {   
       "slot-01": "$entity1.id",   
       "slot-02": "$entity2.id",   
       "slot-03": "$entity3.id",   
       "slot-04": "$entity4.id",   
       "slot-05": "$entity5.id",   
       "slot-06": "$entity6.id",   
       "slot-07": "$entity7.id",   
       "slot-08": "$entity8.id",   
       "slot-09": "$entity9.id",   
       "slot-10": "$entity10.id"   
      },   
      "activityDetails": {   
       "mbox.name": "email-mbox",   
       "campaign.name": "\${campaign.name}",   
       "campaign.id": "\${campaign.id}",   
       "campaign.recipe.name": "\${campaign.recipe.name}",   
       "campaign.recipe.id": "\${campaign.recipe.id}",   
       "offer.name": "\${offer.name}",   
       "offer.id": "\${offer.id}",   
       "criteria.title": "$criteria.title",   
       "algorithm.name": "$algorithm.name",   
       "algorithm.dayCount": "$algorithm.dayCount"   
      },   
      "visitorProfile": {   
       "profile.favorite-category": "\${profile.favorite-category}",   
       "profile.test": "\${profile.test}",   
       "user.endpoint.lastPurchasedEntity": "\${user.endpoint.lastPurchasedEntity}",   
       "user.endpoint.lastViewedEntity": "\${user.endpoint.lastViewedEntity}",   
       "user.endpoint.mostViewedEntity": "\${user.endpoint.mostViewedEntity}",   
       "user.endpoint.categoryAffinity": "\${user.endpoint.categoryAffinity}",   
       "profile.geolocation.city": "\${profile.geolocation.city}",   
       "profile.geolocation.dma": "\${profile.geolocation.dma}",   
       "profile.geolocation.state": "\${profile.geolocation.state}",   
       "profile.geolocation.country": "\${profile.geolocation.country}",   
       "profile.sessionCount": "\${profile.sessionCount}",   
       "profile.averageDaysBetweenVisits": "\${profile.averageDaysBetweenVisits}",   
       "profile.browserTime": "\${profile.browserTime}",   
       "user.activeActivities": "\${user.activeActivities}",   
       "user.pcId": "\${user.pcId}",   
       "user.isFirstSession": "\${user.isFirstSession}",   
       "user.isNewSession": "\${user.isNewSession}",   
       "user.header": "\${user.header}",   
       "user.parameter": "\${user.parameter}"   
      },   
      "recKey": {   
       "recKeyDetails": {   
        "id": "$key.id",   
        "name": "$key.name",   
        "category": "$key.category",   
        "pageUrl": "$key.pageUrl",   
        "thumbnailUrl": "$key.thumbnailUrl"   
       }   
      },   
      "recDetailedResults": {   
       "recEntity1Details": {   
        "id": "$entity1.id",   
        "name": "$entity1.name",   
        "category": "$entity1.category",   
        "pageUrl": "$entity1.pageUrl",   
        "thumbnailUrl": "$entity1.thumbnailUrl"   
       },   
       "recEntity2Details": {   
        "id": "$entity2.id",   
        "name": "$entity2.name",   
        "category": "$entity2.category",   
        "pageUrl": "$entity2.pageUrl",   
        "thumbnailUrl": "$entity2.thumbnailUrl"   
       },   
       "recEntity3Details": {   
        "id": "$entity3.id",   
        "name": "$entity3.name",   
        "category": "$entity3.category",   
        "pageUrl": "$entity3.pageUrl",   
        "thumbnailUrl": "$entity3.thumbnailUrl"   
       },   
       "recEntity4Details": {   
        "id": "$entity4.id",   
        "name": "$entity4.name",   
        "category": "$entity4.category",   
        "pageUrl": "$entity4.pageUrl",   
        "thumbnailUrl": "$entity4.thumbnailUrl"   
       },   
       "recEntity5Details": {   
        "id": "$entity5.id",   
        "name": "$entity5.name",   
        "category": "$entity5.category",   
        "pageUrl": "$entity5.pageUrl",   
        "thumbnailUrl": "$entity5.thumbnailUrl"   
       },   
       "recEntity6Details": {   
        "id": "$entity6.id",   
        "name": "$entity6.name",   
        "category": "$entity6.category",   
        "pageUrl": "$entity6.pageUrl",   
        "thumbnailUrl": "$entity6.thumbnailUrl"   
       },   
       "recEntity7Details": {   
        "id": "$entity7.id",   
        "name": "$entity7.name",   
        "category": "$entity7.category",   
        "pageUrl": "$entity7.pageUrl",   
        "thumbnailUrl": "$entity7.thumbnailUrl"   
       },   
       "recEntity8Details": {   
        "id": "$entity8.id",   
        "name": "$entity8.name",   
        "category": "$entity8.category",   
        "pageUrl": "$entity8.pageUrl",   
        "thumbnailUrl": "$entity8.thumbnailUrl"   
       },   
       "recEntity9Details": {   
        "id": "$entity9.id",   
        "name": "$entity9.name",   
        "category": "$entity9.category",   
        "pageUrl": "$entity9.pageUrl",   
        "thumbnailUrl": "$entity9.thumbnailUrl"   
       },   
       "recEntity10Details": {   
        "id": "$entity10.id",   
        "name": "$entity10.name",   
        "category": "$entity10.category",   
        "pageUrl": "$entity10.pageUrl",   
        "thumbnailUrl": "$entity10.thumbnailUrl"   
       }   
      }   
     }   
    }  
```

## Utbildningsvideo: Skapa egna designer i ikonen Rekommendationer (3:20) ![Översikt](/help/assets/overview.png)

Den här videon innehåller följande information:

* Skapa en egen design
* Förstå hur du refererar till visningsvariabler i dina designer

>[!VIDEO](https://video.tv.adobe.com/v/27687)
