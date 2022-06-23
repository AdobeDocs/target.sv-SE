---
keywords: implementera;implementera;implementera;adobe launch;starta;etapp;redirect;experience platform launch;platform launch;taggar;adobe platform
description: Lär dig implementera [!DNL Adobe Target] at.js-bibliotek med [!DNL Adobe Experience Platform], den metod som ska implementeras [!DNL Target].
title: Hur implementerar jag [!DNL Target] använda [!DNL Adobe Experience Platform]?
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Implementera [!DNL Target] använda [!DNL Adobe Experience Platform]

Taggar i [!DNL Adobe Experience Platform] är nästa generations tagghanteringsfunktioner från [!DNL Adobe]. Taggar ger kunderna ett enkelt sätt att driftsätta och hantera de analys-, marknadsförings- och reklamtaggar som behövs för att skapa relevanta kundupplevelser.

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] har omklassificerats som en serie datainsamlingstekniker i [!DNL Adobe Experience Platform]. Som ett resultat av detta har flera terminologiska förändringar införts i produktdokumentationen. Se följande [dokument](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) för en konsoliderad hänvisning till terminologiska förändringar.

I följande tabell visas de olika källor där du kan få mer information:

| Resurs | Detaljer |
|--- |--- |
| [Lägg till [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | Den här självstudiekursen innehåller stegvisa instruktioner för att implementera [!DNL Target] på en webbplats med taggar i [!DNL Adobe Experience Platform]. Du kan lägga till JavaScript-biblioteket at.js, bränna den globala mbox, lägga till parametrar och integrera med andra lösningar. Den här artikeln är en del av en större självstudiekurs som visar hur du implementerar [!DNL Adobe Experience Platform]och andra [!DNL Adobe Experience Cloud] lösningar. |
| [Snabbstartguide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | Information om driftsättning och hantering av de analys-, marknadsförings- och annonstaggar som krävs för relevanta kundupplevelser. |
| [Adobe [!DNL Target] tilläggsöversikt](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | Information om implementering [!DNL Target] använda [!DNL Adobe Experience Platform]. |

## Fördelar med att implementera at.js med [!DNL Target] extension {#section_48B3F938B6F8491DAF798E0DB54EF304}

Följande fördelar gäller bara om du använder taggar i [!DNL Adobe Experience Platform] att implementera at.js. Av denna anledning [!DNL Adobe] rekommenderar starkt att du använder taggar i [!DNL Adobe Experience Platform] i stället för en manuell implementering av at.js.

* **Lösningar [!DNL Adobe Analytics] och [!DNL Target] tävlingsvillkor:** På grund av [!DNL Analytics] samtalet kunde utlösas innan [!DNL Target] ring [!DNL Target] anropet är inte fäst vid [!DNL Analytics] ring. Den här ordningsföljden kan leda till felaktiga data. The [!DNL Target] tillägget säkerställer att [!DNL Analytics] telefonsamtal väntar tills [!DNL Target] samtalet slutförs, slutförs eller inte. Använda taggar i [!DNL Adobe Experience Platform] löser de inkonsekvenser i datan som kunderna kan uppleva när de implementerar manuellt.

   >[!NOTE]
   >
   >Använd [!UICONTROL Send Beacon] i [!DNL Adobe Analytics] så att [!DNL Analytics] samtal väntar på [!DNL Target] ring. Om du ringer `s.t()` eller `s.tl()` med egen kod, [!DNL Analytics] samtal inte väntar tills [!DNL Target] samtalen är slutförda.

* **Förhindrar felaktig hantering av omdirigeringserbjudanden:** Om du har [!DNL Target] och [!DNL Analytics] på sidan, och ett omdirigeringserbjudande från [!DNL Target]kan du uppleva en situation där [!DNL Analytics] spåraren utlöser en begäran när den inte ska utföras (eftersom användaren omdirigeras till en annan URL). Om du implementerar [!DNL Target] och [!DNL Analytics] via taggar i [!DNL Adobe Experience Platform]kommer du inte att märka detta problem. Använda taggar i [!DNL Adobe Experience Platform], [!DNL Target] handledare [!DNL Analytics] för att avbryta [!DNL Analytics] beacon request.
