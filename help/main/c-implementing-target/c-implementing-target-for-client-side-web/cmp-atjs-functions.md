---
keywords: at.js;funktioner;javascript-bibliotek
description: Visa en lista med funktioner som kan användas med 1.x- och 2.x-versionerna av JavaScript-biblioteket at.js i Adobe Target.
title: Vilka funktioner kan jag använda med at.js?
feature: at.js
role: Developer
exl-id: a386e478-16f4-4bf6-9771-6b1e75f2e362
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 0%

---

# Funktionerna at.js

Lista över funktioner som kan användas med Adobe Target at.js JavaScript-bibliotek. Klicka på länkarna i kolumnen Funktion för mer information och exempel.

|  -funktion | Detaljer |
| --- | --- | 
| [adobe.target.getOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/) | Den här funktionen utlöser en begäran om att få ett Target-erbjudande. Använd med `adobe.target.applyOffer()` för att bearbeta svaret eller använda din egen hantering av lyckade resultat. |
| [adobe.target.getOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/)<br>(at.js 2.x) | Med den här funktionen kan du hämta flera erbjudanden genom att skicka in flera rutor. Dessutom kan flera erbjudanden hämtas för alla vyer i aktiva aktiviteter.<br>**Obs!** Den här funktionen introducerades med at.js 2.x. Den här funktionen är inte tillgänglig för at.js version 1.*x*. |
| [adobe.target.applyOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffer/) | Den här funktionen används för att tillämpa svarsinnehållet. |
| [adobe.target.applyOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffers-atjs-2/)<br>(at.js 2.x) | Med den här funktionen kan du tillämpa mer än ett erbjudande som har hämtats av adobe.target.getOffers().<br>**Obs!** Den här funktionen introducerades med at.js 2.x. Den här funktionen är inte tillgänglig för at.js version 1.*x*. |
| [adobe.target.triggerView (viewName, options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-triggerview-atjs-2/)<br>(at.js 2.x) | Den här funktionen kan anropas när en ny sida läses in eller när en komponent på en sida återges på nytt.<br> Den här funktionen ska implementeras för enkelsidiga program (SPA) för att använda Visual Experience Composer (VEC) för att skapa A/B-tester och XT-aktiviteter (Experience Targeting). |
| [adobe.target.trackEvent(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-trackevent/) | Den här funktionen utlöser en begäran om att rapportera användaråtgärder, till exempel klickningar och konverteringar. Den levererar inte någon verksamhet som svar. |
| [mboxCreate(mbox,params)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxcreate-atjs/)<br>(at.js 1.x) | Kör en begäran och tillämpar erbjudandet på närmaste DIV med mboxDefault-klassnamn.<br>**Obs!** Den här funktionen är tillgänglig för version 1 av at.js.*x* endast. Den här funktionen har ersatts med versionen av at.js 2.x. Den här funktionen returnerar standardinnehåll om den används med at.js 2.x. |
| [mboxDefine(options) och mboxUpdate(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxdefine-mboxupdate-atjs-1x/)<br>(at.js 1.x) | Definiera och uppdatera en mbox.<br>**Obs!** Den här funktionen är tillgänglig för version 1 av at.js.*x* endast. Den här funktionen har ersatts med versionen av at.js 2.x. Den här funktionen returnerar standardinnehåll om den används med at.js 2.x. |
| [targetGlobalSettings(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) | Du kan åsidosätta inställningarna i at.js-biblioteket med `targetGlobalSettings()`i stället för att konfigurera inställningarna i gränssnittet för målstandard/Premium eller genom att använda REST API:er.<ul><li>Dataleverantörer: Med den här inställningen kan kunder samla in data från tredjepartsleverantörer av data, som Demandbase, BlueKai och anpassade tjänster, och skicka data till Target som mbox-parametrar i den globala mbox-begäran.</li></ul> |
| [targetPageParams(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparams/) | Med den här metoden kan du bifoga parametrar till den globala mbox utanför begärandekoden. |
| [targetPageParamsAll(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/) | Med den här metoden kan du bifoga parametrar till alla rutor utanför begärandekoden. |
| [registerExtension(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/registerextension-atjs-1x/)<br>(at.js 1.x) | Tillhandahåller ett standardsätt att registrera ett specifikt tillägg.<br>**Obs!** Den här funktionen är tillgänglig för version 1 av at.js.*x* endast. Den här funktionen har ersatts med versionen av at.js 2.x. Den här funktionen returnerar standardinnehåll om den används med at.js 2.x. |
| [at.js, anpassade händelser](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-custom-events/) | anpassade at.js-händelser talar om när en mbox-begäran eller ett erbjudande misslyckas eller lyckas. |
| [adobe.target.sendNotifications(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-sendnotifications-atjs-21/)<br>(at.js 2.1.0) | Den här funktionen skickar ett meddelande till Target edge när en upplevelse återges utan att använda `adobe.target.applyOffer()` eller `adobe.target.applyOffers()`.<br>**Anteckning**: Den här funktionen har introducerats i at.js 2.1.0 och är tillgänglig för alla versioner över 2.1.0. |
