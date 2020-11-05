---
keywords: implement target;implementation;implement at.js;tag manager
description: Information om hur du implementerar Adobe Target utan att använda en tagghanterare (Adobe Launch eller Dynamic Tag Management).
title: Implementera mål utan tagghanterare
feature: implementation general
subtopic: Getting Started
topic: Standard
uuid: 3ecc041a-42d8-40f8-90be-7856e1d3d080
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '1514'
ht-degree: 4%

---


# Implementera mål utan tagghanterare{#implement-target-without-a-tag-manager}

Information om implementering [!DNL Adobe Target] utan tagghanterare ([!DNL Adobe Launch] eller [!DNL Dynamic Tag Manager]).

>[!NOTE]
>
>[Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) är den bästa metoden för att implementera Target och biblioteket at.js. Följande information gäller inte när du använder Adobe Launch för att implementera Target.

Du öppnar [!UICONTROL Implementation] sidan genom att klicka **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

Du kan ange följande inställningar på den här sidan:

* Kontoinformation
* Implementeringsmetoder
* Profil-API
* Felsökningsverktyg
* Integritet

>[!NOTE]
>
>Du kan åsidosätta inställningarna i at.js-biblioteket i stället för att konfigurera inställningarna i gränssnittet för Target Standard/Premium eller genom att använda REST API:er. Mer information finns i [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Kontoinformation

Du kan visa följande kontoinformation. Dessa inställningar kan inte ändras.

| Inställning | Beskrivning |
| --- | --- |
| Klientkod | Klientkoden är en klientspecifik teckensekvens som ofta krävs när du använder mål-API:er. |
| IMS-organisations-ID | Detta ID kopplar implementeringen till ditt [!DNL Adobe Experience Cloud] konto. |

## Implementeringsmetoder

Följande inställningar kan konfigureras på panelen Implementeringsmetoder:

### Globala inställningar

>[!NOTE]
>
>De här inställningarna används för alla [!DNL Target] .js-bibliotek. När du har gjort ändringar i [!UICONTROL Implementation methods] avsnittet måste du hämta biblioteket och uppdatera det i implementeringen.

| Inställning | Beskrivning |
| --- | --- |
| Sidinläsning aktiverad (skapa en global mbox automatiskt) | Välj om du vill bädda in det globala mbox-anropet i filen at.js så att det automatiskt utlöses vid varje sidinläsning. |
| Global mbox | Välj ett namn för den globala mbox-filen. Som standard är namnet target-global-mbox.<br>Specialtecken, inklusive et-tecken (&amp;), kan användas i mbox-namn med at.js. |
| Timeout (sekunder) | Om [!DNL Target] inte svarar med innehåll inom den angivna perioden, inträffar serveranropet och standardinnehållet visas. Ytterligare anrop fortsätter att utföras under besökarens session. Standardvärdet är 5 sekunder.<br>I at.js-biblioteket används timeoutinställningen i `XMLHttpRequest`. Tidsgränsen startar när begäran utlöses och avbryts när [!DNL Target] ett svar hämtas från servern. For more information, see [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout) on the Mozilla Developer Network.<br>Om den angivna tidsgränsen inträffar innan svaret tas emot, visas standardinnehåll och besökaren kan räknas som deltagare i en aktivitet eftersom all datainsamling sker på [!DNL Target] kanten. Om begäran når [!DNL Target] kanten räknas besökaren.<br>Tänk på följande när du konfigurerar timeoutinställningen:<ul><li>Om värdet är för lågt kan användarna se standardinnehåll oftast, men besökaren kan räknas som deltagare i aktiviteten.</li><li>Om värdet är för högt kan besökarna se tomma områden på webbsidan eller tomma sidor om du använder dolt innehåll under längre tidsperioder.</li></ul>Om du vill få en bättre förståelse för svarstiderna i mbox kan du titta på fliken Nätverk i webbläsarens utvecklingsverktyg. Du kan också använda verktyg för övervakning av webbprestanda från tredje part, till exempel Catchpoint.<br>**Obs**: Inställningen [visitorApiTimeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) ser till att [!DNL Target] inte väntar på Visitor API-svar för länge. Den här inställningen och Timeout-inställningen för at.js som beskrivs här påverkar inte varandra. |
| Profilens livstid | Den här inställningen avgör hur långa besökarprofiler lagras. Som standard lagras profiler i två veckor. Denna kan ökas upp till 90 dagar.<br>Om du vill ändra inställningen för Profilens livstid kontaktar du [kundtjänst](https://helpx.adobe.com/se/contact/enterprise-support.ec.html). |

### Huvudsaklig implementeringsmetod

>[!IMPORTANT]
>
>Target-teamet stöder både at.js 1.*x* och at.js 2.*x*. Uppgradera till den senaste uppdateringen av någon större version av at.js för att säkerställa att du kör en version som stöds.

Klicka på lämplig **[!UICONTROL Download]** knapp om du vill hämta en at.js-version.

Om du vill redigera at.js-inställningarna klickar du **[!UICONTROL Edit]** bredvid den önskade at.js-versionen.

>[!IMPORTANT]
>
>Innan du ändrar dessa standardinställningar bör du kontakta [kundtjänst](/help/cmp-resources-and-contact-information.md) så att du inte påverkar den aktuella implementeringen.

Förutom de inställningar som förklaras ovan är följande specifika at.js-inställningar också tillgängliga:

| Inställning | Beskrivning |
|--- |--- |
| Anpassat bibliotekshuvud | Lägg till ett anpassat JavaScript som ska inkluderas högst upp i biblioteket. |
| Anpassa bibliotekets sidfot | Lägg till ett anpassat JavaScript som ska inkluderas längst ned i biblioteket. |

### Profil-API

Aktivera eller inaktivera autentisering för batchuppdateringar via API och generera en profilautentiseringstoken.

Mer information finns i [Profil-API-inställningar](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/profile-api-settings.md).

### Felsökningsverktyg

Generera en auktoriseringstoken för att använda avancerade [!DNL Target] felsökningsverktyg. Klicka på **[!UICONTROL Generate New Authentication Token]**.

![Generera ny autentiseringstoken](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### Integritet

Dessa inställningar gör att du kan använda dem [!DNL Target] i enlighet med gällande datasekretesslagstiftning.

Välj önskad inställning i listrutan Förhindra besökarens IP-adress:

* Senaste oktettförvrängning
* Hela IP-förvrängningen
* Ingen

Mer information finns i [Sekretess](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md).

>[!NOTE]
>
>Alternativet Stöd för äldre webbläsare var tillgängligt i version 0.9.3 och tidigare av at.js. Det här alternativet togs bort i at.js version 0.9.4. En lista över webbläsare som stöds av at.js finns i [Webbläsare](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)som stöds.<br>Äldre webbläsare är äldre webbläsare som inte har fullständigt stöd för CORS (Cross Origin Resource Sharing). Följande webbläsare innehåller: Internet Explorer-webbläsare tidigare än version 11 och Safari version 6 och tidigare. Om stöd för äldre webbläsare inaktiverades kunde Target inte leverera innehåll eller räkna besökare i rapporter för dessa webbläsare. Om det här alternativet är aktiverat rekommenderas kvalitetssäkring i äldre webbläsare för att säkerställa en bra kundupplevelse.

## Ladda ned på.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Instruktioner för att hämta biblioteket via [!DNL Target] gränssnittet eller hämtnings-API:t.

>[!NOTE]
>
>* [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) är den bästa metoden för att implementera Target och biblioteket at.js. Följande information gäller inte när du använder Adobe Launch för att implementera Target.
   >
   >
* Target-teamet stöder både at.js 1.*x* och at.js 2.*x*. Uppgradera till den senaste uppdateringen av någon större version av at.js för att säkerställa att du kör en version som stöds. Mer information om vad som finns i respektive version finns [i versionsinformationen](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)för at.js.


### Hämta at.js med Target-gränssnittet {#section_1F5EE401C2314338910FC57F9592894E}

Så här hämtar du [!DNL at.js] från [!DNL Target] gränssnittet:

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.
1. Klicka på [!UICONTROL Implementation methods] knappen bredvid den önskade at.js-versionen i **[!UICONTROL Download]** avsnittet.

### Hämta at.js med Target Download API {#section_C0D9D2A9068144708D08526BA5CA10D0}

Hämta [!DNL at.js] med API:t.

1. Hämta din klientkod.

   Klientkoden finns längst upp på **[!UICONTROL Administration]** >- **[!UICONTROL Implementation]** sidan i [!DNL Target] gränssnittet.

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
   >Target-teamet underhåller endast två versioner av [!DNL at.js]- den aktuella versionen och den andra senaste versionen. Uppgradera [!DNL at.js] om det behövs för att säkerställa att du kör en version som stöds. Mer information om vad som finns i respektive version finns [i versionsinformationen](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)för at.js.

   När du läser in den här URL:en börjar hämtningen av den anpassade [!DNL at.js] filen.

## at.js-implementering {#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js ska implementeras i elementet `<head>` på alla sidor på webbplatsen.

En typisk implementering av Target som inte använder en tagghanterare som [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#topic_5234DDAEB0834333BD6BA1B05892FC25) eller [Dynamic Tag Management](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md#concept_3A40AF6FFC0E4FD2AA81B303A79D0B96) ser ut så här:

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
* Föranslutning och Förhämtning är alternativ som kan hjälpa webbsidorna att läsas in snabbare. Om du använder dessa konfigurationer måste du ersätta `<client code>` med din egen klientkod, som du kan få från sidan **[!UICONTROL Administration]** > **[!UICONTROL Implementation] .
* Om du har ett datalager är det optimalt att definiera så mycket som möjligt av det på `<head>` sidorna innan at.js läses in. Den här placeringen ger maximal möjlighet att utnyttja informationen i Target för personalisering.
* Särskilda Target-funktioner, till exempel `targetPageParams()`, `targetPageParamsAll()`Data Providers, och `targetGlobalSettings()` ska definieras efter datalagret och innan at.js läses in. De kan också sparas i avsnittet på [!UICONTROL Library Header] sidan och sparas som en del av [!UICONTROL Edit at.js Settings] at.js-biblioteket. Mer information om de här funktionerna finns i [funktionerna](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)at.js.
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