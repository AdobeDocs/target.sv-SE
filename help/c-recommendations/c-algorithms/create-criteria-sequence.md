---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria
description: Använd sekvenser med upp till fem kriterier för att få bättre kontroll över de objekt som visas i dina Recommendations-aktiviteter.
title: Skapa villkorssekvenser
feature: null
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Skapa villkorssekvenser{#create-criteria-sequences}

Använd sekvenser med upp till fem kriterier för att få bättre kontroll över de objekt som visas i dina Recommendations-aktiviteter.

>[!NOTE]
>
>Villkorssekvenser kan inte användas med [!UICONTROL Recommendations] aktiviteter som skapats före oktober 2016-versionen av [!DNL Target Premium].

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

Det finns flera sätt att nå [!UICONTROL Create Criteria Sequence] skärmen. Vissa skärmalternativ varierar beroende på hur du kommer till skärmen.

* När du skapar en [!UICONTROL Recommendations] aktivitet klickar du **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]** på [!UICONTROL Select Criteria] skärmen. Du kan spara den nya villkorssekvensen och använda den med andra [!UICONTROL Recommendations] aktiviteter.
* När du redigerar en [!UICONTROL Recommendations] aktivitet klickar du i en [!UICONTROL Recommendations Location] ruta på sidan och väljer **[!UICONTROL Change Criteria]**. På [!UICONTROL Select Criteria] skärmen klickar du **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Du kan spara dina nya villkor och använda dem med andra [!UICONTROL Recommendations] aktiviteter.
* På skärmen **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** bibliotek klickar du **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. Kriterierna som du skapar här blir automatiskt tillgängliga för alla [!UICONTROL Recommendations] aktiviteter.

1. Klicka på **[!UICONTROL Create Criteria]** eller **[!UICONTROL Create New]**.

   ![Skapa nya villkor](/help/c-recommendations/c-algorithms/assets/button_CreateCriteria_new.png)

1. Välj **[!UICONTROL Create Criteria Sequence]**.

   ![](assets/CreateCriteriaSequence.png)

1. Skriv ett **[!UICONTROL Name]** för sekvensen.

   Det här är det&quot;interna&quot; namnet som används för att beskriva villkorssekvensen. Besökare på platsen kommer inte att se det här namnet.
1. Skriv in en offentlig sida **[!UICONTROL Generic Display Title]** som ska visas på sidan om flera villkor i sekvensen används för att fylla i [!UICONTROL Recommendations] designen.

   Du kanske vill ersätta&quot;Kunder som tittade på det här även visade..&quot;. med&quot;Recommended for You&quot; om designen kan innehålla objekt som baseras på mer än en [!UICONTROL Recommendations] nyckel.
1. Ange en kort **[!UICONTROL Description]** av villkorssekvensen.

   Beskrivningen bör hjälpa dig att identifiera villkorssekvensen och kan innehålla information om dess syfte.
1. Välj en **[!UICONTROL Industry Vertical]**.

   Standardbranschens lodräta stil visas automatiskt.
1. Välj en **[!UICONTROL Page Type]**.

   Du kan välja flera sidtyper.

   Tillsammans används de vertikala metoderna och sidtyperna i branschen för att kategorisera de sparade villkorssekvenserna, vilket gör det enklare att återanvända sekvenser för andra [!UICONTROL Recommendations] aktiviteter.
1. Ange dina **[!UICONTROL Content]** regler.

   När du skapar en villkorssekvens ignoreras rekommendationer för säkerhetskopiering och partiella designåtergivningsinställningar för de enskilda villkoren som utgör sekvensen. Om du vill använda rekommendationer för säkerhetskopiering och partiell designåtergivning måste du aktivera dem för sekvensen. Välj lämpliga reglage. Om du väljer att tillåta rekommendationer för säkerhetskopiering kan du också välja om inkluderingsregler ska tillämpas på säkerhetskopiorna.
1. Ange sekvensordningen.

1. Klicka på **[!UICONTROL Add Criteria]**.
1. Välj ett villkor på skärmen Lägg till villkor.
1. Klicka på **[!UICONTROL Add]**.

   Du kan lägga till upp till fem villkor i en sekvens.
1. Klicka på **[!UICONTROL Save]**.

   Villkorssekvensen visas i kriterielistan.

   ![](assets/CriteriaSequenceCard.png)

   Mer information om alternativ för rekommendationslogik finns i [Kriterier](../../c-recommendations/c-algorithms/algorithms.md#concept_4BD01DC437F543C0A13621C93A302750).

## Utbildningsvideo: Skapa villkor i Recommendations (12:33) ![självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa villkor
* Skapa villkorssekvenser
* Överför anpassade villkor

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
