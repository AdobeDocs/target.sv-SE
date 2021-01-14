---
keywords: implement;at.js;javascript library
description: Information om hur du distribuerar Adobe Target JavaScript-biblioteket, at.js, med Adobe Launch, utan en tagghanterare eller med hjälp av Adobe Dynamic Tag Management (DTM).
title: Så här distribuerar du at.js
feature: Implement Server-side
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---


# Så här distribuerar du at.js

Information om hur du distribuerar Adobe Target JavaScript-biblioteket, at.js, med Adobe Launch, utan en tagghanterare eller med hjälp av Adobe Dynamic Tag Management (DTM).

Du kan distribuera at.js på följande sätt:

* **[Implementera mål med hjälp av Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**: Launch är nästa generationens tagghanteringsplattform från Adobe och är den metod som rekommenderas för att implementera Adobe Target. Launch ger kunderna ett enkelt sätt att driftsätta och hantera alla analyser, marknadsförings- och annonstaggar som behövs för att driva relevanta kundupplevelser.
* **[Implementera mål utan en tagghanterare](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**: Du kan implementera Target utan att använda en tagghanterare (Adobe Launch eller Dynamic Tag Management).
* **[Implementera mål med dynamisk tagghantering](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md)**: Du kan implementera Target med Adobe Dynamic Tag Management (DTM), Adobe ImageLegacy-tagghanterare. Adobe Launch är den föredragna, aktuella metoden för implementering av Target och biblioteket at.js. Använd Launch för nya målimplementeringar.
* **Implementera mål med en tagghanterare** från tredje part:  [Adobe ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) Launchis är den föredragna metoden för att genomföra Target. Men du kan också implementera Target med en tredjeparts tagghanterare, som Tealium, Ensighten, Google Tag, osv. En lista över fördelarna med att använda Launch finns i [Fördelarna med att implementera at.js med tillägget Target Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304).

   Men om du vet hur du implementerar Target utan en tagghanterare kan du enkelt implementera det med en tredjeparts tagghanterare i stället för att hårdkoda at.js i platskoden.

   Här är två relevanta ämnen som hjälper dig att implementera Target med en tredjeparts tagghanterare:

   * [Innan du implementerar](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [Implementera mål utan tagghanterare](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   Mer information finns i dokumentationen till tagghanteraren från tredje part.

Information om hur du implementerar Target när du använder Single Page-program (SPA) finns i [Implementering av Single Page-program](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).