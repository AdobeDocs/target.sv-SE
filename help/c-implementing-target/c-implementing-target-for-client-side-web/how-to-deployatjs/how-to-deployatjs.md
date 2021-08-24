---
keywords: implementera;at.js;javascript-bibliotek
description: Lär dig hur du distribuerar JavaScript-biblioteket Adobe [!DNL Target] at.js med Adobe Experience Platform Launch eller utan en tagghanterare.
title: Hur distribuerar jag på .js?
feature: Implementera serversidan
role: Developer
exl-id: a11b916a-923e-43d2-af0f-8efde7cd547e
source-git-commit: 82629fb4c543220796fc99d9c034ebb725e1a645
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Så här distribuerar du at.js

Information om hur du distribuerar JavaScript-biblioteket [!DNL Adobe Target], at.js, med hjälp av taggar i [!DNL Adobe Experience Platform] eller utan en tagghanterare.

Du kan distribuera at.js på följande sätt:

* **[Implementera  [!DNL Target] taggar i [!DNL Adobe Experience Platform]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)**: Taggar i  [!DNL Adobe Experience Platform] är nästa generations tagghanteringsfunktioner från  [!DNL Adobe]. Taggar ger kunderna ett enkelt sätt att driftsätta och hantera de analys-, marknadsförings- och annonstaggar som behövs för att skapa relevanta kundupplevelser.

   >[!NOTE]
   >
   >[!DNL Adobe Experience Platform Launch] har omklassificerats som en serie datainsamlingstekniker i  [!DNL Adobe Experience Platform]. Som ett resultat av detta har flera terminologiska förändringar införts i produktdokumentationen. Se följande [dokument](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) för en konsoliderad referens till terminologiska ändringar.

* **[Implementera mål utan en tagghanterare](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)**: Du kan implementera Target utan att använda en tagghanterare (till exempel taggar i  [!DNL Adobe Experience Platform]).
* **Implementera mål med en tagghanterare** från tredje part:  [Taggar  [!DNL Adobe Experience Platform]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) är den metod som föredras för att implementera Target. Men du kan också implementera Target med en tredjeparts tagghanterare, som Tealium, Ensighten och Google Tag. En lista över fördelarna med att använda Launch finns i [Fördelar med att implementera at.js med  [!DNL Adobe Target] tillägget](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md#section_48B3F938B6F8491DAF798E0DB54EF304).

   Men om du vet hur du implementerar [!DNL Target] utan en tagghanterare kan du enkelt implementera med en tredjeparts tagghanterare i stället för att hårdkoda at.js i platskoden.

   Här är två relevanta ämnen som hjälper dig att implementera [!DNL Target] med en tredjeparts tagghanterare:

   * [Innan du implementerar](/help/c-implementing-target/c-considerations-before-you-implement-target/considerations-before-you-implement-target.md)
   * [Implementera [!DNL Target] utan tagghanterare](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md)

   Mer information finns i dokumentationen till tagghanteraren från tredje part.

Information om hur du implementerar [!DNL Target] när du använder Single Page-program (SPA) finns i [Implementering av Single Page-program](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).
