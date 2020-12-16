---
keywords: visual experience composer limitations;browser support;integrations;plugins;asynchronous considerations
description: Det finns vissa skillnader mellan at.js och mbox.js. I det här avsnittet beskrivs några skillnader och begränsningar som hjälper dig att lyckas med at.js.
title: at.js Begränsningar
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
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

Vissa funktioner i [!DNL mbox.js] är inte tillgängliga i [!DNL at.js]. Interna [mbox.js-objekt och -metoder](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537) (till exempel `mbox`, `mboxCurrent`, `mboxFactoryDefault` och `mboxFactories`) stöds inte längre av [!DNL at.js] (till exempel: `mboxFactoryDefault`). Detta är utformat för att avskräcka dig från att&quot;hacka&quot; [!DNL at.js] för att utveckla funktionalitet som inte stöds och som på lång sikt kan klappa en implementering och göra det omöjligt att uppgradera. De enda exponerade metoderna beskrivs på API-sidorna i den här dokumentationen. På grund av detta:

* Äldre, sidbaserade [integreringar](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39) med andra Adobe-lösningar kanske inte fungerar och bör uppgraderas till nyare serverintegreringar.
* [Anpassade plugin-program som utvecklats för mbox.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF) jsfungerar kanske inte om de inte har uppdaterats för  [!DNL at.js].

   Se till att du inkluderar alla [plugin-program](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF) som en del av testningen.

## Asynkrona överväganden {#section_B586360A3DD34E2995AE25A18E3FB953}

Eftersom alla rutor nu är asynkrona blockerar de inte sidåtergivning eller returnerar i den ordning som de utlöses.

* Om du använder en global mbox i [formulärbaserad Experience Composer](/help/c-experiences/experiences.md#section_3643394BD424463C8768F2907DEBCC22) ska du tänka på att HTML-erbjudanden bara ska innehålla taggarna `<script>`, `<style>` och `<link>`.

   Under leveransen filtrerar [!DNL at.js] bort alla andra HTML-taggar när globala mbox-erbjudanden används. Global Mbox-erbjudanden gäller för HTML HEAD, vilket inte tillåter DIV, SPAN o.s.v. Det går till exempel inte att använda `<div>test</div>` eftersom taggen `<div>` bara kan användas i HTML BODY.

* Äldre sidbaserad integrering mellan [!DNL Target] och [!DNL Analytics] fungerar inte.

   Den här integreringen kräver att anropet [!DNL Target] görs före anropet [!DNL Analytics].

* Se upp för JavaScript-beroenden mellan ditt erbjudande och sidan.

   Du bör inte anta att JavaScript-koden i ditt erbjudande kommer att köras före den hårdkodade JavaScript-koden nedanför mbox.

* Se upp för JavaScript-beroenden mellan flera erbjudanden på sidan.

   Du kan inte längre anta att erbjudandet som levereras av den första mbox kommer att verkställas innan erbjudandet som levereras av den andra mbox.

* Erbjudanden om DOM-manipulering och omdirigering ska levereras via den automatiskt skapade globala mbox i [!DNL at.js] och levereras i `<head>`.

   En `mboxCreate()`-funktion högst upp i `<body>` kommer troligen att resultera i att standardinnehållet flimrar.

