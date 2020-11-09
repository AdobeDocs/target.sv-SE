---
keywords: Targeting
description: Fliken Konflikter på sidan Aktivitetsöversikt visar aktivitetskonflikter på din webbplats.
title: Aktivitetskollisioner
feature: vec
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---


# Aktivitetskollisioner{#activity-collisions}

Fliken Konflikter på sidan Aktivitetsöversikt visar aktivitetskonflikter på din webbplats.

En aktivitetskollision inträffar när flera aktiviteter har konfigurerats för att leverera innehåll till samma sida. Om en aktivitetskonflikt inträffar kanske du inte ser det förväntade innehållet på sidan.

Om din aktivitet innehåller potentiella kollisioner finns fliken [!UICONTROL Collisions] tillgänglig på sidan med aktivitetsöversikt. Alla aktiviteter på samma URL listas, oavsett målgrupp i varje aktivitet. Öppna den här fliken om du vill se en lista över aktiviteter som kan kollidera. Klicka på en aktivitet i listan för att visa översiktssidan för den aktiviteten. Om kollisionen ändrar den förväntade upplevelsen redigerar du aktiviteten.

Med kollisionslistan kan du:

* Identifiera om ett test redan körs på en sida innan du skapar en ny aktivitet
* Felsöka en aktivitet om det förväntade innehållet inte visas

I listan Konflikter visas alla målstandardscenarier där rutan används och där samma URL används. För varje potentiell kollision visas aktivitets-URL:en, namnet på mbox-filen där kollisionen kan inträffa och alla aktiviteter som matchar båda villkoren. Om det finns flera kryssrutor visas de var och en.

I listan visas status och prioritet för varje potentiell kollision, tillsammans med annan information. Du kan använda status och prioritet för att hjälpa dig att avgöra sannolikheten för en kollision. Om det till exempel finns en möjlig kollision mellan två aktiviteter och en är inaktiv, uppstår ingen faktisk kollision om inte den inaktiva aktiviteten aktiveras. Om den potentiella kollisionen är mellan två aktiva aktiviteter med samma prioritet och samma målgrupp, kommer en kollision att inträffa. Du kan ändra prioritet eller status för att förhindra kollisionen.

Om målgrupperna är olika finns det fortfarande en potentiell kollision eftersom det är möjligt att en viss besökare kan tillhöra flera målgrupper.
