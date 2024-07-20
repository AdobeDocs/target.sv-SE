---
keywords: Multivariata tester;felsökning;felsökning;mvt
description: Utforska potentiella utmaningar som du kan ställas inför när du använder [!UICONTROL Multivariate Test] (MVT)-aktiviteter i  [!DNL Adobe Target], tillsammans med förslag på lösningar.
title: Hur felsöker jag en [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Felsöka [!UICONTROL Multivariate Test] aktiviteter

Den här artikeln innehåller förslag på hur du löser vissa problem som kan uppstå när du designar en [!UICONTROL Multivariate Test] (MVT) i [!DNL Adobe Target].

* Om du använde [!DNL Analytics]-baserade mätvärden när du redigerade en aktivitet och rapportsviten inte läses in (snurrskärmar), växlar du måtten till [!DNL Target] och växlar sedan igen till [!DNL Analytics]-baserade mätvärden. Rapportsviten bör nu läsas in.
* Om du ändrar ett test som redan körs kan du återställa testet och dess data.

  Med [!DNL Target] kan du redigera en aktiv aktivitet. Om du redigerar en pågående aktivitet kan testet återställas, så rapporter kanske inte känner igen vissa ändringar.

  Det är säkert att göra små ändringar, till exempel redigera befintlig text eller HTML-erbjudanden.

  De specifika åtgärder som återställer namn och rapporter för upplevelsen är bland annat:

   * Lägga till en ny plats
   * Ta bort en plats
   * Lägga till nya erbjudanden eller ta bort erbjudanden från en befintlig plats
