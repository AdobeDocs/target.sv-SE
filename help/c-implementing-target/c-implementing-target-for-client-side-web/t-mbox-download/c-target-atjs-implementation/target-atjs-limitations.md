---
keywords: visual experience composer limitations;browser support;integrations;plugins;asynchronous considerations
description: Det finns vissa skillnader mellan at.js och mbox.js. I det här avsnittet beskrivs några skillnader och begränsningar som hjälper dig att lyckas med at.js.
title: at.js Begränsningar
feature: null
uuid: 6c2dfd85-4c4d-4204-a9e9-e358f0b70ded
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---


# at.js Begränsningar{#at-js-limitations}

Det finns vissa skillnader mellan at.js och mbox.js. I det här avsnittet beskrivs några skillnader och begränsningar som hjälper dig att lyckas med at.js.

## Kända begränsningar för Visual Experience Composer {#section_4B63C97169DE4C93B22944E880FD3DF1}

* Alternativen Infoga element och Ordna om i Visual Experience Composer bör undvikas i enkelsidiga program.

   Eftersom DOM inte rensas på sidinläsningshändelser i enkelsidiga program, som det är med traditionella webbplatser, kan ändringarna Infoga element och Ordna om tillämpas flera gånger beroende på hur besökaren navigerar i SPA.

## Integreringar och plugin-program {#section_D92E31170176406AAC7B5005F03D3425}

Vissa funktioner i [!DNL mbox.js] är inte tillgängliga i [!DNL at.js]. Interna [mbox.js-objekt och -metoder](../../../../c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537) (som `mbox`, `mboxCurrent`, `mboxFactoryDefault`, `mboxFactories`m.fl.) stöds inte längre av [!DNL at.js] (exempel: `mboxFactoryDefault`). Detta är utformat för att avskräcka dig från att&quot;hacka&quot; [!DNL at.js] för att utveckla funktioner som inte stöds och som på lång sikt kan förlama en implementering och göra det omöjligt att uppgradera. De enda exponerade metoderna beskrivs på API-sidorna i den här dokumentationen. På grund av detta:

* Äldre, sidbaserade [integreringar](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39) med andra Adobe-lösningar kanske inte fungerar och bör uppgraderas till nyare, serverbaserade integreringar.
* [Anpassade plugin-program som utvecklats för mbox.js](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF) kanske inte fungerar om de inte har uppdaterats för [!DNL at.js].

   Se till att du inkluderar eventuella [plugin-program](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF) som en del av testningen.

## Asynkrona överväganden {#section_B586360A3DD34E2995AE25A18E3FB953}

Eftersom alla rutor nu är asynkrona blockerar de inte sidåtergivning eller returnerar i den ordning som de utlöses.

* Om du använder en global mbox i den [formulärbaserade Experience Composer](../../../../c-experiences/experiences.md#section_3643394BD424463C8768F2907DEBCC22)ska du tänka på att HTML-erbjudanden bara ska innehålla `<script>`-, `<style>`- och `<link>` -taggar.

   Under leveransen filtreras alla andra HTML-taggar bort när globala mbox-erbjudanden tillämpas [!DNL at.js] . Global Mbox-erbjudanden gäller för HTML HEAD, vilket inte tillåter DIV, SPAN o.s.v. Det `<div>test</div>` går till exempel inte att använda eftersom `<div>` -taggen bara kan användas inuti HTML BODY.

* Äldre sidbaserad [!DNL Target] till [!DNL Analytics] integration fungerar inte.

   Den här integreringen kräver att [!DNL Target] samtalet görs före [!DNL Analytics] samtalet.

* Se upp för JavaScript-beroenden mellan ditt erbjudande och sidan.

   Du bör inte anta att JavaScript-koden i ditt erbjudande kommer att köras före den hårdkodade JavaScript-koden nedanför mbox.

* Se upp för JavaScript-beroenden mellan flera erbjudanden på sidan.

   Du kan inte längre anta att erbjudandet som levereras av den första mbox kommer att verkställas innan erbjudandet som levereras av den andra mbox.

* Erbjudandena om DOM-manipulering och omdirigering bör levereras via den automatiskt skapade globala mbox i [!DNL at.js] och levereras i `<head>`.

   En `mboxCreate()` funktion högst upp i `<body>` kommer troligen att resultera i att standardinnehållet flimrar.

