---
keywords: multivariat;mvt;metrics;set metrics;target metric;activity settings;success metric;conversion;revenue;engagement
description: Lär dig hur du anger mätvärden i en Adobe [!DNL Target] Multivariera testaktivitet för att avgöra när ett besök lyckas, t.ex. konvertering, intäkter och engagemang.
title: Hur ställer jag in målvärden i en multivariat testaktivitet (MVT)?
feature: Multivariate Tests
exl-id: 8530b3f1-5daa-4a03-a482-93b10eb23208
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# Ange mått för multivariata tester

Använd mätvärden i ett Adobe Target Multivariate-test för att avgöra när ett besök lyckas.

Detaljerad information om framgångsmått finns på [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Ange aktivitetens mål.
1. Välj en [framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Ange måttlista](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list.png)

   The [!UICONTROL Select Metrics] visas de framgångsmått du kan välja för din aktivitet. Resultaten delas in i följande kategorier:

   * Konvertering
   * Intäkter
   * Engagemang

   Du kan använda vilken som helst av de färdiga mätvärdena för framgång eller skapa ett anpassat framgångsmått. Du kan också markera ett framgångsmått som ett primärt mått. Rapporter och Experience Cloud-kort visar som standard det primära måttet, om ett sådant har angetts.
1. Ange inställningarna för mätvärden.

   Vilka inställningar som är tillgängliga beror på vilket framgångsmått du använder.

   Om den är aktiverad visas [!UICONTROL Estimated Value of the Conversion]fältet (inte tillgängligt för Page Score-värden) ger ett värde för ditt mål. Detta värde gör att Target kan beräkna en uppskattad ökning av intäkterna. Detta fält är valfritt; Inkrementella intäkter för icke-intäktsmått kan dock inte beräknas utan detta. Datatypen är valuta. Det här fältet visas progressivt efter att användaren har indikerat vilken åtgärd som har vidtagits för att uppnå målet. Se [Uppskattar Lyft i intäkt](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) för mer information.

   Korrekt konfigurering av framgångsmått är avgörande för att ni ska få de data ni förväntar er.

   Mer information finns i [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)
1. (Valfritt) Lägg till ytterligare mått.
1. Klicka **[!UICONTROL Continue]** när du är klar med att ställa in mätvärden.
Observera att följande tecken inte tillåts när du namnger eller byter namn på ett mätresultat:

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

## Utbildningsvideo: Aktivitetsmått (7:43) ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller information om hur du arbetar med framgångsmått.

* Förstå målvärden
* Förstå och bygga mått för konvertering, intäkter och engagemang
* Bygg ett klickspårningsmått

>[!VIDEO](https://video.tv.adobe.com/v/17380)
