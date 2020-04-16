---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria
description: Använd sekvenser med upp till fem kriterier för att få bättre kontroll över objekten som visas i dina rekommendationer-aktiviteter.
title: Skapa villkorssekvenser
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
translation-type: tm+mt
source-git-commit: 0ba817898366e9d18fec6cc0fc75013c78a136e9

---


# ![PREMIUM](/help/assets/premium.png) Skapa villkorssekvenser{#create-criteria-sequences}

Använd sekvenser med upp till fem kriterier för att få bättre kontroll över objekten som visas i dina rekommendationer-aktiviteter.

>[!NOTE]
>
>Villkorssekvenser kan inte användas med [!UICONTROL rekommendationer] som skapats före oktoberversionen 2016 av [!DNL Target Premium].

Om du vill skapa en villkorssekvens måste du först skapa de villkor som du vill inkludera i sekvensen. Mer information finns i [Skapa villkor](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE) .

Genom att använda en villkorssekvens kan du ange ytterligare riktade rekommendationer, i stället för att använda mer allmänna rekommendationer för säkerhetskopiering, när ett villkor inte returnerar tillräckligt många resultat för att fylla din design. Vanligtvis går en villkorssekvens från mer specifik målgruppsanpassning, som kan returnera färre resultat, till mer allmän målgruppsanpassning, som vanligtvis ger fler resultat.

En villkorssekvens för en produktsida kan till exempel följa den här ordningen:

1. Baserat på aktuellt objekt, från samma varumärke
1. Baserat på aktuellt objekt, från alla varumärken
1. Baserat på innehållets likhet
1. Baserat på de främsta säljarna
1. Baserat på de mest visade objekten på webbplatsen

En villkorssekvens för startsidan kan följa den här ordningen:

1. Baserat på besökarens senaste köp
1. Baserat på besökarens favoritobjekt
1. Baserat på besökarens favoritkategori
1. Baserat på de främsta säljarna
1. Baserat på de mest visade sidorna på webbplatsen

Det finns flera sätt att nå skärmen [!UICONTROL Skapa villkorssekvens] . Vissa skärmalternativ varierar beroende på hur du kommer till skärmen.

* När du skapar en [!UICONTROL rekommendationsaktivitet] klickar du på **[!UICONTROL Skapa ny]** > **[!UICONTROL Skapa villkorssekvens]** på skärmen [!UICONTROL Välj villkor] . Du kan spara din nya villkorssekvens och använda den med andra [!UICONTROL rekommendationer] -aktiviteter.
* När du redigerar en [!UICONTROL rekommendationsaktivitet] klickar du i rutan [!UICONTROL Rekommenderingsplats] på sidan och väljer **[!UICONTROL Ändra villkor]**. På skärmen [!UICONTROL Välj villkor] klickar du på **[!UICONTROL Skapa nytt]** > **[!UICONTROL Skapa villkorssekvens]**. Du kan spara dina nya villkor och använda dem tillsammans med andra [!UICONTROL rekommendationer] -aktiviteter.
* På biblioteksskärmen **[!UICONTROL Rekommendationer]** > **[!UICONTROL Kriterier]** klickar du på **[!UICONTROL Skapa villkor]** > **[!UICONTROL Skapa villkorssekvens]**. Kriterierna som du skapar här är automatiskt tillgängliga för alla aktiviteter som [!UICONTROL rekommenderas] .

1. Klicka på **[!UICONTROL Skapa villkor]** eller **[!UICONTROL Skapa nytt]**.

   ![Skapa nya villkor](/help/c-recommendations/c-algorithms/assets/button_CreateCriteria_new.png)

1. Välj **[!UICONTROL Skapa villkorssekvens]**.

   ![](assets/CreateCriteriaSequence.png)

1. Ange ett **[!UICONTROL namn]** för sekvensen.

   Det här är det&quot;interna&quot; namnet som används för att beskriva villkorssekvensen. Besökare på platsen kommer inte att se det här namnet.
1. Ange en allmän **[!UICONTROL visningsrubrik]** som ska visas på sidan om flera villkor i sekvensen används för att fylla i designen [!UICONTROL Rekommendationer] .

   Du kanske vill ersätta&quot;Kunder som tittade på det här även visade..&quot;. med&quot;Recommended for You&quot; om designen kan innehålla objekt som baseras på mer än en [!UICONTROL Recommendations] key.
1. Skriv en kort **[!UICONTROL beskrivning]** av villkorssekvensen.

   Beskrivningen bör hjälpa dig att identifiera villkorssekvensen och kan innehålla information om dess syfte.
1. Välj en **[!UICONTROL branschvertikal]**.

   Standardbranschens lodräta stil visas automatiskt.
1. Välj en **[!UICONTROL sidtyp]**.

   Du kan välja flera sidtyper.

   Tillsammans används de vertikala metoderna och sidtyperna för att kategorisera de sparade kriteriesekvenserna, vilket gör det enklare att återanvända sekvenser för andra [!UICONTROL rekommendationer] .
1. Ange **[!UICONTROL innehållsregler]** .

   När du skapar en villkorssekvens ignoreras rekommendationer för säkerhetskopiering och partiella designåtergivningsinställningar för de enskilda villkoren som utgör sekvensen. Om du vill använda rekommendationer för säkerhetskopiering och partiell designåtergivning måste du aktivera dem för sekvensen. Välj lämpliga reglage. Om du väljer att tillåta rekommendationer för säkerhetskopiering kan du också välja om inkluderingsregler ska tillämpas på säkerhetskopiorna.
1. Ange sekvensordningen.

1. Klicka på **[!UICONTROL Lägg till villkor]**.
1. Välj ett villkor på skärmen Lägg till villkor.
1. Klicka på **[!UICONTROL Lägg till]**.

   Du kan lägga till upp till fem villkor i en sekvens.
1. Klicka på **[!UICONTROL Spara]**.

   Villkorssekvensen visas i kriterielistan.

   ![](assets/CriteriaSequenceCard.png)

   Mer information om alternativ för rekommendationslogik finns i [Kriterier](../../c-recommendations/c-algorithms/algorithms.md#concept_4BD01DC437F543C0A13621C93A302750).

## Utbildningsvideo: Skapa villkor i ![självstudiekursen Rekommendationer (12:33)](/help/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa villkor
* Skapa villkorssekvenser
* Överför anpassade villkor

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
