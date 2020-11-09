---
description: Information om hur man på ett säkert sätt distribuerar at.js till en icke-produktionsmiljö.
title: Distribuera at.js till en icke-produktionsmiljö
feature: null
uuid: 7f1adc43-35b4-442c-bb06-feab60604a87
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---


# Distribuera at.js till en icke-produktionsmiljö{#deploy-at-js-to-a-non-production-environment}

Information om teknikerna för säker driftsättning i at.js till en icke-produktionsmiljö.

## Distribuera till DTM-mellanlagring

Om du använder DTM kan du enkelt spara at.js i Adobe Target Tool-konfigurationen.

När du har sparat biblioteket använder du DTM Switch-verktyget för att testa det mot din produktionskod. Detta gör det också enkelt för dina Adobe-konsulter att ge dig support.

Mer information finns i [alternativ 3: Implementera Target manuellt med målbiblioteket för JavaScript, som finns hos DTM](https://experienceleague.adobe.com/docs/dtm/implementing/target/add-target/t-implementing-target-manually-js-hosted-dtm.html) , i *Best Practices för implementering av Adobe Target med hjälp av guiden för dynamisk tagghantering* .

## Använd Chrome-tillägget &quot;True&quot; för att mappa till en annan fil

>[!NOTE]
>
>Utöver följande information kan du använda webbläsartillägget [](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) Adobe Target VEC Helper för Google Chrome.

[Ärligt talat](https://chrome.google.com/webstore/detail/requestly/mdnleldcmiljblolnjhpnblkcekpdkpa?hl=en) är det ett kostnadsfritt Chrome-tillägg som gör att du kan omdirigera begäranden till en alternativ URL.

Du distribuerar at.js till en URL och använder sedan True för att mappa din aktuella mbox.js-fils-URL till den nya at.js-URL:en. När webbplatsen sedan försöker läsa in mbox.js läses den in på .js i stället. Detta gör det också enklare för Adobe att ge stöd.

## Distribuera till en utvecklings-, staging- eller QA-miljö

Om du har mbox.js i din kodbas och enkelt kan uppdatera dina kodmiljöer kan du distribuera at at.js till en av dina lägre miljöer.

Om du vill ha bättre stöd från Adobe ska du distribuera filen i en miljö som Adobe har åtkomst till.

## Använd Charles eller Fiddler för att mappa till en lokal fil

[Charles Web Debugging Proxy](https://www.charlesproxy.com/) är ett program för Mac och Windows vars funktion Map Local kan användas för att mappa inläsningen av din mbox.js-fil till en lokal kopia av at.js. Det finns en kostnadsfri testversion att ladda ned för Mac och Windows.

[Fiddler](https://www.telerik.com/fiddler) är ett liknande verktyg som finns som kostnadsfri nedladdning för Windows.

## Distribuera till en annan tagghanteringsmiljö

Om du använder en annan tagghanterare har den antagligen ett sätt att distribuera at.js på ett säkert sätt utan att påverka produktionstrafiken.