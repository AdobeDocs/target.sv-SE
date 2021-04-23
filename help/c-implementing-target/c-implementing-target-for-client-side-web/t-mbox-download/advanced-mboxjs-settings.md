---
keywords: avancerade inställningar för mbox.js;client;server domain;xdomain;compression level;client session id support;secureOnly;client pc id support;pass page;referenssida;trafiknivå;trafikvaraktighet;mboxParameters() function body body;mboxSupported() function body;mboxCookieDomain() function body body;Extra JavaScript;SiteCatalyst plug-in;Get mbox.js as self-self-self-self-funktionbody extrahera JavaScript;flimmer;brödtext döljer;dölj brödtext
description: Läs om den gamla implementeringen av mbox.js i Adobe Target. Migrera till Adobe Experience Platform Web SDK (AEP Web SDK) eller till den senaste versionen av at.js.
title: Hur konfigurerar jag biblioteket [!DNL Target] mbox.js?
feature: at.js
role: Developer
exl-id: 17821e60-2692-49af-a225-764bd1b6aec1
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Konfigurera mbox.js

Information som hjälper dig att ange flera inställningar på sidan med inställningar för mbox.js.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

Standardinställningarna för funktionsbiblioteket [!DNL mbox.js] uppfyller behoven hos de flesta [!DNL Target]-kunder.

Kontakta din kontorepresentant om det behövs för att ändra [!DNL mbox.js]-inställningarna.

Följande inställningar är tillgängliga:

## Klient

Klientkoden för ditt konto.

När du visar [!UICONTROL Administration > Implementation] är klienten överst klientkoden för ditt konto.

## Timeout

Timeout för målbegäran.

När du visar [!UICONTROL Administration > Implementation] är inställningen Timeout (sekunder) timeout för målbegäran. Som standard är det här värdet 15 sekunder, men vi rekommenderar att du anger ett värde mellan 2 sekunder och 5 sekunder.

## XDomain

Avgör om webbläsaren ställer in cookies i din egen domän (cookies från första part), målets domän eller både och.

Om du ändrar den här inställningen påverkas både mbox.js och at.js.

## Komprimeringsnivå

Anger hur komprimerad biblioteksfilen mbox.js är. Om du ökar komprimeringsnivån minskar sidinläsningstiden.

## Funktionstexten mboxParameters()

Returnerar extra parametrar som ska skickas till varje mbox-anrop.

Exempel:

return &quot;test=123&quot;;

## Funktionstexten mboxSupported()

Returnerar false för att exkludera specifika användare.

Exempel:

return !navigator.userAgent.indexOf(&#39;Safari&#39;) != -1;

Följande webbläsare kan accepteras eller uteslutas:

* IE 5.0 eller senare (Windows)
* Netscape 5.0 eller senare (Mac, Windows, Linux)
* Safari 1.2.4 eller senare (Mac)
* Mozilla Firefox 1.0 eller senare (Mac, Windows, Linux)

## Funktionstexten mboxCookieDomain()

Returnerar en sträng som beskriver domänen för att ange cookies från första part.

Exempel:

return &quot;YOUR-DOMAIN&quot;;

## Extra JavaScript

Inkluderar eventuellt ytterligare JavaScript som du vill köra på varje sida.

## SiteCatalyst plug-in

Aktiverar plugin-programmet Analytics Target.

Om det här alternativet är aktiverat genererar Analytics-plugin-programmet plugin-kod i mbox.js. Detta skickar Analytics-tagginformation till Target-servrar som en mbox-begäran på varje sida som taggas med Analytics.

Observera att plugin-programmet Analytics fortfarande måste refereras till på sidan.

## secureOnly

Anger om mbox.js ska använda enbart HTTPS eller tillåtas växla mellan HTTP och HTTPS baserat på sidprotokollet. Det här är en avancerad inställning som har standardvärdet False.
