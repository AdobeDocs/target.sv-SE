---
keywords: Målgrupper;målkategorier;målförhållanden;målgruppshanterare;anpassade profilparametrar;besökarprofil;anpassade användarparametrar;målregler
description: Lär dig hur du använder kategorier (till exempel webbläsare, geo, nätverk, operativsystem, besökarprofil) för att rikta innehåll.
title: Vilka är kategorierna för målgrupper?
feature: Målgrupper
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---

# Kategorier för målgrupper

Du kan använda [!DNL Adobe Target] som mål för alla olika kategoriattribut. Om du vill skapa målinriktningsregler (eller grupper) för varje attribut drar och släpper du de önskade attributen i målgruppsverktyget .

![Attribut för målgrupper](/help/c-target/c-audiences/assets/attributes.png)

När en viss kategori är markerad kan du använda ett eller flera målinriktningsvillkor. I kategorin Geo definierar du till exempel en regel som City=San Francisco. Om du lägger till flera värden skapas ett OR-villkor. Besökaren behöver bara matcha ett av värdena för att uppfylla målinriktningsvillkoret. Skapa ett anpassat uttrycksmål för AND-villkor på samma parameter.

När du har skapat en regel klickar du på **[!UICONTROL Done]**. En sammanfattning av regeln visas bredvid mållänken för den nivå du har som mål.

Du kan förfina en regel ytterligare genom att lägga till fler villkor eller genom att skapa ytterligare regler i andra kategorier. Du kan till exempel bara rikta dig till Firefox-användare från San Francisco som har öppnat din webbplats från Google. Ställ in kategorin [!UICONTROL Geo] på målanvändare från San Francisco, kategorin [!UICONTROL Browser] på målanvändare som använder Firefox och kategorin [!UICONTROL Traffic Sources] på målanvändare som kommer från [!UICONTROL From Google]. Regler som skapas mellan kategorier kombineras med operatorn AND.

Skapa ett uttrycksmål om du vill skapa komplexa målinriktningsregler som innehåller OR-åtgärder i olika kategorier.

Du kan också ange anpassade profilparametrar och `user.`-parametrar som mål. När du lägger till en målgrupp drar och släpper du **[!UICONTROL Visitor Profile]** och väljer sedan den parameter som du vill använda som mål för aktiviteten. Om den önskade parametern inte visas har parametern inte utlösts av en mbox.

Använd sökrutan för att söka i din [!UICONTROL Audiences]-lista. Du kan söka efter valfri del av ett målgruppsnamn eller omge en viss sträng med citattecken.

Du kan sortera listan [!UICONTROL Audience] efter målgruppsnamn eller efter det datum då den senast ändrades. Om du vill sortera efter namn eller datum klickar du på kolumnrubriken och väljer sedan att visa målgrupper i stigande eller fallande ordning.

## Utbildningsvideo: Skapar publik ![Självstudiekursikon](/help/assets/tutorial.png)

Den här videon innehåller information om hur du använder målgruppskategorier.

* Skapa målgrupper
* Definiera målgruppskategorier

>[!VIDEO](https://video.tv.adobe.com/v/17392)
