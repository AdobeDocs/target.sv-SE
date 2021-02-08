---
keywords: Multivariata tester;felsökning;felsökning;mvt
description: Utforska eventuella utmaningar som du kan ställas inför när du använder multivariata testaktiviteter i Adobe Target, tillsammans med förslag på lösningar.
title: Hur felsöker jag multivariata tester?
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '175'
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

