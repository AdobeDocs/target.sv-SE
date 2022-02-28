---
keywords: mbox;mbox3rdPartyId;profile syncing;profile synch;PCID
description: Lär dig hur du använder mbox3rdPartyId, som är din organisations besökar-ID, till exempel medlems-ID eller din organisations lojalitetsprogram.
title: Hur använder jag profilsynkronisering i realtid för mbox3rdPartyId?
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 8969b3b04b8f02a4ae9860bafe4b0a1c80a6f35e
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---

# Profilsynkronisering i realtid för mbox3rdPartyId

The `mbox3rdPartyId` in [!DNL Adobe Target] är ditt företags besökar-ID, t.ex. medlemskaps-ID för ditt företags lojalitetsprogram.

När en besökare loggar in på ett företags webbplats skapar företaget vanligtvis ett ID som är knutet till besökarens konto, förmånskort, medlemsnummer eller andra tillämpliga identifierare för det företaget.

När en besökare öppnar en sida där [!DNL Target] är aktiverad, besökaren tilldelas en [!DNL Target] PCID. Om besökaren sedan loggar in och implementeringen lyckas `mbox3rdPartyId` till [!DNL Target], [!DNL Target] ansluter besökarens `mbox3rdPartyId` med [!DNL Target] PCID.

Var tredje till var femte minut synkroniseras uppdateringarna med databasen. När besökaren loggar ut ersätter de sammanfogade data de tidigare data som är kopplade till `mbox3rdPartyId`, som skapar ett fullständigt register över besökarens åtgärder. Om samma attribut finns i båda ID:n, t.ex. finns category=hatts och `mbox3rdPartyId` har category=skis, eller om besökaren såg upplevelsen A före inloggning, men upplevelsen B lagras i `mbox3rdPartyId`—attributet lagras i `mbox3rdPartyId` skriver över attributet från PCID:t. Om besökaren befann sig i en aktivitet eller upplevelse innan han loggade in, men en annan aktivitet och upplevelse lagras i `mbox3rdPartyId`, efter inloggning, placeras besökaren i `mbox3rdPartyId` aktivitet och upplevelser.

| PCID (ej inloggad) | mbox3rdPartyId (inloggad) | Sammanfogad och sparad till mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Aktivitet 1, upplevelse A | Aktivitet 1, upplevelse B | Aktivitet 1, upplevelse B |
| Aktivitet 1 |  | Aktivitet 1 |

När besökaren loggar ut bevaras den sammanfogade profilen.

>[!NOTE]
>
>Om du vill skilja mellan autentiserade (inloggade) användare och icke-autentiserade användare använder du [!DNL Adobe Experience Cloud Identity Service] (ECID) i stället för mbox3rdPartyID. När en användare har associerats med mbox3rdPartyID förblir det associerat med användaren även efter utloggning.

>[!NOTE]
>
>[!DNL Adobe Analytics] mål inte spåras i de fall där [!DNL Adobe Experience Cloud] ID (ECID) ändras (besökaren ändrar till exempel enheter) även om [!DNL Target] Profilen kan sammanfogas baserat på mbox3rdPartyId och har fortfarande aktivitetsinformation. För besökare som identifieras med samma ECID (de som kommer åt sidan med samma enhet), [!DNL Analytics for Target] (A4T) ska fungera som förväntat.

## Överväganden {#considerations}

* Om sidan innehåller flera kryssrutor och bara används en del `3rdPartyID`, [!DNL Target] har ingen separat besökarprofil/kontext för varje besökarbegäran. The `3rdPartyID` context har högre prioritet än PCID-kontexten. Det räcker med en mbox `3rdPartyId` för att dess kontext ska ha företräde framför PCID.

   Anta till exempel att en besökare kommer åt en sida innan han/hon loggar in och ser en upplevelse. Den globala mbox använder inte `3rdPartyID`. Efter inloggning ser besökaren en av tre upplevelser med underordnade kryssrutor, varav vissa använder `3rdPartyID`. Besökaren besöker olika sidor på webbplatsen och använder sedan knappen Bakåt för att gå tillbaka till huvudsidan som öppnats före inloggningen och ser en annan upplevelse. I det här scenariot godkändes inte den globala mbox-filen `3rdPartyID`, men en eller flera av de underordnade rutorna gjorde det. `3rdPartyID` prioriterar PCID.

* Du kan skicka besökares kund-ID till [!DNL Target] använda två metoder:

   1. Använd `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` är parameternamnet när du använder `targetPageParams` eller `targetPageParamsAll`
      * `thirdPartyId` är det parameternamn som du anger direkt i leverans-API-nyttolasten.
      * Du kan bara skicka ett värde i den här parametern.
   1. Använd `setCustomerId`/`customerIds` ECID-tjänstens funktion.

      * `setCustomerId` är en funktion som du kan använda på implementeringar på klientsidan (webbläsare) när VisitorAPI.js är tillgängligt på sidan.
      * `customerIds` är parameternamnet som används när du anger det direkt i nyttolasten för leverans-API och vanligtvis görs på implementeringar på serversidan eller i IOT (Internet of Things).
      * Ogilla `mbox3rdPartyId`/`thirdPartyId`kan du skicka flera ID:n som en lista på det här sättet, men eftersom [!DNL Target] stöder endast ett kund-ID per TnT ID, det använder det första ID:t i listan med ett känt alias (alias konfigurerat i användargränssnittet för kundattribut).

   Du kan använda `mbox3rdPartyId`/`thirdPartyId` if [!DNL Target] är din enda [!DNL Adobe Experience Cloud] och du inte vill använda kundattribut. I alla andra fall rekommenderar vi att du använder `setCustomerId`/`customerIds` för att skicka dina kund-ID:n.

   >[!IMPORTANT]
   >
   > Om båda de metoder som nämns ovan används för en enskild besökare kan det leda till felaktiga profilsammanslagningar av den oautentiserade och autentiserade [!DNL Target] profiler.
   >
   >Adobe rekommenderar inte att du använder båda `mbox3rdPartyId`/`thirdPartyId` och `setCustomerID`/`customerIds` tillsammans.
   >
   >Om du måste använda båda metoderna på ett annat sätt måste du se till att det första ID:t i listan som används av `setCustomerID`/`customerIds` är vad som används av `thirdPartyId`/`mbox3rdPartyId` och vice versa.

