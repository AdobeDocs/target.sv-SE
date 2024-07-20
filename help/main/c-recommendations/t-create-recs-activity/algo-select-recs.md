---
keywords: rekommendationer;rekommendationsaktivitet;kriterier;algoritm
description: Lär dig hur du väljer de villkor (regler som avgör vilka produkter eller vilket innehåll som ska rekommenderas) som ska användas i din Recommendations-aktivitet i Adobe [!DNL Target] .
title: Hur väljer jag kriterier för en Recommendations-aktivitet?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: 119227ec-88c3-4de9-b2cf-f7d5fa2e98f6
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

---

# Välj villkor

Välj det [villkor](/help/main/c-recommendations/c-algorithms/algorithms.md) som ska användas i din [!DNL Adobe Target Recommendations]-aktivitet. Kriterier är regler som bestämmer vilka produkter som ska rekommenderas utifrån en fördefinierad uppsättning besökarbeteenden.

Du kan testa flera rekommendationstyper mot varandra genom att lägga till fler än ett villkor.

Om du väljer flera villkor delas trafiken jämnt mellan de valda villkoren. Om du till exempel har valt två villkor och din aktivitet är utformad för att visa standardinnehåll för 20 % av aktivitetsinspelarna, så ser 40 % av aktivitetsinspelarna rekommendationerna som styrs av respektive villkor. Det finns inget alternativ för att ändra procentsatserna för varje villkor.

* Om du vill söka efter ett befintligt villkor (t.ex. om flera kriteriekort visas) skriver du i sökfältet tills det önskade villkoret visas, markerar villkoret och klickar sedan på **[!UICONTROL Done]**.

  Vissa villkor ingår i [!DNL Recommendations]. Du och ditt team kan också skapa egna kriterier.

* Om du vill skapa ett nytt villkor klickar du på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]** och fyller sedan i informationen för det nya villkoret. Mer information om hur du skapar nya villkor finns i [Skapa nya villkor](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Så här väljer du villkor:**

1. När [skapar en ny rekommendation](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F) letar du upp och väljer ett eller flera villkor i dialogrutan **[!UICONTROL Select Criteria]**.

   ![Dialogrutan Välj villkor](/help/main/c-recommendations/t-create-recs-activity/assets/filters.png)

   Du kan använda kryssrutan [!UICONTROL Industry Type], [!UICONTROL Page Type] filter och [!UICONTROL Compatible] för att filtrera listan med villkor. Dessa alternativ hjälper dig att hitta de önskade villkoren.

   * **Branschtyp:** Branschtypen används för att kategorisera [!DNL Recommendations]-villkor. Om du vill ändra branschens standardinställning för lodrät riktning klickar du på **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]** och väljer önskad standardinställning för **[!UICONTROL Industry Vertical]**.
   * **Sidtyp:** Sidtypen hjälper dig att kategorisera dina rekommendationer. Det finns också inbyggda villkor som kan väljas för varje sidtyp.
   * **Kompatibel:** Visa endast de villkor där den valda sidan skickar nödvändiga data. Alla villkor fungerar inte korrekt på alla sidor. Sidan eller mbox måste skickas in `entity.id` eller `entity.categoryId` för att aktuella rekommendationer för objekt/aktuell kategori ska vara kompatibla. I allmänhet är det bäst att bara visa kompatibla villkor. Om du vill att inkompatibla villkor ska vara tillgängliga för aktiviteten avmarkerar du kryssrutan **[!UICONTROL Compatible]**. Det här alternativet kan inaktiveras eller aktiveras i inställningarna: **[!UICONTROL Recommendations]** > **[!UICONTROL Settings]**.

1. Klicka på **[!UICONTROL Next]** för att visa dialogrutan [Välj design](/help/main/c-recommendations/c-design-overview/design-overview.md).
