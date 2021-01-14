---
keywords: global mbox parameters;targetPageParams;query string;array;json;dtm;dynamic tag management
description: JavaScript-funktionen targetPageParams används för att skicka parametrar till den globala mbox-filen. Detta är nödvändigt i alla situationer där ytterligare information om målinriktning/sammanhang ska skickas till Adobe Target.
title: Skicka parametrar till en global mbox
feature: at.js
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---


# Skicka parametrar till en global mbox

JavaScript-funktionen `targetPageParams` används för att skicka parametrar till den globala mbox i [!DNL Adobe Target]. Detta behövs i alla situationer där ytterligare information om mål/kontext ska skickas till [!DNL Target].

I en [!DNL Recommendations]-aktivitet använder du till exempel parametrarna för att representera den aktuella produkten eller kategorin som visas.

Koden som anropar JavaScript-funktionen måste komma före den globala mbox på sidan, oavsett om den globala mbox utlöses som en del av at.js eller inkluderas manuellt i sidkoden.

>[!NOTE]
>
>Om du vill lägga till parametrar i alla mbox på sidan, inte bara i den globala mbox, använder du funktionen [targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md).

Du kan skicka in parametrar till `target-global-mbox` med funktionen `targetPageParams()` på något av följande sätt:

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

   I det här exemplet har p3 värdet `hello world`, som är URL-kodat.

Följande är ett exempel på hur koden för sidan kan se ut:

```
<html> 
  <head> 
    <title>Title here..</title> 
    <script type="text/javascript"> 
        function targetPageParams() { 
           
<b>return "p1=v1&p2=v2&p3=hello%20world"</b>; 
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