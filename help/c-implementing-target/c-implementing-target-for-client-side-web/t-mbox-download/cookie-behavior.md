---
keywords: Översikt och referens;webbkit
description: Läs om den gamla implementeringen av mbox.js i Adobe Target. Migrera till Adobe Experience Platform Web SDK (AEP Web SDK) eller till den senaste versionen av at.js.
title: Var hittar jag information om mbox.js-cookies?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# mbox.js cookies{#mbox-js-cookies}

Cookie-beteendet beror på om det är en cookie från en annan leverantör, en cookie från en annan tillverkare med en cookie från en annan leverantör eller en cookie från en annan tillverkare.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

>[!NOTE]
>
>Det här avsnittet innehåller information om `mboxSession` och `mboxPC`. Enligt våra implementeringsrutiner bör du inte länka eller lagra känslig information med cookie-data: `mboxSession` eller `mboxPC`.

Se även [Ta bort målcookien](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cookie-deleting.md).

## När cookies från första eller tredje part ska användas {#section_F71B29420C004A7FA3B1921E619B326E}

Din platskonfiguration avgör vilka cookies du vill använda. Det är praktiskt att förstå hur Target fungerar när man försöker förstå cookies från första och tredje part. Mer information finns i [How Adobe Target Works](/help/c-intro/how-target-works.md#concept_459AB4DEE7364A9290C2FD405DC29584).

Det finns tre huvudsakliga användningsområden för cookies:

1. En domän.

   Alla dina tester utförs i en toppnivådomän ( [!DNL `www.domain.com`], [!DNL store.domain.com], [!DNL anysub.domain.com] osv.).

   Metod: Använd endast cookies från första part. Detta är standardinställningen.

1. Användare överskrider domäner och du vill spåra och testa deras beteende i dessa domäner.

   Exempel: En användare kommer till er sajt för att handla men checkar ut genom Yahoos butiker. Tre metoder (samarbeta med din kontorepresentant för att fastställa det bästa tillvägagångssättet):

   * Aktivera cookies från första och tredje part.
   * Aktivera endast tredjepartscookie (mycket sällsynt, men har fördelen att inte ta bort cookie-filen från din domän).
   * Aktivera endast cookies från första part och skicka parametern `mboxSession` när du korsar domänen.

      Parametern `mboxSession` måste skickas till en landningssida där [!DNL mbox.js] refereras. Det kan inte vara en mellanliggande omdirigeringssida.

1. Du använder bara adboxar eller FlashBox på en tredjepartswebbplats.

   Två metoder (arbeta med kundtjänsthanteraren för att fastställa det bästa sättet):

   * Aktivera cookies från första och tredje part.

      För FlashBox och dynamiska kreatörer krävs cookies från första och tredje part.
   * Aktivera endast cookies från tredje part.

      Detta tillvägagångssätt gäller endast i de sällsynta fall där AdBox-implementeringar används utan målinriktning på plats.

## Cookie-beteende för första part {#section_CE6313D979EA4D0897D2F661E7A8AFA7}

Den första partens cookie lagras i [!DNL clientdomain.com], där `clientdomain` är din domän.

[!DNL Mbox.js] skapar en  `mboxSession ID` och lagrar den i mbox-cookien. Det första mbox-svaret innehåller erbjudandet, samt JavaScript-koden som lagrar `mboxPC ID` som genereras av programmet, i mbox-cookien.

>[!NOTE]
>
>Den första [!DNL AMCV_###@AdobeOrg]-partcookien anges alltid med Experience Cloud Visitor-ID:t.

## Cookie-beteende från tredje part {#section_4C3A83990BF8415BB1806602D84AED48}

Cookien från tredje part lagras i [!DNL clientcode.tt.omtrdc.net] och cookie från första part lagras i [!DNL clientdomain.com], där `clientdomain` är din domän.

[!DNL Mbox.js] genererar en  `mboxSession ID`. Den första platsbegäran returnerar HTTP-svarshuvuden som försöker ange cookies från tredje part med namnen `mboxSession` och `mboxPC` och en omdirigeringsbegäran skickas tillbaka med en extra parameter ( `mboxXDomainCheck=true`).

Om webbläsaren accepterar cookies från tredje part inkluderar omdirigeringsbegäran dessa cookies och erbjudandet returneras.

Om webbläsaren avvisar cookies från tredje part inkluderar omdirigeringsbegäran inte dessa cookies, och standardinnehåll visas för alla platser på sidan. Eftersom det inte finns några angivna cookies sker samma process ovan igen vid varje sidbegäran.

>[!NOTE]
>
>Cookien [!DNL demdex.net] anges om cookies från tredje part inte blockeras.

## Cookie-beteende för tredje part och första part {#section_F0C9AD8BFDF8457A999C4A07A0F7A981}

Cookien från tredje part lagras i [!DNL clientcode.tt.omtrdc.net] och cookie från första part lagras i [!DNL clientdomain.com], där `clientdomain` är din domän.

[!DNL Mbox.js] genererar en  `mboxSession ID`. Den första platsbegäran returnerar HTTP-svarshuvuden som försöker ange cookies från tredje part med namnen `mboxSession` och `mboxPC`, och en omdirigeringsbegäran skickas tillbaka med en extra parameter ( `mboxXDomainCheck=true`).

Om webbläsaren accepterar cookies från tredje part inkluderar omdirigeringsbegäran dessa cookies och erbjudandet returneras.

Vissa webbläsare avvisar cookies från tredje part. Om cookie-filen från tredje part är blockerad fungerar fortfarande cookie-filen från den första parten. Målet försöker ange cookie för tredje part, och om den inte kan det kan Target bara spåra på klientens specifika domän. Spårning av korsdomäner fungerar inte om tredjepartsleverantören är blockerad, såvida inte `mboxSession` har lagts till i länken som korsar domäner. I det här fallet ställs en annan cookie in och synkroniseras med den tidigare domänens cookie.

## Cookie-inställningar {#section_B498B8D1A34A444BBF84CC720EE9D87F}

Cookien har flera standardinställningar. Du kan ändra de här inställningarna om det behövs, med undantag för cookie-varaktighet. Kontakta din kontorepresentant när du ändrar cookie-inställningarna.

| Inställning | Information |
|--- |--- |
| Cookie-namn | mbox. |
| Cookie-domän | Den andra och den översta nivån i de domäner som du underhåller innehållet från. Eftersom cookie används av ditt företags domän är den en cookie från första part.<br>Exempel:   `mycompany.com`. |
| Serverdomän | `clientcode.tt.omtrdc.net`, med hjälp av klientkoden för ditt konto. |
| Cookie-varaktighet | Cookien finns kvar i besökarens webbläsare två veckor efter hans eller hennes senaste inloggning. Du kan inte ändra varaktighet för cookie-filen. |
| P3P-princip | Cookien publiceras med en P3P-princip, vilket krävs enligt standardinställningen i de flesta webbläsare. En P3P-profil anger för en webbläsare som skickar cookien och hur informationen ska användas. |

Cookien har ett antal värden för att hantera hur besökarna upplever kampanjer:

| Värde | Definition |
|--- |--- |
| sessions-ID | Ett unikt ID för en användarsession. Som standard varar detta 30 minuter. |
| pc-ID | Ett halvpermanent ID för en besökares webbläsare. Varar 14 dagar. |
| check | Ett enkelt testvärde som används för att avgöra om en besökare stöder cookies. Ange varje gång en besökare begär en sida. |
| disable | Ange om besökarens inläsningstid överskrider den timeout som har konfigurerats i filen mbox.js. Som standard varar detta 1 timme. |

## Påverkan på mål för Safari-besökare på grund av ändringar i Apple WebKit-spårning {#section_2A2E5730ED7D4A0985C904AFEA310AAE}

**Hur fungerar Adobe Target Tracking?**

| Cookies | Detaljer |
|--- |--- |
| Första parts domäner | Detta är standardimplementeringen för Target-kunder.  &quot;mbox&quot;-cookies anges i kundens domän. |
| Spårning från tredje part | Spårning från tredje part är viktigt för reklam och riktad marknadsföring i Target och i Adobe Audience Manager (AAM).  Spårning från tredje part kräver serveröverskridande skripttekniker (cross-site scripting).  Målet använder två cookies, &quot;mboxSession&quot; och &quot;mboxPC&quot;, som anges i domänen `clientcode.tt.omtrd.net`. |


**Vad är Apples uppläggning?**

Från Apple:

&quot;Intelligent Tracking Prevention är en ny WebKit-funktion som minskar spårningen mellan webbplatser genom att ytterligare begränsa cookies och andra webbplatsdata.&quot;

&quot;Detta kallas för spårning mellan webbplatser och den cookie som används av `example-tracker.com` kallas för en cookie från tredje part. I våra tester fann vi populära webbplatser med över 70 sådana spårare, som alla i tysthet samlar in data om användarna.&quot;

| Metod | Detaljer |
|--- |--- |
| Förebyggande av intelligent spårning | Mer information finns i [Intelligent Tracking Prevention](https://webkit.org/blog/7675/intelligent-tracking-prevention/) på webbplatsen WebKit Open Source Web Browser Engine. |
| Cookies | Hur Safari hanterar cookies:<ul><li>Cookies från tredje part som inte finns på en domän som användaren kommer åt direkt sparas aldrig. Det här beteendet är inte nytt. Cookies från tredje part stöds redan i Safari.</li><li>Cookies från tredje part som anges på en domän som användaren kommer åt direkt rensas efter 24 timmar.</li><li>cookies från första part rensas efter 30 dagar om den förstahandsdomänen har klassificerats som spårning av användare på olika webbplatser. Problemet kan gälla stora företag som skickar användare till olika domäner online. Apple har inte klargjort hur dessa domäner kommer att klassificeras eller hur en domän kan avgöra om de har klassificerats som spårning av användare på olika platser.</li></ul> |
| Maskininlärning för att identifiera domäner som är flera platser | Från Apple:<br>Maskinininlärningsklassificering: En maskininlärningsmodell används för att klassificera vilka av de främsta privatkontrollerade domänerna som kan spåra användarens webbplats, baserat på den insamlade statistiken. Av de olika insamlade uppgifterna visade det sig att tre vektorer har en stark signal för klassificering baserat på nuvarande spårningspraxis: underresurs under antal unika domäner, underbildruta under antal unika domäner och antal unika domäner som omdirigeras till. All datainsamling och klassificering sker på enheten.<br>Men om användaren interagerar med example.com som den översta domänen, som ofta kallas förstahandsdomän, anser Intelligent Tracking Prevention att det är en signal om att användaren är intresserad av webbplatsen och tillfälligt anpassar sitt beteende enligt den här tidslinjen:<br>Om användaren interagerade med example.com de senaste 24 timmarna är cookies tillgängliga när  `example.com` är tredje part. Detta gör att du kan logga in med mitt X-konto på Y-inloggningsscenarier.<ul><li>Domäner som besöktes som toppnivådomäner påverkas inte. Exempel på platser som OKTA</li><li>Identifierar domäner som är underdomäner eller underramar till den aktuella sidan över flera unika domäner.</li></ul> |

**Hur kommer Adobe att påverkas?**

| Funktioner som påverkas | Detaljer |
|--- |--- |
| Stöd för avanmälan | Apples WebKit tracking changes break opt out support.<br>Målavanmälan använder en cookie i  `clientcode.tt.omtrdc.net` domänen. Mer information finns i [Integritet](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md).<br>Målet har stöd för två avanmälningar:<ul><li>En per klient (klienten hanterar länken för avanmälan).</li><li>Ett via Adobe som gör att användaren slipper alla Target-funktioner för alla kunder.</li></ul>Båda metoderna använder cookie-filen från tredje part. |
| Verksamheter som riktar sig till | Kunderna kan välja sin längd [för profilens livslängd](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) för sina Target-konton, upp till 90 dagar. Problemet är att om kontots profillivstid är längre än 30 dagar och cookie-filen rensas bort eftersom kundens domän har markerats som spårning av användare på alla webbplatser, påverkas beteendet för Safari-besökare i följande områden i Target:<br>**Målrapporter**: Om en Safari-användare går in i en aktivitet returneras efter 30 dagar och konverteras sedan räknas användaren som två besökare och en konvertering.<br>Detta beteende är detsamma för aktiviteter som använder Analytics som rapportkälla (A4T).<br>**Profil- och aktivitetsmedlemskap**:<ul><li>Profildata raderas när cookie-filen från första part förfaller.</li><li>Aktivitetsmedlemskapet raderas när cookie-filen från första part förfaller.</li><li> Målet fungerar inte i Safari för konton som använder en cookie-implementering från tredje part eller en cookie-implementering från första och tredje part. Observera att det här beteendet inte är nytt. Safari har inte tillåtit cookies från tredje part på ett tag.</li></ul><br>**Förslag**: Om det finns en oro för att kunddomänen kan markeras som en spårning av besökare mellan sessioner, är det säkraste att ange profilens livstid till 30 dagar eller färre i Target. På så sätt spåras användare på samma sätt i Safari och alla andra webbläsare. |