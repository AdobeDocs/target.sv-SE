---
keywords: implementera;implementera;implementera;adobe launch;starta;etapp;redirect;experience platform launch;platform launch
description: Lär dig hur du implementerar biblioteket Adobe [!DNL Target] at.js med Adobe Experience Platform Launch, den metod som rekommenderas för att implementera Adobe [!DNL Target].
title: Hur implementerar jag [!DNL Target] med Adobe Launch?
feature: Implementera serversidan
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
translation-type: tm+mt
source-git-commit: a69737f49a52cde703627f91d4b97609c1796ee6
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 0%

---

# Implementera [!DNL Target] med [!DNL Adobe Platform Launch]

[!DNL Adobe Experience Platform Launch] är nästa generations tagghanteringsplattform från  [!DNL Adobe] och är den metod som rekommenderas för implementering  [!DNL Adobe Target]. [!DNL Platform Launch] ger kunderna ett enkelt sätt att driftsätta och hantera de analys-, marknadsförings- och annonstaggar som behövs för att skapa relevanta kundupplevelser.

## Implementera [!DNL Target] med [!DNL Platform Launch] {#topic_5234DDAEB0834333BD6BA1B05892FC25}

I följande tabell visas de olika källor där du kan få mer information om [!DNL Platform Launch]:

| Resurs | Detaljer |
|--- |--- |
| [Implementera  [!DNL Target] med  [!UICONTROL Adobe Target Extension Tutorial]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | I den här självstudiekursen finns stegvisa instruktioner för hur du implementerar [!DNL Target] på en webbplats med [!DNL Platform Launch]. Du kan lägga till JavaScript-biblioteket at.js, bränna den globala mbox, lägga till parametrar och integrera med andra lösningar. Den här artikeln är en del av en större självstudiekurs som visar hur du implementerar [!DNL Platform Launch] och andra [!DNL Adobe Experience Cloud]-lösningar. |
| [[!DNL Adobe Platform Launch] Dokumentation](https://experienceleague.adobe.com/docs/launch/using/get-started/quick-start.html#get-started) | Information om driftsättning och hantering av de analys-, marknadsförings- och annonstaggar som krävs för relevanta kundupplevelser. |
| [Dokumentation för  [!DNL Target] AdobeExtension](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | Information om hur du implementerar [!DNL Target] med [!DNL Platform Launch]. |

## Fördelar med att implementera at.js med [!DNL Target] [!DNL Platform Launch]-tillägget {#section_48B3F938B6F8491DAF798E0DB54EF304}

Följande fördelar gäller bara om du använder [!DNL Platform Launch] för att implementera at.js. Av den anledningen föreslår [!DNL Adobe] starkt att du använder [!DNL Platform Launch] i stället för en manuell implementering av at.js.

* **Lösning  [!DNL Adobe Analytics] och  [!DNL Target] tävlingsvillkor:** Eftersom  [!DNL Analytics] samtalet kunde utlösas före  [!DNL Target] samtalet sammanfogas inte  [!DNL Target] samtalet till  [!DNL Analytics] samtalet. Den här ordningsföljden kan leda till felaktiga data. Med början från 0.6.0 ser tillägget [!DNL Platform Launch] till att beacon-anropet [!DNL Analytics] väntar tills anropet [!DNL Target] har slutförts, vare sig det lyckades eller inte. Om du använder [!DNL Platform Launch] löses den inkonsekvens i data som kunderna kan uppleva när de implementerar manuellt.
* **Förhindrar felaktig hantering av omdirigeringserbjudanden:** Om du har  [!DNL Target] och  [!DNL Analytics] på sidan och det finns ett omdirigeringserbjudande som körs av  [!DNL Target]kan du uppleva en situation där  [!DNL Analytics] spåraren utlöser en begäran när den inte ska det (eftersom användaren omdirigeras till en annan URL). Om du implementerar [!DNL Target] och [!DNL Analytics] via [!DNL Platform Launch] kommer du inte att märka det här problemet. Med [!DNL Platform Launch] instruerar [!DNL Target] [!DNL Analytics] att avbryta begäran om [!DNL Analytics]-fyrar.
