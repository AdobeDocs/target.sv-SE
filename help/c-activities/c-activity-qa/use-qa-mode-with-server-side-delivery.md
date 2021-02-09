---
keywords: qa;serversida;serversida;förhandsgranska;förhandsvisa länkar
description: Lär dig hur du använder Adobe Target QA-URL:er med leverans på serversidan för att utföra enkel QA-analys från början till slut med förhandsgranskningslänkar som aldrig ändras, målgruppsanpassning som tillval och QA-rapportering som förblir segmenterad från liveaktivitetsdata.
title: Kan jag använda Activity QA med leverans på serversidan?
feature: Activities
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---


# Använd aktivitets-QA med leverans på serversidan

Använd QA-URL:er med leverans på serversidan i [!DNL Adobe Target] för att utföra enkel QA för hela aktiviteten med förhandsgranskningslänkar som aldrig ändras, målgruppsanpassning som tillval och QA-rapportering som förblir segmenterad från liveaktivitetsdata.

Standardimplementeringen av Activity QA har stöd för att skicka `qa_mode`-parametrar via `pageUrl`-parametrar. Detta är praktiskt för standard-/ajax-anrop av typen [!DNL Target]. För anrop från server till server är detta emellertid inte det bästa sättet för ett Mobile SDK-fall när `pageUrl` inte är tillgängligt.

I följande kodexempel visas Activity QA i ett anrop på serversidan:

```json
{
  "mbox" : "orderConfirmPage",
  "clientSideAnalyticsLogging": true,
  "clicked" : true,
  "tntId" : "12121212.17_01",
  "order" : {
    ...
  },
  "profileParameters" : {
    ...
  },
  "mboxParameters" : {
    ...
  },
  "requestLocation" : {
    ...
  },
  "qaMode" : {
    "token" : "<encrypted token string>",
    "bypassEntryAudience" : true,
    "listedActivitiesOnly" : true,
    "evaluateAsTrueAudienceIds" : [audienceId1, audienceId2...],
    "evaluateAsFalseAudienceIds" : [audienceId3, audienceId4...],
    "previewIndexes" : [
       {
         "activityIndex" : 1,
         "experienceIndex" : 1
       }
     ],
  },
  "mboxTrace" : true
}
```

I följande tabell förklaras detaljerna för en begäran på serversidan:

| Parameter | Typ | Standardvärde | Beskrivning |
|--- |--- |--- |--- |
| token | Krypterad token | Ingen.<br>Den får inte vara tom. | En krypterad entitet som innehåller listan över aktivitets-ID:n som tillåts att köras i Activity QA.<br>Valideringsregler: Bör vara en krypterad token som tillhör klienten som anges i  [!DNL Target] begäran. Alla aktiviteter som anges i token ska tillhöra klienten. |
| bypassEntryAudience | Boolean | Falskt | Anger om inmatningsstegsmål för QA-aktiviteter ska utvärderas eller om de ska anses matcha. |
| listedActivitiesOnly | Boolean | Falskt | Anger om QA-aktiviteter ska utföras separat eller om de ska utvärderas som aktiva aktiviteter för den aktuella miljön. |
| evaluateAsTrueAudienceIds | Lista med ID:n | Tom lista. | Lista med målgrupps-ID:n som alltid ska utvärderas som sanna i omfånget för [!DNL Target]-begäran. |
| evaluateAsFalseAudienceIds | Lista med ID:n | Tom lista. | Lista med målgrupps-ID:n som alltid ska utvärderas som falska i omfattningen av [!DNL Target]-begäran. |
| activityIndex | Heltal | Null.<br>Den får inte vara tom. | Aktivitetsindex i den krypterade token. Om activityIndex ligger utanför gränserna för aktiviteten i token eller om null, kommer det att ignoreras. Indexet börjar med 1.<br>Valideringsregler: Bör vara minst ett aktivitetsindex och ska referera till en aktivitet som anges i token. |
| experienceIndex | Heltal | Null. | När det anges väljs en upplevelse per index i aktivitetsdefinitionen. Om den inte anges eller ligger utanför gränserna återgår den till aktivitetens strategi för upplevelseväljare. Index börjar med 1 valideringsregler: Kan vara null eller referera till en upplevelse i aktiviteten. |