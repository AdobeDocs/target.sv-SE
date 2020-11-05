---
keywords: Target Standard;at.js;implementation
description: at.js-biblioteket är ett nytt implementeringsbibliotek för Adobe Target som är utformat för både vanliga webbimplementeringar och enkelsidiga program.
title: Migrera från mbox.js till at.js
feature: null
topic: Standard
uuid: 10da01d7-d308-44e3-9c6e-ff4f713bd312
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# Migrera från mbox.js till at.js{#migrate-from-mbox-js-to-at-js}

at.js-biblioteket är ett nytt implementeringsbibliotek som är utformat för både vanliga webbimplementeringar och enkelsidiga program. [!DNL Adobe Target]

Bland annat [!DNL at.js] förbättrar inläsningstiden för webbimplementeringar och ger bättre implementeringsalternativ för enkelsidiga applikationer.

[!DNL at.js] ersätts [!DNL mbox.js] för [!DNL Target] implementeringar. Biblioteket innehåller också de komponenter som ingick i [!DNL at.js] och därför finns det inte längre något anrop till [!DNL target.js][!DNL target.js].

>[!NOTE]
>
>Adobe Experience Manager (AEM) 6.2 med FP-11577 (eller senare) stöder at.js-implementeringar med integrering av Adobe Target-Cloud Services. Mer information finns i [Funktionspaket](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html) och [Integrera med Adobe Target](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html) i dokumentationen *för* Adobe Experience Manager 6.2.

## Fördelar med at.js {#benefits}

I följande tabell förklaras skillnaderna mellan de två biblioteken:

| Biblioteksreferens | Beskrivning |
|--- |--- |
| at.js | at.js ersätter mbox.js för [!DNL Target] implementeringar.<br>Bland annat har at.js förbättrat sidinläsningstiderna för webblöplementeringar, förbättrat säkerheten, förhindrat dokument.write-varningar i Google Chrome och gett bättre implementeringsalternativ för enkelsidiga program.<br>Mer information finns [i implementeringen](#implement)av at.js. |
| mbox.js | Före den [!DNL Target] 16.3.1 (mars 2016) [!DNL Target] krävdes ett anrop till mbox.js för att skapa den globala mbox som krävs för [!DNL Target] att leverera aktiviteter, spåra klick och spåra de flesta framgångsmått. Den här filen innehåller de bibliotek som behövs för alla dina aktiviteter. Du behöver inte underhålla olika aktivitetsspecifika versioner av filen.<br>Om du redan har kapslade rutor på sidorna från en äldre typ av [!DNL Target] implementering kan dessa rutor fortfarande användas i det nya gränssnittet. Den uppdaterade filen mbox.js krävs fortfarande, men dessa mbox kan väljas för aktiviteter och redigeras med Visual Experience Composer.<br>[!DNL Target] Standard och Premium - uppdatera och komplettera mbox.js med en referens till en target.js-fil. Filen target.js hanteras av Adobe. Med filen Target.js kan du redigera innehåll på alla sidor med Visual Experience Composer, även om sidan inte innehåller fördefinierade rutor. Du måste referera till den här filen på alla sidor på webbplatsen.<br>Mer information finns i Implementering av [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Viktigt**: Biblioteket mbox.js stöds fortfarande, men det kommer inte att finnas några funktionsuppdateringar. Alla kunder bör migrera till at.js. Mer information finns i [Migrera till at.js från mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md) |

## Implementera at.js {#implement}

Om du vill använda [!DNL at.js]ersätter du [!DNL mbox.js] referensen på sidor där du vill implementera den. Du kan inte använda både [!DNL mbox.js] och [!DNL at.js] på en sida. Du kan dock använda båda sidorna på webbplatsen.

Biblioteket fungerar för befintliga implementeringar med funktionerna [!DNL at.js] , `mboxCreate()`och `mboxDefine()``mboxUpdate()` och har stöd för nya funktioner som fokuserar på single-page-app-baserade implementeringar.

Du kan använda [!DNL at.js] var du än använder [!DNL mbox.js].

Biblioteket innehåller flera förbättringar av [!DNL at.js] [!DNL mbox.js] biblioteket, bland annat:

* Helt asynkron kommunikation via AJAX

   >[!IMPORTANT]
   >
   >Även om [!DNL at.js] kommunicerar med [!DNL Target] servrarna asynkront måste själva [!DNL at.js] filen läsas in synkront i `<head>` sidans avsnitt. Helst ska det vara ett av de första inlästa skripten. När den har lästs in körs [!DNL at.js] mbox-anrop asynkront igenom `XMLHttpRequest`och ingen sidåtergivning blockeras.

* Inga fler spärrsamtal
* Ingen `document.write()` användning
* Ingen omedelbar körning av JavaScript i [!DNL Target] svar
* Bättre timeout och felhantering

   * Anpassningsbar [tidsgräns](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) per samtal
   * Inga omladdningar vid timeout

* Funktioner som är särskilt utformade för single page-appar/MVC-ramverk

## Utbildningsvideo: at.js - brickan Advantages and Implementation Best Practices ![Overview](/help/assets/overview.png)

Den här videon är en inspelning av&quot; [Office Hours](/help/cmp-resources-and-contact-information.md)&quot;, ett projekt som leds av kundtjänstteamet på Adobe.

* Så fungerar biblioteket at.js
* Fördelarna med at.js jämfört med mbox.js
* Hur at.js hanterar flimmer
* Felhantering i at.js
* Felsökningsmetoder
* Kända fel och framtida färdplan

>[!VIDEO](https://video.tv.adobe.com/v/22223/)
