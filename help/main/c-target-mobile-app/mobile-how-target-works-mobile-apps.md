---
description: Lär dig hur du använder Adobe Mobile SDK för att visa upp de optimala upplevelserna för era mobilappsbesökare.
title: Hur [!DNL Target] Arbeta i mobilappar?
feature: Implement Mobile
role: Developer
exl-id: 1a5f34dc-932d-47c7-b730-6d1658343fb4
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Hur [!DNL Target] fungerar i mobilappar

Adobe Mobile SDK kontaktar målservern för att få innehållet tillsammans med andra datapunkter för att visa rätt upplevelse för användaren.

## Målplatser och framgångsmått {#section_A08AAB0ABA9C4568A5AFD4D27EF1CE74}

A *målplats* kallas också en mbox. En identifierad plats i appen är aktiverad för testning eller personalisering (till exempel välkomstmeddelandet på startskärmen). Dessa platser identifieras när testet skapas.

A *[framgångsmått](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)* är en åtgärd som utförs av användaren och som identifierar om en viss aktivitet lyckades (som att registrera sig, göra ett köp, boka en biljett och så vidare).

![](assets/mobile-target-location.png)

* **Målplats:** Innehållet som visas under registreringsknappen.

   Den här användaren erbjuds fri frakt till och med 18.00. Den här platsen kan återanvändas i flera Target-aktiviteter för att köra A/B-tester och personalisering.

* **Resultatmått:** Den åtgärd som utförs av användaren där användaren trycker på knappen Register.

**Förstå hur Target fungerar i SDK**

![](assets/how-target-mobile-works.png)
