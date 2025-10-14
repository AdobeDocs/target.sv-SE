---
keywords: rekommendationsdesign;skapa design;kopiera design
description: Lär dig hur du skapar en  [!DNL Target Recommendations] design med en standarddesign eller genom att skapa en anpassad design som passar sidans layout bäst.
title: Hur skapar jag en design i rekommendationer?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 0%

---

# Skapa en design

En design definierar hur rekommendationer visas på en sida.

Du kan skapa en [!UICONTROL Recommendations]-design med en standarddesign eller genom att skapa en anpassad design. Skärmen **[!UICONTROL Recommendations > Designs]** visar både standarddesignkort och alla designer som har skapats i ditt konto.

Tänk på följande när du arbetar med design:

* Du kan skapa en rekommendationsdesign med hjälp av en standarddesign eller skapa en anpassad design.
* Du kan inte redigera eller ta bort en standarddesign.
* Du kan redigera, kopiera eller ta bort en anpassad design.
* Om du vill skapa en design baserad på en standarddesign måste du först kopiera designen och sedan redigera kopian.

Bilden visar standarddesignen 1 x 4:

![1 x 4 standarddesign](/help/main/c-recommendations/c-design-overview/assets/default-design.png)

Den här bilden visar en egen design:

![Egen design](/help/main/c-recommendations/c-design-overview/assets/custom-design.png)

Du kan skapa en design när aktiviteten skapas från [!UICONTROL Visual Experience Composer] (VEC) eller från designbiblioteket utanför aktivitetsskapandet. I följande avsnitt antas du skapa designer från biblioteket, men stegen är liknande.

## Skapa designer

Du kan skapa en design baserad på en standarddesign eller skapa en egen design.

### Skapa en design baserad på en standarddesign

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Designs]** för att visa biblioteket [!UICONTROL Designs].


1. Klicka på ikonen Fler åtgärder ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmallList.svg) ) för den design du vill skapa och klicka sedan på **[!UICONTROL Copy]**.

   Dialogrutan [!UICONTROL Create Design] visas.

1. Skriv in en **[!UICONTROL &#x200B; Name]** och en förhandsvisningsbild som du vill visa på designkortet.

   När du använder en standarddesign visas designnamnet och kopian i fältet **[!UICONTROL Content Name]**. Du kan redigera namnet. Du kan också välja en bild som ska visas på designkortet.

1. (Villkorligt) Redigera designen **[!UICONTROL Code]** efter behov.

   I rekommendationsdesignen används designspråket Velocity med öppen källkod. Information om hastighet finns på [https://velocity.apache.org](https://velocity.apache.org) och i [Anpassa en design med Snabb](/help/main/c-recommendations/c-design-overview/customizing-a-template.md).

   En design kan vara HTML eller icke-HTML. Som standard kapslas HTML Designs med taggen `<div>` så att klickspårning kan användas i en webbmiljö. Designer från andra program än HTML är avsedda för icke-webbaserade miljöer där klickspårning inte är möjlig. Dra [!UICONTROL HTML Design]-växeln till avmarkeringspositionen om du vill använda kod som inte är från HTML.

   >[!NOTE]
   >
   >Det maximala antalet enheter som kan refereras i en design, antingen hårdkodade eller via slingor, är 99.

1. Klicka på **[!UICONTROL Create]**.

### Skapa en egen design

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Designs]** för att visa biblioteket [!UICONTROL Designs].

1. Klicka på **[!UICONTROL Create Design]**.

   Om du vill basera din nya anpassade design på en befintlig design klickar du på ikonen [!UICONTROL More Actions] ( ![Fler åtgärder-ikon &#x200B;](/help/main/assets/icons/MoreSmallList.svg) ) för den design du vill skapa och sedan på [!UICONTROL Copy]. Du kan sedan redigera kopian för att skapa en ny anpassad design.

1. Lägg till en **[!UICONTROL Name]** och en valfri förhandsvisningsbild.

1. (Villkorligt) Redigera designen **[!UICONTROL Code]** efter behov.

   Mer information finns i steg 4 ovan.

1. Klicka på **[!UICONTROL Create]**.

## Redigera, kopiera eller ta bort en design

Kom ihåg att du inte kan redigera eller kopiera en standarddesign. Du kan bara kopiera standarddesigner.

Klicka på ikonen [!UICONTROL More Actions] ( ![Fler åtgärder-ikon](/help/main/assets/icons/MoreSmallList.svg) ) för designen som du vill redigera eller ta bort och klicka sedan på lämplig ikon: [!UICONTROL Edit], [!UICONTROL Copy] eller [!UICONTROL Delete].

Du kan kopiera en befintlig design och skapa en dubblettdesign som du sedan kan ändra. Med den här processen kan du enkelt skapa en liknande design.

Observera att det finns design för hela kontot. Se till att du tar hänsyn till användningen mellan konton innan du tar bort en design. Borttagna designer kan inte återställas.

## JSON-exempel {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

I följande exempel visas hur JSON-svar kan returneras när en aktivitet konfigureras via den [formulärbaserade redigeraren](/help/main/c-experiences/form-experience-composer.md).

1. Skapa en design i [!UICONTROL Design library] eller i det formulärbaserade arbetsflödet. Om du försöker skapa en design i arbetsflödet [!UICONTROL Visual Experience Composer] (VEC) kan du inte skapa något annat än en HTML-design, som är inkapslad i en `<div>` för klickningsspårning.

1. Kontrollera att alternativet&quot;HTML Design&quot; är avaktiverat:

   ![html_design_toggle-bild](assets/html_design_toggle.png)

1. Följande kod är ett exempel på vad du kan klistra in i din design:

   ```javascript
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

1. Konfigurera en formulärbaserad [!DNL Recommendations]-aktivitet som använder den här designen.

   1. Navigera till sidan **[!UICONTROL Activities]**.
   1. Klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL Recommendations]**.
   1. Under **[!UICONTROL Choose Experience Composer]** väljer du **[!UICONTROL Form]** och klickar sedan på **[!UICONTROL Next]**.
   1. Ange texten under platsen: &quot;Sample_Recs_Response&quot;
   1. Klicka på nedpilen under **[!UICONTROL Default Content]** och sedan på **[!UICONTROL Add Recommendation]**.
   1. Välj en sidtyp. Detta avgör den inledande filtreringen för nästa skärm.
   1. Välj ett villkorskort och klicka sedan på **[!UICONTROL Next]**.
   1. Markera designen som du skapade i föregående steg och klicka sedan på **[!UICONTROL Next]**.
   1. Slutför installationsprocessen.
   1. Klicka på högerpilen bredvid **[!UICONTROL Inactive]** och välj sedan **[!UICONTROL Activate]**.

1. När din aktivitet har konfigurerats och aktiverats kan du ställa in en exempelbegäran för att få tillbaka det rena JSON-svaret.

   Från den tidpunkt du sparar aktiviteten måste [!DNL Target] skapa en modell som stöder den valda villkorskonfigurationen. Beroende på ett antal faktorer kan den här processen ta lite tid. Resultaten visas när modellen har byggts.

   Exempel:

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   där

   | Parameter | Värde |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | Målklientkod (finns på /help/target/products.html#recsSettings > Recommendations API-token > Klientkod). |
   | `[YOUR_MBOX_NAME]` | Det namn du har valt i avsnittet &quot;locations&quot; i de formulärbaserade rekommendationerna, i det här fallet Sample_Recs_Response. |
   | `[ENTITY_ID` | `entity.id` för ett objekt i katalogen. |
   | `[AT_PROPERTY_TOKEN]` | (Valfritt) Lägg till om du har valt en egenskap (ingår i Enterprise Permissions) under aktivitetsinställningarna. |

När algoritmen har körts och du har fått resultat bör svaret se ut ungefär så här:

![json_recommendation image](assets/json_recommendation.png){width="575px"}

## Ytterligare tips och tricks för JSON-objekt {#section_C305673C68944749969DB239E3221DC2}

Du kan också skicka tillbaka en enkel kommaavgränsad lista med objekt genom att konfigurera en design med följande syntax:

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

Du kan också skicka ytterligare information i svaret. Följande kodfil är ett mer komplext exempel som returnerar mycket mer än enhets-ID:n med associerade platser (ordning). Det här designexemplet returnerar även aktivitetsinformation, [!UICONTROL Target Profile] detaljer (om tillämpligt) och andra `entity.attributes` som är associerade med de returnerade objekten.

```javascript
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

## Utbildningsvideo: Skapa anpassade designer i rekommendationer (3:20) ![Översikt &#x200B;](/help/main/assets/overview.png)

Den här videon innehåller följande information:

* Skapa en egen design
* Förstå hur du refererar till visningsvariabler i dina designer

>[!VIDEO](https://video.tv.adobe.com/v/27687)
