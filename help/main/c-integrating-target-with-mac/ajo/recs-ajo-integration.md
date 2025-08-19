---
keywords: ajo;adobe travel optimizer;adobe travel optimizer target integration;recommendations;target recommendations;integration
description: Integrera [!DNL Adobe Target Recommendations] med [!DNL Adobe Journey Optimizer].
title: Hur använder jag  [!DNL Target Recommendations] i kundresor med  [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#beta newtab=true" tooltip="Vad är Beta-funktioner i  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
exl-id: 81bbbd51-47fc-4e23-a1cb-7c18fea1c159
source-git-commit: b4f9e14f9dfa94f8648686e43e66eee7e0f7daa1
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# Integrera [!DNL Adobe Target Recommendations] och [!DNL Adobe Journey Optimizer]

Den här artikeln innehåller användningsexempel och vägledning för integrering av [!DNL Adobe Target Recommendations] med [!DNL Adobe Journey Optimizer], vilket gör att du kan leverera sammankopplade, kontextuella och personaliserade kundupplevelser.

Denna integrering hjälper er att få fler konverteringar och se effekten av e-postmeddelanden som innehåller personaliserade rekommendationer.

## Förutsättningar

Om du vill använda integreringen [!DNL Target Recommendations] och [!DNL Adobe Journey Optimizer] behöver du följande:

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) implementeras med [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

  Den här funktionen är inte tillgänglig med en [!DNL Target Standard]-licens eller vid implementering av [!DNL Target] med at.js eller andra [!DNL Target] SDK:er.

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target=_blank}.

## Exempel på användningsområden

De här användningsexemplen är bara några möjliga användningsexempel för integrering av [!DNL Target Recommendations] med [!DNL Adobe Journey Optimizer]:

* **[!DNL Adobe Journey Optimizer]skickar ett anpassat e-postmeddelande efter att vagnen har övergetts**: Det här användningsexemplet baseras på att en kund besöker en webbplats, placerar artiklar i kundvagnen och sedan lämnar webbplatsen utan att slutföra köpprocessen.

  Anta till exempel att en besökare besöker ett klädföretags webbplats och placerar två vinterkattor och en tröja i kundvagnen. Besökaren distraheras sedan och lämnar webbplatsen eller är osäker på köpet och stänger webbläsaren eller appen.

  Efter en angiven period, kanske några timmar eller dag, anropar en anpassad åtgärd i [!DNL Journey Optimizer] [!DNL Target Recommendations] för att bestämma innehållet i den övergivna kundvagnen med hjälp av en [kundvagnsbaserad rekommendationsalgoritm](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md). [!DNL Journey Optimizer] skickar sedan ett personligt e-postmeddelande till besökaren som en påminnelse om att inköpsprocessen inte slutfördes, tillsammans med bilder och länkar till de övergivna objekten.

* **[!DNL Adobe Journey Optimizer]skickar ett e-postmeddelande efter webbplatsbesök för att påminna besökare om vilka objekt som visades**: Det här användningsexemplet baseras på besökare som besöker en webbplats, visar olika objekt och sedan lämnar webbplatsen eller appen utan att placera artiklar i kundvagnen.

  Efter en angiven period gör en anpassad åtgärd i [!DNL Journey Optimizer] ett anrop till [!DNL Target Recommendations] för att avgöra vilka objekt som varje besökare visade, med hjälp av varje besökares [!DNL Adobe Experience Cloud Identifier] (EDID), besökarens [!DNL Target]-profil och en [användarbaserad](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) algoritm. [!DNL Adobe Journey Optimizer] skickar sedan ett personligt e-postmeddelande till varje medlem av den kvalificerade målgruppen med bilder och länkar till de visade objekten så att besökaren kan returnera och göra ett köp.

  I det här scenariot används [!UICONTROL Experience Cloud Visitor ID] (ECID) och innehållet i varje besökares [!DNL Target]-profil för att generera rekommendationen baserat på den senast visade algoritmen.

  Anta till exempel att en besökare besöker en återförsäljarwebbplats och ser flera bevakningar. Den här besökarens [!DNL Target]-profil uppdateras med en lista över de visade bevakningarna. Med hjälp av ECID och besökarens [!DNL Target]-profil skickar [!DNL Target] rekommendationen till [!DNL Journey Optimizer]. [!DNL Journey Optimizer] skickar sedan ett e-postmeddelande med bilder och länkar till de bevakningar som besökaren visade med hjälp av algoritmen som visades nyligen. En annan besökare får ett personligt mejl med bilder och länkar till de objekt som besökaren visade. Varje e-postmeddelande anpassas för varje besökare.

* **[!DNL Adobe Journey Optimizer]skickar ett e-postmeddelande till kvalificerade besökare efter webbplatsbesöket för att föreslå populära objekt**: Det här användningsexemplet baseras på en besökare som besöker en webbplats, men inte på några särskilda objekt. E-postmeddelandet skickas i bulk till alla besökare som är kvalificerade för en viss målgrupp, till exempel:

  Anta att besökaren inte visar några särskilda bevakningar. Kanske klickade besökaren bara runt webbplatsen och visade kategorisidor eller blogginlägg. Därför har profilen [!DNL Target] inte specifik information om nyligen visade objekt. I den här situationen använder [!DNL Target Recommendations] en [rekommendation för säkerhetskopiering](/help/main/c-recommendations/c-algorithms/backup-recs.md) så att [!DNL Journey Optimizer] kan skicka ett e-postmeddelande med bilder och länkar till populära objekt på webbplatsen för att få besökaren att återvända och eventuellt göra ett köp.
