---
keywords: Multivariata tester;felsökning;felsökning;mvt
description: Utforska eventuella utmaningar som du kan ställas inför när du använder multivariata testaktiviteter i Adobe Target, tillsammans med förslag på lösningar.
title: Hur felsöker jag multivariata tester?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# Felsöka multivariata tester

Det här avsnittet innehåller förslag på hur du löser vissa problem som kan uppstå när du designar ett [!UICONTROL Multivariate] (MVT) test in [!DNL Adobe Target].

* När du redigerar en aktivitet, om du använde [!DNL Analytics]-baserade mätvärden och rapportsviten inte läses in (snurrskärmar), växla mätvärdena till [!DNL Target] mätvärden och växla sedan igen till [!DNL Analytics]-baserat mätresultat. Rapportsviten bör nu läsas in.
* Om du ändrar ett test som redan körs kan du återställa testet och dess data.

   [!DNL Target] gör att du kan redigera en aktiv aktivitet. Observera att om du redigerar en pågående aktivitet kan testet återställas, vilket innebär att rapporter kanske inte känner igen vissa ändringar.

   Det är säkert att göra små ändringar, till exempel redigera befintlig text eller HTML-erbjudanden.

   De specifika åtgärderna som återställer namn och rapporter för upplevelsen är:

   * Lägga till en ny plats
   * Ta bort en plats
   * Lägga till nya erbjudanden eller ta bort erbjudanden från en befintlig plats
