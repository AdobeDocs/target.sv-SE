---
keywords: adobe.target.trackEvent;trackEvent;trackevent;track event;at.js;functions;function;preventDefault;preventDefault;prevent default
description: Använd funktionen adobe.target.trackEvent() för Adobe [!DNL Target] at.js JavaScript-bibliotek som utlöser en begäran om att rapportera användaråtgärder, till exempel klickningar och konverteringar på din webbplats.
title: Hur använder jag funktionen adobe.target.trackEvent()?
feature: at.js
role: Developer
exl-id: 36005236-ce18-4845-b4fb-e52056018bc7
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# adobe.target.trackEvent(options)

Den här funktionen utlöser en begäran om att rapportera användaråtgärder, till exempel klickningar och konverteringar. Den levererar inte någon verksamhet som svar.

Dessa händelsespårningsanrop kan sedan användas för att definiera mått i aktiviteter. Mer information finns i [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) och [Spåra konverteringar](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/){target=_blank}.

Här är API-informationen:

| Nyckel | Typ | Obligatoriskt | Beskrivning |
|--- |--- |--- |--- |
| mbox | Sträng | Ja | Namn på mbox <br>**Anteckning**: Om ett trackEvent()-anrop utlöses med ett mbox-namn som redan har utlösts på sidan, återställs SDID för trackEvent() och skiljer sig från Target-anropen på sidan. Om du däremot startar ett trackEvent()-anrop med ett annat mbox-namn, blir SDID för anropet trackEvent() konsekvent med anropet till Page Load Request/triggerView() på sidan. |
| väljare | Sträng | Nej | CSS-väljare som används för att hitta elementen i HTML. Händelseavlyssnarna bifogas till de hittade elementen. |
| type | Sträng | Nej | Representerar en registrerad händelsetyp. Det kan vara både HTML-kända händelser som: musklickningar, musklickningar osv. samt anpassade HTML-händelser. |
| preventDefault | Boolean | Nej | Anger om ska användas `event.preventDefault()` i händelseavlyssnaråteranrop. Standardvärdet är false.<br>**Anteckning**: Endast `form[submit]` och `a[click]` stöds. Andra scenarier stöds inte på grund av komplexitet och ett stort antal scenarier som ska stödjas. |
| parametrar | Objekt | Nej | Mbox-parametrar. Ett objekt med nyckelvärdepar som har följande struktur:<br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | Nummer | Nej | Timeout i millisekunder.<br>Om inget anges används standardvärdet:<br>`...timeoutInSeconds: 0.15...}` |
| framgång |  -funktion | Nej | En callback-funktion som används för att signalera att en händelse har rapporterats. |
| fel |  -funktion | Nej | En återanropsfunktion som används för att signalera att händelsen inte kunde rapporteras. |

## Exempel

```javascript
<a href="https://asite.com">click me!</a> 
```

plus JavaScript-kod som ska tilldelas `trackEvent`:

```javascript
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

Eller:

```javascript
adobe.target.trackEvent({ 
    "mbox": "clicked-cta", 
    "params": { 
        "param1": "value1" 
    } 
});
```

>[!NOTE]
>
>Om de obligatoriska fälten inte anges utförs ingen begäran och ett fel genereras.
