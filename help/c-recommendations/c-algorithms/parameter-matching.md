---
keywords: inkluderingsregler;inklusionskriterier;rekommendationer;befordran;kampanjer;dynamisk filtrering;dynamisk;parametermatchning
description: Lär dig hur du filtrerar dynamiskt i Adobe Target Recommendations genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).
title: Hur filtrerar jag efter parametermatchning i Recommendations-aktiviteter?
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# ![Matchning av ](/help/assets/premium.png) PREMIUMParameter

Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).

Rekommendera t.ex. bara innehåll som matchar parametern&quot;branschsida&quot; eller andra parametrar som enhetsdimensioner eller geolokalisering, som i följande exempel.

* Mbox-parametrar för skärmbredd och -höjd kan användas för att rikta sig till mobilbesökare och endast rekommendera mobila enheter och tillbehör.
* Skapa en rekommendationsregel som endast returnerar de mest sålda mobiltelefonerna som matchar eller överskrider skärmhöjden på den mobila enhet som besökaren använder för att visa sidan.
* Regionala geopositioneringsparametrar kan användas för att returnera rekommendationer för verktyg under vintern. Snöblåsare och andra verktyg för att minska snön kan rekommenderas för besökare i områden där det snöar men inte för besökare i områden där det inte snöar.

>[!NOTE]
>
>Om aktiviteten skapades före 31 oktober 2016 misslyckas leveransen om det använder filtret Parametermatchning. Så här undviker du problemet:
>
>* Skapa en ny aktivitet och lägg till dina villkor i den.
>* Använd ett villkor som inte innehåller filtret Parametermatchning.
>* Ta bort filtret &quot;Parametermatchning&quot; från villkoren.


## Exempel på parametermatchning

[!UICONTROL Parameter Matching] I kan du rekommendera innehåll som matchar sidparametrarna eller besökarens parametrar, till exempel enhetsdimensioner eller geolokalisering, som i följande exempel:

[!DNL Recommendations] kan matcha parametervärden som skickas i  [!DNL Target] anropet. I det här fallet upptäcker [!DNL Target] att en besökare använder en mobil enhet, baserat på de parametrar för skärmhöjd och skärmbredd som skickades i [!DNL Target]-anropet, och rekommenderar endast objekt som är mobila enheter.

Titta på följande exempel på Target-anrop:

![Målsamtal](/help/c-recommendations/c-algorithms/assets/example-target-call-2.png)

På sidan som besökaren tittar på ser han eller hon produkter för mobila enheter.

![Produkter för mobila enheter](/help/c-recommendations/c-algorithms/assets/phones.png)
