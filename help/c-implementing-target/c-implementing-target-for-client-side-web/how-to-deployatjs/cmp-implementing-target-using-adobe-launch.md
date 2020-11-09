---
keywords: implement;implementing;implementation;adobe launch;launch;race;redirect;experience platform launch
description: Adobe Experience Platform Launch är nästa generation av tagghanteringsplattform från Adobe och är den bästa metoden att implementera Adobe Target. Launch ger kunderna ett enkelt sätt att driftsätta och hantera alla analyser, marknadsförings- och annonstaggar som behövs för att driva relevanta kundupplevelser.
title: Implementera mål med Adobe Launch
feature: implementation with launch
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 0%

---


# Implementera mål med Adobe Launch{#implement-target-using-adobe-launch}

Adobe Experience Platform Launch är nästa generation av tagghanteringsplattform från Adobe och är den bästa metoden att implementera Adobe Target. Launch ger kunderna ett enkelt sätt att driftsätta och hantera alla analyser, marknadsförings- och annonstaggar som behövs för att driva relevanta kundupplevelser.

## Implementera mål med Adobe Launch {#topic_5234DDAEB0834333BD6BA1B05892FC25}

Launch är nästa generationens tagghanteringsplattform från Adobe och är den metod som rekommenderas för att implementera Adobe Target. Launch ger kunderna ett enkelt sätt att driftsätta och hantera alla analyser, marknadsförings- och annonstaggar som behövs för att driva relevanta kundupplevelser.

I följande tabell visas de olika källorna där du kan få mer information om Launch:

| Resurs | Detaljer |
|--- |--- |
| [Implementera mål med hjälp av självstudiekursen för Adobe Target Extension](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | Den här självstudiekursen innehåller stegvisa instruktioner för hur du implementerar Adobe Target på en webbplats med Launch. Du kan lägga till JavaScript-biblioteket at.js, bränna den globala mbox, lägga till parametrar och integrera med andra lösningar. Artikeln är en del av en större självstudiekurs som visar hur du implementerar Adobe Launch, samt andra Adobe Experience Cloud-lösningar. |
| [Adobe - startdokumentation](https://experienceleague.adobe.com/docs/launch/using/intro/get-started/quick-start.html) | Information om driftsättning och hantering av alla analys-, marknadsförings- och annonstaggar som behövs för att driva relevanta kundupplevelser. |
| [Adobe Target Extension Documentation](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | Information om hur du implementerar Target med Launch. |

## Fördelar med att implementera at.js med tillägget Target Launch {#section_48B3F938B6F8491DAF798E0DB54EF304}

Följande fördelar gäller bara om du använder Adobe Launch för att implementera at.js. Därför rekommenderar vi starkt att du använder Adobe Launch i stället för DTM eller en manuell implementering av at.js.

* **Löser Analytics och Target Race Condition:** Eftersom Analytics-anropet kunde utlösas före Target-anropet sammanfogas inte med Analytics-anropet. Detta kan leda till felaktiga data. Från och med 0.6.0 ser Target Launch-tillägget till att Analytics-anropet väntar tills Target-anropet slutförs, vare sig det lyckas eller inte. Detta bör lösa de inkonsekvenser som kunderna kan ha upplevt.
* **Förhindrar felaktig hantering av omdirigeringserbjudanden:** Om du har Target och Analytics på sidan, och om det finns ett omdirigeringserbjudande som körs av Target, kan du uppleva en situation där Analytics-spåraren utlöser en begäran när den inte borde göra det (eftersom användaren omdirigeras till en annan URL). Om ni implementerar Target och Analytics via Launch kommer ni inte att märka det här problemet. Med Launch instruerar Target Analytics att avbryta analysbeacon-begäran.
