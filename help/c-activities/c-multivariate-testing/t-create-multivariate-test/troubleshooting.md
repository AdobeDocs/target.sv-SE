---
keywords: Mobile Web Experience Editor
description: Det här avsnittet innehåller förslag på hur du löser vissa problem som kan uppstå när du utformar ett MVT-test.
title: Felsöka multivariata tester
feature: null
subtopic: Mobile Viewports
topic: Standard
uuid: 4de03e03-cbbd-4e8f-a1b9-19ba8b2e6951
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---


# Felsöka multivariata tester{#troubleshoot-multivariate-tests}

Det här avsnittet innehåller förslag på hur du löser vissa problem som kan uppstå när du utformar ett MVT-test.

* När du redigerar en aktivitet, om du använde Analytics-baserade mätvärden och rapportsviten inte läses in (snurra skärmar), växlar du mätvärdena till Target-mätvärden och växlar sedan igen till Analytics-baserade mätvärden. Rapportsviten bör nu läsas in.
* Om du ändrar ett test som redan körs kan du återställa testet och dess data.

   Med Target kan du redigera en aktiv aktivitet. Observera att om du redigerar en pågående aktivitet kan testet återställas, vilket innebär att rapporter kanske inte känner igen vissa ändringar.

   Det är säkert att göra små ändringar, till exempel redigera befintlig text eller HTML-erbjudanden.

   De specifika åtgärderna som återställer namn och rapporter för upplevelsen är:

   * Lägga till en ny plats
   * Ta bort en plats
   * Lägga till nya erbjudanden eller ta bort erbjudanden från en befintlig plats

