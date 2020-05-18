---
keywords: A/B;activity metrics;metrics;set metrics;goal metric;activity settings;success metric;conversion;revenue;engagement
description: Använd mätvärden i en A/B-aktivitet för att avgöra när ett besök lyckas.
title: Ange mått
solution: Target,standard
uuid: 57f84da4-10f9-42f3-b9ce-06cf41007157
translation-type: tm+mt
source-git-commit: fdf75402a0283c3189952fb74997d4ab536d5098
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---


# Ange mått{#set-metrics}

Använd mätvärden i en A/B-aktivitet för att avgöra när ett besök lyckas.

Mer information om framgångsmått finns i [Success Metrics](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Ange aktivitetens mål.
1. Välj ett [framgångsmått](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Välj framgångsmått](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_metrics-new.png)

   På [!UICONTROL Select Metrics] sidan visas de framgångsmått du kan välja för din aktivitet. Resultaten delas in i följande kategorier:

   * Konvertering
   * Intäkter
   * Engagemang
   Du kan använda vilken som helst av de färdiga mätvärdena för framgång eller skapa ett anpassat framgångsmått. Du kan också markera ett framgångsmått som ett primärt mått. Rapporter och Experience Cloud-kort visar som standard det primära måttet, om ett sådant har angetts.
1. Ange inställningarna för mätvärden.

   Vilka inställningar som är tillgängliga beror på vilket framgångsmått du använder.

   Om det här alternativet är aktiverat ger [!UICONTROL Estimated Value of the Conversion]fältet (inte tillgängligt för sidbakgrundsmätningar) ett värde för ditt mål. Detta värde gör att Target kan beräkna en uppskattad ökning av intäkterna. Detta fält är valfritt; Inkrementella intäkter för icke-intäktsmått kan dock inte beräknas utan detta. Datatypen är valuta. Det här fältet visas progressivt efter att användaren har indikerat vilken åtgärd som har vidtagits för att uppnå målet. Mer information finns i [Beräkna Lyft i intäkter](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) .

   Korrekt konfigurering av framgångsmått är avgörande för att ni ska få de data ni förväntar er.

   Mer information finns i [Success Metrics](../../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).
1. (Valfritt) Lägg till ytterligare mått.
1. Klicka **[!UICONTROL Continue]** när du är klar med mätvärdena.

Observera att följande tecken inte tillåts när du namnger eller byter namn på ett mätresultat:

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

## Utbildningsvideo: Aktivitetsmått (7:43) ![Självstudiekursidentitet](/help/assets/tutorial.png)

Den här videon innehåller information om hur du arbetar med framgångsmått.

* Förstå målvärden
* Förstå och bygga mått för konvertering, intäkter och engagemang
* Bygg ett klickspårningsmått

>[!VIDEO](https://video.tv.adobe.com/v/17380)
