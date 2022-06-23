---
keywords: globala mbox-parametrar;targetPageParams;query string;array;json;dtm
description: Lär dig hur du använder funktionen targetPageParams för att skicka ytterligare information om målinriktning eller kontext till Adobe [!DNL Target] global mbox.
title: Hur skickar jag parametrar till en global mbox?
feature: at.js
role: Developer
exl-id: 37d143af-83a8-48fd-91eb-58f21f8c7b94
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# Skicka parametrar till en global mbox

JavaScript `targetPageParams` -funktionen används för att skicka parametrar till den globala mbox i [!DNL Adobe Target]. Detta behövs i alla situationer där ytterligare information om målinriktning/kontext ska skickas till [!DNL Target].

I en [!DNL Recommendations] använder du parametrarna för att representera den aktuella produkten eller kategorin som visas.

Koden som anropar JavaScript-funktionen måste komma före den globala mbox på sidan, oavsett om den globala mbox utlöses som en del av at.js eller inkluderas manuellt i sidkoden.

>[!NOTE]
>
>Om du vill lägga till parametrar i alla kryssrutor på sidan, inte bara i den globala rutan, använder du [targetPageParamsAll()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/)Funktionen {target=_blank}.

Du kan skicka in parametrar till `target-global-mbox` med `targetPageParams()` på något av följande sätt:

* En array
* Ett JSON-objekt
* En avgränsad lista

Använd dessa tre metoder för att verifiera att parametrarna skickas korrekt. Du kan också verifiera att parametrar skickas med [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html).

Du måste definiera JavaScript-funktionen innan du lägger till den globala mbox-filen på sidan. Namnet måste vara `targetPageParams`.

## Frågesträng

```
p1=v1&p2=v2&p3=hello%20world
```

* Namn: `targetPageParams`
* Returvärde: en&quot;&amp;&quot;-avgränsad parameter med URL-kodade parametervärden.

   Exempel:

   I det här exemplet har p3 värdet `hello world`, som är URL-kodad.

Följande är ett exempel på hur koden för sidan kan se ut:

```
<html> 
  <head> 
    <title>Title here..</title> 
    <script type="text/javascript"> 
        function targetPageParams() { 
          return "p1=v1&p2=v2&p3=hello%20world";
        } 
    </script> 
    <script src="mbox.js" type="text/javascript"></script> 
  </head> 
  <body>Body here... 
  </body> 
</html>
```

I det här exemplet skickas följande data till mbox-kanten:

* p1=v1
* p2=v2
* p3=hello world

## Array

```
<!--window.-->targetPageParams = function() { 
  return ["a=1", "b=2", "c=hello world"]; 
}; 
```

Värdena behöver inte vara URL-kodade. Om ett värde till exempel innehåller ett blanksteg behöver du inte koda det.

I det här exemplet skickas följande data till mbox-kanten:

* a=1
* b=2
* c=hello world

## JSON

JSON är ett kraftfullt sätt att skicka parametrar. Target använder JSON-objektnycklarna för att förenkla komplicerade strukturer till enkla parametrar.

```
<!--window.-->targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
                  "memberStatus": Gold, 
                  "country": { 
                                "city": "San Francisco" 
                            } 
              } 
  }; 
}; 
```

Värdena behöver inte vara URL-kodade. &quot;San Francisco&quot; kräver till exempel inte att utrymmet kodas. Det räcker med utrymme.

I det här exemplet skickas följande data till mbox-kanten:

* a=1
* b=2
* `profile.memberStatus`=Guld
* `profile.country.city`=San Francisco
