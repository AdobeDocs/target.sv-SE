---
keywords: multivariat;mvt;metrics;set metrics;target metric;activity settings;success metric;conversion;revenue;engagement
description: Lär dig hur du anger mätvärden i en [!DNL Adobe Target] [!UICONTROL Multivariate Test] aktivitet för att avgöra när ett besök är lyckat, t.ex. [!UICONTROL Conversion], [!UICONTROL Revenue]och [!UICONTROL Engagement].
title: Hur ställer jag in målvärden i en [!UICONTROL Multivariate Test] Aktivitet?
feature: Multivariate Tests
exl-id: 8530b3f1-5daa-4a03-a482-93b10eb23208
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---

# Ange mått för en [!UICONTROL Multivariate Test] aktivitet

Använd mätvärden i en [!DNL Adobe Target] [!UICONTROL Multivariate Test] för att avgöra när ett besök är lyckat.

Detaljerad information om framgångsmått finns på [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Ange aktivitetens mål.
1. Välj en [framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Ange måttlista](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list.png)

   The [!UICONTROL Select Metrics] visas de framgångsmått du kan välja för din aktivitet. Resultaten delas in i följande kategorier:

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Du kan använda vilken som helst av de färdiga mätvärdena för framgång eller skapa ett anpassat framgångsmått. Du kan också markera ett framgångsmått som ett primärt mått. Rapporter och Experience Cloud-kort visar som standard det primära måttet, om ett sådant har angetts.

1. Ange inställningarna för mätvärden.

   Vilka inställningar som är tillgängliga beror på vilket framgångsmått du använder.

   Om den är aktiverad visas [!UICONTROL Estimated Value of the Conversion] fält (ej tillgängligt för [!UICONTROL Page Score] mätvärden) ger ett värde för ditt mål. Detta värde aktiverar [!DNL Target] att beräkna en uppskattad ökning av intäkterna. Det här fältet är valfritt, men inkrementella intäkter för icke-intäktsmått kan inte beräknas utan det. Datatypen är valuta. Det här fältet visas progressivt efter att användaren har indikerat vilken åtgärd som har vidtagits för att uppnå målet. Se [Uppskattar Lyft i intäkt](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) för mer information.

   Korrekt konfigurering av framgångsmått är avgörande för att ni ska få de data ni förväntar er.

   Mer information finns i [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

1. (Valfritt) Lägg till ytterligare mått.
1. Klicka **[!UICONTROL Continue]** när du är klar med att ställa in mätvärden.

När du namnger eller byter namn på ett mätresultat tillåts inte följande tecken:

| Tecken | Beskrivning |
|--- |--- |
| `/` | Snedstreck |
| `?` | Frågetecken |
| `#` | Nummertecken |
| `:` | Colon |
| `=` | Lika med |
| `+` | Plus |
| `-` | Minus |
| `@` | Vid tecken |

## Utbildningsvideo: aktivitetsstatistik (7:43) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller information om hur du arbetar med framgångsmått.

* Förstå målvärden
* Förstå och bygga [!UICONTROL Conversion], [!UICONTROL Revenue]och [!UICONTROL Engagement] mått
* Bygg ett klickspårningsmått

>[!VIDEO](https://video.tv.adobe.com/v/17380)
