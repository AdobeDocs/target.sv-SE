---
keywords: Recommendations;settings;preferences;industry vertical;filter incompatible criteria;default host group;thumb base url;recommendations api token
description: Vad du behöver veta innan du skapar en rekommendationsaktivitet.
title: Planera och implementera rekommendationer
uuid: 37be7fb3-3686-4dec-9cca-478d28191985
translation-type: tm+mt
source-git-commit: 96b62977729064da624e3b8fc951bbef3f9a36c1

---


# ![PREMIUM](/help/assets/premium.png) Planera och implementera rekommendationer {#plan-and-implement-recommendations}

Vad du behöver veta innan du skapar en rekommendationsaktivitet.

## Planera och implementera rekommendationer {#concept_02AA644A4C7D4D5CB1D9CADA208CF8D1}

Vad du behöver veta innan du skapar en [!DNL Recommendations] aktivitet.

[!DNL Recommendations] kräver att du ställer in följande informationshierarki:

| Steg | Information | Detaljer |
|--- |--- |--- |
| ![Steg 1](/help/c-recommendations/assets/step1_red.png) | JavaScript-bibliotek | Varje sida kräver en referens till at.js version 0.9.1 (eller senare) eller mbox.js version 55 (eller senare). Det här implementeringssteget krävs på alla sidor där en Target-aktivitet ska användas och kan innehålla nycklar som ett produkt- eller kategori-ID.<BR>Mer information om at.js finns [i implementeringen](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md)av at.js.<br>Mer information om mbox.js finns i Implementering av [Mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md). |
| ![Steg 2](/help/c-recommendations/assets/step2_red.png) | Tangenter | Nyckeln avgör vilken typ av produkt eller innehåll som visas i dina rekommendationer. Nyckeln kan till exempel vara en produktkategori. Se [Basera rekommendationen på en rekommendationsnyckel](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B). |
| ![Steg 3](/help/c-recommendations/assets/step3_red.png) | Attribut | Attribut ger mer specifik information om de produkter som du vill visa. Du kanske vill visa produkter inom ett visst prisintervall, eller artiklar som uppfyller ett lagertröskelvärde. Attribut kan anges i mbox eller via en [feed](/help/c-recommendations/c-products/feeds.md).<br>Se [Inkluderingsregler](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_28DB20F968B1451481D8E51BAF947079) och [Entitetsattribut](/help/c-recommendations/c-products/entity-attributes.md). |
| ![Steg 4](/help/c-recommendations/assets/step4_red.png) | Undantag | Undantag avgör vilka specifika objekt som inte visas i dina rekommendationer.<br>Se [Undantag](/help/c-recommendations/c-products/exclusions.md). |
| ![Steg 5](/help/c-recommendations/assets/step5_red.png) | Inköpsinformation | Inköpsinformationen innehåller information om inköpta artiklar och beställningen när köpet har slutförts. |

## Basimplementering {#concept_D1154A3FB0FB4467A29AD2BDD21C82D5}

Basimplementeringen kräver att du skickar parametrar till sidan som avgör vilka produkter eller tjänster som visas i dina rekommendationer.

Innan du börjar konfigurera en [!DNL Recommendations] aktivitet bör du förstå hur produktdata tillhandahålls [!DNL Recommendations]och bestämma vilken metod som fungerar bäst för dina behov.

Det finns två sätt att tillhandahålla information om produkter och tjänster till [!DNL Recommendations]:

| Metod | Beskrivning |
|--- |--- |
| Skicka parametrar direkt till sidan | Den här metoden fungerar bra för objekt som ändras ofta. Men eftersom det krävs att ändringar görs direkt på sidan måste IT-avdelningen och de personer som implementerar sidorna vara involverade i många organisationer. |
| Skicka parametrar via en Google- eller CSV-feed | Den här metoden fungerar bra för samlingar som inte ändras så ofta. Det är oftast inte nödvändigt att ändra implementeringen eller annan sidkod för att ge produktinformation via en feed. Produktlistan är dock fortfarande statisk, så snabba ändringar är svårare. Mer information finns i [Feeds](/help/c-recommendations/c-products/feeds.md). |

Dessa metoder kan användas separat eller tillsammans, som i följande exempel.

## Exempel ett: Kombinera sidor och feeds {#section_DF6BAE4BF11548BD9C44D0A426BCF5A7}

Ett vanligt [!DNL Recommendations] implementeringsalternativ använder både sidparametrar och feeds.

Den här metoden kan föredras av en återförsäljare som har en relativt angiven produktkatalog, men som kanske vill betona vissa säsongsartiklar eller artiklar som är på rea. De flesta kunder kan tillhandahålla sina uppgifter huvudsakligen via flödet, med endast tillfälliga justeringar på sidan.

Använd en feed för att ange information som inte ändras så ofta. Använd följande parametrar oavsett om du använder en CSV-fil eller Google-feed:

* Obligatoriska parametrar

   * `entity.id`

* Användbara parametrar

   * `entity.name`
   * `entity.categoryId`
   * `entity.brand`
   * `entity.pageUrl`
   * `entity.thumbnailUrl`
   * `entity.message`
   * Alla anpassade attribut

När du har konfigurerat och skickat flödet till [!DNL Recommendations]skickar du parametrar på sidan för attribut som ändras ofta, dvs. oftare än dagligen.

* Obligatoriska parametrar

   * `entity.id`
   * `entity.categoryId`

* Användbara parametrar

   * `entity.inventory`
   * `entity.value`

Den uppsättning med data som körs senast prioriteras. Om du skickar flödet först och sedan uppdaterar sidparametrarna visas de ändringar som har gjorts i sidparametrarna och ersätter den objektinformation som skickas i flödet.

## Exempel två: Skicka alla parametrar på informationssidan för produkten (eller innehållet) {#section_D5A4F69457604CA7AACFD7BFF79B58A9}

Om du skickar alla parametrar på sidan kan du snabbt göra uppdateringar genom att uppdatera sidan. I vissa organisationer kräver detta att IT-avdelningen eller webbdesignteamet är engagerade.

Det här exemplet kan vara särskilt användbart för medieföretag med innehåll som ändras kontinuerligt.

* Obligatoriska parametrar

   * `entity.id`
   * `entity.categoryId`
   * Alla andra attribut

## Exempelkod {#section_6E8A73376F30468BB549F337C4C220B1}

Du kan till exempel använda följande kod i rubrikavsnittet på produkt- eller innehållssidorna:

```
function targetPageParams() {
 return {
    "entity": {
       "id": "32323",
       "categoryId": "My Category",
       "value": 105.56,
       "inventory": 329
    }
 }
}
```

Fler exempel på koden som du kan använda på olika typer av sidor finns i [Implementering enligt sidtyp](../c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC).

## Implementering enligt sidtyp {#reference_DE38BB07BD3C4511B176CDAB45E126FC}

Sidtypen påverkar [!DNL Recommendations] implementeringen.

De typer av rekommendationer du vill presentera kan till exempel vara annorlunda på en produktsida än på en kategorisida eller din hemsida. För varje sida kan du köra specifika funktioner före mbox-anropet för att visa lämpliga rekommendationer.

Mer information om attributen i exemplen finns i [Entitetsattribut](../c-recommendations/c-products/entity-attributes.md#reference_3BCC1383FB3F44F4A2120BB36270387F).

Giltig JSON-formatering krävs.

Funktionen `targetPageParams` som visas nedan är särskilt användbar om du använder en tagghanteringslösning för att implementera sidorna. [!DNL Adobe Launch] eller [!DNL Adobe Dynamic Tag Manager] (DTM) placerar at.js/mbox.js och `targetPageParams` funktionen på sidan och gör att du kan konfigurera värdena. Du bör antingen placera den funktionen före ditt at.js/mbox.js eller placera den i avsnittet Extra JavaScript i din at.js/mbox.js.

## Alla sidor {#section_A22061788BAB42BB82BA087DEC3AA4AD}

Alla sidor som innehåller rekommendationer kräver antingen en [!DNL at.js] referens eller en [!DNL mbox.js] referens på sidan. Lägg till en av följande referenser på alla sidor med rekommendationer:

```
<script src="../at.js /></script>
```

```
<script src="../mbox.js /></script>
```

Implementeringen kräver:

* [!DNL at.js] version 0.9.2 (eller senare) eller [!DNL mbox.js] version 55 (eller senare)

* [!DNL mbox.js] måste innehålla en referens till [!DNL target.js] (kräver [!DNL at.js] ingen referens till [!DNL target.js])

Mer information om implementering [!DNL at.js]finns i [Distribuera at.js](../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md#topic_ECF2D3D1F3384E2386593A582A978556).

Mer information om implementering [!DNL mbox.js]finns i Implementering av [Mbox.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).

Mer information om skillnaderna mellan de två Target JavaScript-biblioteken finns i [Fördelar med at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits).

## Kategorisida {#section_F51A1AAEAC0E4B788582BBE1FEC3ABDC}

På en kategorisida vill du antagligen begränsa dina rekommendationer till produkter eller innehåll i den kategorin. Om du vill konfigurera en kategorisida anger du de tangenter som används av sidan. Mer information om nycklar finns i [Basera rekommendationen på en rekommendationsnyckel](../c-recommendations/c-algorithms/create-new-algorithm.md#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B).

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": "My Category" 
      } 
   } 
}
```

## Produktsida {#section_205B3953C9664125A17CA8574FA6B2A3}

På en produktsida kanske du vill rekommendera specifika artiklar, eller artiklar med ett visst pris eller lagernivå. För en produktsida kan du behöva ställa in attribut som ändras ofta (till exempel värde och lager), utöver de nycklar som krävs för en kategorisida.

```
function targetPageParams() { 
   return { 
      "entity": { 
         "id": "32323", 
         "categoryId": "My Category", 
         "value": 105.56, 
         "inventory": 329 
      } 
   } 
}
```

## Kundsida {#section_D37E48700F074556B925D0CA0291405E}

På en kundvagnssida vill du förmodligen utesluta vissa artiklar från dina rekommendationer, till exempel de som redan finns i kundvagnen.

```
<script type="text/javascript">
function targetPageParams() {
   return {
      "excludedIds": [352, 223, 23432, 432, 553]
      }
}
</script>
```

## Tack {#section_C6126A4517A1478693AB7EC2A1D4ACCA}

På sidan Tack kanske du vill visa ordersumman och beställnings-ID:t och visa de produkter som köpts, utan att rekommendera ytterligare artiklar. Du kan implementera en andra mbox för att hämta orderinformationen.

* Om du använder at.js läser du [Spåra konverteringar](../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).
* Om du använder mbox.js läser du [Skapa en mbox med orderbekräftelse - mbox.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/orderconfirm-create.md#task_0036D5F6C062442788BB55E872816D82).

## Inställningar {#concept_C1E1E2351413468692D6C21145EF0B84}

Använd inställningarna för att hantera [!DNL Recommendations] implementeringen.

Du öppnar [!UICONTROL Recommendations Settings] alternativen genom att öppna [!DNL Target] i [!DNL Adobe Experience Cloud]och sedan klicka **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**.

![](assets/recs_settings.png)

Följande alternativ är tillgängliga:

| Inställning | Beskrivning |
|--- |--- |
| Anpassad global mbox | (Valfritt) Ange den anpassade globala mbox som används för [!DNL Target] aktiviteter. Som standard används den globala mbox som används av [!DNL Target} för [!DNL Recommendations].<br>Obs! Det här alternativet är inställt på [!DNL Target][!UICONTROL Setup] sidan. Öppna [!DNL Target]och klicka sedan på [!UICONTROL Setup]. |
| Branschvertikal | Branschvertikalen används för att kategorisera era era rekommendationer. Detta hjälper teammedlemmarna att hitta kriterier som passar en viss sida, till exempel kriterier som passar bäst för kundvagnssidan eller för en mediesida. |
| Filtrera inkompatibla villkor | Aktivera det här alternativet om du bara vill visa de villkor där den valda sidan skickar de data som krävs. Alla villkor fungerar inte korrekt på alla sidor. Sidan eller mbox måste skickas `entity.id` eller `entity.categoryId` för att aktuella artikel/aktuella kategorirekommendationer ska vara kompatibla. I allmänhet är det bäst att bara visa kompatibla villkor. Om du vill att inkompatibla villkor ska vara tillgängliga för aktiviteten avmarkerar du det här alternativet.<br>Du bör inaktivera det här alternativet om du använder en tagghanteringslösning.<br>Mer information om det här alternativet finns i Vanliga frågor om [rekommendationer](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md). |
| Standardvärdgrupp | Välj din standardvärdgrupp. Ingen innebär att standardvärdgruppen för rapportinställningen i [!DNL Target Classic] används för standardvärdgruppen.<br>Värdgruppen kan användas för att skilja de tillgängliga objekten i katalogen åt för olika användningsområden. Du kan till exempel använda värdgrupper för utvecklings- och produktionsmiljöer, olika varumärken eller olika geografiska platser. Som standard baseras förhandsgranskningsresultaten i Katalogsökning, Samlingar och Undantag på standardvärdgruppen. (Du kan också välja en annan värdgrupp om du vill förhandsgranska resultaten med hjälp av miljöfiltret.) Som standard är nyligen tillagda objekt tillgängliga i alla värdgrupper om inte ett miljö-ID anges när objektet skapas eller uppdateras. Levererade rekommendationer beror på värdgruppen som anges i begäran.<br>Om du inte ser dina produkter bör du kontrollera att du använder rätt värdgrupp. Om du t.ex. har konfigurerat din rekommendation att använda en mellanlagringsmiljö och du har angett mellanlagringsgruppen som värdgrupp kan du behöva återskapa dina samlingar i mellanlagringsmiljön för att produkterna ska kunna visas. Om du vill se vilka produkter som är tillgängliga i respektive miljö använder du Katalogsökning för varje miljö. Du kan också förhandsgranska innehållet i Rekommendationer-samlingar och undantag för en vald miljö (värdgrupp).<br>**Obs!**När du har ändrat den valda miljön måste du klicka på Sök för att uppdatera de returnerade resultaten.<br>Filtret är tillgängligt från följande platser i[!UICONTROL Environment][!DNL Target]gränssnittet:<ul><li>Katalogsökning ([!UICONTROL Recommendations > Katalogsökning)</li><li>Dialogrutan Skapa samling ([!UICONTROL Recommendations > Collections > Create New])</li><li>Dialogrutan Uppdatera samling ([!UICONTROL Recommendations > Collections > Edit])</li><li>Dialogrutan Skapa undantag ([!UICONTROL Recommendations > Exclusions > Create New])</li><li>Dialogrutan Uppdatera undantag ([!UICONTROL Recommendations > Exclusions > Edit])</li></ul>Mer information finns i [Värdar](/help/administrating-target/hosts.md). |
| Bas-URL för miniatyrbild | Genom att ange en bas-URL för din produktkatalog kan du använda relativa URL-adresser när du anger miniatyrbilder för dina produkter när du skickar en miniatyrbilds-URL.<br>Till exempel:<br>`"entity.thumbnailURL=/Images/Homepage/product1.jpg"`<br>anger en URL som är relativ till miniatyrbildens bas-URL. |
| API-token för rekommendationer | Använd denna token i API-anrop för rekommendationer, till exempel API för hämtning. |
