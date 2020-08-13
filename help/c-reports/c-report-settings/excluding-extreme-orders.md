---
keywords: Target;reports;report settings;extreme orders;extreme values
description: Du kan utesluta extrema värden från att påverka rapporter i Adobe Target så att några ovanliga order inte påverkar aktivitetsresultaten. Ett exempel på en ovanlig beställning kan vara en coach som köper uniformer för ett helt team i stället för att köpa individuella uniformer åt enskilda köpare.
title: Exkludera extrema värden i Adobe Target-rapporter
feature: report settings
uuid: bb151b54-09ef-40b5-bc04-95c61b761f5a
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---


# Exkludera extrema värden{#exclude-extreme-values}

Du kan utesluta extrema värden från att påverka rapporter så att några ovanliga order inte påverkar aktivitetsresultaten. Ett exempel på en ovanlig beställning kan vara en coach som köper uniformer för ett helt team i stället för att köpa individuella uniformer åt enskilda köpare.

>[!NOTE]
>
>Flaggan [!UICONTROL Exclude Extreme Values] gäller endast för aktiviteter med måtten Intäkter och engagemang.

Extrema värden flaggas automatiskt baserat på reglerna som beskrivs nedan. Du kan växla mellan att se och utesluta extrema värden från dina rapporter. En aktivitet kommer att ha sina extrema värden uteslöts efter att aktiviteten har körts i en timme eller efter 15 order, beroende på vilket som inträffar först.

Ett värde anses vara extrem om det är mer än +/- 3 standardavvikelser från det genomsnittliga ordervärdet med hjälp av den sista månaden med data (fram till den tidpunkt då beräkningen gjordes).

Filtret för det extrema värdet är till exempel ofta användbart när RPV används. RPV kombinerar konverteringsgrad och genomsnittligt ordervärde och exponerar ofta volatiliteten i dessa värden. Om du använder RPV och fastställer att order inte verkar distribueras normalt, kan du se mer normala resultat om du använder filtret för extrem ordning.

När ett värde är markerat som extremt ersätts dess ordervärde med det genomsnittliga ordervärdet för upplevelsen den senaste månaden, exklusive extremvärdena. Ordern markeras också som extrem i rapporten Orderdetaljer och i CSV-nedladdningen för dagliga resultat.

**Exkludera extrema värden från rapporter:**

1. Öppna en aktivitet som innehåller mättyper för Intäkter eller engagemang och klicka sedan på **[!UICONTROL Reports]** fliken.
1. Klicka på kugghjulsikonen.

   ![Rapportinställningar](/help/c-reports/c-report-settings/assets/report-settings-gear-icon.png)

   Dialogrutan [!UICONTROL Report Settings] Alternativ visas.

   ![Stegresultat](assets/exclude_extreme_values.png)

1. Aktivera eller inaktivera alternativet **[!UICONTROL Exclude Extreme Values]** .
1. Klicka på **[!UICONTROL Save]**.
