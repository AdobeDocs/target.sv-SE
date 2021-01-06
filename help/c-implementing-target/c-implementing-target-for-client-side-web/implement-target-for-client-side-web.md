---
keywords: implement;implementation;at.js;adobe experience platform web sdk;aep web sdk
description: Information om hur du implementerar Adobe Target för klientwebben med at.js.
title: Implementera Adobe Target för webben på klientsidan
feature: at.js
translation-type: tm+mt
source-git-commit: 863c5137383d35b2eaa33082c2136b81793281ca
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---


# Översikt: implementera Target för webben på klientsidan

I en implementering av [!DNL Adobe Target] på klientsidan levererar [!DNL Target] upplevelserna som är kopplade till en aktivitet direkt till klientwebbläsaren. Webbläsaren avgör vilken upplevelse som ska visas och visar den. Med en implementering på klientsidan kan du använda en WYSIWYG-redigerare, [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) eller ett icke-visuellt gränssnitt, [formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md), för att skapa din aktivitet och dina personaliseringsupplevelser.

Om du vill implementera [!DNL Adobe Target] på klientsidan måste du använda biblioteket [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html), [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) eller mbox.js.

>[!IMPORTANT]
>
>**mbox.js - utgånget**: Den 31 mars 2021  [!DNL Adobe Target] kommer inte längre att ha stöd för mbox.js-biblioteket. Efter den 31 mars 2021 kommer alla anrop från mbox.js att misslyckas och påverka de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används. Vi rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser.
>
>* **Adobe Experience Platform Web SDK**: Med  [!UICONTROL Adobe Experience Platform Web SDK] kan du interagera med de olika tjänsterna i  [!DNL Experience Cloud] (inklusive  [!DNL Target]) via Adobe Experience Edge Network. Om du väljer att migrera till [!DNL Adobe Experience Platform Web SDK] läser du [What is Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) i *Web SDK Guide*. Se [Målöversikt](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html) för [!DNL Target]-specifik information.
   >
   >
* **at.js**: JavaScript-biblioteket at.js har många fördelar jämfört med mbox.js. Bland annat har at.js förbättrat sidinläsningstiden för webblöplementeringar, förbättrat säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program. Om du väljer att migrera till at.js, se [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKompetensverktyg: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Även om det finns stöd för mbox.js (fram till 31 mars 2021) har vi inte tillhandahållit några funktionsuppdateringar för det här biblioteket sedan juli 2017. Genom att flytta alla kunder till [!UICONTROL Adobe Experience Platform Web SDK] eller at.js kan våra tekniker och vår supporttekniker ge dig nya funktioner och erbjuda den support du förväntar dig från Adobe.
