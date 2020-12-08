---
keywords: qa;server side;server-side;preview;preview links
description: Använd Adobe Target QA-URL:er med leverans på serversidan för att utföra enkel QA för hela aktiviteten med förhandsgranskningslänkar som aldrig ändras, målgruppsanpassning som tillval och QA-rapportering som förblir segmenterad från liveaktivitetsdata.
title: Använd aktivitets-QA med leverans på serversidan
feature: qa
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 0%

---


# Använd aktivitets-QA med leverans på serversidan{#use-activity-qa-with-server-side-delivery}

Använd QA-URL:er med leverans på serversidan för att utföra enkel QA för hela aktiviteten med förhandsgranskningslänkar som aldrig ändras, målgruppsanpassning som tillval och QA-rapportering som förblir segmenterad från live-aktivitetsdata.

Standardimplementeringen av Activity QA har stöd för att skicka `qa_mode` parametrar via `pageUrl` parametrar. Detta är bekvämt för standard-/ajax- [!DNL Target] anrop. För anrop från server till server är detta emellertid inte det bästa sättet för ett Mobile SDK-fall när det inte `pageUrl` är tillgängligt.

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
| token | Krypterad token | Ingen.<br>Den får inte vara tom. | En krypterad entitet som innehåller listan över aktivitets-ID:n som tillåts att köras i Activity QA.<br>Valideringsregler: Bör vara en krypterad token som tillhör klienten som anges i [!DNL Target] begäran. Alla aktiviteter som anges i token ska tillhöra klienten. |
| bypassEntryAudience | Boolean | Falskt | Anger om inmatningsstegsmål för QA-aktiviteter ska utvärderas eller om de ska anses matcha. |
| listedActivitiesOnly | Boolean | Falskt | Anger om QA-aktiviteter ska utföras separat eller om de ska utvärderas som aktiva aktiviteter för den aktuella miljön. |
| evaluateAsTrueAudienceIds | Lista med ID:n | Tom lista. | Lista med målgrupps-ID:n som alltid ska utvärderas som sanna i [!DNL Target] begärans omfattning. |
| evaluateAsFalseAudienceIds | Lista med ID:n | Tom lista. | Lista med målgrupps-ID:n som alltid ska utvärderas som falska i [!DNL Target] begärans omfattning. |
| activityIndex | Heltal | Null.<br>Den får inte vara tom. | Aktivitetsindex i den krypterade token. Om activityIndex ligger utanför gränserna för aktiviteten i token eller om null, kommer det att ignoreras. Indexet börjar med 1.<br>Valideringsregler: Bör vara minst ett aktivitetsindex och ska referera till en aktivitet som anges i token. |
| experienceIndex | Heltal | Null. | När det anges väljs en upplevelse per index i aktivitetsdefinitionen. Om den inte anges eller ligger utanför gränserna återgår den till aktivitetens strategi för upplevelseväljare. Index börjar med 1 valideringsregler: Kan vara null eller referera till en upplevelse i aktiviteten. |