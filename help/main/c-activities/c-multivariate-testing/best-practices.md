---
keywords: mvt;multivariate test;multivariate test best practices;mvt best practices;mvt combinations;mvt reports
description: Lär dig hur du kan förbättra prestanda, undvika problem och korrigera kända fel som kan uppstå när du skapar och kör [!UICONTROL Multivariate Test]-aktiviteter i  [!DNL Adobe Target].
title: Vilka är de bästa metoderna för en [!UICONTROL Multivariate Test]-aktivitet?
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 0%

---

# [!UICONTROL Multivariate Test] bästa praxis

Tips som hjälper dig att förbättra prestanda, undvika problem och korrigera kända fel som kan uppstå när du skapar och kör [!UICONTROL Multivariate Test] (MVT)-aktiviteter i [!DNL Adobe Target].

## Plan {#section_4D4A1F6226F042379BF48DB753608579}

* Observera de platser på sidan som kan ge betydande resultat.

  En banderoll eller en hjältebild kommer till exempel att leda till fler konverteringar än en sidfotsändring. Om du tar med mindre inflytelserika platser i ditt test ökar bara mängden trafik och den tid som krävs för att testa de mer framträdande platserna på sidan.
* Förbered sidvariationerna i förväg.

  Var uppmärksam på skillnaderna i innehåll för varje erbjudande och skapa bilder, text och HTML som du förväntar dig att använda i MVT-testet.

## Skapa {#section_C59C722CA82E48ABA58A4A7FA758F193}

* Inkludera inte fler kombinationer än nödvändigt för testet.

  Varje testad kombination ökar avsevärt den trafik och tid som krävs för att uppnå godtagbara resultat. Om du till exempel har tre platser med tre erbjudanden, finns det 27 möjliga kombinationer (3x3x3). Tre platser, där två platser innehåller tre möjliga erbjudanden och en plats har två erbjudanden, erbjuder 18 alternativ (3x3x2). Antalet ökar avsevärt för varje ytterligare plats och erbjudande.

* Ange platser och erbjudanden.

  Du kan byta namn på varje plats och erbjuda något mer användbart i testet. Antalet erbjudanden på varje plats visas i platshuvudet. Användbara namn hjälper dig att identifiera dina erbjudanden när du undersöker rapporter.

* Använd förhandsgranskningsfunktionerna för att undvika oönskade kombinationer av innehåll.

  Granska alla upplevelser som genererats av testet innan du publicerar det. Se till att det inte finns några kombinationer med motstridiga påståenden (till exempel 20 % rabatt och 19 USD rabatt i samma upplevelse) eller inkompatibla designer som att ha bakgrund och teckensnitt med samma färg.

* Använd [Trafikberäkning](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) för att kontrollera att ditt test är utformat för den mängd trafik som sidan tar emot.

  Se till att Traffic Estimator ger din testkonfiguration grönt ljus så att du kan få önskat resultat.

* Alternativen för varje element bör skilja sig avsevärt från varandra.

## Analysera {#section_9A2118CF1039451681C13D9AE79A58AB}

* Använd [platsbidragsrapporten](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) ofta för att övervaka prestanda för varje plats och erbjudande.
* I [Experience Performance-rapporten](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) kan du basera dina beslut på de data som visas med filtren [!UICONTROL Best 5] och [!UICONTROL Worst 5].

  Filtret [!UICONTROL All] gör det svårt att extrahera den önskade informationen, och alla upplevelser kan inte visas i diagrammet. Använd filtret [!UICONTROL All] om du vill titta på en specifik upplevelse som inte är i de bästa eller värsta fem.

## Följ upp {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* Även om [!DNL Target] tillåter dig att redigera en aktiv aktivitet kan du återställa testet om du redigerar en pågående aktivitet. Rapporterna kanske inte känner igen vissa ändringar. Det är tryggt att ändra erbjudandena på HTML endast i erbjudandebiblioteket.

  Specifika åtgärder som återställer namn och rapporter för upplevelser är:

   * Lägga till en ny plats
   * Ta bort en plats
   * Lägga till nya erbjudanden eller ta bort erbjudanden från en befintlig plats
   * Redigera RTF-erbjudanden
   * Redigera bakgrundsfärger

* Genom att följa ett MVT-test med ett eller flera A/B-tester kan du fastställa vilket innehåll som är bäst för de resultat du vill ha.

  När du har fastställt vilka platser och vilket innehåll som är mest användbart för att du ska kunna uppnå dina mål, kan du köra ett A/B-test för att förfina resultaten ytterligare. Om du till exempel vet vilka platser som är viktigast testar du två specifika bilder mot varandra eller jämför ordalydelsen eller färgerna i en uppmaning.
