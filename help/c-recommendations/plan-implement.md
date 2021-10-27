---
keywords: Recommendations;settings;preferences;industry vertical;filter inkompatibla villkor;default host group;thumb base url;recommendations api token
description: 'Lär dig implementera Recommendations-aktiviteter i Adobe Target. '
title: Hur genomför jag Recommendations-aktiviteter?
feature: Recommendations
exl-id: b6edb504-a8b6-4379-99c1-6907e71601f9
source-git-commit: 1128d4b2d29f78492e5a5ec420c1177aec8d9e75
workflow-type: tm+mt
source-wordcount: '1505'
ht-degree: 0%

---

# ![PREMIUM](/help/assets/premium.png) Planera och implementera [!DNL Recommendations]

Innan du konfigurerar [!DNL Recommendations] aktivitet i [!DNL Adobe Target]utför du följande steg:

1. [Implementera [!DNL Target]](#implement-target) på de webbsidor och mobilappar som du vill använda för att fånga upp användarbeteenden och leverera rekommendationer.
1. [Konfigurera [!DNL Recommendations] katalog](#rec-catalog) av produkter eller innehåll som du vill rekommendera dina användare.
1. [Överför beteendeinformation och sammanhang](#pass-behavioral) till [!DNL Target Recommendations] för att kunna leverera personaliserade rekommendationer.
1. [Konfigurera globala undantag](#exclusions).
1. [Konfigurera [!DNL Recommendations] inställningar](#concept_C1E1E2351413468692D6C21145EF0B84).

## Implementera [!DNL Target] {#implement-target}

[!DNL Target Recommendations] kräver att du implementerar [!DNL Adobe Experience Platform Web SDK] eller at.js 0.9.2 (eller senare). Se [Implementera [!DNL Target]](/help/c-implementing-target/implementing-target.md) för mer information.

## Konfigurera din Recommendations-katalog {#rec-catalog}

För att kunna leverera högkvalitativa rekommendationer [!DNL Target] måste känna till vilka produkter eller vilket innehåll du vill rekommendera. Katalogen bör vanligtvis innehålla tre typer av information om de objekt som du vill rekommendera. Anta att du rekommenderar filmer. Inkludera följande:

1. Data som du vill visa för användaren som tar emot rekommendationen. Du kan till exempel visa namnet på filmen och en URL för en miniatyrbild av filmminiatyren.
1. Data som är användbara för att tillämpa marknadsförings- och marknadsföringskontroller. Du kan till exempel visa filmens klassificering så att du inte rekommenderar NC-17-filmer.
1. Data som är användbara när du vill fastställa likheter mellan objekt och andra objekt. Du kan till exempel visa filmens genre och filmens regissör.

[!DNL Target] har flera integreringsalternativ för att fylla i katalogen. Dessa alternativ kan användas tillsammans för att uppdatera olika objekt i katalogen eller för att uppdatera olika objektattribut för olika frekvenser.

| Metod | Vad det är | När ska den användas | Ytterligare information |
| --- | --- | --- | --- |
| Katalogfeed | Schemalägg en feed (CSV, Google Product XML eller [!DNL Analytics Product Classifications]) som ska överföras och förtäras dagligen. | Om du vill skicka information om flera objekt samtidigt. För att skicka information som ändras sällan. | Se [Feeds](/help/c-recommendations/c-products/feeds.md). |
| Entiteter-API | Anropa ett API för att skicka uppdateringar som är aktuella för ett enskilt objekt. | För att skicka uppdateringar när de inträffar, ungefär ett objekt i taget. För att skicka information som ändras ofta (till exempel pris, lager/lagernivå). | Se [Dokumentation för utvecklare av entitets-API](https://developers.adobetarget.com/api/recommendations/#tag/Entities). |
| Skicka uppdateringar på sidan | Skicka uppdateringarna till de allra senaste för ett enskilt objekt med JavaScript på sidan eller med hjälp av leverans-API:t. | För att skicka uppdateringar när de inträffar, ungefär ett objekt i taget. För att skicka information som ändras ofta (till exempel pris, lager/lagernivå). | Se [Artikelvyer/produktsidor](#items-product-pages) nedan. |

De flesta kunder bör implementera minst en feed. Du kan sedan välja att komplettera din feed med uppdateringar för ofta ändrade attribut eller objekt med hjälp av antingen Entity API eller on-the-page method.

## Överför beteendeinformation och sammanhang {#pass-behavioral}

Den beteendeinformation och det sammanhang som du bör skicka till [!DNL Target] beror på vad besökaren gör, vilket ofta är kopplat till den typ av sida som besökaren interagerar med.

### Artikelvyer/produktsidor {#items-product-pages}

På sidor där en besökare visar ett enstaka objekt, till exempel en produktinformationssida, bör du skicka identiteten för det objekt som besökaren visar. Du bör även skicka den mest detaljerade kategorin av objektet som besökaren visar, så att filterrekommendationer tillåts till den aktuella kategorin.

Du kan också skicka vissa attribut som snabbt ändras på själva produktsidan. Du kan till exempel skicka priset (`value`) och lager/lagernivå.

```
<script type="text/javascript">
function targetPageParams() { 
   return { 
      "entity": { 
         "id": "32323", 
         "categoryId": "running-shoes", 
         "value": 119.99, 
         "inventory": 329 
      } 
   } 
}
</script>
```

### Kategorivyer/kategorisidor

På en kategorisida vill du troligtvis begränsa dina rekommendationer till produkter eller innehåll i den kategorin. Om du vill göra det måste du skicka identiteten för den kategori som visas.

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": "running-shoes" 
      } 
   } 
}
```

### Vyer/utcheckningssidor för kundvagn {#cart}

På en kundvagnssida kan du rekommendera artiklar baserat på innehållet i besökarens aktuella kundvagn. Om du vill göra det skickar du ID:n för alla objekt i besökarens kundvagn med hjälp av den särskilda parametern `cartIds`.

```
function targetPageParams() {
   return {
      "cartIds": ["352", "223", "23432", "432", "553"]
      }
}
```

Cart-baserad rekommendationslogik liknar den[!UICONTROL Recommended For You]användarbaserad algoritm och till[!UICONTROL People Who Viewed These, Bought Those]&quot; och &quot;[!UICONTROL People Who Bought These, Bought Those]objektbaserade algoritmer.

[!DNL Target] använder tekniker för samverkansfiltrering för att fastställa likheter för varje objekt i besökarens kundvagn, och kombinerar sedan dessa beteendelikheter för varje objekt för att få en sammanfogad lista.

[!DNL Target] ger även marknadsförarna möjlighet att se besökarnas beteende i en eller flera sessioner:

* **Inom en enda session**: Baserat på vad andra besökare gjorde under en och samma session.

* **Över flera sessioner**: Baserat på vad andra besökare gjorde under flera sessioner. 

Oavsett om du tittar på besökarnas beteende under en eller flera sessioner, [!DNL Target] rekommenderar besökaren baserat på artiklarna i kundvagnen.

Om du tittar på beteenden under en session kan det verka klokt om du tycker att produkter &quot;passar ihop&quot; baserat på användning, tillfälle eller händelse. En besökare köper till exempel en skrivare och kan även behöva bläck och papper. Eller så köper besökaren jordnötssmör och behöver bröd och gelé.

Om du tittar på beteenden i flera sessioner kan det vara bra om det finns en känsla av att produkterna&quot;följer med&quot; varandra baserat på besökarens önskemål eller smak. En besökare gillar till exempel Star Wars och kan också gilla Indiana Jones, även om besökaren inte nödvändigtvis vill se båda filmerna på samma plats. Eller så tycker en besökare om styrelsemötet&quot;Codenames&quot; och kanske också om styrelsemötet&quot;Avalon&quot;, även om besökaren inte kan spela båda spelen samtidigt.

### Uteslut artiklar som redan finns i besökarens kundvagn

På sidor på hela webbplatsen kan du utesluta vissa objekt från rekommendationerna. Du kanske inte vill rekommendera artiklar som redan finns i besökarens kundvagn. Om du vill göra det skickar du ID:n för alla objekt som du vill utesluta med den speciella parametern `excludedIds`.

```
function targetPageParams() {
   return {
      "excludedIds": ["352", "223", "23432", "432", "553"]
      }
}
```

### Bekräftelsesidor för inköp/beställning

När en köphändelse inträffar skickar du identiteten för den eller de köpta artiklarna. Se [Spåra konverteringar](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053) in *Implementera [!DNL Target] utan tagghanterare*.

## Konfigurera globala undantag {#exclusions}

Uteslut alla objekt på global nivå som du aldrig vill rekommendera en besökare. Se [Undantag](/help/c-recommendations/c-products/exclusions.md).

## Konfigurera [!DNL Recommendations] inställningar {#concept_C1E1E2351413468692D6C21145EF0B84}

Använd inställningarna för att hantera [!DNL Recommendations] implementering.

Så här öppnar du [!UICONTROL Recommendations Settings] alternativ, öppna [!DNL Target] i [!DNL Adobe Experience Cloud]och sedan klicka **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**.

![](assets/recs_settings.png)

Följande alternativ är tillgängliga:

| Inställning | Beskrivning |
|--- |--- |
| Anpassad global Mbox | (Valfritt) Ange den anpassade globala mbox som används för att hantera [!DNL Target] verksamhet. Som standard används den globala mbox som [!DNL Target] används för [!DNL Recommendations].<br>Obs! Det här alternativet är inställt på [!DNL Target] [!UICONTROL Administration] sida. Öppna [!DNL Target]och sedan klicka [!UICONTROL Administration] > [!UICONTROL Visual Experience Composer]. |
| Branschvertikal | Branschvertikalen används för att kategorisera era era rekommendationer. Den här informationen hjälper teammedlemmarna att hitta kriterier som passar en viss sida, till exempel kriterier som passar bäst för kundvagnssidan eller för en mediesida. |
| Filtrera inkompatibla villkor | Aktivera det här alternativet om du bara vill visa de villkor där den valda sidan skickar de data som krävs. Alla villkor fungerar inte korrekt på alla sidor. Sidan eller mbox måste skickas `entity.id` eller `entity.categoryId` för aktuell artikel/aktuella kategorirekommendationer att vara kompatibla. I allmänhet är det bäst att bara visa kompatibla villkor. Om du vill att inkompatibla villkor ska vara tillgängliga för aktiviteten avmarkerar du det här alternativet.<br>Du bör inaktivera det här alternativet om du använder en tagghanteringslösning.<br>Mer information om det här alternativet finns i [Recommendations FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md). |
| Standardvärdgrupp | Välj din standardvärdgrupp.<br>Värdgruppen kan användas för att skilja de tillgängliga objekten i katalogen åt för olika användningsområden. Du kan till exempel använda värdgrupper för utvecklings- och produktionsmiljöer, olika varumärken eller olika geografiska platser. Som standard baseras förhandsgranskningsresultaten i Katalogsökning, Samlingar och Undantag på standardvärdgruppen. (Du kan också välja en annan värdgrupp om du vill förhandsgranska resultaten med hjälp av miljöfiltret.) Som standard är nyligen tillagda objekt tillgängliga i alla värdgrupper om inte ett miljö-ID anges när objektet skapas eller uppdateras. Levererade rekommendationer beror på värdgruppen som anges i begäran.<br>Om du inte ser dina produkter bör du kontrollera att du använder rätt värdgrupp. Om du t.ex. har konfigurerat din rekommendation att använda en mellanlagringsmiljö och du har angett mellanlagringsgruppen som värdgrupp kan du behöva återskapa dina samlingar i mellanlagringsmiljön för att produkterna ska kunna visas. Om du vill se vilka produkter som är tillgängliga i respektive miljö använder du Katalogsökning för varje miljö. Du kan också förhandsgranska innehållet i Recommendations-samlingar och undantag för en vald miljö (värdgrupp).<br>**Obs!** När du har ändrat den valda miljön måste du klicka på Sök för att uppdatera de returnerade resultaten.<br>The [!UICONTROL Environment] filtret är tillgängligt från följande platser i [!DNL Target] Gränssnitt:<ul><li>Katalogsökning ([!UICONTROL Recommendations] > Katalogsökning)</li><li>Dialogrutan Skapa samling ([!UICONTROL Recommendations > Collections > Create New])</li><li>Uppdatera samling, dialogruta ([!UICONTROL Recommendations > Collections > Edit])</li><li>Dialogrutan Skapa undantag ([!UICONTROL Recommendations > Exclusions > Create New])</li><li>Dialogrutan Uppdatera undantag ([!UICONTROL Recommendations > Exclusions > Edit])</li></ul>Mer information finns i [Värdar](/help/administrating-target/hosts.md). |
| Bas-URL för miniatyrbild | Genom att ange en bas-URL för din produktkatalog kan du använda relativa URL-adresser när du anger miniatyrbilder för dina produkter när du skickar en miniatyrbilds-URL.<br>Till exempel:<br>`"entity.thumbnailURL=/Images/Homepage/product1.jpg"`<br>anger en URL som är relativ till miniatyrbildens bas-URL. |
| Recommendations API-token | Använd denna token i Recommendations API-anrop, till exempel Download API. |
