---
keywords: Multivariata tester;felsökning;felsökning;mvt
description: Utforska potentiella utmaningar som du kan ställas inför när du använder [!UICONTROL Multivariate Test] MVT-verksamhet [!DNL Adobe Target], tillsammans med förslag på lösningar.
title: Hur felsöker jag en [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Felsökning [!UICONTROL Multivariate Test] verksamhet

Den här artikeln innehåller förslag på hur du löser vissa problem som kan uppstå när du designar en [!UICONTROL Multivariate Test] (MVT) in [!DNL Adobe Target].

* När du redigerar en aktivitet, om du använde [!DNL Analytics]-baserade mätvärden och rapportsviten inte läses in (snurrskärmar), växla mätvärdena till [!DNL Target] mätvärden och växla sedan igen till [!DNL Analytics]-baserat mätresultat. Rapportsviten bör nu läsas in.
* Om du ändrar ett test som redan körs kan du återställa testet och dess data.

  [!DNL Target] gör att du kan redigera en aktiv aktivitet. Om du redigerar en pågående aktivitet kan testet återställas, så rapporter kanske inte känner igen vissa ändringar.

  Det är säkert att göra små ändringar, till exempel redigera befintlig text eller HTML-erbjudanden.

  De specifika åtgärder som återställer namn och rapporter för upplevelsen är bland annat:

   * Lägga till en ny plats
   * Ta bort en plats
   * Lägga till nya erbjudanden eller ta bort erbjudanden från en befintlig plats
