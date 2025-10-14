---
keywords: A/B;aktivitetsmått;mätvärden;ange mått;målmått;aktivitetsinställningar;framgångsmått;konvertering;intäkt;engagemang
description: Upptäck hur du ställer in mätvärden i en A/B-aktivitet för att avgöra om besöket lyckades, inklusive [!UICONTROL Conversion], [!UICONTROL Revenue] och [!UICONTROL Engagement].
title: Hur ställer jag in målvärden i en A/B-aktivitet?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Ange mått

Använd mätvärden i en [!DNL Adobe Target] A/B-aktivitet för att avgöra när ett besök lyckas.

Mer information om framgångsmått finns i [Framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Välj ett **[!UICONTROL Reporting Settings]** framgångsmått **[!UICONTROL Goals & Settings]** i avsnittet [&#x200B; på sidan &#x200B;](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

   Alternativet [!UICONTROL Select Metrics] visar de framgångsmått som du kan välja för din aktivitet. Resultaten delas in i följande kategorier:

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Du kan använda vilken som helst av de färdiga mätvärdena för framgång eller skapa ett anpassat framgångsmått. Du kan också markera ett framgångsmått som ett primärt mått. Rapporter och Experience Cloud-kort visar som standard det primära måttet, om ett sådant har angetts.

1. Ange inställningarna för mätvärden.

   Vilka inställningar som är tillgängliga beror på vilket framgångsmått du använder.

   Om det här alternativet är aktiverat tillhandahåller fältet [!UICONTROL Estimated Value of the Conversion] (inte tillgängligt för [!UICONTROL Page Score]-måtten) ett värde för ditt mål. Detta värde gör att [!DNL Target] kan beräkna en uppskattad ökning av intäkterna. Det här fältet är valfritt, men inkrementella intäkter för icke-intäktsmått kan inte beräknas utan det. Datatypen är valuta. Det här fältet visas progressivt efter att användaren har indikerat vilken åtgärd som har vidtagits för att uppnå målet. Mer information finns i [Beräknar Lyft i intäkt](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

   Korrekt konfigurering av framgångsmått är avgörande för att du ska kunna få de data du förväntar dig.

   Mer information finns i [Resultatmått](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. (Valfritt) Lägg till ytterligare mått.

När du namnger eller byter namn på ett mätresultat tillåts inte följande tecken:

| Tecken | Beskrivning |
|--- |--- |
| / | Snedstreck |
| ? | Frågetecken |
| # | Nummertecken |
| : | Colon |
| = | Lika med |
| + | Plus |
| - | Minus |
| @ | Vid tecken |
