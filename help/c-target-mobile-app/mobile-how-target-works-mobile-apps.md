---
description: Adobe Mobile SDK kontaktar målservern för att få innehållet tillsammans med andra datapunkter för att visa rätt upplevelse för användaren.
title: Hur Target fungerar i mobilappar
feature: mobile implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---


# Hur Target fungerar i mobilappar{#how-target-works-in-mobile-apps}

Adobe Mobile SDK kontaktar målservern för att få innehållet tillsammans med andra datapunkter för att visa rätt upplevelse för användaren.

## Målplatser och framgångsmått {#section_A08AAB0ABA9C4568A5AFD4D27EF1CE74}

En *målplats* kallas också en mbox. En identifierad plats i appen är aktiverad för testning eller personalisering (till exempel välkomstmeddelandet på startskärmen). Dessa platser identifieras när testet skapas.

Ett *[framgångsmått](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)* är en åtgärd som utförs av användaren och som identifierar om en viss aktivitet lyckades (som att registrera sig, göra ett köp, boka en biljett och så vidare).

![](assets/mobile-target-location.png)

* **Målplats:** Innehållet som visas under knappen Registrera.

   Den här användaren erbjuds fri frakt till och med 18.00. Den här platsen kan återanvändas i flera Target-aktiviteter för att köra A/B-tester och personalisering.

* **Resultatmått:** Den åtgärd som utfördes av användaren där användaren trycker på knappen Register.

**Förstå hur Target fungerar i SDK**

![](assets/how-target-mobile-works.png)

