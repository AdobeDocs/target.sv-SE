---
keywords: at.js;non-production;non-production;deploy
description: Information om hur man på ett säkert sätt distribuerar at.js till en icke-produktionsmiljö.
title: Distribuera at.js till en icke-produktionsmiljö
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---


# Distribuera at.js till en icke-produktionsmiljö

Information om teknikerna för säker driftsättning i at.js till en icke-produktionsmiljö.

## Distribuera till DTM-mellanlagring

Om du använder DTM kan du enkelt spara at.js i Adobe Target Tool-konfigurationen.

När du har sparat biblioteket använder du DTM Switch-verktyget för att testa det mot din produktionskod. Detta gör det också enkelt för dina Adobe-konsulter att ge dig support.

Mer information finns i [Alternativ 3: Implementera mål manuellt med JavaScript-målbiblioteket som finns på DTM](https://experienceleague.adobe.com/docs/dtm/implementing/target/add-target/t-implementing-target-manually-js-hosted-dtm.html) i guiden *Best Practices for Implementera Adobe Target med Dynamic Tag Management*.

## Använd Chrome-tillägget &quot;True&quot; för att mappa till en annan fil

>[!NOTE]
>
>Utöver följande information kan du använda webbläsartillägget [Adobe Target VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) för Google Chrome.

[Request ](https://chrome.google.com/webstore/detail/requestly/mdnleldcmiljblolnjhpnblkcekpdkpa?hl=en) är ett kostnadsfritt Chrome-tillägg som gör att du kan omdirigera begäranden till en alternativ URL.

Du distribuerar at.js till en URL och använder sedan True för att mappa din aktuella mbox.js-fils-URL till den nya at.js-URL:en. När webbplatsen sedan försöker läsa in mbox.js läses den in på .js i stället. Detta gör det också enklare för Adobe att ge stöd.

## Distribuera till en utvecklings-, staging- eller QA-miljö

Om du har mbox.js i din kodbas och enkelt kan uppdatera dina kodmiljöer kan du distribuera at at.js till en av dina lägre miljöer.

Om du vill ha bättre stöd från Adobe ska du distribuera filen i en miljö som Adobe har åtkomst till.

## Använd Charles eller Fiddler för att mappa till en lokal fil

[Charles Web Debugging ](https://www.charlesproxy.com/) Proxyis är ett program för Mac och Windows vars funktion Map Local kan användas för att mappa inläsningen av din mbox.js-fil till en lokal kopia av at.js. Det finns en kostnadsfri testversion att ladda ned för Mac och Windows.

[Fiddler ](https://www.telerik.com/fiddler) är ett liknande verktyg som finns som kostnadsfri nedladdning för Windows.

## Distribuera till en annan tagghanteringsmiljö

Om du använder en annan tagghanterare har den antagligen ett sätt att distribuera at.js på ett säkert sätt utan att påverka produktionstrafiken.