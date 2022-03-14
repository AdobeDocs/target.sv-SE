---
keywords: implementera;at.js;javascript-bibliotek
description: Lär dig distribuera Adobe [!DNL Target] at.js JavaScript-bibliotek som använder taggar i Adobe Experience Platform eller utan en tagghanterare.
title: Hur distribuerar jag på .js?
feature: Implement Server-side
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# Så här distribuerar du at.js

Information om hur du distribuerar [!DNL Adobe Target] JavaScript-bibliotek, at.js, använda taggar i [!DNL Adobe Experience Platform] eller utan tagghanterare.

Du kan distribuera at.js på följande sätt:

* **[Implementera [!DNL Target] använda taggar i [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**: Taggar i [!DNL Adobe Experience Platform] är nästa generations tagghanteringsfunktioner från [!DNL Adobe]. Taggar ger kunderna ett enkelt sätt att driftsätta och hantera de analys-, marknadsförings- och reklamtaggar som behövs för att skapa relevanta kundupplevelser.

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] har omklassificerats som en serie datainsamlingstekniker i [!DNL Adobe Experience Platform]. Som ett resultat av detta har flera terminologiska förändringar införts i produktdokumentationen. Se följande [dokument](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) för en konsoliderad hänvisning till terminologiska förändringar.

* **[Implementera mål utan en tagghanterare](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**: Du kan implementera Target utan att använda en tagghanterare (till exempel taggar i [!DNL Adobe Experience Platform]).
* **Implementera mål med hjälp av en tagghanterare från tredje part**: [Taggar i [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) is the preferred method to implement Target; however, you can also implement Target using a third-party tag manager, including Tealium, Ensighten, and Google Tag. For a list of benefits of using Launch, see [Advantages of implementing at.js using the [!DNL Adobe Target] extension](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304).

   Om du vet hur man implementerar [!DNL Target] utan en tagghanterare kan du enkelt implementera med en tredjeparts tagghanterare i stället för att hårdkoda at.js i webbplatskoden.

   Här är två ämnen som kommer att hjälpa dig att implementera [!DNL Target] med en tagghanterare från tredje part:

   * [Innan du implementerar](/help/main/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [Implementera [!DNL Target] utan tagghanterare](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   Mer information finns i dokumentationen till tagghanteraren från tredje part.

Att implementera [!DNL Target] när du använder appar för en sida (SPA), se [Implementering av Single Page-program](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).
