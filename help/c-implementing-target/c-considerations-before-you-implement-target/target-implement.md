---
keywords: document.write;target;implement;implement target;dtm;dynamic tag management;at.js;mbox.js;target.js;mbox;adobe experience platform web skd;aep web sdk;web sdk
description: Implementera Adobe Target genom att referera till Target-biblioteken (at.js eller mbox.js) på dina webbsidor.
title: Förstå målbiblioteken i JavaScript
feature: Implementation
translation-type: tm+mt
source-git-commit: bffda8c3461998767a002d66fd9340252237ae5d
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---


# Förstå [!DNL Target] JavaScript-biblioteken

Implementera [!DNL Target] genom att referera till [!DNL Adobe Target]-biblioteken (Adobe Experience Platform Web SDK, at.js eller mbox.js) på dina webbsidor.

>[!NOTE]
>
>Biblioteket mbox.js utvecklas inte längre. Alla kunder bör migrera från mbox.js till at.js. Mer information finns i [Migrera till at.js från mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## Skillnader mellan mål-JavaScript-bibliotek {#section_40117C78C2F84FECAC4F1BA40CC4F171}

I följande tabell förklaras skillnaderna mellan JavaScript-biblioteken [!DNL Target]:

| Biblioteksreferens | Beskrivning |
|--- |--- |
| Adobe Experience Platform Web SDK | Med [!UICONTROL Adobe Experience Platform Web SDK] kan du interagera med de olika tjänsterna i [!DNL Experience Cloud] (inklusive [!DNL Target]) via Adobe Experience Edge-nätverket. Om du väljer att migrera till [!DNL Adobe Experience Platform Web SDK] läser du [What is Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) i *Web SDK Guide*. |
| at.js | at.js ersätter mbox.js för [!DNL [!DNL Target]] implementeringar.<br>Bland annat har at.js förbättrat sidinläsningstiderna för webblöplementeringar, förbättrat säkerheten, förhindrat dokument.write-varningar i Google Chrome och gett bättre implementeringsalternativ för enkelsidiga program.<br>Mer information finns  [i implementeringen](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md) av at.js. |
| mbox.js | Före [!DNL Target] 16.3.1 (mars 2016) behövde [!DNL Target] ett anrop till mbox.js för att skapa den globala mbox som krävs för att [!DNL Target] ska kunna leverera aktiviteter, spåra klick och spåra de flesta framgångsmått. Den här filen innehåller de bibliotek som behövs för alla dina aktiviteter. Du behöver inte underhålla olika aktivitetsspecifika versioner av filen.<br>Om du redan har kapslade rutor på sidorna från en äldre  [!DNL Target] implementeringsstil kan dessa rutor fortfarande användas i det nya gränssnittet. Den uppdaterade filen mbox.js krävs fortfarande, men dessa mbox kan väljas för aktiviteter och redigeras med Visual Experience Composer.<br>[!DNL Target] Standard och Premium - uppdatera och komplettera mbox.js med en referens till en target.js-fil. Filen target.js hanteras av Adobe. Med filen Target.js kan du redigera innehåll på alla sidor med Visual Experience Composer, även om sidan inte innehåller fördefinierade rutor. Du måste referera till den här filen på alla sidor på webbplatsen.<br>Mer information finns i Implementering av  [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Viktigt**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används. Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser.<br> |

## Inverkan av at.js och mbox.js på sidinläsningstid {#section_16630CD0FF0A498EB596A51381366A5A}

Många kunder och konsulter vill veta hur [!DNL at.js] och [!DNL mbox.js] påverkar sidinläsningstiden, särskilt när det gäller nya användare och användare som returneras. Tyvärr är det svårt att mäta och ge konkreta siffror för hur [!DNL at.js] eller [!DNL mbox.js] påverkar sidladdningstiden på grund av varje kunds implementering.

Om besökar-API:t finns på sidan kan vi bättre förstå hur [!DNL at.js] och [!DNL mbox.js] påverkar sidinläsningstiden.

>[!NOTE]
>
>Besökar-API:t och [!DNL at.js] eller [!DNL mbox.js] påverkar bara sidinläsningstiden när du använder den globala mbox (på grund av tekniken för att dölja brödtext). Regionala kryssrutor påverkas inte av integreringen med Visitor API.

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
