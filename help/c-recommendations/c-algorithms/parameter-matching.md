---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;parameter matching
description: Filtrera dynamiskt i Adobe Target Recommendations genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).
title: Filtrera efter parametermatchning i dynamiska inkluderingsregler i Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---


# ![Matchning av PREMIUM](/help/assets/premium.png) -parameter

Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).

Rekommendera t.ex. bara innehåll som matchar parametern&quot;branschsida&quot; eller andra parametrar som enhetsdimensioner eller geolokalisering, som i följande exempel.

* Mbox-parametrar för skärmbredd och -höjd kan användas för att rikta sig till mobilbesökare och endast rekommendera mobila enheter och tillbehör.
* Regionala geopositioneringsparametrar kan användas för att returnera rekommendationer för verktyg under vintern. Snöblåsare och andra verktyg för att minska snön kan rekommenderas för besökare i områden där det snöar men inte för besökare i områden där det inte snöar.

>[!NOTE]
>
>Om aktiviteten skapades före 31 oktober 2016 misslyckas leveransen om det använder filtret Parametermatchning. Så här undviker du problemet:
>
>* Skapa en ny aktivitet och lägg till dina villkor i den.
>* Använd ett villkor som inte innehåller filtret Parametermatchning.
>* Ta bort filtret &quot;Parametermatchning&quot; från villkoren.


Tillgängliga operatorer:

* är lika med
* är inte lika med
* innehåller
* innehåller inte
* börjar med
* slutar med
* är större än eller lika med
* är mindre än eller lika med
* är mellan