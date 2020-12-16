---
keywords: at.js;functions;javascript library
description: Lista över funktioner som kan användas med JavaScript-biblioteket at.js i Adobe Target.
title: Funktioner i Adobe Target at.js
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# at.js-funktioner{#at-js-functions}

Lista över funktioner som kan användas med Adobe Target at.js JavaScript-bibliotek. Klicka på länkarna i kolumnen Funktion för mer information och exempel.

|  -funktion | Detaljer |
| --- | --- | 
| [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) | Den här funktionen utlöser en begäran om att få ett Target-erbjudande. Använd med `adobe.target.applyOffer()` för att bearbeta svaret eller använda din egen hantering av lyckade åtgärder. |
| [adobe.target.getOffers(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)<br>(at.js 2.x) | Med den här funktionen kan du hämta flera erbjudanden genom att skicka in flera rutor. Dessutom kan flera erbjudanden hämtas för alla vyer i aktiva aktiviteter.<br>**Obs!** Den här funktionen introducerades med at.js 2.x. Den här funktionen är inte tillgänglig för at.js version 1.*x*. |
| [adobe.target.applyOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) | Den här funktionen används för att tillämpa svarsinnehållet. |
| [adobe.target.applyOffers(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffers-atjs-2.md)<br>(at.js 2.x) | Med den här funktionen kan du tillämpa mer än ett erbjudande som har hämtats av adobe.target.getOffers().<br>**Obs!** Den här funktionen introducerades med at.js 2.x. Den här funktionen är inte tillgänglig för at.js version 1.*x*. |
| [adobe.target.triggerView (viewName, options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md)<br>(at.js 2.x) | Den här funktionen kan anropas när en ny sida läses in eller när en komponent på en sida återges på nytt.<br> Den här funktionen ska implementeras för enkelsidiga program (SPA) för att använda Visual Experience Composer (VEC) för att skapa A/B-tester och XT-aktiviteter (Experience Targeting). |
| [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) | Den här funktionen utlöser en begäran om att rapportera användaråtgärder, till exempel klickningar och konverteringar. Den levererar inte någon verksamhet som svar. |
| [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)<br>(at.js 1.x) | Kör en begäran och tillämpar erbjudandet på närmaste DIV med mboxDefault-klassnamn.<br>**Obs!** Den här funktionen är tillgänglig för at.js version 1.*Endast* . Den här funktionen har ersatts med versionen av at.js 2.x. Den här funktionen returnerar standardinnehåll om den används med at.js 2.x. |
| [mboxDefine(options) och mboxUpdate(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxdefine-mboxupdate-atjs-1x.md)<br>(at.js 1.x) | Definiera och uppdatera en mbox.<br>**Obs!** Den här funktionen är tillgänglig för at.js version 1.*Endast* . Den här funktionen har ersatts med versionen av at.js 2.x. Den här funktionen returnerar standardinnehåll om den används med at.js 2.x. |
| [targetGlobalSettings(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Du kan åsidosätta inställningarna i at.js-biblioteket med `targetGlobalSettings()`, i stället för att konfigurera inställningarna i Target Standard/Premium-gränssnittet eller genom att använda REST API:er.<ul><li>Dataleverantörer: Med den här inställningen kan kunder samla in data från tredjepartsleverantörer av data, som Demandbase, BlueKai och anpassade tjänster, och skicka data till Target som mbox-parametrar i den globala mbox-begäran.</li></ul> |
| [targetPageParams(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) | Med den här metoden kan du bifoga parametrar till den globala mbox utanför begärandekoden. |
| [targetPageParamsAll(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) | Med den här metoden kan du bifoga parametrar till alla rutor utanför begärandekoden. |
| [registerExtension(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/registerextension-atjs-1x.md)<br>(at.js 1.x) | Tillhandahåller ett standardsätt att registrera ett specifikt tillägg.<br>**Obs!** Den här funktionen är tillgänglig för at.js version 1.*Endast* . Den här funktionen har ersatts med versionen av at.js 2.x. Den här funktionen returnerar standardinnehåll om den används med at.js 2.x. |
| [at.js, anpassade händelser](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | anpassade at.js-händelser talar om när en mbox-begäran eller ett erbjudande misslyckas eller lyckas. |
| [adobe.target.sendNotifications(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)<br>(at.js 2.1.0) | Den här funktionen skickar ett meddelande till Target edge när en upplevelse återges utan att använda `adobe.target.applyOffer()` eller `adobe.target.applyOffers()`.<br>**Obs**: Den här funktionen har introducerats i at.js 2.1.0 och är tillgänglig för alla versioner över 2.1.0. |

