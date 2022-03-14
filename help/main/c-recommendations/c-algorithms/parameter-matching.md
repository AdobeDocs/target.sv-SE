---
keywords: inkluderingsregler;inklusionskriterier;rekommendationer;befordran;kampanjer;dynamisk filtrering;dynamisk;parametermatchning
description: Lär dig filtrera dynamiskt i Adobe [!DNL Target] Recommendations genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).
title: Hur filtrerar jag efter parametermatchning i Recommendations-aktiviteter?
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Parametermatchning

Filtrera dynamiskt genom att jämföra objekt (entiteter) med ett värde i begäran (API eller mbox).

Rekommendera t.ex. bara innehåll som matchar parametern&quot;branschsida&quot; eller andra parametrar som enhetsdimensioner eller geolokalisering, som i följande exempel.

* Mbox-parametrar för skärmbredd och -höjd kan användas för att rikta sig till mobilbesökare och bara rekommendera mobila enheter och tillbehör.
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

[!DNL Recommendations] kan matcha parametervärden som skickas i [!DNL Target] ring. I det här fallet [!DNL Target] identifierar att en besökare använder en mobil enhet, baserat på de parametrar för skärmhöjd och -bredd som skickas i [!DNL Target] ringa och rekommenderar endast objekt som är mobila enheter.

Titta på följande exempel på Target-anrop:

![Målsamtal](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

På sidan som besökaren tittar på ser han eller hon produkter för mobila enheter.

![Produkter för mobila enheter](/help/main/c-recommendations/c-algorithms/assets/phones.png)
