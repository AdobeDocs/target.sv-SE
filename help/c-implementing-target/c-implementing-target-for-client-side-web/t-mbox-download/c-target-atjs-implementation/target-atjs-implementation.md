---
keywords: Target Standard;at.js;implementation
description: at.js-biblioteket är ett nytt implementeringsbibliotek för Adobe Target som är utformat för både vanliga webbimplementeringar och enkelsidiga program.
title: Migrera från mbox.js till at.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# Migrera från mbox.js till at.js{#migrate-from-mbox-js-to-at-js}

at.js-biblioteket är ett nytt implementeringsbibliotek för [!DNL Adobe Target] som är utformat för både vanliga webbimplementeringar och enkelsidiga program.

[!DNL at.js] ger bland annat bättre sidladdningstider för webbimplementeringar och bättre implementeringsalternativ för enkelsidiga program.

[!DNL at.js] ersätts  [!DNL mbox.js] för  [!DNL Target] implementeringar. [!DNL at.js]-biblioteket innehåller även de komponenter som ingick i [!DNL target.js], så det finns inte längre något anrop till [!DNL target.js].

>[!NOTE]
>
>Adobe Experience Manager (AEM) 6.2 med FP-11577 (eller senare) stöder at.js-implementeringar med integrering av Adobe Target-Cloud Services. Mer information finns i [Funktionspaket](https://docs.adobe.com/docs/en/aem/6-2/release-notes/feature-packs.html) och [Integrera med Adobe Target](https://docs.adobe.com/docs/en/aem/6-2/administer/integration/marketing-cloud/target.html) i *Adobe Experience Manager 6.2-dokumentationen*.

## Fördelar med at.js {#benefits}

I följande tabell förklaras skillnaderna mellan de två biblioteken:

| Biblioteksreferens | Beskrivning |
|--- |--- |
| at.js | at.js ersätter mbox.js för [!DNL Target] implementeringar.<br>Bland annat har at.js förbättrat sidinläsningstiderna för webblöplementeringar, förbättrat säkerheten, förhindrat dokument.write-varningar i Google Chrome och gett bättre implementeringsalternativ för enkelsidiga program.<br>Mer information finns  [i implementeringen](#implement) av at.js. |
| mbox.js | Före [!DNL Target] 16.3.1 (mars 2016) behövde [!DNL Target] ett anrop till mbox.js för att skapa den globala mbox som krävs för att [!DNL Target] ska kunna leverera aktiviteter, spåra klick och spåra de flesta framgångsmått. Den här filen innehåller de bibliotek som behövs för alla dina aktiviteter. Du behöver inte underhålla olika aktivitetsspecifika versioner av filen.<br>Om du redan har kapslade rutor på sidorna från en äldre  [!DNL Target] implementeringsstil kan dessa rutor fortfarande användas i det nya gränssnittet. Den uppdaterade filen mbox.js krävs fortfarande, men dessa mbox kan väljas för aktiviteter och redigeras med Visual Experience Composer.<br>[!DNL Target] Standard och Premium - uppdatera och komplettera mbox.js med en referens till en target.js-fil. Filen target.js hanteras av Adobe. Med filen Target.js kan du redigera innehåll på alla sidor med Visual Experience Composer, även om sidan inte innehåller fördefinierade rutor. Du måste referera till den här filen på alla sidor på webbplatsen.<br>Mer information finns i Implementering av  [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Viktigt**: Biblioteket mbox.js stöds fortfarande, men det kommer inte att finnas några funktionsuppdateringar. Alla kunder bör migrera till at.js. Mer information finns i [Migrera till at.js från mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md) |

## Implementera at.js {#implement}

Om du vill använda [!DNL at.js] ersätter du referensen [!DNL mbox.js] på sidor där du vill implementera den. Du kan inte använda både [!DNL mbox.js] och [!DNL at.js] på en enda sida. Du kan dock använda båda sidorna på webbplatsen.

Biblioteket [!DNL at.js] fungerar för befintliga implementeringar med funktionerna `mboxCreate()`, `mboxDefine()` och `mboxUpdate()` och har stöd för nya funktioner som fokuserar på single-page-appbaserade implementeringar.

Du kan använda [!DNL at.js] var du än använder [!DNL mbox.js].

[!DNL at.js]-biblioteket innehåller flera förbättringar av [!DNL mbox.js]-biblioteket, bland annat:

* Helt asynkron kommunikation via AJAX

   >[!IMPORTANT]
   >
   >Även om [!DNL at.js] kommunicerar med [!DNL Target]-servrarna asynkront måste själva [!DNL at.js]-filen läsas in synkront i `<head>`-avsnittet på sidan. Helst ska det vara ett av de första inlästa skripten. När den har lästs in kör [!DNL at.js] mbox-anrop asynkront via `XMLHttpRequest`, och blockerar inte sidåtergivning.

* Inga fler spärrsamtal
* Ingen `document.write()` används
* Ingen omedelbar körning av JavaScript i [!DNL Target]-svar
* Bättre timeout och felhantering

   * Anpassningsbar [timeout](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) per anrop
   * Inga omladdningar vid timeout

* Funktioner som är särskilt utformade för single page-appar/MVC-ramverk

## Utbildningsvideo: at.js - Fördelar och bästa praxis för implementering ![Översikt](/help/assets/overview.png)

Den här videon handlar om inspelningen av &quot; [kontorstid](/help/cmp-resources-and-contact-information.md)&quot;, ett projekt som leds av kundtjänstteamet på Adobe.

* Så fungerar biblioteket at.js
* Fördelarna med at.js jämfört med mbox.js
* Hur at.js hanterar flimmer
* Felhantering i at.js
* Felsökningsmetoder
* Kända fel och framtida färdplan

>[!VIDEO](https://video.tv.adobe.com/v/22223/)
