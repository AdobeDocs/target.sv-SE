---
keywords: multivariat;mvt;metrics;set metrics;target metric;activity settings;success metric;conversion;revenue;engagement
description: Lär dig hur du anger mått i en  [!DNL Adobe Target] [!UICONTROL Multivariate Test]-aktivitet för att avgöra när ett besök lyckas, till exempel [!UICONTROL Conversion], [!UICONTROL Revenue] och [!UICONTROL Engagement].
title: Hur ställer jag in målvärden i en [!UICONTROL Multivariate Test]-aktivitet (MVT)?
feature: Multivariate Tests
hide: true
hidefromtoc: true
source-git-commit: 4805da617962e29794bd3af16138f3887ad250d0
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Ange mått för en [!UICONTROL Multivariate Test]-aktivitet

Använd mätvärden i en [!DNL Adobe Target] [!UICONTROL Multivariate Test] för att avgöra när ett besök lyckas.

Mer information om framgångsmått finns i [Framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Ange aktivitetens mål.
1. Välj ett [framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Ange måttlista](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list-new.png)

   På sidan [!UICONTROL Select Metrics] visas de framgångsmått som du kan välja för din aktivitet. Resultaten delas in i följande kategorier:

   * [!UICONTROL Conversion]
   * [!UICONTROL Revenue]
   * [!UICONTROL Engagement]

   Du kan använda vilken som helst av de färdiga mätvärdena för framgång eller skapa ett anpassat framgångsmått. Du kan också markera ett framgångsmått som ett primärt mått. Rapporter och Experience Cloud-kort visar som standard det primära måttet, om ett sådant har angetts.

1. Ange inställningarna för mätvärden.

   Vilka inställningar som är tillgängliga beror på vilket framgångsmått du använder.

   Om det här alternativet är aktiverat tillhandahåller fältet [!UICONTROL Estimated Value of the Conversion] (inte tillgängligt för [!UICONTROL Page Score]-måtten) ett värde för ditt mål. Detta värde gör att [!DNL Target] kan beräkna en uppskattad ökning av intäkterna. Det här fältet är valfritt, men inkrementella intäkter för icke-intäktsmått kan inte beräknas utan det. Datatypen är valuta. Det här fältet visas progressivt efter att användaren har indikerat vilken åtgärd som har vidtagits för att uppnå målet. Mer information finns i [Beräknar Lyft i intäkt](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

   Korrekt konfigurering av framgångsmått är avgörande för att ni ska få de data ni förväntar er.

   Mer information finns i [Resultatmått](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

1. (Valfritt) Lägg till ytterligare mått.
1. Klicka på **[!UICONTROL Save and Close]** när du är klar med att ange mätvärden.

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

## Utbildningsvideo: Aktivitetsmått (7:43) ![Självstudiekursens badge](/help/main/assets/tutorial.png)

Den här videon innehåller information om hur du arbetar med framgångsmått.

* Förstå målvärden
* Förstå och skapa [!UICONTROL Conversion]-, [!UICONTROL Revenue]- och [!UICONTROL Engagement]-mått
* Bygg ett klickspårningsmått

>[!VIDEO](https://video.tv.adobe.com/v/17380)
