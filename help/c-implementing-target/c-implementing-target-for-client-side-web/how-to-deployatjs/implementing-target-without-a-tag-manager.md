---
keywords: order confirmation;orderConfirmPage
description: Information om hur du implementerar Adobe Target utan att använda en tagghanterare (Adobe Launch eller Dynamic Tag Management).
title: Implementera mål utan tagghanterare
subtopic: Getting Started
topic: Standard
uuid: 3ecc041a-42d8-40f8-90be-7856e1d3d080
translation-type: tm+mt
source-git-commit: ff3e0d7baacc149e53641f0340dded3a310c60f9

---


# Implementera mål utan tagghanterare{#implement-target-without-a-tag-manager}

Information om implementering [!DNL Adobe Target] utan tagghanterare (Adobe Launch eller Dynamic Tag Management).

## Implementera mål utan tagghanterare {#topic_397FFA3D6918456BBE02A9FBE9537894}

Information om hur du implementerar Adobe Target utan att använda en tagghanterare (Adobe Launch eller Dynamic Tag Management).

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) är den bästa metoden för att implementera Target och biblioteket at.js. Följande information gäller inte när Adobe Launch används för att implementera Target.

## at.js-konfigurationer {#concept_2FA0456607D04F82B0539C5BF5309812}

Information som hjälper dig att ange flera inställningar på sidan med at.js-inställningar.

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) är den bästa metoden för att implementera Target och biblioteket at.js. Följande information gäller inte när Adobe Launch används för att implementera Target.

>[!NOTE]
>
>Du kan åsidosätta inställningarna i at.js-biblioteket i stället för att konfigurera inställningarna i gränssnittet för Target Standard/Premium eller genom att använda REST API:er. Mer information finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

Så här öppnar du [!UICONTROL sidan Inställningar] :

1. Klicka på **[!UICONTROL Inställningar]** > **[!UICONTROL Implementering]**.
1. Välj **[!UICONTROL at.js]** > **[!UICONTROL Redigera at.js-inställningar]**.

## Inställningar för innehållsleverans {#section_118D290DFC444509AD8E4AE86C9D92C0}

Kontakta kundtjänst innan du ändrar inställningarna. De här inställningarna krävs för de flesta implementeringar.

| Inställning | Beskrivning |
|--- |--- |
| Skapa global mbox automatiskt | Välj om du vill bädda in det globala mbox-anropet i filen at.js så att det automatiskt utlöses vid varje sidinläsning.<br>Om du ändrar den här inställningen påverkas både at.js och mbox.js. |
| Namn på global mbox | Välj ett namn för den globala mbox-filen. Som standard är namnet target-global-mbox.<br>Specialtecken, inklusive et-tecken (&amp;), kan användas i mbox-namn med at.js.<br>Om du ändrar den här inställningen påverkas både at.js och mbox.js. |

## Avancerade inställningar {#section_33B697B77BA64A01B5939D7EC75231F2}

| Inställning | Beskrivning |
|--- |--- |
| Klientkod | Klientkoden är en klientspecifik teckensekvens som ofta krävs när du använder mål-API:er.<br>Den här inställningen kan inte ändras. |
| IMS-organisations-ID | Detta ID kopplar implementeringen till ditt [!DNL Adobe Experience Cloud] konto.<br>Den här inställningen kan inte ändras. |
| Profilens livstid | Den här inställningen avgör hur långa besökarprofiler lagras. Som standard lagras profiler i två veckor. Denna kan ökas upp till 90 dagar.<br>Om du vill ändra inställningen för Profilens livstid kontaktar du [kundtjänst](https://helpx.adobe.com/contact/enterprise-support.ec.html). |
| X-domän | Avgör om webbläsaren ställer in cookies i din egen domän (cookies från första part), målets domän eller både och.<br>Om du ändrar den här inställningen påverkas både at.js och mbox.js. |
| Timeout | Om [!DNL Target] inte svarar med innehåll inom den angivna perioden, inträffar serveranropet och standardinnehållet visas. Ytterligare anrop fortsätter att utföras under besökarens session. Standardvärdet är 5 sekunder.<br>Om du ändrar den här inställningen påverkas både at.js och mbox.js.<br>I at.js-biblioteket används timeoutinställningen i `XMLHttpRequest`. Tidsgränsen startar när begäran utlöses och avbryts när Target får ett svar från servern. For more information, see [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout) on the Mozilla Developer Network.<br>Om den angivna tidsgränsen inträffar innan svaret tas emot, visas standardinnehåll och besökaren kan räknas som deltagare i en aktivitet eftersom all datainsamling sker på [!DNL Target] kanten. Om begäran når [!DNL Target] kanten räknas besökaren.<br>Tänk på följande när du konfigurerar timeoutinställningen:<ul><li>Om värdet är för lågt kan användarna se standardinnehåll oftast, men besökaren kan räknas som deltagare i aktiviteten.</li><li>Om värdet är för högt kan besökarna se tomma områden på webbsidan eller tomma sidor om du använder dolt innehåll under längre tidsperioder.</li></ul>Om du vill få en bättre förståelse för svarstiderna i mbox kan du titta på fliken Nätverk i webbläsarens utvecklingsverktyg. Du kan också använda verktyg för övervakning av webbprestanda från tredje part, till exempel Catchpoint.<br>**Obs **: Inställningen[visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md)ser till att[!DNL Target]inte väntar på Visitor API-svar för länge. Den här inställningen och Timeout-inställningen för at.js som beskrivs här påverkar inte varandra. |
| Stöd för äldre webbläsare | **Obs**: Alternativet Stöd för äldre webbläsare finns i version 0.9.3 och tidigare av at.js. Det här alternativet togs bort i at.js version 0.9.4. En lista över webbläsare som stöds av at.js finns i [Webbläsare](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)som stöds.<br>Äldre webbläsare är äldre webbläsare som inte har fullständigt stöd för CORS (Cross Origin Resource Sharing). Följande webbläsare innehåller: Internet Explorer-webbläsare tidigare än version 11 och Safari version 6 och tidigare. Om stöd för äldre webbläsare är inaktiverat levererar inte Target innehåll och räknar inte besökare i rapporter i dessa webbläsare. Om det här alternativet är aktiverat rekommenderas kvalitetssäkring i äldre webbläsare för att säkerställa en bra kundupplevelse. |

## Kodinställningar {#section_D41C905D0F8149949F525C85F2CCFF7F}

| Inställning | Beskrivning |
|--- |--- |
| Bibliotekshuvud | Lägg till ett anpassat JavaScript som ska inkluderas högst upp i biblioteket. |
| Bibliotekets sidfot | Lägg till ett anpassat JavaScript som ska inkluderas längst ned i biblioteket. |

## Ladda ned på.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Instruktioner för att hämta biblioteket med Target-gränssnittet eller Download API.

<!-- 

ov2/c_target-configure-atjs.xml

 -->

>[!NOTE]
>
>[Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) är den bästa metoden för att implementera Target och biblioteket at.js. Följande information gäller inte när Adobe Launch används för att implementera Target.

>[!IMPORTANT]
>
>Target-teamet underhåller endast två versioner av [!DNL at.js]- den aktuella versionen och den andra senaste versionen. Uppgradera [!DNL at.js] om det behövs för att säkerställa att du kör en version som stöds. Mer information om vad som finns i respektive version finns [i versionsinformationen](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)för at.js.

## Hämta at.js med Target-gränssnittet {#section_1F5EE401C2314338910FC57F9592894E}

Så här hämtar du [!DNL at.js] från [!DNL Target] gränssnittet:

1. Klicka på **[!UICONTROL Inställningar]** > **[!UICONTROL Implementering]**.
1. Välj **[!UICONTROL at.js]**.
1. Klicka på **[!UICONTROL Hämta på.js]**.

## Hämta at.js med Target Download API {#section_C0D9D2A9068144708D08526BA5CA10D0}

Hämta [!DNL at.js] med API:t.

1. Hämta din klientkod.

   Klientkoden finns högst upp på sidan **[!UICONTROL Inställningar]** > **[!UICONTROL Implementering]** > **[!UICONTROL Redigera at.js-inställningar]** i [!DNL Target] gränssnittet.

1. Hämta ditt administratörsnummer.

   Läs in denna URL:

   ```
   https://admin.testandtarget.omniture.com/rest/v1/endpoint/<varname>client code</varname>
   ```

   Ersätt `client code` med klientkoden från steg 1.

   Resultatet av att läsa in den här URL:en ska se ut ungefär som i följande exempel:

   ```
   { 
     "api": "https://admin6.testandtarget.omniture.com/admin/rest/v1" 
   }
   ```

   I det här exemplet är &quot;6&quot; administratörsnumret.

1. Ladda ned [!DNL at.js].

   Läs in den här URL:en med följande struktur:

   ```
   https://admin<varname>admin number</varname>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code</varname>&version=<version number>
   ```

   * Ersätt `admin number` med ditt administratörsnummer.
   * Ersätt `client code` med klientkoden från steg 1.
   * Ersätt `version number` med det önskade at.js-versionsnumret (till exempel 2.2).
   >[!IMPORTANT]
   >
   >Target-teamet underhåller endast två versioner av [!DNL at.js]- den aktuella versionen och den andra senaste versionen. Uppgradera [!DNL at.js] om det behövs för att säkerställa att du kör en version som stöds. Mer information om vad som finns i respektive version finns [i versionsinformationen](../../../c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)för at.js.

   När du läser in den här URL:en börjar hämtningen av den anpassade [!DNL at.js] filen.

## at.js-implementering {#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js ska implementeras i elementet `<head>` på alla sidor på webbplatsen.

En typisk implementering av Target som inte använder en tagghanterare som [Adobe Launch](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) eller [Dynamic Tag Management](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md#concept_3A40AF6FFC0E4FD2AA81B303A79D0B96) ser ut så här:

```
<!doctype html> 
<html> 
 
<head> 
    <meta charset="utf-8"> 
    <title>Title of the Page</title> 
    <!--Preconnect and DNS-Prefetch to improve page load time--> 
    <link rel="preconnect" href="//<client code>.tt.omtrdc.net"> 
    <link rel="dns-prefetch" href="//<client code>.tt.omtrdc.net"> 
    <!--/Preconnect and DNS-Prefetch--> 
    <!--Data Layer to enable rich data collection and targeting--> 
    <script> 
        var digitalData = { 
            "page": { 
                "pageInfo": { 
                    "pageName": "Home" 
                } 
            } 
        }; 
    </script> 
    <!--/Data Layer--> 
    <!-- targetPageParams(), targetPageParamsAll(), Data Providers or targetGlobalSettings() functions to enrich the visitor profile or modify the library settings--> 
    <script> 
        targetPageParams = function() { 
            return { 
                "a": 1, 
                "b": 2, 
                "pageName": digitalData.page.pageInfo.pageName, 
                "profile": { 
                    "age": 26, 
                    "country": { 
                        "city": "San Francisco" 
                    } 
                } 
            }; 
        }; 
    </script> 
    <!--/targetPageParams()--> 
 
    <!--jQuery or other helper libraries should be implemented before at.js if you would like to use their methods in Target--> 
    <script src="jquery-3.3.1.min.js"></script> 
    <!--/jQuery--> 
    <!--Target's JavaScript SDK, at.js--> 
    <script src="at.js"></script> 
    <!--/at.js--> 
</head> 
 
<body> 
    The default content of the page 
</body> 
 
</html>
```

Tänk på följande viktiga punkter:

* HTML5-dokumenttypen (t.ex. `<!doctype html>`) bör användas. Dokumenttyper som inte stöds eller äldre kan göra att Target inte kan göra en begäran.
* Föranslutning och Förhämtning är alternativ som kan hjälpa webbsidorna att läsas in snabbare. Om du använder dessa konfigurationer måste du ersätta `<client code>` med din egen klientkod, som du kan få på sidan **[!UICONTROL Inställningar]** > **[!UICONTROL Implementering]** > **[!UICONTROL Redigera at.js-inställningar]** .
* Om du har ett datalager är det optimalt att definiera så mycket som möjligt av det på `<head>` sidorna innan at.js läses in. Den här placeringen ger maximal möjlighet att utnyttja informationen i Target för personalisering.
* Särskilda Target-funktioner, till exempel `targetPageParams()`, `targetPageParamsAll()`Data Providers, och `targetGlobalSettings()` ska definieras efter datalagret och innan at.js läses in. De kan också sparas i delen [!UICONTROL Library Header] på sidan [!UICONTROL Edit at.js Settings] och sparas som en del av biblioteket at.js. Mer information om de här funktionerna finns i [funktionerna](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)at.js.
* Om du använder hjälpbibliotek för JavaScript, till exempel jQuery, kan du inkludera dem före Target så att du kan utnyttja deras syntax och metoder när du skapar Target-upplevelser.
* Inkludera at.js på `<head>` sidorna.

## Spåra konverteringar {#task_E85D2F64FEB84201A594F2288FABF053}

I rutan Orderbekräftelse registreras detaljer om beställningar på er webbplats och du kan rapportera baserat på intäkter och order. I rutan Orderbekräftelse kan du också skapa rekommendationsalgoritmer, till exempel&quot;Personer som köpt produkten x har också köpt produkten y&quot;.

>[!NOTE]
>
>Om användarna gör inköp på webbplatsen rekommenderar vi att du implementerar en orderbekräftelseruta även om du använder Analytics for Target (A4T) för din rapportering.

1. Infoga mbox-skriptet efter modellen nedan på sidan med orderinformation.
1. Ersätt ORD I VERSALA BOKSTÄVER med antingen dynamiska eller statiska värden från katalogen.

   >[!NOTE]
   >
   >Använd kommaavgränsning för att avgränsa flera produkt-ID:n.

   **Tips:** Du kan också skicka beställningsinformation i valfri ruta (den behöver inte namnges `orderConfirmPage`). Du kan också skicka beställningsinformation i flera rutor inom samma kampanj.

   ```
   <script type="text/javascript"> 
   adobe.target.trackEvent({ 
       "mbox": "orderConfirmPage", 
       "params":{  
           "orderId": "ORDER ID FROM YOUR ORDER PAGE",  
           "orderTotal": "ORDER TOTAL FROM YOUR ORDER PAGE",  
           "productPurchasedId": "PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3"  
       } 
   }); 
   </script> 
   ```

I rutan Orderbekräftelse används följande parametrar:

| Parameter | Beskrivning |
|--- |--- |
| orderId | Unikt värde för att identifiera en order för konverteringsinventering.<br>Värdet `orderId` måste vara unikt. Dubblettorder ignoreras i rapporter. |
| orderTotal | Köpets monetära värde.<br>Skicka inte valutasymbolen. Använd ett decimaltecken (inte kommatecken) för att ange decimalvärden. |
| productPurchasedId (valfritt) | En kommaseparerad lista över produkt-ID:n som köpts i ordern.<br>Dessa produkt-ID:n visas i granskningsrapporten som stöd för ytterligare rapportanalyser. |