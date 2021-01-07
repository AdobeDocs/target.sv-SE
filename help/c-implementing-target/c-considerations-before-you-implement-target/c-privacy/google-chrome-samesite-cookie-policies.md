---
keywords: google;samesite;cookies;chrome 80;ietf
description: Information om Adobe Target och IETF-standarden SameSite som introducerades med Google Chrome version 80.
title: Cookie-policyer för Adobe Target och Google's SameSite
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '2033'
ht-degree: 0%

---


# Google Chrome SameSite cookie-principer

Google börjar som standard att införa nya cookie-principer för användare som börjar med Chrome 80, som kommer att släppas i början av 2020. I den här artikeln förklaras allt du behöver veta om de nya reglerna för cookie-filer för samma plats, hur [!DNL Adobe Target] stöder dessa principer och hur du kan använda [!DNL Target] för att följa de nya reglerna för cookie-filer för samma plats i Google Chrome.

Från och med Chrome 80 måste webbutvecklare uttryckligen ange vilka cookies som kan användas på olika webbplatser. Det här är den första av många meddelanden som Google planerar att göra för att förbättra sekretess och säkerhet på webben.

Med tanke på att Facebook har funnits på plats när det gäller sekretess och säkerhet har andra stora aktörer som Apple, och nu Google, snabbt dragit nytta av möjligheten att skapa nya identiteter som integritets- och säkerhetskamrater. Apple ledde paketet genom att först meddela ändringar av cookie-reglerna tidigt i år via ITP 2.1 och nyligen ITP 2.2. I ITP 2.1 blockerar Apple helt cookies från tredje part och sparar cookies som skapats i webbläsaren i endast sju dagar. I ITP 2.2 sparas cookies i endast en dag. Googles kungörelse är inte alls lika aggressiv som Apples, men det är det första steget mot samma slutmål. Mer information om Apples regler finns i [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

## Vad är cookies och hur används de?

Innan vi börjar dyka upp i Googles ändringar av cookies-policyn måste vi ta hänsyn till vilka cookies som är och hur de används. Kakor är enkelt uttryckt små textfiler som lagras i webbläsaren och som används för att komma ihåg användarattribut.

Cookies är viktiga eftersom de förbättrar användarens upplevelse när han/hon surfar på webben. Om du till exempel handlar på en e-handelswebbplats och lägger till något i kundvagnen, men inte loggar in eller köper på det besöket, kommer cookies att spara dina artiklar i kundvagnen för nästa besök. Eller tänk om du tvingades ange ditt användarnamn och lösenord på nytt varje gång du besöker din sociala medias webbplats. Cookies löser det problemet också eftersom de lagrar information som hjälper webbplatser att identifiera vem du är. Den här typen av cookies kallas cookies från första part eftersom de skapas och används av webbplatsen som du besökte.

Det finns även cookies från tredje part. Låt oss titta på följande exempel för att förstå dem bättre:

Låt oss säga att ett hypotetiskt företag för sociala medier, som kallas&quot;vänner&quot;, har en Dela-knapp som andra webbplatser implementerar för att göra det möjligt för vänner-användare att dela webbplatsens innehåll på Vänner-flödet. Nu läser en användare en nyhetsartikel på en nyhetswebbplats som använder knappen Dela och klickar på den för att automatiskt publicera den på sitt vänkonto.

För att detta ska hända hämtar webbläsaren knappen Dela vänner från `platform.friends.com` när nyhetsartikeln läses in. I den här processen bifogar webbläsaren cookies, som innehåller användarens inloggade uppgifter, till begäran till vänservrar. Detta gör att vänner kan publicera nyhetsartikeln i sin feed åt användaren utan att användaren behöver logga in.

Allt detta är möjligt med cookies från tredje part. I det här fallet sparas cookien från tredje part i webbläsaren för `platform.friends.com`, så att `platform.friends.com` kan göra inlägget i appen Vänner för användarens räkning.

Om du för ett ögonblick tänker dig hur du ska uppnå detta utan cookies från tredje part måste användaren följa en massa manuella steg. Först måste användaren kopiera länken till nyhetsartikeln. För det andra måste användaren logga in i Friends-appen separat. Användaren klickar sedan på knappen Skapa inlägg. Användaren kopierar och klistrar sedan in länken i textfältet och klickar slutligen på Publicera. Som du ser kan cookies från tredje part hjälpa användaren att uppleva manuella steg som kan minskas drastiskt.

Mer generellt gör cookies från tredje part det möjligt att lagra data i en användares webbläsare utan att användaren behöver besöka en webbplats explicit.

## Säkerhetsproblem

Även om cookies förbättrar användarupplevelser och strömannonsering kan de även medföra säkerhetsrisker som CSRF-attacker (Cross-Site Request Forgery). Om en användare till exempel loggar in på en bankwebbplats för att betala kreditkortsräkningar och lämnar webbplatsen utan att logga ut och sedan bläddrar till en skadlig webbplats i samma session, kan en CSRF-attack inträffa. Den skadliga webbplatsen kan innehålla kod som gör en förfrågan till bankwebbplatsen som verkställs när sidan läses in. Eftersom användaren fortfarande är autentiserad på bankwebbplatsen kan sessionscookie användas för att starta en CSRF-attack för att initiera en penningöverföringshändelse från användarens bankkonto. Detta beror på att när du besöker en webbplats bifogas alla cookies i HTTP-begäran. Och på grund av dessa säkerhetsproblem försöker Google nu mildra dem.

## Hur använder Target cookies?

Låt oss se hur [!DNL Target] använder cookies. För att du ska kunna använda [!DNL Target] måste du installera JavaScript-biblioteket [!DNL Target] på din plats. Detta gör att du kan placera en cookie från en annan leverantör i webbläsaren på den användare som besöker webbplatsen. När användaren interagerar med webbplatsen kan du skicka användarens beteendedata och intressedata till [!DNL Target] via JavaScript-biblioteket. JavaScript-biblioteket [!DNL Target] använder cookies från första part för att extrahera identifieringsinformation om användaren för att mappa till användarens beteende och intressedata. Dessa data används sedan av [!DNL Target] för att driva dina personaliseringsaktiviteter.

Target använder även (ibland) cookies från tredje part. Om du har flera webbplatser som finns på olika domäner och du vill spåra användarresan över dessa webbplatser kan du använda cookies från tredje part genom att utnyttja spårning mellan domäner. Genom att aktivera spårning över domäner i JavaScript-biblioteket [!DNL Target] börjar ditt konto använda cookies från tredje part. När en användare hoppar från en domän till en annan kommunicerar webbläsaren med backend-servern för [!DNL Target], och i den här processen skapas en cookie från tredje part som placeras i användarens webbläsare. Genom den cookie från tredje part som finns i användarens webbläsare kan [!DNL Target] leverera en enhetlig upplevelse över olika domäner för en enskild användare.

## Googles nya cookie-recept

Google planerar att lägga till stöd för en IETF-standard som kallas SameSite, vilket kräver att webbutvecklare hanterar cookies med attributkomponenten SameSite i huvudet Set-Cookie, för att skydda cookies som skickas mellan webbplatser så att användare skyddas.

Det finns tre olika värden som kan skickas till attributet SameSite: Strikt, Lax eller Ingen.

| Värde | Beskrivning |
| --- | --- |
| Strikt | Cookies med den här inställningen går bara att komma åt när du besöker den domän där den ursprungligen var inställd. Strict blockerar med andra ord helt cookie-filen från att användas på olika webbplatser. Det här alternativet passar bäst för program som kräver hög säkerhet, t.ex. banker. |
| Lax | Cookies med den här inställningen skickas endast på begäranden på samma plats eller navigering på den översta nivån med icke-idempotenta HTTP-begäranden, som `HTTP GET`. Det här alternativet skulle därför användas om cookien kan användas av tredje part, men med en extra säkerhetsförmån som skyddar användarna från att bli skadade av CSRF-attacker. |
| Ingen | Cookies med den här inställningen fungerar på samma sätt som cookies fungerar idag. |

Med Chrome 80 i åtanke introduceras två oberoende inställningar för användare: &quot;Samma webbplats som standard måste vara en säker cookies och &quot;Cookies utan SameSite.&quot; De här inställningarna aktiveras som standard i Chrome 80.

![Dialogrutan SameSite](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

* **Samma webbplats som standard: cookies**: När detta anges kommer alla cookies som inte anger attributet SameSite automatiskt att tvingas använda  `SameSite = Lax`.
* **Cookies utan SameSite måste vara säkra**: När detta anges  `SameSite = None` måste cookies utan attributet SameSite eller med Secure användas. Säkert i det här sammanhanget innebär att alla webbläsarbegäranden måste följa HTTPS-protokollet. Cookies som inte uppfyller detta krav avvisas. Alla webbplatser bör använda HTTPS för att uppfylla detta krav.

## Målet följer Googles bästa säkerhetspraxis

På Adobe vill vi alltid stödja branschens senaste metoder för säkerhet och integritet. Vi är glada att kunna meddela att [!DNL Target] stöder de nya säkerhets- och sekretessinställningarna som Google har infört.

För inställningen&quot;SameSite som standard-cookies&quot; kommer [!DNL Target] att fortsätta leverera personalisering utan påverkan och åtgärder från dig. [!DNL Target] använder cookies från första part och fortsätter att fungera korrekt när flaggan  `SameSite = Lax` används av Google Chrome.

För alternativet&quot;Cookies without SameSite must be secure&quot; (cookies utan SameSite måste vara säkra) fortsätter cookies från första part i [!DNL Target] att fungera om du inte väljer funktionen för spårning av korsdomän i [!DNL Target].

Om du väljer att använda spårning mellan domäner för att utnyttja [!DNL Target] i flera domäner kräver Chrome att `SameSite = None` och Säker flagga används för cookies från tredje part. Det innebär att du måste se till att dina webbplatser använder HTTPS-protokollet. Klientsidans bibliotek i [!DNL Target] använder automatiskt HTTPS-protokollet och bifogar flaggorna `SameSite = None` och Secure till cookies från tredje part i [!DNL Target] för att säkerställa att alla aktiviteter fortsätter att leverera.

## Vad behöver du göra?

Om du vill veta vad du behöver göra för att [!DNL Target] ska kunna fortsätta att arbeta för användare med Google Chrome 80+ läser du tabellen nedan, där du kommer att se följande kolumner:

* **JavaScript-målbibliotek**: Om du använder mbox.js, at.js 1.*x* eller at.js 2.*Visa* dina sajter.
* **SameSite som standard cookies = Aktiverad**: Om dina användare har aktiverat &quot;SameSite som standard-cookies&quot;, hur påverkar det dig och finns det något du behöver göra för  [!DNL Target] att fortsätta arbeta.
* **Cookies utan SameSite måste vara säkra = Aktiverad**: Om dina användare har aktiverat&quot;Cookies without SameSite must be secure&quot;, hur påverkar det dig och finns det något du behöver göra för att  [!DNL Target] fortsätta arbeta.

| JavaScript-målbibliotek | SameSite som standard-cookies = Aktiverad | Cookies utan SameSite måste vara säkra = Enabled |
| --- | --- | --- |
| mbox.js med endast cookie från första part. | Ingen påverkan. | Ingen påverkan om du inte använder spårning mellan domäner. |
| mbox.js med spårning mellan domäner aktiverat. | Ingen påverkan. | Du måste aktivera HTTPS-protokollet för din plats.<br>[!DNL Target] använder en cookie från tredje part för att spåra användare och Google kräver att cookies från tredje part har  `SameSite = None` och Säker flagga. För flaggan Secure måste dina webbplatser använda HTTPS-protokollet. |
| at.js 1.** med cookie. | Ingen påverkan. | Ingen påverkan om du inte använder spårning mellan domäner. |
| at.js 1.** xmed spårning mellan domäner aktiverat. | Ingen påverkan. | Du måste aktivera HTTPS-protokollet för din plats.<br>[!DNL Target] använder en cookie från tredje part för att spåra användare och Google kräver att cookies från tredje part har  `SameSite = None` och Säker flagga. För flaggan Secure måste dina webbplatser använda HTTPS-protokollet. |
| at.js 2.*x* | Ingen påverkan. | Ingen påverkan. |

## Vad behöver Target göra?

Så vad behöver vi göra på vår plattform för att hjälpa er att följa de nya cookie-reglerna för Google Chrome 80+ SameSite?

| JavaScript-målbibliotek | SameSite som standard-cookies = Aktiverad | Cookies utan SameSite måste vara säkra = Enabled |
| --- | --- | --- |
| mbox.js med endast cookie från första part. | Ingen påverkan. | Ingen påverkan om du inte använder spårning mellan domäner. |
| mbox.js med spårning mellan domäner aktiverat. | Ingen påverkan. | [!DNL Target] lägger till  `SameSite = None` och säkrar-flaggan i tredjeparts-cookie när  [!DNL Target] servrar anropas. |
| at.js 1.** med cookie. | Ingen påverkan. | Ingen påverkan om du inte använder spårning mellan domäner. |
| at.js 1.** xmed spårning mellan domäner aktiverat. | Ingen påverkan. | at.js 1.** xmed spårning mellan domäner aktiverat. |
| at.js 2.*x* | Ingen påverkan. | Ingen påverkan. |

## Vilken är effekten om du inte går över till HTTPS-protokollet?

Det enda användningsfallet som påverkar dig är om du använder funktionen för domänövergripande spårning i [!DNL Target] till mbox.js eller at.js 1.*x*. Utan att gå över till HTTPS, vilket är ett krav från Google, kommer ni att se en topp i unika besökare i era domäner eftersom den cookie från tredje part som vi använder kommer att tas bort av Google. Och eftersom cookie-filen från tredje part kommer att tas bort kommer [!DNL Target] inte att kunna tillhandahålla en konsekvent och anpassad upplevelse för den användaren när användaren navigerar från en domän till en annan. Den cookie som används av tredje part används främst för att identifiera en enskild användare som navigerar över domäner som du äger.

## Slutsats

I takt med att branschen strävar efter att skapa en säkrare webbsajt för konsumenterna är [!DNL Adobe] ett absolut engagemang för att hjälpa våra kunder att leverera personaliserade upplevelser på ett sätt som säkerställer säkerhet och integritet för slutanvändarna. Allt du behöver göra är att följa de ovan nämnda bästa metoderna och dra nytta av [!DNL Target] för att följa Google Chrome nya SameSite Cookie-principer.
