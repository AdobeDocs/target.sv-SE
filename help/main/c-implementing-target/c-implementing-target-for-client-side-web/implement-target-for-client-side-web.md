---
keywords: implementera;implementering;at.js;adobe experience platform web sdk;aep web sdk
description: Lär dig implementera Adobe [!DNL Target] för webben på klientsidan med Adobe Experience Platform Web SDK (AEP Web SDK) eller [!DNL Target] at.js JavaScript-bibliotek.
title: Hur implementerar jag [!DNL Target] för klientsidan
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# Översikt: implementera [!DNL Target] för webben på klientsidan

I en implementering på klientsidan av [!DNL Adobe Target], [!DNL Target] levererar upplevelserna som är kopplade till en aktivitet direkt till klientwebbläsaren. Webbläsaren avgör vilken upplevelse som ska visas och visar den. Med en implementering på klientsidan kan du använda en WYSIWYG-redigerare, [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC), eller ett icke-visuellt gränssnitt, [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md), för att skapa din aktivitet och dina personaliseringsupplevelser.

Att implementera [!DNL Adobe Target] på klientsidan måste du använda något av följande JavaScript-bibliotek:

* [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/)

   The [!UICONTROL Adobe Experience Platform Web SDK] kan du interagera med de olika tjänsterna i [!DNL Experience Cloud] (inklusive [!DNL Target]) via Adobe Experience Edge Network. Om du väljer att migrera till [!DNL Adobe Experience Platform Web SDK], se [Vad är Adobe Experience Platform Web SDK?](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/) i *Web SDK Guide*.

* [Target at.js JavaScript library](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/)

   JavaScript-biblioteket at.js förbättrar sidinläsningstiderna för webbimplementeringar, förbättrar säkerheten och erbjuder bättre implementeringsalternativ för enkelsidiga program. Om du väljer att migrera till at.js finns mer information i [How At.js Works](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/) och [Adobe Target Experience Builder: Developer chat, migrera Adobe Target mbox.js till at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).



