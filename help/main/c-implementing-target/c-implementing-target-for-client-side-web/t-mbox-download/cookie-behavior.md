---
keywords: Översikt och referens;webbkit;cookies;first-party;third-party;1st-party;3third-party
description: Läs mer om [!DNL Target] cookie-beteende (cookie från första part, cookie från tredje part med cookie från första part eller cookie från tredje part enbart).
title: Var hittar jag information om [!DNL Target] Cookies?
feature: at.js
role: Developer
exl-id: 1c4e5b0b-8ae4-4526-aea0-318a33f4d247
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '1557'
ht-degree: 0%

---

# Målcookies

Cookie-beteendet beror på om det är en cookie från en annan leverantör, en cookie från en annan tillverkare med en cookie från en annan leverantör eller en cookie från en annan tillverkare.

>[!NOTE]
>
>Det här avsnittet innehåller information om `mboxSession` och `mboxPC`. Bästa praxis för implementering rekommenderar att du inte länkar eller lagrar känslig information med cookie-data: `mboxSession` eller `mboxPC`.

Se även [Ta bort målcookien](https://developer.adobe.com/target/before-implement/privacy/cookie-deleting/){target=_blank}.

## När cookies från första eller tredje part ska användas {#section_F71B29420C004A7FA3B1921E619B326E}

Platskonfigurationen avgör vilka cookies du vill använda. Det är till hjälp att förstå hur [!DNL Target] fungerar när du försöker förstå cookies från första och tredje part. Se [Hur [!DNL Adobe Target] Works](/help/main/c-intro/how-target-works.md#concept_459AB4DEE7364A9290C2FD405DC29584) för mer information.

Det finns tre huvudsakliga användningsområden för cookies:

1. En domän.

   Alla testerna utförs i en toppnivådomän (`www.domain.com`, `store.domain.com`, `anysub.domain.com`och så vidare).

   Metod: Använd endast cookies från första part (standard).

1. Användare överskrider domäner och du vill spåra och testa deras beteende i dessa domäner.

   Exempel: En användare kommer till er sajt för att handla men checkar ut genom Yahoos butiker. Tre metoder (samarbeta med din kontorepresentant för att fastställa det bästa tillvägagångssättet):

   * Aktivera cookies från första och tredje part.
   * Aktivera endast tredjepartscookie (sällsynt, men har fördelen att inte ta bort mbox-cookien från din domän).
   * Aktivera endast cookies och pass från första part `mboxSession` parameter när domänen korsas.

      The `mboxSession` -parametern måste skickas till en landningssida och refereras från JavaScript-biblioteket (Adobe Experience Platform Web SDK eller at.js). Det kan inte vara en mellanliggande omdirigeringssida.

1. Du använder bara adboxar eller FlashBox på en tredjepartswebbplats.

   Två metoder (tillsammans med din kontorepresentant för att fastställa det bästa tillvägagångssättet):

   * Aktivera cookies från första och tredje part.

      För FlashBox och dynamiska kreatörer krävs cookies från första och tredje part.

   * Aktivera endast cookies från tredje part.

      Detta tillvägagångssätt gäller endast i de sällsynta fall där AdBox-implementeringar används utan målinriktning på plats.

## Cookie-beteende från första part {#section_CE6313D979EA4D0897D2F661E7A8AFA7}

Den första partens cookie lagras i [!DNL clientdomain.com], där `clientdomain` är din domän.

JavaScript-biblioteket genererar en `mboxSession ID` och sparar det i [!DNL Target] cookie. Det första mbox-svaret innehåller erbjudandet och JavaScript-koden som lagrar `mboxPC ID` som genereras av programmet, i mbox-cookien.

>[!NOTE]
>
>The [!DNL AMCV_###@AdobeOrg] cookie för första part anges alltid med [!DNL Experience Cloud Visitor ID].

## Cookie-beteende från tredje part {#section_4C3A83990BF8415BB1806602D84AED48}

Tredjepartskakan lagras i [!DNL clientcode.tt.omtrdc.net] och cookie-filen från första part lagras i [!DNL clientdomain.com], där `clientdomain` är din domän.

JavaScript-biblioteket genererar en `mboxSession ID`. Den första platsbegäran returnerar HTTP-svarshuvuden som försöker ange cookies från tredje part med namnet `mboxSession` och `mboxPC` och en omdirigeringsbegäran skickas tillbaka med en extra parameter ( `mboxXDomainCheck=true`).

Om webbläsaren accepterar cookies från tredje part inkluderar omdirigeringsbegäran dessa cookies och erbjudandet returneras.

Om webbläsaren avvisar cookies från tredje part inkluderar omdirigeringsbegäran inte dessa cookies, och standardinnehåll visas för alla platser på sidan. Eftersom det inte finns några angivna cookies sker samma process ovan igen vid varje sidbegäran.

>[!NOTE]
>
>The [!DNL demdex.net] cookie anges om cookies från tredje part inte blockeras.

## Cookie-beteende för tredje part och första part {#section_F0C9AD8BFDF8457A999C4A07A0F7A981}

Tredjepartskakan lagras i [!DNL clientcode.tt.omtrdc.net] och cookie-filen från första part lagras i [!DNL clientdomain.com], där `clientdomain` är din domän.

JavaScript-biblioteket genererar en `mboxSession ID`. Den första platsbegäran returnerar HTTP-svarshuvuden som försöker ange cookies från tredje part med namnet `mboxSession` och `mboxPC`och en omdirigeringsbegäran skickas tillbaka med en extra parameter (`mboxXDomainCheck=true`).

Om webbläsaren accepterar cookies från tredje part inkluderar omdirigeringsbegäran dessa cookies och erbjudandet returneras.

Vissa webbläsare avvisar cookies från tredje part. Om cookie-filen från tredje part är blockerad fungerar fortfarande cookie-filen från den första parten. [!DNL Target] försöker ange cookie-filen från tredje part, och om den inte kan göra det [!DNL Target] kan bara spåra på klientens specifika domän. Spårning över domäner fungerar inte om cookie-filen från tredje part blockeras, såvida inte `mboxSession` läggs till i länken som korsar domäner. I det här fallet ställs en annan cookie in och synkroniseras med den tidigare domänens cookie.

## Cookie-inställningar {#section_B498B8D1A34A444BBF84CC720EE9D87F}

Cookien har flera standardinställningar. Du kan ändra de här inställningarna om det behövs, förutom cookie-varaktighet. Kontakta din kontorepresentant när du ändrar cookie-inställningarna.

| Inställning | Information |
|--- |--- |
| Cookie-namn | mbox. |
| Cookie-domän | Den andra och den översta nivån i de domäner som du underhåller innehållet från. Eftersom cookie används av ditt företags domän är den en cookie från första part.<br>Exempel: `mycompany.com`. |
| Serverdomän | `clientcode.tt.omtrdc.net`, med hjälp av klientkoden för ditt konto. |
| Cookie-varaktighet | Cookien finns kvar i besökarens webbläsare två veckor efter den senaste inloggningen. Du kan inte ändra varaktighet för cookie-filen. |
| P3P-princip | Cookien publiceras med en P3P-princip, vilket krävs enligt standardinställningen i de flesta webbläsare. En P3P-profil anger för en webbläsare som skickar cookien och hur informationen används. |

Denna cookie har olika värden för att hantera hur besökarna upplever kampanjer:

| Värde | Definition |
|--- |--- |
| sessions-ID | Ett unikt ID för en användarsession. Detta ID varar som standard i 30 minuter. |
| pc-ID | Ett halvpermanent ID för en besökares webbläsare. Varar 14 dagar. |
| check | Ett enkelt testvärde som används för att avgöra om en besökare stöder cookies. Ange varje gång en besökare begär en sida. |
| disable | Ange om besökarens inläsningstid överskrider den timeout som har konfigurerats i JavaScript-biblioteksfilen. Som standard varar det här värdet en timme. |

## Påverkan på [!DNL Target] för Safari-besökare på grund av Apple WebKit-spårningsändringar {#section_2A2E5730ED7D4A0985C904AFEA310AAE}

**Hur [!DNL Adobe Target] spårningsarbete?**

| Cookies | Detaljer |
|--- |--- |
| Första parts domäner | Standardimplementering för [!DNL Target] kunder. &quot;mbox&quot;-cookies anges i kundens domän. |
| Spårning från tredje part | Spårning från tredje part är viktigt för annonsering och målgruppsanvändning i [!DNL Target] och in [!DNL Adobe Audience Manager] (AAM). Spårning från tredje part kräver serveröverskridande skripttekniker (cross-site scripting). [!DNL Target] använder två cookies, &quot;mboxSession&quot; och &quot;mboxPC&quot; som anges i `clientcode.tt.omtrd.net` domän. |
**Vad är Apple tillvägagångssätt?**

Från Apple:

&quot;Intelligent Tracking Prevention är en ny WebKit-funktion som minskar spårningen mellan webbplatser genom att ytterligare begränsa cookies och andra webbplatsdata.&quot;

&quot;Det här kallas spårning på olika webbplatser och cookie-filen som används av `example-tracker.com` kallas en cookie från tredje part. I våra tester fann vi populära webbplatser med över 70 sådana spårare, som alla i tysthet samlar in data om användarna.&quot;

| Metod | Detaljer |
|--- |--- |
| Förebyggande av intelligent spårning | Mer information finns i [Intelligent spårningsförebyggande](https://webkit.org/blog/7675/intelligent-tracking-prevention/) på webbplatsen WebKit Open Source Web Browser Engine. |
| Cookies | Hur Safari hanterar cookies:<ul><li>Cookies från tredje part som inte finns på en domän som användaren kommer åt direkt sparas aldrig. Det här beteendet är inte nytt. Cookies från tredje part stöds redan i Safari.</li><li>Cookies från tredje part som anges på en domän som användaren kommer åt direkt rensas efter 24 timmar.</li><li>cookies från första part rensas efter 30 dagar om den förstahandsdomänen har klassificerats som spårning av användare på olika webbplatser. Problemet kan gälla stora företag som skickar användare till olika domäner online. Apple har inte klargjort hur exakt dessa domäner klassificeras, eller hur en domän kan avgöra om de har klassificerats som spårning av användare på olika webbplatser.</li></ul> |
| Maskininlärning för att identifiera domäner som är flera platser | Från Apple:<br>Maskininlärningsklassificering: En maskininlärningsmodell används för att klassificera vilka av de främsta privatkontrollerade domänerna som kan spåra användarens webbplats, baserat på insamlad statistik. Av de olika insamlade uppgifterna visade det sig att tre vektorer har en stark signal för klassificering baserat på nuvarande spårningspraxis: underresurs under antal unika domäner, underbildruta under antal unika domäner och antal unika domäner som omdirigeras till. All datainsamling och klassificering sker på enheten.<br>Men om användaren interagerar med `example.com` Som den översta domänen, som ofta kallas förstahandsdomän, anser Intelligent Tracking Prevention att det är en signal om att användaren är intresserad av webbplatsen och tillfälligt anpassar sitt beteende enligt den här tidslinjen:<br>Om användaren interagerade med `example.com` de senaste 24 timmarna är cookies tillgängliga när `example.com` är en tredje part. Den här metoden tillåter inloggning med mitt X-konto på Y.<ul><li>Domäner som besöktes som toppnivådomäner påverkas inte. Exempel på platser som OKTA</li><li>Identifierar domäner som är underdomäner eller underramar till den aktuella sidan över flera unika domäner.</li></ul> |

**Hur påverkas Adobe?**

| Funktioner som påverkas | Detaljer |
|--- |--- |
| Stöd för avanmälan | Stöd för avanmälan om ändringsbrytningar för Apple WebKit-spårning.<br>[!DNL Target] avanmälan använder en cookie i `clientcode.tt.omtrdc.net` domän. Mer information finns i [Integritet](https://developer.adobe.com/target/before-implement/privacy/privacy/){target=_blank}.<br>[!DNL Target] har stöd för två avanmälningar:<ul><li>En per klient (klienten hanterar länken för avanmälan).</li><li>En via [!DNL Adobe] som gör användaren borta från alla [!DNL Target] för alla kunder.</li></ul>Båda metoderna använder cookie-filen från tredje part. |
| [!DNL Target] verksamhet | Kunderna kan själva välja [livslängd för profil](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) för [!DNL Target] konton (upp till 90 dagar). Problemet är att om kontots profillivstid är längre än 30 dagar och cookie-filen rensas bort eftersom kundens domän har markerats som spårning av användare på alla webbplatser påverkas beteendet för Safari-besökare i följande områden i [!DNL Target]:<br>**[!DNL Target] rapporter **: Om en Safari-användare går in i en aktivitet returneras efter 30 dagar och konverteras sedan räknas användaren som två besökare och en konvertering.<br>Detta beteende är detsamma för aktiviteter som använder [!DNL Analytics] som rapportkälla (A4T).<br>** Profil- och aktivitetsmedlemskap **:<ul><li>Profildata raderas när cookie-filen från första part förfaller.</li><li>Aktivitetsmedlemskapet raderas när cookie-filen från första part förfaller.</li><li> [!DNL Target] fungerar inte i Safari för konton som använder en cookie-implementering från tredje part eller en cookie-implementering från första och tredje part. Det här beteendet är inte nytt. Safari har inte tillåtit cookies från tredje part på ett tag.</li></ul><br>**Förslag**: Om det finns en oro för att kunddomänen kan markeras som en spårning av besökare under en korssession, är det säkraste att ange profilens livstid till 30 dagar eller mindre under [!DNL Target]. Den här gränsen gör att användare spåras på liknande sätt i Safari och alla andra webbläsare. |
