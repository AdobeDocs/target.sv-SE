---
keywords: mål;kollisioner;konflikter
description: Förhindra att innehåll kolliderar på samma sida genom att konfigurera aktiviteter korrekt i Adobe Target.
title: Hur undviker jag aktivitetskonflikter?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
source-git-commit: 5c963e97dae11326396a5c1c5e32d19f4d463c74
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# Aktivitetskollisioner

Fliken [!UICONTROL Collisions] på sidan [!UICONTROL Activity Overview] i [!DNL Adobe Target] visar aktivitetskonflikter på webbplatsen.

En aktivitetskollision inträffar när flera aktiviteter har konfigurerats för att leverera innehåll till samma sida. Om en aktivitetskonflikt inträffar kanske du inte ser det förväntade innehållet på sidan.

Fliken [!UICONTROL Collisions] är tillgänglig på sidan för aktivitetsöversikt och kan informera dig om din aktivitet innehåller potentiella konflikter.

Du öppnar fliken [!UICONTROL Collisions] genom att klicka på **[!UICONTROL Activities]** > på önskad aktivitet i listan > och sedan klicka på **[!UICONTROL Collisions]** i den vänstra listen.

Alla aktiviteter på samma URL listas, oavsett målgrupp i varje aktivitet. Öppna den här fliken om du vill se en lista över aktiviteter som kan kollidera. Om kollisionen ändrar den förväntade upplevelsen redigerar du aktiviteten.

Listan [!UICONTROL Collisions] hjälper dig att:

* Identifiera om ett test redan körs på en sida innan du skapar en ny aktivitet
* Felsöka en aktivitet om det förväntade innehållet inte visas

Listan [!UICONTROL Collisions] visar alla [!DNL Target]-scenarier där mbox används och där samma URL används. För varje potentiell kollision visas aktivitets-URL:en, namnet på mbox-filen där kollisionen kan inträffa och alla aktiviteter som matchar båda villkoren. Om det finns flera mbox-rutor visas var och en i listan.

I listan visas status och prioritet för varje potentiell kollision, tillsammans med annan information. Du kan använda status och prioritet för att hjälpa dig att avgöra sannolikheten för en kollision. Överväg två aktiviteter som kan kollidera. Om en aktivitet inte är aktiv kan en kollision inte inträffa. En kollision är bara möjlig om den inaktiva aktiviteten blir aktiv. Om den potentiella kollisionen inträffar mellan två aktiva aktiviteter med samma prioritet och samma målgrupp inträffar en kollision. Du kan ändra prioritet eller status för att förhindra kollisionen.

Om målgrupperna är olika finns det fortfarande en potentiell kollision eftersom det är möjligt att en viss besökare kan tillhöra flera målgrupper.
