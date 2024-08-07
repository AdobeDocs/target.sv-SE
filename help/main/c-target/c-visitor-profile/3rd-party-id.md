---
keywords: mbox;mbox3rdPartyId;profile syncing;profile synch;PCID
description: Lär dig hur du använder mbox3rdPartyId, som är din organisations besökar-ID, till exempel medlems-ID eller din organisations lojalitetsprogram.
title: Hur använder jag profilsynkronisering i realtid för mbox3rdPartyId?
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 0%

---

# Profilsynkronisering i realtid för mbox3rdPartyId

`mbox3rdPartyId` i [!DNL Adobe Target] är ditt företags besökar-ID, till exempel medlemskaps-ID:t för ditt företags lojalitetsprogram.

När en besökare loggar in på ett företags webbplats skapar företaget vanligtvis ett ID som är knutet till besökarens konto, förmånskort, medlemsnummer eller andra tillämpliga identifierare för det företaget.

När en besökare kommer åt en sida där [!DNL Target] är aktiverat tilldelas den besökaren ett [!DNL Target] PCID. Om besökaren sedan loggar in och implementeringen skickar `mbox3rdPartyId` till [!DNL Target] ansluter [!DNL Target] besökarens `mbox3rdPartyId` till [!DNL Target] PCID.

Uppdateringar synkroniseras med profilarkivet var 5-10:e minut. När besökarens session avslutas ersätter de sammanfogade data de tidigare data som är associerade med `mbox3rdPartyId`, vilket skapar en fullständig post för besökarens åtgärder. Om samma attribut finns i båda ID:n, till exempel, har PCID kategori=hattar och `mbox3rdPartyId` har category=skis, eller om besökaren såg upplevelsen A före inloggning, men upplevelse B lagras i `mbox3rdPartyId`, skriver attributet som lagras i `mbox3rdPartyId` över attributet från PCID:t. Om besökaren befann sig i en aktivitet eller en upplevelse innan inloggningen, men en annan aktivitet och upplevelse lagras i `mbox3rdPartyId`, efter inloggningen, placeras den besökaren i aktiviteten och upplevelsen `mbox3rdPartyId`.

| PCID (ej inloggad) | mbox3rdPartyId (inloggad) | Sammanfogad och sparad till mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|   | store=94103 | store=94103 |
| Aktivitet 1, upplevelse A | Aktivitet 1, upplevelse B | Aktivitet 1, upplevelse B |
| Aktivitet 1 |  | Aktivitet 1 |

När besökaren loggar ut bevaras den sammanfogade profilen.

>[!NOTE]
>
>Om du vill skilja mellan autentiserade (inloggade) användare och icke-autentiserade användare använder du [!DNL Adobe Experience Cloud Identity Service] (ECID) i stället för mbox3rdPartyID. När en användare har associerats med mbox3rdPartyID förblir det associerat med användaren även efter utloggning.

>[!NOTE]
>
>[!DNL Adobe Analytics] mål spåras inte i fall där [!DNL Adobe Experience Cloud] ID (ECID) ändras (till exempel ändras enheter), även om profilen [!DNL Target] kan sammanfogas baserat på mbox3rdPartyId och fortfarande har aktivitetsinformation. För besökare som identifieras med samma ECID (de som kommer åt sidan med samma enhet), ska [!DNL Analytics for Target] (A4T) fungera som förväntat.

## Överväganden {#considerations}

* Om sidan innehåller flera kryssrutor och bara en del `3rdPartyID` används, har [!DNL Target] inte en separat besökarprofil/kontext för varje besökarbegäran. Kontexten `3rdPartyID` har högre prioritet än PCID-kontexten. Det räcker med att en mbox skickar `3rdPartyId` för att dess kontext ska få högre prioritet än PCID.

  Anta till exempel att en besökare kommer åt en sida innan han/hon loggar in och ser en upplevelse. Den globala mbox använder inte `3rdPartyID`. Efter inloggning ser besökaren en av tre upplevelser med underordnade kryssrutor, varav vissa använder `3rdPartyID`. Besökaren besöker olika sidor på webbplatsen och använder sedan knappen Bakåt för att gå tillbaka till huvudsidan som öppnats före inloggningen och ser en annan upplevelse. I det här scenariot godkändes inte `3rdPartyID` av den globala mbox-filen, men en eller flera av de underordnade mbox-filerna gjorde det. `3rdPartyID` prioriterades före PCID.

* Du kan skicka besökares kund-ID till [!DNL Target] på två sätt:

   1. Använd `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` är parameternamnet när du använder `targetPageParams` eller `targetPageParamsAll`
      * `thirdPartyId` är det parameternamn som du anger direkt i leverans-API-nyttolasten.
      * Du kan bara skicka ett värde i den här parametern.

   1. Använd funktionen `setCustomerId`/`customerIds` i ECID-tjänsten.

      * `setCustomerId` är en funktion som du kan använda på implementeringar på klientsidan (webbläsare) när VisitorAPI.js är tillgängligt på sidan.
      * `customerIds` är det parameternamn som används när du anger det direkt i nyttolasten för leverans-API och vanligtvis görs på implementeringar på serversidan eller i IOT (Internet of Things).
      * Till skillnad från `mbox3rdPartyId`/`thirdPartyId` kan du skicka flera ID:n som en lista i den här metoden, men eftersom [!DNL Target] bara stöder ett enda kund-ID per TnT ID används det första ID:t i listan med ett känt alias (alias konfigurerat i användargränssnittet för kundattribut).

  Du kan använda `mbox3rdPartyId`/`thirdPartyId` om [!DNL Target] är den enda [!DNL Adobe Experience Cloud]-lösningen och du inte vill använda kundattribut. I alla andra fall rekommenderar vi att du använder `setCustomerId`/`customerIds` för att skicka dina kund-ID:n.

  >[!IMPORTANT]
  >
  > Om du använder båda de metoder som nämns ovan för en enskild besökare kan det leda till felaktiga profilsammanslagningar av de oautentiserade och autentiserade [!DNL Target]-profilerna.
  >
  >Adobe rekommenderar inte att du använder både `mbox3rdPartyId`/`thirdPartyId` och `setCustomerID`/`customerIds` tillsammans.
  >
  >Om du måste använda båda metoderna för varandra måste du se till att det första ID:t i listan som används av `setCustomerID`/`customerIds` är det som används av `thirdPartyId`/`mbox3rdPartyId` och vice versa.

