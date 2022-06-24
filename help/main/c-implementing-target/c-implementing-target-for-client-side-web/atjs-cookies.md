---
keywords: at.js;2.0;1.x;cookies
description: Information om hur Adobe [!DNL Target] hantera cookies i at.js 2.x och at.js 1.x
title: at.js Cookies
feature: at.js
role: Developer
exl-id: 101be093-72fa-4f66-95bd-4b60e584a059
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '1852'
ht-degree: 0%

---

# at.js cookies

Information om at.js 2.x och at.js 1.*x* cookie-beteende.

## cookie-beteende i at.js 2.x

For at.js version 2.0.0, *endast cookies från första part stöds*. Precis som i at.js 1.*x*, den första partens cookie,&quot;mbox&quot;, lagras i `clientdomain.com`, där `clientdomain` är din domän.

at.js genererar ett sessions-ID och lagrar det i cookien. Det första svaret innehåller all aktivitetsinformation samt `TNT` eller `PC ID` genereras av [!DNL Target] servrar. at.js skriver sedan `TNT/PC ID` till kakan.

The `AMCV_###@AdobeOrg` cookie för första part anges alltid av [!DNL Experience Cloud ID Service]trots att `ECID` skickas in [!DNL Target] förfrågningar.

### Cookies från tredje part och spårning över domäner stöds inte

Spårning mellan domäner gör det möjligt att se sessioner på två relaterade webbplatser, men med olika domäner, som en enda session. Du kan skapa en [!DNL Target] aktivitet som spänner över `siteA.com` och `siteB.com` och besökaren skulle förbli i samma upplevelse när de korsade domäner. Den här funktionen är kopplad till at.js 1.*x* cookie-beteende från tredje part och från första part.

I at.js 1.*x*, lagrades cookie-filen från tredje part i `[CLIENTCODE].tt.omtrdc.net` domän och cookie-filen från första part lagrades i `clientdomain.com`. Den första begäran returnerade HTTP-svarshuvuden som försökte ange cookies med namn från tredje part `mboxSession` och `mboxPC`, medan en omdirigeringsbegäran skickas tillbaka med en extra parameter (`mboxXDomainCheck=true`). Om webbläsaren accepterade cookies från tredje part inkluderar omdirigeringsbegäran dessa cookies och erbjudandet returnerades. Det här arbetsflödet var möjligt eftersom at.js 1.*x* använder HTTP GET-metoden.

I at.js 2.x används emellertid inte längre HTTP-GET utan HTTP-POST. HTTP-POST används nu via at.js för att skicka JSON-nyttolaster till [!DNL Target] edge-servrar i stället för nyckelvärdesparametrar. Detta innebär att omdirigeringsbegäran för att kontrollera om en webbläsare stöder cookies från tredje part nu avbryts. Detta beror på att HTTP GET-begäranden är idempotenta transaktioner medan HTTP-POST är icke-idempotent och inte får upprepas godtyckligt.

Därför stöds varken cookies från tredje part eller korsdomänsspårning i at.js 2.0.0.

## at.js 1.*x* cookie-beteende {#at-js-1x-cookie-behavior}

För at.js version 1.*x* Men cookie-beteendet beror på om det är en cookie från första part, en cookie från tredje part med en cookie från första part eller en cookie från tredje part.

### När cookies från tredje part ska användas

Platskonfigurationen avgör vilka cookies du vill använda. Det är praktiskt att förstå hur Target fungerar när man försöker förstå cookies från första part och tredje part. Se [Så här fungerar Adobe Target](/help/main/c-intro/how-target-works.md) för mer information.

Det finns tre huvudsakliga användningsområden för cookies:

1. En domän.

   Alla testerna utförs inom en toppnivådomän (`www.domain.com`, `store.domain.com`, `anysub.domain.com`, osv.).

   Använd endast cookies från första part. Detta är standardinställningen.

1. Användare överskrider domäner och du vill spåra och testa deras beteende i dessa domäner.

   Exempel: En användare kommer till er sajt för att handla men checkar ut genom Yahoos butiker. Tre metoder (samarbeta med din kontorepresentant för att fastställa det bästa tillvägagångssättet):

   * Aktivera cookies från första och tredje part.
   * Aktivera endast tredjepartsprodukter (mycket sällsynt, men har fördelen att inte ta bort cookien at.js från domänen).
   * Aktivera endast cookies och pass från första part `mboxSession` parameter när domänen korsas.

      The `mboxSession` -parametern måste skickas till en landningssida med referenser till at.js. Det kan inte vara en mellanliggande omdirigeringssida.

1. Du använder bara adboxar eller FlashBox på en tredjepartswebbplats.

   Två metoder (arbeta med kundtjänsthanteraren för att fastställa det bästa sättet):

   * Aktivera cookies från andra tillverkare.

      För FlashBox och dynamiska kreatörer krävs cookies från andra leverantörer.

   * Aktivera endast cookies från tredje part.

      Detta tillvägagångssätt gäller endast i de sällsynta fall där adbox-implementeringar används utan anpassning till webbplatsen.

### cookie-beteende från första part

Den första partens cookie lagras i `clientdomain.com`, där `clientdomain` är din domän.

at.js genererar en `mboxSession ID` och lagrar den i kakan. Det första svaret innehåller erbjudandet samt JavaScript-koden som lagrar `mboxPC ID` som genereras av programmet, i cookien.

>[!NOTE]
>
>The `AMCV_###@AdobeOrg` cookie för första part anges alltid med [!DNL Experience Cloud Visitor ID].

### Cookie-beteende från tredje part

Tredjepartskakan lagras i `clientcode.tt.omtrdc.net` och cookie-filen från första part lagras i `clientdomain.com`, där `clientdomain` är din domän.

at.js genererar en `mboxSession ID`. Den första platsbegäran returnerar HTTP-svarshuvuden som försöker ange cookies från tredje part med namnet `mboxSession` och `mboxPC` och en omdirigeringsbegäran skickas tillbaka med en extra parameter (`mboxXDomainCheck=true`).

Om webbläsaren accepterar cookies från tredje part inkluderar omdirigeringsbegäran dessa cookies och erbjudandet returneras.

Om webbläsaren avvisar cookies från tredje part inkluderar omdirigeringsbegäran inte dessa cookies, och standardinnehåll visas för alla platser på sidan. Eftersom det inte finns några angivna cookies sker samma process ovan igen vid varje sidbegäran.

### cookie-beteende från tredje part och första part

Tredjepartskakan lagras i `clientcode.tt.omtrdc.net` och cookie-filen från första part lagras i `clientdomain.com`, där `clientdomain` är din domän.

at.js genererar en `mboxSession ID`. Den första platsbegäran returnerar HTTP-svarshuvuden som försöker ange cookies från tredje part med namnet `mboxSession` och `mboxPC`och en omdirigeringsbegäran skickas tillbaka med en extra parameter (`mboxXDomainCheck=true`).

Om webbläsaren accepterar cookies från tredje part inkluderar omdirigeringsbegäran dessa cookies och erbjudandet returneras.

Vissa webbläsare avvisar cookies från tredje part. Om cookie-filen från tredje part är blockerad fungerar fortfarande cookie-filen från den första parten. [!DNL Target] försöker ange cookie-filen från tredje part, och om den inte kan göra det [!DNL Target] kan bara spåra på klientens specifika domän. Spårning mellan domäner fungerar inte om tredje part blockeras, såvida inte `mboxSession` läggs till i länken som korsar domäner. I det här fallet ställs en annan cookie in och synkroniseras med den tidigare domänens cookie.

## Cookie-inställningar

Cookien har flera standardinställningar. Du kan ändra de här inställningarna om det behövs, med undantag för cookie-varaktighet. Kontakta din kontorepresentant när du ändrar cookie-inställningarna.

| Inställning | Information |
|--- |--- |
| Cookie-namn | mbox. |
| Cookie-domän | Den andra och den översta nivån i de domäner som du underhåller innehållet från. Eftersom cookie används av ditt företags domän är den en cookie från första part. Exempel: `mycompany.com`. |
| Serverdomän | `clientcode.tt.omtrdc.net`, med hjälp av klientkoden för ditt konto. |
| Cookie-varaktighet | Cookien finns kvar i besökarens webbläsare två år efter den senaste inloggningen.<br>The `deviceIdLifetime` inställningen kan åsidosättas i [at.js version 2.3.1 eller senare](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}. Mer information finns i [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}. |
| P3P-princip | Cookien publiceras med en P3P-princip, vilket krävs enligt standardinställningen i de flesta webbläsare. En P3P-profil anger för en webbläsare som skickar cookien och hur informationen ska användas. |

Cookien har ett antal värden för att hantera hur besökarna upplever kampanjer:

| Värde | Definition |
|--- |--- |
| sessions-ID | Ett unikt ID för en användarsession. Som standard varar detta 30 minuter. |
| pc-ID | Ett halvpermanent ID för en besökares webbläsare. Varar 14 dagar. |
| at_check | Ett enkelt testvärde som används för att avgöra om en besökare stöder cookies. Ange varje gång en besökare begär en sida. |
| disable | Ange om besökarens inläsningstid överskrider den tidsgräns som konfigurerats i [!DNL Adobe Experience Platform Web SDK] eller filen at.js. Som standard varar detta 1 timme. |

## Påverkan på [!DNL Target] för Safari-besökare på grund av Apple WebKit-spårningsändringar

Tänk på följande:

### Hur gör Adobe? [!DNL Target] Spåra arbetet?

| Cookies | Detaljer |
|--- |--- |
| Första parts domäner | Detta är standardimplementeringen för Target-kunder.  &quot;mbox&quot;-cookies anges i kundens domän. |
| Spårning från tredje part | Spårning från tredje part är viktigt för reklam och riktad marknadsföring i Target och i Adobe Audience Manager (AAM).  Spårning från tredje part kräver serveröverskridande skripttekniker (cross-site scripting).  Målet använder två cookies, &quot;mboxSession&quot; och &quot;mboxPC&quot;, som anges i `clientcode.tt.omtrd.net` domän. |

### Vad är Apple tillvägagångssätt?

Från Apple:

&quot;Intelligent Tracking Prevention är en ny WebKit-funktion som minskar spårningen mellan webbplatser genom att ytterligare begränsa cookies och andra webbplatsdata.&quot;

&quot;Det här kallas spårning på olika webbplatser och cookie-filen som används av `example-tracker.com` kallas en cookie från tredje part. I våra tester fann vi populära webbplatser med över 70 sådana spårare, som alla i tysthet samlar in data om användarna.&quot;

| Metod | Detaljer |
|--- |--- |
| Förebyggande av intelligent spårning | Mer information finns i [Intelligent spårningsförebyggande](https://webkit.org/blog/7675/intelligent-tracking-prevention/) på webbplatsen WebKit Open Source Web Browser Engine. |
| Cookies | Hur Safari hanterar cookies:<ul><li>Cookies från tredje part som inte finns på en domän som användaren kommer åt direkt sparas aldrig. Det här beteendet är inte nytt. Cookies från tredje part stöds redan i Safari.</li><li>Cookies från tredje part som anges på en domän som användaren kommer åt direkt rensas efter 24 timmar.</li><li>cookies från första part rensas efter 30 dagar om den förstahandsdomänen har klassificerats som spårning av användare på olika webbplatser. Problemet kan gälla stora företag som skickar användare till olika domäner online. Apple har inte klargjort hur dessa domäner ska klassificeras, eller hur en domän kan avgöra om de har klassificerats som spårning av användare på olika webbplatser.</li></ul> |
| Maskininlärning för att identifiera domäner som är flera platser | Från Apple:<br>Maskininlärningsklassificering: En maskininlärningsmodell används för att klassificera vilka av de främsta privatkontrollerade domänerna som kan spåra användarens webbplats, baserat på den insamlade statistiken. Av de olika insamlade uppgifterna visade det sig att tre vektorer har en stark signal för klassificering baserat på nuvarande spårningspraxis: underresurs under antal unika domäner, underbildruta under antal unika domäner och antal unika domäner som omdirigeras till. All datainsamling och klassificering sker på enheten.<br>Men om användaren interagerar med example.com som den översta domänen, som ofta kallas förstahandsdomän, ser Intelligent Tracking Prevention det som en signal om att användaren är intresserad av webbplatsen och tillfälligt anpassar sitt beteende enligt den här tidslinjen:<br>Om användaren interagerade med example.com de senaste 24 timmarna är cookies tillgängliga när `example.com` är en tredje part. Detta gör att du kan logga in med mitt X-konto på Y-inloggningsscenarier.<ul><li>Domäner som besöktes som toppnivådomäner påverkas inte. Exempel på platser som OKTA</li><li>Identifierar domäner som är underdomäner eller underramar till den aktuella sidan över flera unika domäner.</li></ul> |

### Hur kommer Adobe att påverkas?

| Funktioner som påverkas | Detaljer |
|--- |--- |
| Stöd för avanmälan | Stöd för avanmälan om ändringsbrytningar för Apple WebKit-spårning.<br>Målavanmälan använder en cookie i `clientcode.tt.omtrdc.net` domän. Mer information finns i [Integritet](https://developer.adobe.com/target/before-implement/privacy/privacy/){target=_blank}.<br>Målet har stöd för två avanmälningar:<ul><li>En per klient (klienten hanterar länken för avanmälan).</li><li>Ett via Adobe som gör att användaren slipper alla Target-funktioner för alla kunder.</li></ul>Båda metoderna använder cookie-filen från tredje part. |
| Verksamheter som riktar sig till | Kunderna kan själva välja [livslängd för profil](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) för sina Target-konton - upp till 90 dagar. Orsaken är att om kontots profillivslängd är längre än 30 dagar och cookie-filen rensas eftersom kundens domän har markerats som spårning av användare på alla webbplatser, påverkas beteendet för Safari-besökare i följande områden i Target:<br>**Målrapporter**: Om en Safari-användare går in i en aktivitet returneras efter 30 dagar och konverteras sedan räknas användaren som två besökare och en konvertering.<br>Detta beteende är detsamma för aktiviteter som använder Analytics som rapportkälla (A4T).<br>**Profil- och aktivitetsmedlemskap**:<ul><li>Profildata raderas när cookie-filen från första part förfaller.</li><li>Aktivitetsmedlemskapet raderas när cookie-filen från första part förfaller.</li><li> Målet fungerar inte i Safari för konton som använder en cookie-implementering från tredje part eller en cookie-implementering från första och tredje part. Observera att det här beteendet inte är nytt. Safari har inte tillåtit cookies från tredje part på ett tag.</li></ul><br>**Förslag**: Om det finns en oro för att kunddomänen kan markeras som en spårning av besökare mellan sessioner, är det säkraste att ange profilens livstid till 30 dagar eller färre i Target. På så sätt spåras användare på samma sätt i Safari och alla andra webbläsare. |
