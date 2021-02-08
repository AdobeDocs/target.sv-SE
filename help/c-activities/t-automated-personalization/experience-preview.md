---
keywords: upplevelseförhandsgranskning;upplevelse-URL;generera URL;visa upplevelse-URL:er
description: Lär dig hur du använder URL:er för förhandsgranskning av upplevelser för Adobe Target Automated Personalization-aktiviteter för att visa innehåll direkt på din webbplats innan aktiviteten publiceras.
title: Hur kan jag använda URL:er för förhandsgranskning i Automated Personalization-aktiviteter?
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMPörhandsgranska Automated Personalization-aktiviteter med URL:er för förhandsgranskning av upplevelser

URL:er för förhandsgranskning av upplevelser kan genereras för Automated Personalization-aktiviteter för att visa innehåll direkt på webbplatsen innan aktiviteten är aktiv för förhandsgranskning och kvalitetskontroll. Förhandsgranska URL:er utan att ange målinriktning för att framtvinga visning av en viss upplevelse.

>[!NOTE]
>
>URL:er för förhandsgranskning för Automated Personalization skiljer sig från QA-läget för aktivitet. I läget Activity QA kan du skapa aktivitets-URL:er för andra typer av aktiviteter. Mer information finns i [Aktivitets-QA](/help/c-activities/c-activity-qa/activity-qa.md).
>
>URL:er för förhandsgranskning av AP-aktiviteter är bara tillgängliga när du använder at.js 1.x. URL:er för förhandsgranskning för AP-aktiviteter stöds för närvarande inte för at.js 2.x.

Använd URL:er för förhandsgranskning av upplevelser för att dela upplevelser med teammedlemmar och till QA-upplevelser i olika webbläsare och miljöer, utan att skapa en separat QA-aktivitet. Den här funktionen är särskilt användbar om en webbplats är komplex eller om dina säkerhetsprofiler inte tillåter att webbplatsen visas i en simulator.

1. Skapa en [Automated Personalization-aktivitet](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) eller klicka på aktiviteten för att öppna den.

   Aktiviteten behöver inte vara aktiv för att kunna förhandsgranska en upplevelse.
1. Klicka på de tre lodräta prickarna på sammanfattningssidan och klicka sedan på **[!UICONTROL View Experience URLs]**.
1. Granska och/eller ange dina URL-adresser.

   * Om du använder Visual Experience Composer anges den standardwebbadress du angav för aktiviteten automatiskt och en länk skapas för varje upplevelse i din aktivitet. Du kan ändra den här URL-adressen och lägga till andra om du vill.
   * Om du använder formulärbaserad Experience Composer anges ingen standard-URL automatiskt. Om du inte redan har skapat URL:er för förhandsgranskning av upplevelse klickar du på **Lägg till ny URL**. Du måste ange alla URL-adresser som du vill förhandsgranska samt ett namn för varje URL-adress.

   Du kan lägga till flera URL-adresser, vilket är användbart när du kör ett flersidigt test eller ett malltest, och du vill förhandsgranska aktiviteten på mer än en sida.

   Ett modalt fönster visar länkar till era upplevelser på er webbplats för att få en&quot;riktig förhandsvisning&quot; av upplevelserna utanför Target Visual Experience Composer. Du måste dela länkarna från meddelandet för att kunna dela förhandsgranskningen. Det går inte att klicka på en länk och sedan kopiera den resulterande URL-adressen från sidan eftersom URL-adressen innehåller en parameter som bara visar sidan korrekt när du öppnar sidan från länken i meddelandet. I stället kopierar du texten i det modala fönstret och mejlar hela texten till teamet.
1. Klicka på **[!UICONTROL Generate All]** och klicka sedan på varje upplevelse för att förhandsgranska den.

   Om du sedan gör ändringar i upplevelsen ska du se till att generera nya förhandsgranskningslänkar för ditt team genom att gå tillbaka till det modala fönstret och klicka på **Förnya länkar** för att få nya länkar.

   **Obs!** Länkarna för förhandsgranskning öppnas på nya flikar och kräver att blockering av popup-fönster i webbläsaren är inaktiverat.

1. Klicka på varje upplevelsenamn för att förhandsgranska aktiviteten.

   Sidan öppnas och aktiviteten visas.
1. Klicka på **[!UICONTROL Done]** för att återgå till aktivitetssammanfattningen.

## Överväganden {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Generera URL för förhandsvisning av upplevelse**

* URL:en för förhandsvisning av upplevelser påverkas inte av trafikdivision mellan upplevelser.
* Målgruppsanpassning påverkar inte förhandsvisningen.
* Du kan automatiskt generera maximalt 300 URL:er för upplevelsen per aktivitet. Därefter måste du generera URL-adresserna manuellt.
* Du kan automatiskt generera maximalt 300 URL:er för upplevelsen per aktivitet. Därefter måste du generera URL-adresserna manuellt.
* Beroende på antalet upplevelser kan det ta upp till fem minuter att generera URL:er. Stäng inte dialogrutan eftersom de genererade URL:erna inte kommer att gå förlorade.
* De förhandsgranskningslänkar som skapas gäller i två månader. Därefter måste du generera om URL:erna för förhandsgranskningen.
* Du måste generera om varje gång en upplevelse ändras.

**URL:er för förhandsvisning av delad upplevelse**

* Du kan förhandsgranska en upplevelse även om du inte är en del av målgruppen.
* Du kan dela URL:er för förhandsgranskning av upplevelser med kollegor som inte har tillgång till Adobe Target.

**Visa upplevelser med URL:er för förhandsgranskning av upplevelse**

* Förhandsgranskningsfunktionerna för alla sparade aktiviteter, så länge som sidan inte har ändrats.
* URL:en för förhandsgranskning av upplevelse är tillgänglig oavsett om aktiviteten är aktiv eller inaktiv.
* Du kan inte förhandsgranska en upplevelse som har statusen Utkast.
* Rapporteringen påverkas inte av URL:er för förhandsgranskning av upplevelse.

**Felsöka URL:er för Experience Preview**

* Om du inte kan se förhandsvisningen på den nya fliken (på grund av webbläsarens cacheminne) kan du försöka uppdatera två eller tre gånger eller kopiera länken och öppna den i en ny webbläsare, en ny session eller i ett läge för en privat webbläsare.
