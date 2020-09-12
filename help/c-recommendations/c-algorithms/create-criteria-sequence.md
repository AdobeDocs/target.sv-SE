---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria;sequence;limit number of items returned
description: Använd sekvenser med upp till fem kriterier för att få bättre kontroll över de objekt som visas i dina Adobe Target Recommendations-aktiviteter.
title: Skapa villkorssekvenser
feature: criteria
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
translation-type: tm+mt
source-git-commit: 81de460e5cd9277adcee4bd6e1e0175b0e350605
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Skapa villkorssekvenser

Använd sekvenser med upp till fem kriterier för att få bättre kontroll över de objekt som visas i dina [!UICONTROL Recommendations] aktiviteter.

>[!NOTE]
>
>Villkorssekvenser kan inte användas med [!UICONTROL Recommendations] aktiviteter som skapats före oktober 2016-versionen av [!DNL Target Premium].

Om du vill skapa en villkorssekvens måste du först skapa de villkor som du vill inkludera i sekvensen. Mer information finns i [Skapa villkor](/help/c-recommendations/c-algorithms/create-new-algorithm.md) .

Genom att använda en villkorssekvens kan du ange ytterligare riktade rekommendationer, i stället för att använda mer allmänna rekommendationer för säkerhetskopiering, när ett villkor inte returnerar tillräckligt många resultat för att fylla din design. Vanligtvis går en villkorssekvens från mer specifik målgruppsanpassning, som kan returnera färre resultat, till mer allmän målgruppsanpassning, som vanligtvis ger fler resultat.

Dina villkorssekvenser kan variera i ordning beroende på sidtypen, vilket visas i följande exempel:

| Sidtyp | Möjlig sekvensordning |
| --- | --- |
| Produktsida | <ol><li>Baserat på aktuellt objekt, från samma varumärke</li><li>Baserat på aktuellt objekt, från alla varumärken</li><li>Baserat på innehållets likhet</li><li>Baserat på de främsta säljarna</li><li>Baserat på de mest visade objekten på webbplatsen</li></ol> |
| Startsida | <ol><li>Baserat på besökarens senaste köp </li><li>Baserat på besökarens favoritobjekt</li><li>Baserat på besökarens favoritkategori</li><li>Baserat på de främsta säljarna</li><li>Baserat på de mest visade sidorna på webbplatsen</li></ol> |

## Skapa en villkorssekvens

Du skapar villkorssekvenser från [!UICONTROL Create Criteria Sequence] skärmen.

Det finns flera sätt att nå [!UICONTROL Create Criteria Sequence] skärmen. Vissa skärmalternativ varierar beroende på hur du kommer till skärmen.

* På skärmen **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** bibliotek klickar du **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. Kriterierna som du skapar här blir automatiskt tillgängliga för alla [!UICONTROL Recommendations] aktiviteter.
* När du skapar en [!UICONTROL Recommendations] aktivitet går du till skärmen Välj villkor och klickar på **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Du kan spara den nya villkorssekvensen och använda den med andra [!UICONTROL Recommendations] aktiviteter.
* När du redigerar en [!UICONTROL Recommendations] aktivitet klickar du i en [!UICONTROL Recommendations Location] ruta på sidan och väljer sedan **[!UICONTROL Change Criteria]**. På [!UICONTROL Select Criteria] skärmen klickar du **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Du kan spara dina nya villkor och använda dem med andra [!UICONTROL Recommendations] aktiviteter.

Följande steg förutsätter att du kommer åt [!UICONTROL Create Criteria Sequence] skärmen med den första metoden: på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** biblioteksskärmen.

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Klicka på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**.

   ![](assets/CreateCriteriaSequence.png)

1. Fyll i informationen under [Grundläggande information](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info) .

1. Klicka i **[!UICONTROL Criteria Sequence]** avsnittet **[!UICONTROL Add Criteria]**.

   Sekvensordningen definierar i vilken ordning en design fylls. Om Villkor 1 inte har tillräckligt många rekommendationer för att fylla din design fylls de återstående platserna med villkor 2 och så vidare.

   ![Lägg till villkor](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. Markera ett villkor på [!UICONTROL Select Criteria] skärmen och klicka sedan på **[!UICONTROL Add]**.

   Du kan använda sökrutan och listrutorna för filter för att hitta önskat villkor.

   ![Välj villkor](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. (Valfritt) Skjut **[!UICONTROL Limit the number of items returned]** växlingsknappen till&quot;på&quot;-positionen och ange sedan antalet objekt (mellan 1 och 50).

   ![Begränsa antalet returnerade objekt](/help/c-recommendations/c-algorithms/assets/limit-number.png)

   Du kan förstå värdet av [!UICONTROL Limit the number of items returned] alternativet på följande sätt:

   * **Användningsfall 1**: Du vill ha en blandning av olika typer av objekt i ett enda rekommendationsfack. Du kan till exempel visa en blandning av ytterkläder (schaket) och överdelar (skjortor, T-shirts). För att uppnå detta ska du använda en samling för aktiviteten som innehåller alla möjliga produkttyper du vill ha i platserna i designen. Ange sedan dina första kriterier med ett statiskt filter som begränsar kriterierna så att de bara omfattar ytterkläder, och ange dina andra kriterier med ett statiskt filter som begränsar kriterierna så att de bara omfattar toppar. Lägg slutligen till båda villkoren i en villkorssekvens och begränsa det första villkoret till 2 kortplatser.

      Rekommendationsfältet kan se ut så här på din webbplats:

      ![Rekommendationsfack för produkter](/help/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Användningsfall 2**: Du vill ha en blandning av både alternativa objekt och kompletterande objekt. Ange ett villkor för att använda en visad/visad algoritm och använd ett dynamiskt filter som begränsar de rekommenderade objekten till det aktuella objektets kategori. Ställ in det andra villkoret för att använda en visad/köpt algoritm och använd ett dynamiskt filter som endast innehåller rekommenderade objekt som inte matchar det aktuella objektets kategori. Lägg slutligen till båda villkoren i en sekvens och begränsa det första villkoret till två kortplatser.

1. Fortsätt lägga till ytterligare villkor i sekvensen. Du kan lägga till upp till fem villkor i en sekvens.

1. Aktivera alternativ för [innehåll](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content)för säkerhetskopiering.

1. Klicka på **[!UICONTROL Save]**.

   Villkorssekvensen visas i kriterielistan.

   Mer information om alternativ för rekommendationslogik finns i [Kriterier](../../c-recommendations/c-algorithms/algorithms.md).

## Utbildningsvideo: Skapa villkor i Recommendations (12:33) ![självstudiemärke](/help/assets/tutorial.png)

Den här videon innehåller följande information:

* Skapa villkor
* Skapa villkorssekvenser
* Överför anpassade villkor

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
