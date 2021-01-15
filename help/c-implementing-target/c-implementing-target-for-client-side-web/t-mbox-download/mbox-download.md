---
keywords: implementation;mbox;download mbox.js;download api;mbox.js api
description: Om du vill använda Adobe Target Standard eller Target Premium lägger du till en kodrad för att anropa mbox.js.
title: mbox.js implementation
feature: null
translation-type: tm+mt
source-git-commit: a85a5c10c31fb0d7eb00c21ff03b2012d044de45
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# mbox.js implementation

Om du vill använda [!DNL Adobe Target Standard] eller [!DNL Target Premium] lägger du till en kodrad för att anropa mbox.js.

Du kan använda en av två biblioteksreferenser: [!DNL Adobe Experience Platform Web SDK] eller [!DNL at.js]. [Fördelarna med at.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsexuell förenklar skillnaderna mellan mbox.js- och at.js-biblioteken.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används. Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser.
>
>* **Adobe Experience Platform Web SDK**: Med  [!UICONTROL Adobe Experience Platform Web SDK] kan du interagera med de olika tjänsterna i  [!DNL Experience Cloud] (inklusive  [!DNL Target]) via Adobe Experience Edge Network. Om du väljer att migrera till [!DNL Adobe Experience Platform Web SDK], se [Vad är Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) i *Web SDK Guide*.
   >
   >
* **at.js**: JavaScript-biblioteket at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiden för webblöplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program. Om du väljer att migrera till at.js, se [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKompetensverktyg: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Även om det finns stöd för mbox.js (fram till 31 mars 2021) har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Genom att flytta alla kunder till [!UICONTROL Adobe Experience Platform Web SDK] eller at.js kan våra tekniker och vår supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig från Adobe.

Den enda referensen till [!DNL mbox.js] på varje sida innehåller de bibliotek som behövs för alla dina aktiviteter. [!DNL mbox.js] anropar  [!DNL Target] från varje sida som refererar till  [!DNL mbox.js] filen. Detta gör att [!DNL Target] kan göra följande:

* Leverera målaktiviteter
* Spåra klick
* Spåra de flesta framgångsmått

>[!TIP]
>
>För att förenkla implementeringen kan du referera till [!DNL mbox.js] i din globala rubrik.

Du behöver inte underhålla olika aktivitetsspecifika versioner av filen.

1. Referera [!DNL mbox.js] i `<head>`-avsnittet på varje sida på webbplatsen.

   `<script src="/ *``*/ *`katalogskript`*/mbox.js"></script>`

   Där ` *`katalog`*/ *`skript`*` är den katalog där du sparade din [!DNL mbox.js]-fil när du laddat ned den.
Om du redan har mbox-filer på sidan från en äldre implementering kan dessa mbox-filer fortfarande användas i det nya gränssnittet. Den uppdaterade [!DNL mbox.js]-filen krävs fortfarande, men dessa kryssrutor kan markeras för aktiviteter och redigeras med [!UICONTROL Visual Experience Composer].