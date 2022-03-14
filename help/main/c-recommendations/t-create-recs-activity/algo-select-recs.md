---
keywords: rekommendationer;rekommendationsaktivitet;kriterier;algoritm
description: Lär dig hur du väljer de villkor (regler som avgör vilka produkter eller vilket innehåll som ska rekommenderas) som ska användas i Adobe [!DNL Target] Recommendations aktivitet.
title: Hur väljer jag kriterier för en Recommendations-aktivitet?
feature: Recommendations
exl-id: 119227ec-88c3-4de9-b2cf-f7d5fa2e98f6
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 0%

---

# ![PREMIUM](/help/main/assets/premium.png) Välj villkor

Välj [kriterier](/help/main/c-recommendations/c-algorithms/algorithms.md) att använda i [!DNL Adobe Target Recommendations] aktivitet. Kriterier är regler som bestämmer vilka produkter som ska rekommenderas utifrån en fördefinierad uppsättning besökarbeteenden.

Du kan testa flera rekommendationstyper mot varandra genom att lägga till fler än ett villkor.

Om du väljer flera villkor delas trafiken jämnt mellan de valda villkoren. Om du till exempel har valt två villkor och din aktivitet är utformad för att visa standardinnehåll för 20 % av aktivitetsinspelarna, så ser 40 % av aktivitetsinspelarna rekommendationerna som styrs av respektive villkor. Det finns inget alternativ för att ändra procentsatserna för varje villkor.

* Om du vill söka efter ett befintligt villkor (t.ex. om flera kriteriekort visas) skriver du i sökfältet tills det önskade villkoret visas, markerar villkoret och klickar sedan på **[!UICONTROL Done]**.

   Vissa villkor ingår [!DNL Recommendations]. Du och ditt team kan också skapa egna kriterier.

* Om du vill skapa ett nytt villkor klickar du på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]** Fyll sedan i informationen för de nya villkoren. Mer information om hur du skapar nya villkor finns i [Skapa ett nytt villkor](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Så här väljer du villkor:**

1. while [skapa en ny rekommendation](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), i **[!UICONTROL Select Criteria]** letar du upp och väljer ett eller flera villkor.

   ![Välj villkor, dialogruta](/help/main/c-recommendations/t-create-recs-activity/assets/filters.png)

   Du kan använda [!UICONTROL Industry Type] filter, [!UICONTROL Page Type] och [!UICONTROL Compatible] om du vill filtrera listan med villkor. Dessa alternativ hjälper dig att hitta de önskade villkoren.

   * **Branschtyp:** Branschtypen används för att kategorisera [!DNL Recommendations] kriterier. Om du vill ändra branschens standardinställningar lodrätt klickar du **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** och välj önskad standard **[!UICONTROL Industry Vertical]** inställning.
   * **Sidtyp:** Sidtypen hjälper dig att kategorisera dina rekommendationer. Det finns också inbyggda villkor som kan väljas för varje sidtyp.
   * **Kompatibel:** Visa endast de villkor där den valda sidan skickar de data som krävs. Alla villkor fungerar inte korrekt på alla sidor. Sidan eller mbox måste skickas `entity.id` eller `entity.categoryId` för aktuell artikel/aktuella kategorirekommendationer att vara kompatibla. I allmänhet är det bäst att bara visa kompatibla villkor. Om du vill att inkompatibla villkor ska vara tillgängliga för aktiviteten, avmarkerar du **[!UICONTROL Compatible]** kryssruta. Det här alternativet kan inaktiveras eller aktiveras i inställningarna: **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**.

1. Klicka **[!UICONTROL Next]** för att visa [Välj design](/help/main/c-recommendations/c-design-overview/design-overview.md) -dialogrutan.
