---
keywords: recommendations;recommendations activity;criteria
description: Välj de kriterier som ska användas i din Adobe Target Recommendations-aktivitet.
title: Välj villkor
feature: null
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Select-villkor{#select-criteria}

Välj [villkor](/help/c-recommendations/c-algorithms/algorithms.md) som ska användas i din Recommendations-aktivitet. Kriterier är regler som bestämmer vilka produkter som ska rekommenderas utifrån en fördefinierad uppsättning besökarbeteenden.

Du kan testa flera rekommendationstyper mot varandra genom att lägga till fler än ett villkor.

Om du väljer flera villkor delas trafiken jämnt mellan de valda villkoren. Om du till exempel har valt två villkor och din aktivitet är utformad för att visa standardinnehåll för 20 % av aktivitetsinspelarna, så ser 40 % av aktivitetsinspelarna rekommendationerna som styrs av respektive villkor. Det finns inget alternativ för att ändra procentsatserna för varje villkor.

* Om du vill söka efter ett befintligt villkor (t.ex. om flera kriteriekort visas) skriver du i sökfältet tills det önskade villkoret visas, markerar villkoret och klickar sedan på **[!UICONTROL Done]**.

   Vissa villkor ingår [!DNL Recommendations]. Du och ditt team kan också skapa egna kriterier.

* Om du vill skapa ett nytt villkor klickar du på **[!UICONTROL Create Criteria]** och fyller sedan i informationen för det nya villkoret. Mer information om hur du skapar nya villkor finns i [Skapa nya villkor](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Så här väljer du villkor:**

1. När du [skapar en ny rekommendation](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)letar du reda på och väljer ett eller flera villkor i **[!UICONTROL Criteria]** dialogrutan.

   ![Välj villkor, dialogruta](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   Du kan använda [!UICONTROL Industry Type] filtret, [!UICONTROL Page Type] filtret och [!UICONTROL Compatible] kryssrutan för att filtrera listan med villkor. Dessa alternativ hjälper dig att hitta de önskade villkoren.

   * **Branschtyp:** Branschtypen används för att kategorisera [!DNL Recommendations] kriterier. Om du vill ändra branschens standardinställningar i lodrät riktning klickar du på **[!UICONTROL Settings]** och väljer önskad **[!UICONTROL Industry Vertical]** standardinställning.
   * **Sidtyp:** Sidtypen hjälper dig att kategorisera dina rekommendationer. Det finns också inbyggda villkor som kan väljas för varje sidtyp.
   * **Kompatibel:** Visa endast de villkor där den valda sidan skickar de data som krävs. Alla villkor fungerar inte korrekt på alla sidor. Sidan eller mbox måste skickas `entity.id` eller `entity.categoryId` för att aktuella artikel/aktuella kategorirekommendationer ska vara kompatibla. I allmänhet är det bäst att bara visa kompatibla villkor. Om du vill att inkompatibla villkor ska vara tillgängliga för aktiviteten avmarkerar du **[!UICONTROL Compatible]** kryssrutan. Det här alternativet kan inaktiveras eller aktiveras i din dator [!DNL Target] [!UICONTROL Preferences].

1. Klicka **[!UICONTROL Next]** för att visa dialogrutan [Välj design](/help/c-recommendations/c-design-overview/design-overview.md) .
