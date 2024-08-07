---
keywords: Mål;rapporter;rapportinställningar;extrema order;extrema värden
description: Lär dig hur du exkluderar extrema värden från att påverka rapporter i Adobe [!DNL Target] så att några ovanliga order inte påverkar dina aktivitetsresultat.
title: Hur utesluter jag extrema värden i rapporter?
feature: Reports
exl-id: fd2d0c18-62c0-41e0-800c-b2ae123f0e74
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Exkludera extrema värden

Du kan utesluta extrema värden från att påverka rapporter i [!DNL Adobe Target] så att några ovanliga order inte påverkar aktivitetsresultaten. Ett exempel på en ovanlig beställning kan vara en coach som köper uniformer för ett helt team i stället för att köpa individuella uniformer åt enskilda köpare.

>[!NOTE]
>
>Flaggan [!UICONTROL Exclude Extreme Values] gäller endast för aktiviteter med måtttyperna [!UICONTROL Revenue] och [!UICONTROL Engagement].

Extrema värden flaggas automatiskt baserat på reglerna som beskrivs nedan. Du kan växla mellan att se och utesluta extrema värden från dina rapporter. En aktivitet kommer att ha sina extrema värden uteslöts efter att aktiviteten har körts i en timme eller efter 15 order, beroende på vilket som inträffar först.

Ett värde anses vara extrem om det är mer än +/- 3 standardavvikelser från det genomsnittliga ordervärdet med hjälp av den sista månaden med data (fram till den tidpunkt då beräkningen gjordes).

Filtret för det extrema värdet är till exempel ofta användbart när RPV används. RPV kombinerar konverteringsgrad och genomsnittligt ordervärde och exponerar ofta volatiliteten i dessa värden. Om du använder RPV och fastställer att order inte verkar distribueras normalt, kan du se mer normala resultat om du använder filtret för extrem ordning.

När ett värde är markerat som extremt ersätts dess ordervärde med det genomsnittliga ordervärdet för upplevelsen den senaste månaden, exklusive extremvärdena. Ordern markeras också som extrem i [!UICONTROL Order Details]-rapporten och i CSV-nedladdningen för dagliga resultat.

**Så här exkluderar du extrema värden från dina rapporter:**

1. Öppna en aktivitet som innehåller mättyper för Intäkter eller engagemang och klicka sedan på fliken **[!UICONTROL Reports]**.
1. Klicka på kugghjulsikonen för att visa dialogrutan **[!UICONTROL Settings]**.

   ![Stegresultat](assets/exclude_extreme_values.png)

1. Dra **[!UICONTROL Exclude Extreme Values]**-växeln till läget&quot;på&quot; eller&quot;av&quot; efter behov.
1. Klicka på **[!UICONTROL Save]**.
