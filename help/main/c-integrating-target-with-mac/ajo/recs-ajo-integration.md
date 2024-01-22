---
keywords: ajo;adobe travel optimizer;adobe travel optimizer target integration;recommendations;target recommendations;integration
description: Integrera [!DNL Adobe Target Recommendations] med [!DNL Adobe Journey Optimizer].
title: Hur använder jag [!DNL Target Recommendations] på kundresor som använder [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="Vad är Beta-funktioner i [!DNL Adobe Target]."
hide: true
hidefromtoc: true
source-git-commit: 1faedc44c4f8f95000b666af8eecaf1eca5bf48d
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%

---

# Integrera [!DNL Adobe Target Recommendations] och [!DNL Adobe Journey Optimizer]

I den här artikeln beskrivs användningsexempel och information som hjälper dig att konfigurera integreringen mellan [!DNL Adobe Target Recommendation] och [!DNL Adobe Journey Optimizer] för att hjälpa er att leverera sammankopplade, kontextuella och personaliserade upplevelser till era kunder.

## Förutsättningar

Använd [!DNL Target Recommendations] och [!DNL Adobe Journey Optimizer] -integrering behöver du följande:

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) implementerat med [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

  Funktionen är inte tillgänglig med en [!DNL Target Standard] licens eller vid implementering [!DNL Target] med at.js eller andra [!DNL Target] SDK:er.

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## Exempel på användningsområden

Följande är bara två möjliga användningsområden för integrering [!DNL Target Recommendations] med [!DNL Adobe Journey Optimizer]:

* **[!DNL Customer Journey Optimizer]skickar ett personaliserat e-postmeddelande när kundvagnen har övergetts**: Det här användningsexemplet bygger på att en kund besöker en webbplats, placerar artiklar i kundvagnen och sedan lämnar webbplatsen utan att slutföra köpprocessen.

  Anta till exempel att en besökare besöker ett klädföretags webbplats och placerar två vinterkattor och en tröja i kundvagnen. Besökaren distraheras sedan och lämnar webbplatsen eller är osäker på köpet och stänger webbläsaren eller appen.

  Efter en viss tid, kanske några timmar eller dag, kan en anpassad åtgärd som [!DNL Adobe Journey Optimizer] ringer till [!DNL Target Recommendations] för att fastställa innehållet i den övergivna kundvagnen. [!DNL Adobe Journey Optimizer] skickar sedan ett personligt mejl till besökaren som en påminnelse om att köpprocessen inte har slutförts, tillsammans med bilder och länkar till de övergivna objekten.

* **[!DNL Customer Journey Optimizer]skickar ett e-postmeddelande efter webbplatsbesök med användarprofilen**: Det här användningsexemplet bygger på att en kund besöker en webbplats, visar olika artiklar och sedan lämnar webbplatsen utan att placera artiklar i kundvagnen.

  Efter en angiven tidsperiod utförs en anpassad åtgärd i [!DNL Adobe Journey Optimizer] ringer till [!DNL Target Recommendations] för att avgöra vilka objekt besökaren visade med hjälp av besökarens [!DNL Adobe Experience Cloud Identifier] (EDID). [!DNL Adobe Journey Optimizer] skickar sedan ett personligt mejl till besökaren som en påminnelse om att köpprocessen inte har slutförts, tillsammans med bilder och länkar till de övergivna objekten.

