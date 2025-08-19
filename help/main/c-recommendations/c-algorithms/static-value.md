---
keywords: inkluderingsregler;inklusionskriterier;rekommendationer;befordran;kampanjer;dynamisk filtrering;statiskt;statiskt filter
description: Lär dig hur du anger ett eller flera statiska värden manuellt för att filtrera med inkluderingsregler i Adobe [!DNL Target] Rekommendationer.
title: Hur filtrerar jag efter statiska värden i rekommenderade aktiviteter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# [!UICONTROL Static Filter]

Ange manuellt ett eller flera statiska värden som ska filtreras med inkluderingsregler i [!DNL Adobe Target Recommendations].

Rekommendera t.ex. endast innehåll med graderingen &quot;G&quot; eller &quot;PG&quot; i Motion Picture Association (MPA).

Du kan skapa så många inkluderingsregler som behövs. Inkluderingsreglerna kopplas till en AND-operator. Alla regler måste uppfyllas för att ett objekt ska kunna inkluderas i en rekommendation.

>[!NOTE]
>
>Om du känner till hur inkluderingsregler konfigurerades före Target 17.6.1-versionen (juni 2017) kommer du att märka att vissa alternativ och operatorer har ändrats. Endast de operatorer som kan användas för den valda alternativvisningen och vissa operatorer har bytt namn (&quot;match&quot; är nu lika med) för att vara mer konsekventa och intuitiva. Alla befintliga undantagsregler som skapades före den här versionen migrerades automatiskt till den nya strukturen. Ni behöver inte göra någon omstrukturering.

## Rekommendera innehåll med klassificering G eller PG

Om du vill skapa en inkluderingsregel med statiska värden för att rekommendera innehåll med MPA-klassificeringen &quot;G&quot; eller &quot;PG&quot; (exkludera innehållet &quot;R&quot; och &quot;NC17&quot;), kan du skapa följande filtreringsregler &quot;filmrankning är lika med något av de graderade&quot; och &quot;filmrankning är lika med något av de graderade&quot;.
