---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Ange manuellt ett eller flera statiska värden som ska filtreras med inkluderingsregler i Adobe Target Recommendations.
title: Filtrera efter statiska värden i inkluderingsregler i Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) - statiskt filter

Ange manuellt ett eller flera statiska värden som ska filtreras med inkluderingsregler i Adobe Target Recommendations.

Rekommendera t.ex. endast innehåll med MPAA-klassificeringen &quot;G&quot; eller &quot;PG&quot;.

Tillgängliga operatorer:

* är lika med
* är inte lika med
* innehåller
* innehåller inte
* börjar med
* slutar med
* värde finns
* värdet finns inte
* är större än eller lika med
* är mindre än eller lika med

>[!NOTE]
>
>Om du känner till hur inkluderingsregler konfigurerades före Target 17.6.1-versionen (juni 2017) kommer du att märka att vissa alternativ och operatorer har ändrats. Endast de operatorer som kan användas för den valda alternativvisningen och vissa operatorer har bytt namn (&quot;match&quot; är nu lika med) för att vara mer konsekventa och intuitiva. Alla befintliga undantagsregler som skapades före den här versionen migrerades automatiskt till den nya strukturen. Ni behöver inte göra någon omstrukturering.

Du kan skapa så många inkluderingsregler som behövs. Inkluderingsreglerna kopplas till en AND-operator. Alla regler måste uppfyllas för att ett objekt ska kunna inkluderas i en rekommendation.