---
keywords: implementera;implementering;at.js;adobe experience platform web sdk;aep web sdk
description: Lär dig hur du implementerar JavaScript-biblioteket Adobe [!DNL Target] for client-side web using the Adobe Experience Platform Web SDK  (AEP Web SDK) or the [!DNL Target] at.js.
title: Hur implementerar jag [!DNL Target] för klientwebben?
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Översikt: implementera [!DNL Target] för klientwebben

I en implementering av [!DNL Adobe Target] på klientsidan levererar [!DNL Target] upplevelserna som är kopplade till en aktivitet direkt till klientwebbläsaren. Webbläsaren avgör vilken upplevelse som ska visas och visar den. Med en implementering på klientsidan kan du använda en WYSIWYG-redigerare, [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) eller ett icke-visuellt gränssnitt, [formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md), för att skapa din aktivitet och dina personaliseringsupplevelser.

Om du vill implementera [!DNL Adobe Target] på klientsidan måste du använda ett av följande JavaScript-bibliotek:

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Target at.js JavaScript library](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**mbox.js - utgånget**: 31 mars 2021 har  [!DNL Adobe Target] inte längre stöd för mbox.js-biblioteket. Efter den 31 mars 2021 misslyckas alla anrop från mbox.js på ett säkert sätt och påverkar de sidor där [!DNL Target]-aktiviteter körs genom att standardinnehåll används. Adobe rekommenderar att alla kunder migrerar till den senaste versionen av nya [!DNL Adobe Experience Platform Web SDK] eller JavaScript-biblioteket at.js före detta datum för att undvika eventuella problem med dina webbplatser.
>
>* **Adobe Experience Platform Web SDK**: Med  [!UICONTROL Adobe Experience Platform Web SDK] kan du interagera med de olika tjänsterna i  [!DNL Experience Cloud] (inklusive  [!DNL Target]) via Adobe Experience Edge Network. Om du väljer att migrera till [!DNL Adobe Experience Platform Web SDK], se [Vad är Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) i *Web SDK Guide*.
   >
   >
* **at.js**: JavaScript-biblioteket at.js förbättrar sidinläsningstiderna för webbimplementeringar, förbättrar säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program. Om du väljer att migrera till at.js, se [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) och [Adobe Target SKompetensverktyg: Utvecklarchatt, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).


