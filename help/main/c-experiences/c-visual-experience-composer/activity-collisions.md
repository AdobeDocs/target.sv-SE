---
keywords: mål;kollisioner;konflikter
description: Konflikter inträffar när flera aktiviteter har konfigurerats för att leverera innehåll till samma sida. Lär dig hur du undviker kollisioner när du använder Adobe Target.
title: Hur undviker jag aktivitetskonflikter?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
source-git-commit: b34701113ebdc9f539e5a3d7163aa3dd85368af3
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 0%

---

# Aktivitetskollisioner

The [!UICONTROL Collisions] på [!UICONTROL Activity Overview] sida in [!DNL Adobe Target] visar aktivitetskonflikter på din webbplats.

En aktivitetskollision inträffar när flera aktiviteter har konfigurerats för att leverera innehåll till samma sida. Om en aktivitetskonflikt inträffar kanske du inte ser det förväntade innehållet på sidan.

The [!UICONTROL Collisions] finns på sidan Aktivitetsöversikt och kan informera dig om din aktivitet innehåller potentiella konflikter. Alla aktiviteter på samma URL listas, oavsett målgrupp i varje aktivitet. Öppna den här fliken om du vill se en lista över aktiviteter som kan kollidera. Klicka på en aktivitet i listan för att visa översiktssidan för den aktiviteten. Om kollisionen ändrar den förväntade upplevelsen redigerar du aktiviteten.

The [!UICONTROL Collisions] listan hjälper dig att:

* Identifiera om ett test redan körs på en sida innan du skapar en ny aktivitet
* Felsöka en aktivitet om det förväntade innehållet inte visas

The [!UICONTROL Collisions] listan visar var [!DNL Target] scenario där mbox används och där samma URL används. För varje potentiell kollision visas aktivitets-URL:en, namnet på mbox-filen där kollisionen kan inträffa och alla aktiviteter som matchar båda villkoren. Om det finns flera mbox-rutor visas var och en av dem.

I listan visas status och prioritet för varje potentiell kollision, tillsammans med annan information. Du kan använda status och prioritet för att hjälpa dig att avgöra sannolikheten för en kollision. Om det till exempel finns en möjlig kollision mellan två aktiviteter och en är inaktiv, uppstår ingen faktisk kollision om inte den inaktiva aktiviteten aktiveras. Om den potentiella kollisionen är mellan två aktiva aktiviteter med samma prioritet och samma målgrupp, kommer en kollision att inträffa. Du kan ändra prioritet eller status för att förhindra kollisionen.

Om målgrupperna är olika finns det fortfarande en potentiell kollision eftersom det är möjligt att en viss besökare kan tillhöra flera målgrupper.
