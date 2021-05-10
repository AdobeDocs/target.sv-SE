---
keywords: document.write;target;implementera;implementera target;dtm;at.js;mbox.js;target.js;mbox;adobe experience platform web skd;aep web sdk;web sdk
description: Implementera Adobe [!DNL Target] by referencing the [!DNL Target] bibliotek (at.js eller mbox.js) på dina webbsidor.
title: Förstå [!DNL Target] JavaScript-biblioteken
feature: Implementering
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---


# Förstå [!DNL Target] JavaScript-biblioteken

Implementera [!DNL Adobe Target] genom att referera till [!DNL Adobe Target]-biblioteken (Adobe Experience Platform Web SDK eller at.js) på dina webbsidor.

>[!NOTE]
>
>Biblioteket mbox.js utvecklas inte längre. Alla kunder måste migrera från mbox.js till at.js eller till [!UICONTROL Adobe Experience Platform Web SDK] före 31 mars 2021. Mer information finns i [Migrera till at.js från mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA) eller [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md).

## Skillnader mellan [!DNL Target] JavaScript-biblioteken {#section_40117C78C2F84FECAC4F1BA40CC4F171}

I följande tabell förklaras skillnaderna mellan JavaScript-biblioteken [!DNL Target]:

| Biblioteksreferens | Beskrivning |
|--- |--- |
| Adobe Experience Platform Web SDK | Med [!UICONTROL Adobe Experience Platform Web SDK] kan du interagera med de olika tjänsterna i [!DNL Experience Cloud] (inklusive [!DNL Target]) via Adobe Experience Edge-nätverket. Om du väljer att migrera till [!DNL Adobe Experience Platform Web SDK], se [Vad är Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) i *Web SDK Guide*. |
| at.js | at.js ersätter mbox.js för [!DNL [!DNL Target]] implementeringar.<br>Bland annat har at.js förbättrat sidinläsningstiderna för webblöplementeringar, förbättrat säkerheten, förhindrat dokument.write-varningar i Google Chrome och gett bättre implementeringsalternativ för enkelsidiga program.<br>Mer information finns  [i implementeringen](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md) av at.js. |

## Inverkan av at.js på sidinläsningstid {#section_16630CD0FF0A498EB596A51381366A5A}

Många kunder och konsulter vill veta hur [!DNL at.js] påverkar sidladdningstiden, särskilt när det gäller nya jämfört med återkommande användare. Tyvärr är det svårt att mäta och ge konkreta siffror för hur [!DNL at.js] påverkar sidladdningstiden på grund av varje kunds implementering.

Om besökar-API:t finns på sidan kan [!DNL Target] bättre förstå hur [!DNL at.js] påverkar sidinläsningstiden.

>[!NOTE]
>
>Besökar-API:t och [!DNL at.js] påverkar bara sidinläsningstiden när du använder den globala mbox (på grund av tekniken för att dölja brödtext). Regionala kryssrutor påverkas inte av integreringen med Visitor API.

I följande avsnitt beskrivs åtgärdssekvensen för nya och återkommande besökare:

### Nya besökare

1. Besökar-API:t läses in, tolkas och körs.
1. at.js läses in, tolkas och körs.
1. Om den globala mbox-skaparen är aktiverad, är JavaScript-biblioteket [!DNL Target]:

   * Instansierar Visitor-objektet.
   * [!DNL Target]-biblioteket försöker hämta [!UICONTROL Experience Cloud Visitor ID]-data.
   * För en ny besökare utlöser besöks-API:t en korsdomänbegäran till `demdex.net`.
   * När [!UICONTROL Experience Cloud Visitor ID]-data har hämtats utlöses en begäran till Target.

### Returnerande besökare

1. Besökar-API:t läses in, tolkas och körs.
1. at.js läses in, tolkas och körs.
1. Om den globala mbox-skaparen är aktiverad, är JavaScript-biblioteket [!DNL Target]:

   * Instansierar Visitor-objektet.
   * [!DNL Target]-biblioteket försöker hämta [!UICONTROL Experience Cloud Visitor ID]-data.
   * Besökar-API:t hämtar data från cookies.
   * När [!UICONTROL Experience Cloud Visitor ID]-data har hämtats utlöses en begäran till [!DNL Target].

>[!NOTE]
>
>För nya besökare går [!DNL Target] igenom tråden flera gånger när besökar-API:t finns för att se till att [!DNL Target]-begäranden innehåller [!UICONTROL Experience Cloud Visitor ID]-data. För återkommande besökare går [!DNL Target] bara över tråden till [!DNL Target] för att hämta det anpassade innehållet.
