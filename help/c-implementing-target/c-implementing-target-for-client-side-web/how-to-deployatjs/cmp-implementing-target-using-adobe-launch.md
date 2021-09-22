---
keywords: implementera;implementera;implementera;adobe launch;starta;etapp;redirect;experience platform launch;platform launch;taggar;adobe platform
description: Lär dig hur du implementerar biblioteket [!DNL Adobe Target] at.js med [!DNL Adobe Experience Platform], the preferred method to implement [!DNL Target].
title: Hur implementerar jag [!DNL Target] med [!DNL Adobe Experience Platform]?
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 0%

---

# Implementera [!DNL Target] med [!DNL Adobe Experience Platform]

Taggar i [!DNL Adobe Experience Platform] är nästa generation av tagghanteringsfunktioner från [!DNL Adobe]. Taggar ger kunderna ett enkelt sätt att driftsätta och hantera de analys-, marknadsförings- och annonstaggar som behövs för att skapa relevanta kundupplevelser.

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] har omklassificerats som en serie datainsamlingstekniker i  [!DNL Adobe Experience Platform]. Som ett resultat av detta har flera terminologiska förändringar införts i produktdokumentationen. Se följande [dokument](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) för en konsoliderad referens till terminologiska ändringar.

I följande tabell visas de olika källor där du kan få mer information:

| Resurs | Detaljer |
|--- |--- |
| [Lägg till  [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | Den här självstudiekursen innehåller stegvisa instruktioner för att implementera [!DNL Target] på en webbplats med taggar i [!DNL Adobe Experience Platform]. Du kan lägga till JavaScript-biblioteket at.js, bränna den globala mbox, lägga till parametrar och integrera med andra lösningar. Den här artikeln är en del av en större självstudiekurs som visar hur du implementerar [!DNL Adobe Experience Platform] och andra [!DNL Adobe Experience Cloud]-lösningar. |
| [Snabbstartguide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | Information om driftsättning och hantering av de analys-, marknadsförings- och annonstaggar som krävs för relevanta kundupplevelser. |
| [Översikt över  [!DNL Target] Adobe-tillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | Information om hur du implementerar [!DNL Target] med [!DNL Adobe Experience Platform]. |

## Fördelar med att implementera at.js med tillägget [!DNL Target] {#section_48B3F938B6F8491DAF798E0DB54EF304}

Följande fördelar gäller bara om du använder taggar i [!DNL Adobe Experience Platform] för att implementera at.js. Av den anledningen föreslår [!DNL Adobe] starkt att du använder taggar i [!DNL Adobe Experience Platform] i stället för en manuell implementering av at.js.

* **Lösning  [!DNL Adobe Analytics] och  [!DNL Target] tävlingsvillkor:** Eftersom  [!DNL Analytics] samtalet kunde utlösas före  [!DNL Target] samtalet sammanfogas inte  [!DNL Target] samtalet till  [!DNL Analytics] samtalet. Den här ordningsföljden kan leda till felaktiga data. Tillägget [!DNL Target] ser till att beacon-anropet [!DNL Analytics] väntar tills anropet [!DNL Target] slutförs, vare sig det lyckades eller inte. Om du använder taggar i [!DNL Adobe Experience Platform] löses den inkonsekvens i data som kunderna kan uppleva när de implementerar manuellt.

   >[!NOTE]
   >
   >Använd åtgärden [!UICONTROL Send Beacon] i tillägget [!DNL Adobe Analytics] så att anropet [!DNL Analytics] väntar på anropet [!DNL Target]. Om du anropar `s.t()` eller `s.tl()` direkt med anpassad kod väntar inte [!DNL Analytics] anrop förrän [!DNL Target] anrop har slutförts.

* **Förhindrar felaktig hantering av omdirigeringserbjudanden:** Om du har  [!DNL Target] och  [!DNL Analytics] på sidan och det finns ett omdirigeringserbjudande som körs av  [!DNL Target]kan du uppleva en situation där  [!DNL Analytics] spåraren utlöser en begäran när den inte ska det (eftersom användaren omdirigeras till en annan URL). Om du implementerar [!DNL Target] och [!DNL Analytics] via taggar i [!DNL Adobe Experience Platform] kommer du inte att märka det här problemet. Med hjälp av taggar i [!DNL Adobe Experience Platform] instruerar [!DNL Target] [!DNL Analytics] att avbryta [!DNL Analytics]-beacon-begäran.
