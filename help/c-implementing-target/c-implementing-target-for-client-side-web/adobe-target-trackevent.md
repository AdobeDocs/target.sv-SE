---
keywords: adobe.target.trackEvent;trackEvent;trackevent;track event;at.js;functions;function;preventDefault;preventdefault;prevent default
description: Information om funktionen adobe.target.trackEvent(options) för Adobe Target JavaScript-biblioteket at.js.
title: adobe.target.trackEvent(options)
feature: client-side
translation-type: tm+mt
source-git-commit: a841c492e5d9e4bfedb20133ba32e37daf738c57
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---


# adobe.target.trackEvent(options)

Den här funktionen utlöser en begäran om att rapportera användaråtgärder, till exempel klickningar och konverteringar. Den levererar inte någon verksamhet som svar.

Dessa händelsespårningsanrop kan sedan användas för att definiera mått i aktiviteter. Mer information finns i [Success Metrics](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) and [Track Conversions](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).

Här är API-informationen:

| Nyckel | Typ | Obligatoriskt | Beskrivning |
|--- |--- |--- |--- |
| mbox | Sträng | Ja | Mbox <br>**nameNote**: Om ett trackEvent()-anrop utlöses med ett mbox-namn som redan har utlösts på sidan, återställs SDID för trackEvent() och skiljer sig från Target-anropen på sidan. Om du däremot startar ett trackEvent()-anrop med ett annat mbox-namn, blir SDID för anropet trackEvent() konsekvent med anropet till Page Load Request/triggerView() på sidan. |
| väljare | Sträng | Nej | CSS-väljare som används för att hitta HTML-elementen. Händelseavlyssnarna bifogas till de hittade elementen. |
| type | Sträng | Nej | Representerar en registrerad händelsetyp. Det kan vara både HTML-kända händelser som: klicka, musknappen o.s.v. samt anpassade HTML-händelser. |
| preventDefault | Boolean | Nej | Anger om det ska användas `event.preventDefault()` i händelseavlyssnaråteranropet. Standardvärdet är false.<br>**Obs**: Endast `form[submit] and `[en klickning]stöds. Andra scenarier stöds inte på grund av komplexitet och ett stort antal scenarier som ska stödjas. |
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