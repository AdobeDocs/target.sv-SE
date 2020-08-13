---
description: Information om hur du implementerar Adobe Target för klientwebben.
title: Implementera Adobe Target för webben på klientsidan
feature: client-side
topic: Standard
uuid: 8ed04881-3dd9-496f-9c9c-feb9c740ed80
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# Översikt: implementera Target för webben på klientsidan

I en implementering av [!DNL Adobe Target][!DNL Target] på klientsidan levererar upplevelserna som är kopplade till en aktivitet direkt till klientwebbläsaren. Webbläsaren avgör vilken upplevelse som ska visas och visar den. Med en implementering på klientsidan kan du använda en WYSIWYG-redigerare, [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) eller ett icke-visuellt gränssnitt, den [formulärbaserade Experience Composer](/help/c-experiences/form-experience-composer.md), för att skapa din aktivitet och dina personaliseringsupplevelser.

För att implementera [!DNL Adobe Target] klientsidan måste du använda biblioteket [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) eller mbox.js.

>[!NOTE]
>
>Biblioteket mbox.js utvecklas inte längre. Alla kunder bör [driftsätta at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) eller [migrera från mbox.js till at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md).
