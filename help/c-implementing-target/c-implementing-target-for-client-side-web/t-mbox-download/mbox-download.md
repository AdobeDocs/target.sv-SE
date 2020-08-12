---
keywords: Implementation;Mbox;download mbox.js;download api;mbox.js api
description: Om du vill använda Target Standard eller Target Premium lägger du till en kodrad för att anropa mbox.js.
title: mbox.js implementation
feature: null
subtopic: Getting Started
topic: Standard
uuid: aa53dfd4-db42-4a33-b561-7e84ca7e4497
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---


# mbox.js implementation{#mbox-js-implementation}

Om du vill använda Target Standard eller Target Premium lägger du till en kodrad för att anropa mbox.js.

Du kan använda en av två biblioteksreferenser: [!DNL mbox.js] eller [!DNL at.js]. [Fördelarna med at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) förklarar skillnaderna mellan de två biblioteken.

>[!NOTE]
>
>**borttagning** av mbox.js: 30 augusti 2020 stöder inte Adobe Target längre mbox.js-biblioteket. Efter den 30 augusti 2020 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där Target-aktiviteter körs genom att standardinnehåll används. Vi rekommenderar att alla kunder migrerar till den senaste versionen av at.js-biblioteket före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
>
>Även om mbox.js stöds för närvarande har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Den nyare at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiderna för webbimplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program.
>
>Genom att flytta alla kunder till at.js kan våra ingenjörer och supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig från Adobe.

Den enda referensen till [!DNL mbox.js] på varje sida innehåller de bibliotek som behövs för alla dina aktiviteter. [!DNL mbox.js] anropar [!DNL Target] från varje sida som refererar till [!DNL mbox.js] filen. Detta gör [!DNL Target] att du kan göra följande:

* Leverera målaktiviteter
* Spåra klick
* Spåra de flesta framgångsmått

>[!TIP]
>
>Om du vill förenkla implementeringen kan du referera [!DNL mbox.js] i det globala sidhuvudet.

Du behöver inte underhålla olika aktivitetsspecifika versioner av filen.

1. Referens [!DNL mbox.js] i `<head>` avsnittet på varje sida på webbplatsen.

   `<script src="/ *``*/ *`katalogskript`*/mbox.js"></script>`

   Där ` *``*/ *`katalogskript`*` är den katalog där du sparade din [!DNL mbox.js] fil efter att ha hämtat den.
Om du redan har mbox-filer på sidan från en äldre implementering kan dessa mbox-filer fortfarande användas i det nya gränssnittet. Den uppdaterade [!DNL mbox.js] filen krävs fortfarande, men du kan välja de här rutorna för aktiviteter och redigera dem med hjälp av [!UICONTROL Visual Experience Composer].