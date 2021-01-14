---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria;sequence;limit number of items returned;slot level control;slot
description: Använd sekvenser med upp till fem kriterier för att få bättre kontroll över de objekt som visas i dina Adobe Target Recommendations-aktiviteter.
title: Skapa villkorssekvenser
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 0%

---


# ![](/help/assets/premium.png) PREMIUMCreate-villkorssekvenser

Använd sekvenser med upp till fem kriterier för att få bättre kontroll över objekten som visas i dina [!UICONTROL Recommendations]-aktiviteter. Du kan också begränsa antalet returnerade objekt (kallas ibland för&quot;platskontrollen&quot;).

>[!NOTE]
>
>Villkorssekvenser kan inte användas med [!UICONTROL Recommendations]-aktiviteter som skapats före oktoberversionen 2016 av [!DNL Target Premium].

Om du vill skapa en villkorssekvens måste du först skapa de villkor som du vill inkludera i sekvensen. Mer information finns i [Skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md).

Genom att använda en villkorssekvens kan du ange ytterligare riktade rekommendationer, i stället för att använda mer allmänna rekommendationer för säkerhetskopiering, när ett villkor inte returnerar tillräckligt många resultat för att fylla din design. Vanligtvis går en villkorssekvens från mer specifik målgruppsanpassning, som kan returnera färre resultat, till mer allmän målgruppsanpassning, som vanligtvis ger fler resultat.

Dina villkorssekvenser kan variera i ordning beroende på sidtypen, vilket visas i följande exempel:

| Sidtyp | Möjlig sekvensordning |
| --- | --- |
| Produktsida | <ol><li>Baserat på aktuellt objekt, från samma varumärke</li><li>Baserat på aktuellt objekt, från alla varumärken</li><li>Baserat på innehållets likhet</li><li>Baserat på de främsta säljarna</li><li>Baserat på de mest visade objekten på webbplatsen</li></ol> |
| Startsida | <ol><li>Baserat på besökarens senaste köp </li><li>Baserat på besökarens favoritobjekt</li><li>Baserat på besökarens favoritkategori</li><li>Baserat på de främsta säljarna</li><li>Baserat på de mest visade sidorna på webbplatsen</li></ol> |

## Skapa en villkorssekvens

Du skapar villkorssekvenser från skärmen [!UICONTROL Create Criteria Sequence].

Det finns flera sätt att nå skärmen [!UICONTROL Create Criteria Sequence]. Vissa skärmalternativ varierar beroende på hur du kommer till skärmen.

* På **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** biblioteksskärmen klickar du på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. De villkor som du skapar här är automatiskt tillgängliga för alla [!UICONTROL Recommendations]-aktiviteter.
* När du skapar en [!UICONTROL Recommendations]-aktivitet klickar du på **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]** på skärmen Välj villkor. Du kan spara din nya villkorssekvens och använda den med andra [!UICONTROL Recommendations]-aktiviteter.
* När du redigerar en [!UICONTROL Recommendations]-aktivitet klickar du i en [!UICONTROL Recommendations Location]-ruta på sidan och väljer sedan **[!UICONTROL Change Criteria]**. På skärmen [!UICONTROL Select Criteria] klickar du på **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Du kan spara dina nya villkor och använda dem med andra [!UICONTROL Recommendations]-aktiviteter.

Följande steg förutsätter att du kommer åt skärmen [!UICONTROL Create Criteria Sequence] med den första metoden: **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** biblioteksskärmen.

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Klicka på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**.

   ![](assets/CreateCriteriaSequence.png)

1. Fyll i informationen i [avsnittet Grundläggande information](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Klicka på **[!UICONTROL Add Criteria]** i **[!UICONTROL Criteria Sequence]**-avsnittet.

   Sekvensordningen definierar i vilken ordning en design fylls. Om Villkor 1 inte har tillräckligt många rekommendationer för att fylla din design fylls de återstående platserna med villkor 2 och så vidare.

   ![Lägg till villkor](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. Välj ett villkor på skärmen [!UICONTROL Select Criteria] och klicka sedan på **[!UICONTROL Add]**.

   Du kan använda sökrutan och listrutorna för filter för att hitta önskat villkor.

   ![Välj villkor](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. (Valfritt) Dra reglaget **[!UICONTROL Limit the number of items returned]** till&quot;on&quot;-positionen och ange sedan antalet objekt (mellan 1 och 50).

   ![Begränsa antalet returnerade objekt](/help/c-recommendations/c-algorithms/assets/limit-number.png)

   För att du ska få en förståelse för värdet på alternativet [!UICONTROL Limit the number of items returned] (kallas ibland&quot;platskontrollen&quot;) bör du överväga följande användningsexempel:

   * **Användningsfall 1**: Du vill ha en blandning av olika typer av objekt i ett enda rekommendationsfack. Du kan till exempel visa en blandning av ytterkläder (schaket) och överdelar (skjortor, T-shirts). För att uppnå detta ska du använda en samling för aktiviteten som innehåller alla möjliga produkttyper du vill ha i platserna i designen. Ange sedan dina första kriterier med ett statiskt filter som begränsar kriterierna så att de bara omfattar ytterkläder, och ange dina andra kriterier med ett statiskt filter som begränsar kriterierna så att de bara omfattar toppar. Lägg slutligen till båda villkoren i en villkorssekvens och begränsa det första villkoret till 2 kortplatser.

      Rekommendationsfältet kan se ut så här på din webbplats:

      ![Rekommendationsfack för produkter](/help/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Användningsfall 2**: Du vill ha en blandning av både alternativa objekt och kompletterande objekt. Ange ett villkor för att använda en visad/visad algoritm och använd ett dynamiskt filter som begränsar de rekommenderade objekten till det aktuella objektets kategori. Ställ in det andra villkoret för att använda en visad/köpt algoritm och använd ett dynamiskt filter som endast innehåller rekommenderade objekt som inte matchar det aktuella objektets kategori. Lägg slutligen till båda villkoren i en sekvens och begränsa det första villkoret till två kortplatser.

1. Fortsätt lägga till ytterligare villkor i sekvensen. Du kan lägga till upp till fem villkor i en sekvens.

1. Aktivera [Alternativ för Säkerhetskopiera innehåll](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Klicka på **[!UICONTROL Save]**.

   Villkorssekvensen visas i kriterielistan.

   Mer information om alternativ för rekommendationslogik finns i [Kriterier](/help/c-recommendations/c-algorithms/algorithms.md).

## Utbildningsvideo: Skapa villkor i Recommendations (12:33) ![Tutorial badge](/help/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa villkor
* Skapa villkorssekvenser
* Överför anpassade villkor

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
