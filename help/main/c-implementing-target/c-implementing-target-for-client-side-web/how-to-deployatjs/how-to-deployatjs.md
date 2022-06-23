---
keywords: implementera;at.js;javascript-bibliotek
description: Lär dig distribuera Adobe [!DNL Target] at.js JavaScript-bibliotek som använder taggar i Adobe Experience Platform eller utan en tagghanterare.
title: Hur distribuerar jag på .js?
feature: Implement Server-side
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 0%

---

# Så här distribuerar du at.js

Information om hur du distribuerar [!DNL Adobe Target] JavaScript-bibliotek, at.js, använda taggar i [!DNL Adobe Experience Platform] eller utan tagghanterare.

Du kan distribuera at.js på följande sätt:

* **[Implementera [!DNL Target] använda taggar i [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/)**: Taggar i [!DNL Adobe Experience Platform] är nästa generations tagghanteringsfunktioner från [!DNL Adobe]. Taggar ger kunderna ett enkelt sätt att driftsätta och hantera de analys-, marknadsförings- och reklamtaggar som behövs för att skapa relevanta kundupplevelser.

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] har omklassificerats som en serie datainsamlingstekniker i [!DNL Adobe Experience Platform]. Som ett resultat av detta har flera terminologiska förändringar införts i produktdokumentationen. Se följande [dokument](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) för en konsoliderad hänvisning till terminologiska förändringar.

* **[Implementera mål utan en tagghanterare](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)**: Du kan implementera Target utan att använda en tagghanterare (till exempel taggar i [!DNL Adobe Experience Platform]).
* **Implementera mål med hjälp av en tagghanterare från tredje part**: [Taggar i [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/) is the preferred method to implement Target; however, you can also implement Target using a third-party tag manager, including Tealium, Ensighten, and Google Tag. For a list of benefits of using Launch, see [Advantages of implementing at.js using the [!DNL Adobe Target] extension](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/).

   Om du vet hur man implementerar [!DNL Target] utan en tagghanterare kan du enkelt implementera med en tredjeparts tagghanterare i stället för att hårdkoda at.js i webbplatskoden.

   Här är två ämnen som kommer att hjälpa dig att implementera [!DNL Target] med en tagghanterare från tredje part:

   * [Innan du implementerar](https://developer.adobe.com/target/before-implement/)
   * [Implementera [!DNL Target] utan tagghanterare](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)

   Mer information finns i dokumentationen till tagghanteraren från tredje part.

Att implementera [!DNL Target] när du använder appar för en sida (SPA), se [Implementering av Single Page-program](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/).
