---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Ange manuellt ett eller flera statiska värden som ska filtreras med inkluderingsregler i Adobe Target Recommendations.
title: Filtrera efter statiska värden i inkluderingsregler i Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: f8311dbc91b74977a11dc9b97a70465ab4493b93
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) - statiskt filter

Ange manuellt ett eller flera statiska värden som du vill filtrera med inkluderingsregler i [!DNL Adobe Target] [!DNL Recommendations].

Rekommendera t.ex. endast innehåll med graderingen &quot;G&quot; eller &quot;PG&quot; i Motion Picture Association (MPA).

Du kan skapa så många inkluderingsregler som behövs. Inkluderingsreglerna kopplas till en AND-operator. Alla regler måste uppfyllas för att ett objekt ska kunna inkluderas i en rekommendation.

>[!NOTE]
>
>Om du känner till hur inkluderingsregler konfigurerades före Target 17.6.1-versionen (juni 2017) kommer du att märka att vissa alternativ och operatorer har ändrats. Endast de operatorer som kan användas för den valda alternativvisningen och vissa operatorer har bytt namn (&quot;match&quot; är nu lika med) för att vara mer konsekventa och intuitiva. Alla befintliga undantagsregler som skapades före den här versionen migrerades automatiskt till den nya strukturen. Ni behöver inte göra någon omstrukturering.

## Rekommendera innehåll med klassificering G eller PG

Om du vill skapa en inkluderingsregel med statiska värden för att rekommendera innehåll med MPA-klassificeringen &quot;G&quot; eller &quot;PG&quot; (exkludera innehållet &quot;R&quot; och &quot;NC17&quot;) kan du skapa följande filtreringsregler &quot;filmrankning lika med g-rating&quot; och &quot;filmrankning lika med pg-klassificering&quot;, som visas nedan.

![filmrankningsexempel](/help/c-recommendations/c-algorithms/assets/movies.png)

