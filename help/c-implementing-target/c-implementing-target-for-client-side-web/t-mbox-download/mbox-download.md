---
keywords: implementering;mbox;download mbox.js;download api;mbox.js api
description: Om du vill använda Adobe Target Standard eller Target Premium lägger du till en kodrad för att anropa mbox.js.
title: mbox.js-implementering
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---


# mbox.js implementation

Om du vill använda [!DNL Adobe Target Standard] eller [!DNL Target Premium] lägger du till en kodrad för att anropa mbox.js.

Du kan använda en av två biblioteksreferenser: [!DNL Adobe Experience Platform Web SDK] eller [!DNL at.js]. [Fördelarna med at.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsexuell förenklar skillnaderna mellan mbox.js- och at.js-biblioteken.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
>
>Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser. Mer information finns i [Översikt: implementera Target för webben på klientsidan](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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