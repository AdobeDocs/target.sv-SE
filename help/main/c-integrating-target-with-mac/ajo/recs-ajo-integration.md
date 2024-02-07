---
keywords: ajo;adobe travel optimizer;adobe travel optimizer target integration;recommendations;target recommendations;integration
description: Integrera [!DNL Adobe Target Recommendations] med [!DNL Adobe Journey Optimizer].
title: Hur använder jag [!DNL Target Recommendations] på kundresor som använder [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="Vad är Beta-funktioner i [!DNL Adobe Target]."
hide: true
hidefromtoc: true
source-git-commit: 094ae9cc8b9700fab4ec583d045c0c31e741ddcb
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 0%

---

# Integrera [!DNL Adobe Target Recommendations] och [!DNL Adobe Journey Optimizer]

I den här artikeln beskrivs användningsexempel och information som hjälper dig att konfigurera integreringen mellan [!DNL Adobe Target Recommendations] och [!DNL Adobe Journey Optimizer] för att hjälpa er att leverera sammankopplade, kontextuella och personaliserade upplevelser till era kunder.

Denna integrering hjälper er att få fler konverteringar och se effekten av e-postmeddelanden som innehåller personaliserade rekommendationer.

## Förutsättningar

Använd [!DNL Target Recommendations] och [!DNL Adobe Journey Optimizer] -integrering behöver du följande:

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) implementerat med [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

  Den här funktionen är inte tillgänglig med en [!DNL Target Standard] licens eller vid implementering [!DNL Target] med at.js eller andra [!DNL Target] SDK:er.

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## Exempel på användningsområden

Nedan följer några exempel på hur du kan integrera [!DNL Target Recommendations] med [!DNL Adobe Journey Optimizer]:

* **[!DNL Adobe Journey Optimizer]skickar ett personaliserat e-postmeddelande när kundvagnen har övergetts**: Det här användningsexemplet bygger på att en kund besöker en webbplats, placerar artiklar i kundvagnen och sedan lämnar webbplatsen utan att slutföra köpprocessen.

  Anta till exempel att en besökare besöker ett klädföretags webbplats och placerar två vinterkattor och en tröja i kundvagnen. Besökaren distraheras sedan och lämnar webbplatsen eller är osäker på köpet och stänger webbläsaren eller appen.

  Efter en viss period, kanske några timmar eller dag, kan en anpassad åtgärd i [!DNL Adobe Journey Optimizer] ringer till [!DNL Target Recommendations] för att bestämma innehållet i den övergivna kundvagnen med hjälp av en [kundvagnsbaserade rekommendationer](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) algoritm. [!DNL Adobe Journey Optimizer] skickar sedan ett personligt mejl till besökaren som en påminnelse om att köpprocessen inte har slutförts, tillsammans med bilder och länkar till de övergivna objekten.

* **[!DNL Adobe Journey Optimizer]skickar ett e-postmeddelande efter besöket för att påminna besökaren om vilka objekt som visades**: Det här användningsexemplet bygger på att en besökare besöker en webbplats, visar olika artiklar och sedan lämnar webbplatsen eller appen utan att placera artiklar i kundvagnen.

  Efter en angiven punkt utförs en anpassad åtgärd i [!DNL Adobe Journey Optimizer] ringer till [!DNL Target Recommendations] för att avgöra vilka objekt besökaren visade med hjälp av besökarens [!DNL Adobe Experience Cloud Identifier] (EDID), besökarens [!DNL Target] och en [användarbaserad](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) algoritm. [!DNL Adobe Journey Optimizer] skickar sedan besökaren ett personligt e-postmeddelande med bilder och länkar till de visade objekten så att besökaren kan återvända och göra ett köp.

  I det här scenariot är [!UICONTROL Experience Cloud Visitor ID] (ECID) och innehållet i användarens [!DNL Target] används för att generera rekommendationen baserat på den nyligen visade algoritmen.

  Anta till exempel att en besökare besöker en återförsäljarwebbplats och ser flera bevakningar. Den här besökarens [!DNL Target] profilen uppdateras med en lista över de visade bevakningarna. Använda ECID och besökarens [!DNL Target] profil, [!DNL Target] skickar rekommendationen till [!DNL Adobe Journey Optimizer]. [!DNL Adobe Journey Optimizer] skickar sedan ett e-postmeddelande med bilder och länkar till de bevakningar som besökaren visade med algoritmen som visades nyligen.

* **[!DNL Adobe Journey Optimizer]skickar ett e-postmeddelande efter webbplatsbesök för att föreslå populära objekt**: Det här användningsexemplet bygger på att en besökare besöker en webbplats, men inte visar några särskilda objekt. Till skillnad från tidigare användningsfall skickas e-postmeddelandet i bulk till alla som är kvalificerade för en viss målgrupp, till exempel.

  Anta att besökaren inte visar några särskilda bevakningar. Kanske klickade besökaren bara runt webbplatsen och visade kategorisidor eller blogginlägg. Resultatet blev att [!DNL Target] profilen saknar specifik information om nyligen visade objekt. I denna situation [!DNL Target Recommendations] kan använda [rekommendation för säkerhetskopiering](/help/main/c-recommendations/c-algorithms/backup-recs.md) så att [!DNL Adobe Journey Optimizer] kan skicka ett e-postmeddelande med bilder och länkar till populära objekt på webbplatsen för att få besökaren att återvända och eventuellt göra ett köp.


