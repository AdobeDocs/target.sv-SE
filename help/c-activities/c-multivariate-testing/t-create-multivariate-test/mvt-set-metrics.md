---
keywords: multivariate;mvt;metrics;set metrics;goal metric;activity settings;success metric;conversion;revenue;engagement
description: Använd mätvärden i ett Adobe Target Multivariate-test för att avgöra när ett besök lyckas.
title: Ange mått
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---


# Ange mått för multivariata tester

Använd mätvärden i ett Adobe Target Multivariate-test för att avgöra när ett besök lyckas.

Detaljerad information om framgångsmått finns i [Success Metrics](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

1. Ange aktivitetens mål.
1. Välj ett [framgångsmått](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)

   ![Ange måttlista](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_metrics-list.png)

   På sidan [!UICONTROL Select Metrics] visas de framgångsmått du kan välja för din aktivitet. Resultaten delas in i följande kategorier:

   * Konvertering
   * Intäkter
   * Engagemang

   Du kan använda vilken som helst av de färdiga mätvärdena för framgång eller skapa ett anpassat framgångsmått. Du kan också markera ett framgångsmått som ett primärt mått. Rapporter och Experience Cloud-kort visar som standard det primära måttet, om ett sådant har angetts.
1. Ange inställningarna för mätvärden.

   Vilka inställningar som är tillgängliga beror på vilket framgångsmått du använder.

   Om det här alternativet är aktiverat ger fältet [!UICONTROL Estimated Value of the Conversion]ett värde (inte tillgängligt för Page Score-mätvärden) för ditt mål. Detta värde gör att Target kan beräkna en uppskattad ökning av intäkterna. Detta fält är valfritt; Inkrementella intäkter för icke-intäktsmått kan dock inte beräknas utan detta. Datatypen är valuta. Det här fältet visas progressivt efter att användaren har indikerat vilken åtgärd som har vidtagits för att uppnå målet. Mer information finns i [Beräkna Lyft i intäkt](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

   Korrekt konfigurering av framgångsmått är avgörande för att ni ska få de data ni förväntar er.

   Mer information finns i [Success Metrics](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)
1. (Valfritt) Lägg till ytterligare mått.
1. Klicka på **[!UICONTROL Continue]** när du är klar med att ange mätvärden.
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

## Utbildningsvideo: Aktivitetsmått (7:43) ![Tutorial badge](/help/assets/tutorial.png)

Den här videon innehåller information om hur du arbetar med framgångsmått.

* Förstå målvärden
* Förstå och bygga mått för konvertering, intäkter och engagemang
* Bygg ett klickspårningsmått

>[!VIDEO](https://video.tv.adobe.com/v/17380)
