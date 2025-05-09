---
keywords: upplevelseförhandsgranskning;upplevelse-URL;generera URL;visa upplevelse-URL:er
description: Lär dig hur du använder URL:er för förhandsgranskning av upplevelser för Adobe [!DNL Target] Automated Personalization-aktiviteter för att visa innehåll direkt på din webbplats innan aktiviteten är aktiv.
title: Hur kan jag använda URL:er för förhandsgranskning i Automated Personalization-aktiviteter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
exl-id: 9f329b8a-5f86-4cae-a3be-eed24fa0a9cd
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---

# Förhandsgranska Automated Personalization-aktiviteter med URL:er för förhandsgranskning av upplevelse

URL:er för förhandsgranskning av upplevelse kan genereras för [!DNL Target] [!UICONTROL Automated Personalization]-aktiviteter för att visa upplevelseinnehåll direkt på din webbplats innan aktiviteten är aktiv för förhandsgranskning och kvalitetskontroll. Förhandsgranska URL:er utan att ange målinriktning för att tvinga fram en viss upplevelse.

>[!NOTE]
>
>Du kan skapa URL:er för förhandsgranskning av upplevelser för andra typer av [!DNL Target]-aktiviteter. Processen är dock något annorlunda. Mer information finns i [Activity QA](/help/main/c-activities/c-activity-qa/activity-qa.md#preview).

Använd URL:er för förhandsgranskning av upplevelser för att dela upplevelser med teammedlemmar och till QA-upplevelser i olika webbläsare och miljöer, utan att skapa en separat QA-aktivitet. Den här funktionen är särskilt användbar om en webbplats är komplex eller om dina säkerhetsprofiler inte tillåter att webbplatsen visas i en simulator.

1. Skapa en [Automated Personalization-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) eller klicka på aktiviteten för att öppna den.

   Aktiviteten behöver inte vara aktiv för att kunna förhandsgranska en upplevelse.

1. Klicka på de tre lodräta prickarna på sidan Aktivitetsöversikt och klicka sedan på **[!UICONTROL View Experience URLs]**.

1. Granska och/eller ange dina URL-adresser.

   * Om du använder [!UICONTROL Visual Experience Composer] (VEC) anges den standardadress du angav för aktiviteten automatiskt och en länk skapas för varje upplevelse i din aktivitet. Du kan ändra den här URL-adressen och lägga till andra om du vill.
   * Om du använder [!UICONTROL Form-Based Experience Composer] anges ingen standard-URL automatiskt. Om du inte redan har skapat URL:er för förhandsgranskning av upplevelse klickar du på **Lägg till ny URL**. Du måste ange alla URL-adresser som du vill förhandsgranska samt ett namn för varje URL-adress.

   Du kan lägga till flera URL-adresser, vilket är användbart när du kör ett flersidigt test eller ett malltest, och du vill förhandsgranska aktiviteten på mer än en sida.

   Ett modalt fönster visar länkar till dina upplevelser på din webbplats för att få en&quot;riktig förhandsvisning&quot; av upplevelserna utanför [!DNL Target] VEC. Du måste dela länkarna från meddelandet för att kunna dela förhandsgranskningen. Det går inte att klicka på en länk och sedan kopiera den resulterande URL-adressen från sidan eftersom URL-adressen innehåller en parameter som bara visar sidan korrekt när du öppnar sidan från länken i meddelandet. I stället kopierar du texten i det modala fönstret och mejlar hela texten till teamet.

1. Klicka på **[!UICONTROL Generate All]** och klicka sedan på varje upplevelse för att förhandsgranska den.

   Om du sedan gör ändringar i upplevelsen ska du se till att generera nya förhandsgranskningslänkar för ditt team genom att gå tillbaka till det modala fönstret och klicka på **Förnya länkar** för att få nya länkar.

   >[!NOTE]
   >
   >Länkarna för förhandsgranskning öppnas på nya flikar och popup-blockeraren i webbläsaren måste vara inaktiverad.

1. Klicka på varje upplevelsenamn för att förhandsgranska aktiviteten.

   Sidan öppnas och aktiviteten visas.

1. Klicka på **[!UICONTROL Done]** om du vill återgå till aktivitetssammanfattningen.

## Överväganden {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Genererar URL:er för förhandsvisning av upplevelse**

* URL:en för förhandsvisning av upplevelser påverkas inte av trafikdivision mellan upplevelser.
* Målgruppsanpassning påverkar inte förhandsvisningen.
* Du kan automatiskt generera maximalt 300 URL:er för upplevelsen per aktivitet. Därefter måste du generera URL-adresserna manuellt.
* Beroende på antalet upplevelser kan det ta upp till fem minuter att generera URL:er. Stäng inte dialogrutan eftersom de genererade URL:erna inte går förlorade.
* De förhandsgranskningslänkar som skapas är giltiga i två månader. Därefter måste du generera om URL:erna för förhandsgranskningen.
* Du måste generera om varje gång en upplevelse ändras.

**URL:er för förhandsvisning av delad upplevelse**

* Du kan förhandsgranska en upplevelse även om du inte är en del av målgruppen.
* Du kan dela URL:er för förhandsgranskning av upplevelser med kollegor som inte har tillgång till [!DNL Adobe Target].

**Visa upplevelser med URL:er för förhandsvisning av upplevelse**

* Förhandsgranskningsfunktionerna för alla sparade aktiviteter, så länge som sidan inte har ändrats.
* URL:en för förhandsgranskning av upplevelse är tillgänglig oavsett om aktiviteten är aktiv eller inaktiv.
* Du kan inte förhandsgranska en upplevelse som har statusen [!UICONTROL Draft].
* Rapporteringen påverkas inte av URL:er för förhandsgranskning av upplevelse.

**Felsökning av URL:er för förhandsgranskning av upplevelse**

* Om du inte kan se förhandsvisningen på den nya fliken (på grund av webbläsarens cacheminne) kan du försöka uppdatera två eller tre gånger eller kopiera länken och öppna den i en ny webbläsare, en ny session eller i ett läge för en privat webbläsare.
