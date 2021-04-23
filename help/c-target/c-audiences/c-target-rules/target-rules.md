---
keywords: Målgrupper;målkategorier;målförhållanden;målgruppshanterare;anpassade profilparametrar;besökarprofil;anpassade användarparametrar;målregler
description: Lär dig hur du använder kategorier (till exempel webbläsare, geo, nätverk, operativsystem, besökarprofil) för att rikta innehåll.
title: Vilka är kategorierna för målgrupper?
feature: Målgrupper
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---

# Kategorier för målgrupper

Du kan använda en av flera kategorier som mål. Varje kategori fungerar som en flik som gör att du kan skapa målregler (eller grupper) för varje kategori.

När en viss kategori är markerad kan du använda ett eller flera målinriktningsvillkor. I kategorin Geo definierar du till exempel en regel som City=San Francisco. Om du lägger till flera värden skapas ett OR-villkor. Besökaren behöver bara matcha ett av värdena för att uppfylla målinriktningsvillkoret. Skapa ett anpassat uttrycksmål för AND-villkor på samma parameter.

När du har skapat en regel klickar du på **[!UICONTROL Save]**. En sammanfattning av regeln visas bredvid mållänken för den nivå du har som mål.

Du kan förfina en regel ytterligare genom att lägga till fler villkor eller genom att skapa ytterligare regler i andra kategorier. Om du till exempel bara vill rikta sig till Firefox-användare från San Francisco som har öppnat din webbplats från Google anger du kategorin [!UICONTROL Geo] som mål för användare från San Francisco, kategorin [!UICONTROL Visitor Behavior] som Firefox och kategorin [!UICONTROL Traffic Sources] som Google. Alla regler som skapas mellan kategorier kombineras med&quot;AND&quot;. Skapa ett uttrycksmål om du vill skapa komplexa målinriktningsregler som innehåller &quot;OR&quot;-åtgärder i olika kategorier.

Du kan också ange anpassade profilparametrar och `user.`-parametrar som mål. När du lägger till en målgrupp klickar du på **[!UICONTROL Visitor Profile]** och väljer sedan den parameter som du vill använda som mål för aktiviteten. Om den önskade parametern inte visas har parametern inte utlösts av en mbox. Andra anpassade mbox-parametrar är tillgängliga i listrutan [!UICONTROL Custom Parameters].

Använd sökrutan för att söka i din [!UICONTROL Audiences]-lista. Du kan söka efter valfri del av ett målgruppsnamn eller omge en viss sträng med citattecken.

Du kan sortera målgruppslistan efter målgruppsnamn eller efter det datum då den senast ändrades. Om du vill sortera efter namn eller datum klickar du på kolumnrubriken och väljer sedan att visa målgrupper i stigande eller fallande ordning.

## Utbildningsvideo: Skapar publik ![Självstudiekursikon](/help/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
