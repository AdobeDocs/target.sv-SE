---
keywords: mbox;mbox3rdPartyId;profile syncing;profile synch;PCID
description: Information om realtidsprofil
title: Profilsynkronisering i realtid för Mbox3Rdpartyid
feature: Audiences
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---


# Profilsynkronisering i realtid för mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

Mbox3rdPartyId är företagets besökar-ID, till exempel medlemskaps-ID för företagets lojalitetsprogram.

När en besökare loggar in på ett företags webbplats skapar företaget vanligtvis ett ID som är knutet till besökarens konto, förmånskort, medlemsnummer eller andra tillämpliga identifierare för det företaget.

När en besökare öppnar en sida där [!DNL Target] är aktiverat tilldelas besökaren ett [!DNL Target] PCID. Om besökaren sedan loggar in och implementeringen skickar mbox3rdPartyId till [!DNL Target] ansluter [!DNL Target] besökarens mbox3rdPartyId med [!DNL Target] PCID.

Var tredje till var femte minut synkroniseras uppdateringarna med databasen. När besökaren loggar ut ersätter de sammanfogade data de tidigare data som är associerade med mbox3rdPartyId, vilket skapar en mer fullständig post för besökarens åtgärder. Om samma attribut finns i båda ID:n, till exempel, har PCID kategori=hattar och mbox3rdPartyId har category=skis, eller om besökaren såg upplevelsen A före inloggning, men upplevelsen B lagras i mbox3rdPartyId, skriver attributet som lagras i mbox3rdPartyId över attributet från PCID:t. Om besökaren befann sig i en aktivitet eller upplevelse innan inloggningen, men en annan aktivitet och upplevelse lagras i mbox3rdPartyId, placeras den besökaren efter inloggningen i aktiviteten och upplevelsen för mbox3rdPartyId.

| PCID (ej inloggad) | mbox3rdPartyId (inloggad) | Sammanfogad och sparad till mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Aktivitet 1, upplevelse A | Aktivitet 1, upplevelse B | Aktivitet 1, upplevelse B |
| Aktivitet 1 |  | Aktivitet 1 |

När besökaren loggar ut bevaras den sammanfogade profilen.

>[!NOTE]
>
>Om du vill skilja mellan autentiserade (inloggade) användare och icke-autentiserade användare använder du Adobe Experience Cloud Identity Service (ECID) i stället för mbox3rdPartyID. När en användare har associerats med mbox3rdPartyID förblir det associerat med användaren även efter utloggning.

>[!NOTE]
>
>[!DNL Adobe Analytics] mål spåras inte i fall där  [!DNL Adobe Experience Cloud] ID (EDID) ändras (till exempel när besökaren ändrar enheter), även om  [!DNL Target] profilen kan sammanfogas baserat på mbox3rdPartyId och fortfarande har aktivitetsinformation. För besökare som identifieras med samma EDID (de som öppnar sidan med samma enhet) ska [!DNL Analytics for Target] (A4T) fungera som förväntat.

## Överväganden {#considerations}

Om sidan innehåller flera kryssrutor och endast vissa använder 3rdPartyID har Target inte en separat besökarprofil/kontext för varje besökarbegäran. Kontexten för 3rdPartyID har högre prioritet än PCID-kontexten. Det räcker med att en mbox skickar ett 3rdPartyId för att dess kontext ska få högre prioritet än PCID.

Anta till exempel att en besökare kommer åt en sida innan han/hon loggar in och ser en upplevelse. Den globala mbox använder inte 3rdPartyID. Efter inloggning ser besökaren en av tre upplevelser med underordnade kryssrutor, varav vissa använder 3rdPartyID. Besökaren besöker olika sidor på webbplatsen och använder sedan knappen Bakåt för att gå tillbaka till huvudsidan som öppnats före inloggningen och ser en annan upplevelse. I det här scenariot skickades inte 3rdPartyID till den globala mbox, men en eller flera av de underordnade mbox-adresserna gjorde det. 3rdPartyID prioriterades framför PCID.
