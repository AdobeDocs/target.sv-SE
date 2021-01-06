---
keywords: implement;implementation;at.js;adobe experience platform web sdk;aep web sdk
description: Information om hur du implementerar Adobe Target för klientwebben.
title: Implementera Adobe Target för webben på klientsidan
feature: client-side
translation-type: tm+mt
source-git-commit: 1b426e0b2004e729ba75d218a9b6ccd5195449cd
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---


# Översikt: implementera Target för webben på klientsidan

I en implementering av [!DNL Adobe Target] på klientsidan levererar [!DNL Target] upplevelserna som är kopplade till en aktivitet direkt till klientwebbläsaren. Webbläsaren avgör vilken upplevelse som ska visas och visar den. Med en implementering på klientsidan kan du använda en WYSIWYG-redigerare, [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) eller ett icke-visuellt gränssnitt, [formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md), för att skapa din aktivitet och dina personaliseringsupplevelser.

Om du vill implementera [!DNL Adobe Target] på klientsidan måste du använda biblioteket [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html), [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) eller mbox.js.

>[!NOTE]
>
>Biblioteket mbox.js utvecklas inte längre. Alla kunder bör distribuera [AEP Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html), [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) eller [migrera från mbox.js till at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md).
