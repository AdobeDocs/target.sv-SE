---
keywords: A/B;aktivitetsmått;mätvärden;ange mått;målmått;aktivitetsinställningar;framgångsmått;konvertering;intäkt;engagemang
description: Lär dig hur du anger mätvärden i en [!DNL Adobe Target] A/B-aktivitet som avgör när ett besök lyckas, t.ex. [!UICONTROL Conversion], [!UICONTROL Revenue]och [!UICONTROL Engagement].
title: Hur ställer jag in målvärden i en A/B-aktivitet?
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
source-git-commit: 2d5272a852dc879e7307695744b70afe7fee9a38
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---

# Ange mått

Använd mätvärden i en [!DNL Adobe Target] A/B-aktivitet som avgör när ett besök lyckas.

Detaljerad information om framgångsmått finns på [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. I **[!UICONTROL Reporting Settings]** i **[!UICONTROL Goals & Settings]** sida väljer du en [framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Välj framgångsmått](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_metrics-new.png)

   The [!UICONTROL Select Metrics] finns en lista med framgångsmått som du kan välja för din aktivitet. Resultaten delas in i följande kategorier:

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Du kan använda vilken som helst av de färdiga mätvärdena för framgång eller skapa ett anpassat framgångsmått. Du kan också markera ett framgångsmått som ett primärt mått. Rapporter och Experience Cloud-kort visar som standard det primära måttet, om ett sådant har angetts.

1. Ange inställningarna för mätvärden.

   Vilka inställningar som är tillgängliga beror på vilket framgångsmått du använder.

   Om den är aktiverad visas [!UICONTROL Estimated Value of the Conversion] fält (ej tillgängligt för [!UICONTROL Page Score] mätvärden) ger ett värde för ditt mål. Detta värde aktiverar [!DNL Target] att beräkna en uppskattad ökning av intäkterna. Det här fältet är valfritt, men inkrementella intäkter för icke-intäktsmått kan inte beräknas utan det. Datatypen är valuta. Det här fältet visas progressivt efter att användaren har indikerat vilken åtgärd som har vidtagits för att uppnå målet. Se [Uppskattar Lyft i intäkt](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) för mer information.

   Korrekt konfigurering av framgångsmått är avgörande för att du ska kunna få de data du förväntar dig.

   Mer information finns i [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

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

## Utbildningsvideo: aktivitetsstatistik (7:43) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller information om hur du arbetar med framgångsmått.

* Förstå målvärden
* Förstå och bygga mått för konvertering, intäkter och engagemang
* Bygg ett klickspårningsmått

>[!VIDEO](https://video.tv.adobe.com/v/17380)
