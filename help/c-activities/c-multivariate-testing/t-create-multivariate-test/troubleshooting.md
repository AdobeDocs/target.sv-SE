---
keywords: Multivariate Tests;troubleshoot;troubleshooting;mvt
description: Det här avsnittet innehåller förslag på hur du löser vissa problem som kan uppstå när du utformar ett MVT-test i Adobe Target.
title: Felsöka multivariata tester
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 0%

---


# Felsöka multivariata tester

Det här avsnittet innehåller förslag på hur du löser vissa problem som kan uppstå när du utformar ett [!UICONTROL Multivariate]-test (MVT) i [!DNL Adobe Target].

* Om du använde [!DNL Analytics]-baserade mätvärden när du redigerade en aktivitet och rapportsviten inte läses in (snurrskärmar), växlar du mätvärdena till [!DNL Target]-mätvärden och växlar sedan igen till [!DNL Analytics]-baserade mätvärden. Rapportsviten bör nu läsas in.
* Om du ändrar ett test som redan körs kan du återställa testet och dess data.

   [!DNL Target] gör att du kan redigera en aktiv aktivitet. Observera att om du redigerar en pågående aktivitet kan testet återställas, vilket innebär att rapporter kanske inte känner igen vissa ändringar.

   Det är säkert att göra små ändringar, till exempel redigera befintlig text eller HTML-erbjudanden.

   De specifika åtgärderna som återställer namn och rapporter för upplevelsen är:

   * Lägga till en ny plats
   * Ta bort en plats
   * Lägga till nya erbjudanden eller ta bort erbjudanden från en befintlig plats

