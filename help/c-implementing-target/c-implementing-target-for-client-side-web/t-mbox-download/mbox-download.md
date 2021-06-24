---
keywords: implementering;mbox;download mbox.js;download api;mbox.js api
description: Läs om den gamla implementeringen av mbox.js i Adobe Target. Migrera till Adobe Experience Platform Web SDK (AEP Web SDK) eller till den senaste versionen av at.js.
title: Hur implementerar jag [!DNL Target] med mbox.js?
feature: at.js
role: Developer
exl-id: 105095d7-8e29-413b-a7f4-e46e2e30e91f
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# mbox.js implementation

Om du vill använda [!DNL Adobe Target Standard] eller [!DNL Target Premium] lägger du till en kodrad för att anropa mbox.js.

Du kan använda en av två biblioteksreferenser: [!DNL Adobe Experience Platform Web SDK] eller [!DNL at.js].

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används.
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
