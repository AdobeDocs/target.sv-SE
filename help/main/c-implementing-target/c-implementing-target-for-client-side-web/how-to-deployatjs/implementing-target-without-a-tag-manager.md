---
keywords: implementera mål;implementera;implementera at.js;tagghanterare;enhetsbeslut;vid enhetsbeslut
description: Lär dig hur du anger inställningar (kontoinformation, implementeringsmetoder osv.) att implementera Adobe [!DNL Target] at.js-bibliotek utan tagghanterare.
title: Kan jag implementera [!DNL Target] utan en tagghanterare?
feature: Implement Server-side
role: Developer
exl-id: cb57f6b8-43cb-485d-a7ea-12db8170013f
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '1782'
ht-degree: 3%

---

# Implementera [!DNL Target] utan tagghanterare

Information om implementering [!DNL Adobe Target] utan att använda en tagghanterare eller taggar i [!DNL Adobe Experience Platform].

>[!NOTE]
>
>Taggar i [Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/) är den metod som rekommenderas för implementering [!DNL Target] och biblioteket at.js. Följande information gäller inte när du använder taggar i [!DNL Adobe Experience Platform] implementera [!DNL Target].

Så här öppnar du [!UICONTROL Implementation] sida, klicka **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

Du kan ange följande inställningar på den här sidan:

* Kontoinformation
* Implementeringsmetoder
* Profil-API
* Felsökningsverktyg
* Integritet

>[!NOTE]
>
>Du kan åsidosätta inställningarna i at.js-biblioteket i stället för att konfigurera inställningarna i [!DNL Target Standard/Premium] Användargränssnitt eller med REST API:er. Mer information finns i [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).

## Kontoinformation

Du kan visa följande kontoinformation. Dessa inställningar kan inte ändras.

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Client Code] | Klientkoden är en klientspecifik teckensekvens som ofta krävs när du använder [!DNL Target] API:er. |
| [!UICONTROL IMS Organization ID] | Detta ID kopplar implementeringen till din [!DNL Adobe Experience Cloud] konto. |
| [!UICONTROL On-Device Decisioning] | Om du vill aktivera enhetsbeslut flyttar du växlingsknappen till läget&quot;på&quot;.<br>Med enhetsbaserad beslutsfattande kan du cachelagra dina A/B-filer och [!UICONTROL Experience Targeting] (XT) kampanjer på din server och utför minnesbaserad beslutsfattande med en latens som är nästan noll. Mer information finns i [Introduktion till beslut på enheter](https://developer.adobe.com/target/implement/server-side/sdk-guides/on-device-decisioning/) i *[!DNL Adobe Target]SDK* guide. |
| [!UICONTROL Include all existing on-device decisioning qualified activities in the artifact.] | (Villkorligt) Det här alternativet visas om du aktiverar enhetsbeslut.<br>Skjut musknappen till&quot;på&quot;-positionen om du vill att alla dina aktiva Target-aktiviteter som är kvalificerade för enhetsbeslut ska inkluderas automatiskt i artefakten.<br>Om du inte aktiverar det här alternativet måste du återskapa och aktivera alla enhetsspecifika beslutsaktiviteter för att de ska kunna inkluderas i den genererade regelartefakten. |

## Implementeringsmetoder

Följande inställningar kan konfigureras på panelen Implementeringsmetoder:

### Globala inställningar

>[!NOTE]
>
>De här inställningarna används för alla [!DNL Target] .js-bibliotek. När du har gjort ändringar i avsnittet Implementeringsmetoder måste du hämta biblioteket och uppdatera det i implementeringen.

| Inställning | Beskrivning |
| --- | --- |
| Sidinläsning aktiverad (skapa en global mbox automatiskt) | Välj om du vill bädda in det globala mbox-anropet i filen at.js så att det automatiskt utlöses vid varje sidinläsning. |
| Global mbox | Välj ett namn för den globala mbox-filen. Som standard är namnet target-global-mbox.<br>Specialtecken, inklusive et-tecken (&amp;), kan användas i mbox-namn med at.js. |
| Timeout (sekunder) | If [!DNL Target] svarar inte på innehåll inom den angivna perioden, serveranropet tar slut och standardinnehållet visas. Ytterligare anrop fortsätter att utföras under besökarens session. Standardvärdet är 5 sekunder.<br>I at.js-biblioteket används timeoutinställningen i `XMLHttpRequest`. Tidsgränsen startar när begäran utlöses och stannar när [!DNL Target] hämtar ett svar från servern. Mer information finns i [XMLHttpRequest.timeout](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout) på Mozilla Developer Network.<br>Om den angivna tidsgränsen inträffar innan svaret tas emot, visas standardinnehållet och besökaren kan räknas som deltagare i en aktivitet eftersom all datainsamling sker på [!DNL Target] kant. Om begäran når [!DNL Target] besökaren räknas.<br>Tänk på följande när du konfigurerar timeout-inställningen:<ul><li>Om värdet är för lågt kan användarna se standardinnehåll oftast, men besökaren kan räknas som deltagare i aktiviteten.</li><li>Om värdet är för högt kan besökarna se tomma områden på webbsidan eller tomma sidor om du använder dolt innehåll under längre tidsperioder.</li></ul>Om du vill få en bättre förståelse för svarstiderna i mbox kan du titta på fliken Nätverk i webbläsarens utvecklingsverktyg. Du kan också använda verktyg för övervakning av webbprestanda från tredje part, till exempel Catchpoint.<br>**Anteckning**: The [visitorApiTimeout](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) inställningen säkerställer att [!DNL Target] väntar inte på Visitor API-svaret för länge. Den här inställningen och Timeout-inställningen för at.js som beskrivs här påverkar inte varandra. |
| Profilens livstid | Den här inställningen avgör hur långa besökarprofiler lagras. Som standard lagras profiler i två veckor. Den här inställningen kan ökas upp till 90 dagar.<br>Om du vill ändra inställningen för Profilens livstid kontaktar du [Kundtjänst](https://helpx.adobe.com/se/contact/enterprise-support.ec.html). |

### Huvudsaklig implementeringsmetod

>[!IMPORTANT]
>
>Target-teamet stöder både at.js 1.*x* och at.js 2.*x*. Uppgradera till den senaste uppdateringen av någon större version av at.js för att säkerställa att du kör en version som stöds.

Om du vill hämta en at.js-version klickar du på lämplig **[!UICONTROL Download]** -knappen.

Om du vill redigera at.js-inställningarna klickar du på **[!UICONTROL Edit]** bredvid den önskade at.js-versionen.

>[!IMPORTANT]
>
>Innan du ändrar dessa standardinställningar bör du kontakta [Kundtjänst](/help/main/cmp-resources-and-contact-information.md) så att ni inte påverkar er nuvarande implementering.

Förutom de inställningar som förklaras ovan är följande specifika at.js-inställningar också tillgängliga:

| Inställning | Beskrivning |
|--- |--- |
| Anpassat bibliotekshuvud | Lägg till ett anpassat JavaScript som ska inkluderas högst upp i biblioteket. |
| Anpassa bibliotekets sidfot | Lägg till ett anpassat JavaScript som ska inkluderas längst ned i biblioteket. |

### Implementeringsmetoder med On-Device Decision

Från och med version 2.5.0 kan at.js fatta beslut på enheter. Med enhetsbaserad beslutsfattande kan du cachelagra [A/B-test](/help/main/c-activities/t-test-ab/test-ab.md) och [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md) (XT) aktiviteter i webbläsaren som utför minnesbaserad beslutsfattande utan blockerande nätverksbegäran till [!DNL Adobe Target] Edge Network.

Mer information finns i avsnitten:

* [Enhetsbeslut för klientsidan](https://developer.adobe.com/target/implement/client-side/){target=_blank}
* [Enhetsbeslut för serversidan](https://developer.adobe.com/target/implement/server-side/sdk-guides/on-device-decisioning/){target=_blank}

### Profil-API

Aktivera eller inaktivera autentisering för batchuppdateringar via API och generera en profilautentiseringstoken.

Mer information finns i [Profil-API-inställningar](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/profile-api-settings/).

### Felsökningsverktyg

Generera en auktoriseringstoken för avancerad användning [!DNL Target] felsökningsverktyg. Klicka på **[!UICONTROL Generate New Authentication Token]**.

![Generera ny autentiseringstoken](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

### Integritet

Med de här inställningarna kan du använda [!DNL Target] i enlighet med gällande datasekretesslagstiftning.

Välj önskad inställning i listrutan Förhindra besökarens IP-adress:

* Senaste oktettförvrängning
* Hela IP-förvrängningen
* Ingen

Mer information finns i [Integritet](https://developer.adobe.com/target/before-implement/privacy/privacy/).

>[!NOTE]
>
>Alternativet Stöd för äldre webbläsare var tillgängligt i version 0.9.3 och tidigare av at.js. Det här alternativet togs bort i at.js version 0.9.4. En lista över webbläsare som stöds av at.js finns på [Webbläsare som stöds](https://developer.adobe.com/target/before-implement/supported-browsers/).<br>Äldre webbläsare är äldre webbläsare som inte har fullständigt stöd för CORS (Cross Origin Resource Sharing). Följande webbläsare innehåller: Internet Explorer-webbläsare tidigare än version 11 och Safari version 6 och tidigare. Om stöd för äldre webbläsare inaktiverades kunde Target inte leverera innehåll eller räkna besökare i rapporter för dessa webbläsare. Om det här alternativet är aktiverat rekommenderas kvalitetssäkring i äldre webbläsare för att säkerställa en bra kundupplevelse.

## Ladda ned på.js {#concept_1E1F958F9CCC4E35AD97581EFAF659E2}

Instruktioner för att hämta biblioteket med [!DNL Target] för Download API.

>[!NOTE]
>
>* [[!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/) är den metod som rekommenderas för implementering [!DNL Target] och biblioteket at.js. Följande information gäller inte när du använder taggar i [!DNL Adobe Experience Platform] implementera [!DNL Target].
>
>* The [!DNL Target] team har stöd för både at.js 1.*x* och at.js 2.*x*. Uppgradera till den senaste uppdateringen av någon större version av at.js för att säkerställa att du kör en version som stöds. Mer information om vad som finns i respektive version finns i [at.js Versionsinformation](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/).


### Hämta at.js med [!DNL Target] gränssnitt {#section_1F5EE401C2314338910FC57F9592894E}

För nedladdning [!DNL at.js] från [!DNL Target] gränssnitt:

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.
1. Från [!UICONTROL Implementation methods] klickar du på **[!UICONTROL Download]** intill den önskade at.js-versionen.

### Hämta at.js med [!DNL Target] Hämta API {#section_C0D9D2A9068144708D08526BA5CA10D0}

För nedladdning [!DNL at.js] med API:t.

1. Hämta din klientkod.

   Klientkoden finns längst upp på **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** sidan på [!DNL Target] gränssnitt.

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

1. Hämta [!DNL at.js].

   Läs in den här URL:en med följande struktur:

   ```
   https://admin<varname>admin number</varname>.testandtarget.omniture.com/admin/rest/v1/libraries/atjs/download?client=<varname>client code</varname>&version=<version number>
   ```

   * Ersätt `admin number` med ditt administratörsnummer.
   * Ersätt `client code` med klientkoden från steg 1.
   * Ersätt `version number` med det önskade at.js-versionsnumret (till exempel 2.2).

   >[!IMPORTANT]
   >
   >Target-teamet underhåller endast två versioner av [!DNL at.js]- den aktuella versionen och den senaste versionen. Uppgradera [!DNL at.js] vid behov för att säkerställa att du kör en version som stöds. Mer information om vad som finns i respektive version finns i [at.js Versionsinformation](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/).

   När du läser in den här URL:en börjar nedladdningen av din anpassade [!DNL at.js] -fil.

## at.js-implementering {#concept_03CFA86973A147839BEB48A06FEE5E5A}

at.js ska implementeras i `<head>` element på alla sidor på webbplatsen.

En typisk implementering av Target som inte använder en tagghanterare, till exempel taggar i [[!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/) ser ut så här:

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

* Dokumenttypen HTML5 (till exempel `<!doctype html>`) ska användas. Dokumenttyper som inte stöds eller äldre kan göra att Target inte kan göra en begäran.
* Föranslutning och Förhämtning är alternativ som kan hjälpa webbsidorna att läsas in snabbare. Om du använder dessa konfigurationer måste du ersätta `<client code>` med din egen klientkod, som du kan få från **[!UICONTROL Administration]** > **[!UICONTROL Implementation] sida.
* Om du har ett datalager är det optimalt att definiera så mycket som möjligt av det i `<head>` av dina sidor innan at.js läses in. Den här placeringen ger maximal möjlighet att använda den här informationen i Target för personalisering.
* Särskilda Target-funktioner, som `targetPageParams()`, `targetPageParamsAll()`, Data Providers och `targetGlobalSettings()` ska definieras efter datalagret och innan at.js läses in. Dessa funktioner kan också sparas i [!UICONTROL Library Header] i [!UICONTROL Edit at.js Settings] och sparas som en del av at.js-biblioteket. Mer information om de här funktionerna finns i [Funktionerna at.js](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-functions/).
* Om du använder hjälpbibliotek för JavaScript, t.ex. jQuery, kan du inkludera dem före Target så att du kan använda deras syntax och metoder när du skapar Target-upplevelser.
* Inkludera at.js i `<head>` av sidorna.

## Spåra konverteringar {#task_E85D2F64FEB84201A594F2288FABF053}

I rutan Orderbekräftelse registreras detaljer om beställningar på er webbplats och du kan rapportera baserat på intäkter och order. I rutan Orderbekräftelse kan du också skapa rekommendationsalgoritmer, till exempel&quot;Personer som köpt produkten x har också köpt produkten y&quot;.

>[!NOTE]
>
>Om användarna gör inköp på er webbplats rekommenderar Adobe att du implementerar en orderbekräftelseruta även om du använder Analytics for Target (A4T) för din rapportering.

1. Infoga mbox-skriptet efter modellen nedan på sidan med orderinformation.
1. Ersätt ORD I VERSALA BOKSTÄVER med antingen dynamiska eller statiska värden från katalogen.

   >[!NOTE]
   >
   >Använd kommaavgränsning för att avgränsa flera produkt-ID:n.

   **Tips:** Du kan också skicka beställningsinformation i valfri ruta (den behöver inte namnges) `orderConfirmPage`). Du kan också skicka beställningsinformation i flera rutor inom samma kampanj.

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
