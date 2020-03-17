---
keywords: Implementation;Mbox;download mbox.js;download api;mbox.js api
description: Om du vill använda Target Standard eller Target Premium lägger du till en kodrad för att anropa mbox.js.
title: mbox.js implementation
subtopic: Getting Started
topic: Standard
uuid: aa53dfd4-db42-4a33-b561-7e84ca7e4497
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# mbox.js implementation{#mbox-js-implementation}

Om du vill använda Target Standard eller Target Premium lägger du till en kodrad för att anropa mbox.js.

Du kan använda en av två biblioteksreferenser: [!DNL mbox.js] eller [!DNL at.js]. [Fördelarna med at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) förklarar skillnaderna mellan de två biblioteken.

>[!NOTE]
>
>Biblioteket mbox.js stöds fortfarande, men det kommer inte att finnas några funktionsuppdateringar. Alla kunder bör migrera till at.js. Mer information finns i [Migrera till at.js från mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

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