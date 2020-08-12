---
keywords: adobe.target.getOffer;getOffer;getoffer;get offer;at.js;functions;function
description: Information om funktionen adobe.target.getOffer(options) för JavaScript-biblioteket i Adobe Target at.js.
title: Information om funktionen adobe.target.getOffer(options) för JavaScript-biblioteket i Adobe Target at.js.
feature: null
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 0%

---


# adobe.target.getOffer(options)

Den här funktionen utlöser en begäran om att få ett Target-erbjudande.

Använd med `adobe.target.applyOffer()` för att bearbeta svaret eller använd din egen hantering av lyckade resultat. Alternativparametern är obligatorisk och har följande struktur:

| Nyckel | Typ | Obligatoriskt | Beskrivning |
|--- |--- |--- |--- |
| mbox | Sträng | Ja | Namn på mbox |
| parametrar | Objekt | Nej | Mbox-parametrar. Ett objekt med nyckelvärdepar som har följande struktur:<br>`{ "param1": "value1", "param2": "value2"}` |
| framgång |  -funktion | Ja | Återanrop som ska köras när vi får ett svar från servern. Callback-funktionen för lyckade försök får en enda parameter som representerar en array med objekt för erbjudanden. Här är ett exempel på lyckad återanrop:<br>`function handleSuccess(response){......}`<br>Se svar nedan för mer information. |
| fel |  -funktion | Ja | Återanrop som ska utföras när ett fel inträffar. Det finns några fall som anses felaktiga:<ul><li>HTTP-statuskoden skiljer sig från 200 OK</li><li>Svaret kan inte tolkas. Vi har till exempel dåligt konstruerat JSON eller HTML i stället för JSON.</li><li>Svaret innehåller felnyckeln. Ett undantag utlöstes till exempel på kanten som en begäran inte kunde behandlas korrekt. Ett fel kan uppstå när en mbox är blockerad och vi inte kan hämta något innehåll för den, osv. Återanropsfunktionen för fel får två parametrar: status och fel. Här är ett exempel på ett fel vid återanrop: `function handleError(status, error){......}`</li></ul>Mer information finns i Felsvar nedan. |
| timeout | Nummer | Nej | Timeout i millisekunder. Om inget anges används standardtidsgränsen i at.js.<br>Standardtidsgränsen kan anges från [!DNL Target] användargränssnittet under [!UICONTROL Administration > Implementation]. |

## Exempel {#section_97C2D2E03E6549BEA7F4873E3F5E4A0D}

Lägga till parametrar med getOffer() och använd applyOffer() för lyckad hantering:

```
adobe.target.getOffer({   
  "mbox": "target-global-mbox", 
  "params": { 
     "a": 1, 
     "b": 2 
  }, 
  "success": function(offer) {           
        adobe.target.applyOffer( {  
           "mbox": "target-global-mbox", 
           "offer": offer  
        } ); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

Lägga till parametrar och profilparametrar med getOffer() och använd applyOffer() för lyckad hantering:

```
adobe.target.getOffer({   
  "mbox": "target-global-mbox", 
  "params": { 
     "a": 1, 
     "b": 2, 
     "profile.age": 27, 
     "profile.gender": "male" 
  }, 
  "success": function(offer) {           
        adobe.target.applyOffer( {  
           "mbox": "target-global-mbox", 
           "offer": offer  
        } ); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

Använda anpassad tidsgräns och anpassad hantering av lyckade resultat med getOffer():

&quot;YOUR_OWN_CUSTOM_HANDLING_FUNCTION&quot; är en platshållare för en funktion som kunden skulle definiera.

```
adobe.target.getOffer({     
  "mbox": "target-global-mbox",   
  "success": function(offer) { 
    YOUR_OWN_CUSTOM_HANDLING_FUNCTION(offer);   
  }, 
  "error": function(status, error) {                 
    console.log('Error', status, error);   
  },   
  "timeout": 2000 
});
```

## Svar {#section_CF9FD236EF794620BCBF84EB80160183}

Svarsparametern som skickas till motringningen om att åtgärden lyckades är en array med åtgärder. En åtgärd är ett objekt som vanligtvis har följande format:

| Namn | Typ | Beskrivning |
|--- |--- |--- |
| åtgärd | Sträng | Typ av åtgärd som ska tillämpas på det identifierade elementet. |
| väljare | Sting | Representerar en enkelväljare. |
| cssSelector | Sträng | Inbyggd DOM-väljare, används för att dölja element. |
| innehåll | Sträng | Det innehåll som ska användas på det identifierade elementet. |

## Exempel

```
{ 
    "sessionId": "1444512212156-384616", 
    "tntId": "1444512212156-384616.17_35", 
    "offers": [{ 
        "plugins": ["<script type=\"text/javascript\">\r\n/*mboxHighlight+ (1of2) v1 ==> Response Plugin*/\r\nwindow.ttMETA=(typeof(window.ttMETA)!='undefined')?window.ttMETA:[];window.ttMETA.push({'mbox':'target-global-mbox','campaign':'at: redirect ootb','experience':'Experience B','offer':'/at_redirect_ootb/experiences/1/pages/0/1442082890250'});window.ttMBX=function(x){var mbxList=[];for(i=0;i<ttMETA.length;i++){if(ttMETA[i].mbox==x.getName()){mbxList.push(ttMETA[i])}}return mbxList[x.getId()]}\r\n</script>"], 
        "actions": { 
            "content": [{ 
                "passMboxSession": false, 
                "selector": "body", 
                "action": "redirect", 
                "url": "https://example.com/04.html", 
                "includeAllUrlParameters": true 
            }] 
        } 
    }] 
}
```

## Felsvar {#section_1ACCE79AF2CB4FA2AD1371EA06AF129F}

Parametrarna &quot;status&quot; och &quot;error&quot; som skickas till återanropet har följande format:

| Namn | Typ | Beskrivning |
|--- |--- |--- |
| status | Sträng | Representerar felstatusen. Den här parametern kan ha följande värden:<ul><li>timeout: Anger att tidsgränsen för begäran uppnåddes.</li><li>parseerror: Anger att svaret inte kunde tolkas, till exempel om vi får HTML eller oformaterad text i stället för JSON.</li><li>fel: Anger ett allmänt fel som om vi fick en annan HTTP-status än 200 OK</li></ul> |
| fel | Sträng | Innehåller ytterligare data, t.ex. ett undantagsmeddelande eller något annat som kan vara användbart vid felsökning. |