---
keywords: document.write;target;implement;implement target;dtm;dynamic tag management;at.js;mbox.js;target.js;mbox
description: Implementera Target genom att referera till Target-biblioteken (at.js eller mbox.js) på dina webbsidor.
title: Förstå målbiblioteken i JavaScript
feature: implementation general
topic: Target
uuid: c8a254c9-afc9-4a55-be01-788c11bef7cc
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 0%

---


# Förstå [!DNL Target] JavaScript-biblioteken{#understand-the-target-javascript-libraries}

Implementera [!DNL Target] genom att referera till [!DNL Target] biblioteken (at.js eller mbox.js) på dina webbsidor.

>[!NOTE]
>
>Biblioteket mbox.js utvecklas inte längre. Alla kunder bör migrera från mbox.js till at.js. Mer information finns i [Migrera till at.js från mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## Skillnader mellan de två biblioteken {#section_40117C78C2F84FECAC4F1BA40CC4F171}

I följande tabell förklaras skillnaderna mellan de två biblioteken:

| Biblioteksreferens | Beskrivning |
|--- |--- |
| at.js | at.js ersätter mbox.js för [!DNL Target] implementeringar.<br>Bland annat har at.js förbättrat sidinläsningstiderna för webblöplementeringar, förbättrat säkerheten, förhindrat dokument.write-varningar i Google Chrome och gett bättre implementeringsalternativ för enkelsidiga program.<br>Mer information finns [i implementeringen](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md)av at.js. |
| mbox.js | Före den [!DNL Target] 16.3.1 (mars 2016) [!DNL Target] krävdes ett anrop till mbox.js för att skapa den globala mbox som krävs för [!DNL Target] att leverera aktiviteter, spåra klick och spåra de flesta framgångsmått. Den här filen innehåller de bibliotek som behövs för alla dina aktiviteter. Du behöver inte underhålla olika aktivitetsspecifika versioner av filen.<br>Om du redan har kapslade rutor på sidorna från en äldre typ av [!DNL Target] implementering kan dessa rutor fortfarande användas i det nya gränssnittet. Den uppdaterade filen mbox.js krävs fortfarande, men dessa mbox kan väljas för aktiviteter och redigeras med Visual Experience Composer.<br>[!DNL Target] Standard och Premium - uppdatera och komplettera mbox.js med en referens till en target.js-fil. Filen target.js hanteras av Adobe. Med filen Target.js kan du redigera innehåll på alla sidor med Visual Experience Composer, även om sidan inte innehåller fördefinierade rutor. Du måste referera till den här filen på alla sidor på webbplatsen.<br>Mer information finns i Implementering av [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Viktigt**: Biblioteket mbox.js stöds fortfarande, men det kommer inte att finnas några funktionsuppdateringar. Alla kunder bör migrera till at.js. Mer information finns i [Migrera till at.js från mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)<br> |

## Inverkan av at.js och mbox.js på sidinläsningstid {#section_16630CD0FF0A498EB596A51381366A5A}

Många kunder och konsulter vill veta hur stor påverkan [!DNL at.js] och [!DNL mbox.js] hur stor tid det tar att läsa in sidor, särskilt när det gäller nya användare och användare som återvänder. Tyvärr är det svårt att mäta och ge konkreta siffror för hur [!DNL at.js] eller [!DNL mbox.js] hur påverkar sidladdningstiden på grund av varje kunds implementering.

Om besökar-API:t finns på sidan kan vi bättre förstå hur [!DNL at.js] och [!DNL mbox.js] hur sidinläsningstiden påverkas.

>[!NOTE]
>
>Besökar-API:t och [!DNL at.js] eller [!DNL mbox.js] påverkar bara sidinläsningstiden när du använder den globala mbox-filen (på grund av tekniken för att dölja brödtext). Regionala kryssrutor påverkas inte av integreringen med Visitor API.

I följande avsnitt beskrivs åtgärdssekvensen för nya och återkommande besökare:

### Nya besökare

1. Besökar-API:t läses in, tolkas och körs.
1. at.js / mbox.js läses in, tolkas och körs.
1. Om den globala mbox-skaparen är aktiverad, JavaScript-målbiblioteket:

   * Instansierar Visitor-objektet.
   * Målbiblioteket försöker hämta Experience Cloud Visitor-ID-data.
   * Eftersom det här är en ny besökare skickar Visitor-API:t en korsdomänbegäran till demdex.net.
   * När data för Experience Cloud Visitor-ID har hämtats skickas en begäran till Target.

### Returnerande besökare

1. Besökar-API:t läses in, tolkas och körs.
1. at.js / mbox.js läses in, tolkas och körs.
1. Om den globala mbox-skaparen är aktiverad, JavaScript-målbiblioteket:

   * Instansierar Visitor-objektet.
   * Målbiblioteket försöker hämta Experience Cloud Visitor-ID-data.
   * Besökar-API:t hämtar data från cookies.
   * När data för Experience Cloud Visitor-ID har hämtats skickas en begäran till Target.

>[!NOTE]
>
>För nya besökare måste Target gå igenom tråden flera gånger när besökar-API:t finns för att se till att Target-begäranden innehåller data för Experience Cloud Visitor-ID:t. För återkommande besökare går Target bara till Target för att hämta det personaliserade innehållet.
