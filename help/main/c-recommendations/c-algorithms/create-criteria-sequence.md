---
keywords: villkorssekvens;flera kriterier;algoritmer;kriterier;rekommendationer-kriterier;sekvens;gränsantal returnerade objekt;platshållarnivåkontroll;plats
description: Lär dig hur du ställer in sekvenser på upp till fem villkor för att få bättre kontroll över objekten som visas i dina rekommendationer-aktiviteter.
title: Hur skapar jag villkorssekvenser i rekommendationer?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 0%

---

# Skapa villkorssekvenser

Använd sekvenser med upp till fem kriterier för att få större kontroll över objekten som visas i dina [!DNL Adobe Target] [!UICONTROL Recommendations]-aktiviteter. Du kan också begränsa antalet returnerade objekt (kallas ibland för&quot;platskontrollen&quot;).

>[!NOTE]
>
>Villkorssekvenser kan inte användas med [!UICONTROL Recommendations] aktiviteter som skapats före oktober 2016-utgåvan av [!DNL Target Premium].

Om du vill skapa en villkorssekvens måste du först skapa de villkor som du vill inkludera i sekvensen. Mer information finns i [Skapa villkor](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

Genom att använda en villkorssekvens kan du ange ytterligare riktade rekommendationer, i stället för att använda mer allmänna rekommendationer för säkerhetskopiering, när ett villkor inte returnerar tillräckligt många resultat för att fylla din design. Vanligtvis går en villkorssekvens från mer specifik målgruppsanpassning, som kan returnera färre resultat, till mer allmän målgruppsanpassning, som vanligtvis ger fler resultat.

Dina villkorssekvenser kan variera i ordning beroende på sidtypen, vilket visas i följande exempel:

| Sidtyp | Möjlig sekvensordning |
| --- | --- |
| Produktsida | <ol><li>Baserat på aktuellt objekt, från samma varumärke</li><li>Baserat på aktuellt objekt, från alla varumärken</li><li>Baserat på innehållets likhet</li><li>Baserat på de främsta säljarna</li><li>Baserat på de mest visade objekten på webbplatsen</li></ol> |
| Startsida | <ol><li>Baserat på besökarens senaste köp </li><li>Baserat på besökarens favoritobjekt</li><li>Baserat på besökarens favoritkategori</li><li>Baserat på de främsta säljarna</li><li>Baserat på de mest visade sidorna på webbplatsen</li></ol> |

## Skapa en villkorssekvens

Du skapar villkorssekvenser från skärmen [!UICONTROL Create Criteria Sequence].

Det finns flera sätt att nå skärmen [!UICONTROL Create Criteria Sequence]. Vissa skärmalternativ varierar beroende på hur du kommer till skärmen.

* Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** på biblioteksskärmen **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. Kriterier som du skapar här blir automatiskt tillgängliga för alla [!UICONTROL Recommendations]-aktiviteter.
* När du skapar en [!UICONTROL Recommendations]-aktivitet klickar du på [!UICONTROL Select Criteria] > **[!UICONTROL Create New]** på skärmen **[!UICONTROL Create Criteria Sequence]**. Du kan spara din nya villkorssekvens för användning med andra [!UICONTROL Recommendations]-aktiviteter.
* När du redigerar en [!UICONTROL Recommendations]-aktivitet klickar du i en [!UICONTROL Recommendations Location]-ruta på sidan och väljer sedan **[!UICONTROL Change Criteria]**. På skärmen [!UICONTROL Select Criteria] klickar du på **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Du kan spara dina nya villkor och använda dem med andra [!UICONTROL Recommendations]-aktiviteter.

Följande steg förutsätter att du kommer åt skärmen [!UICONTROL Create Criteria Sequence] med den första metoden: biblioteksskärmen **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Klicka på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**.

1. Fyll i informationen i avsnittet [Grundläggande information](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. I avsnittet **[!UICONTROL Criteria Sequence]** klickar du på plustecknet ( + ) för att lägga till en eller flera villkorssekvenser.

   Sekvensordningen definierar i vilken ordning en design fylls. Om Villkor 1 inte har tillräckligt många rekommendationer för att fylla din design fylls de återstående platserna med villkor 2 och så vidare.

1. Välj ett villkor på skärmen [!UICONTROL Select Criteria] och klicka sedan på **[!UICONTROL Save]**.

   Du kan använda rutan [!UICONTROL Search] och filteralternativet för att hitta de önskade villkoren.

1. (Valfritt) Skjut **[!UICONTROL Limit the number of items returned]**-växeln till&quot;på&quot;-positionen och ange sedan antalet objekt (mellan 1 och 50).

   För att du ska förstå värdet för alternativet [!UICONTROL Limit the number of items returned] (kallas ibland&quot;platskontrollen&quot;) bör du överväga följande användningsexempel:

   * **Använd fall 1**: Du vill ha en blandning av olika typer av objekt i ett enda rekommendationsfack. Du kan till exempel visa en blandning av ytterkläder (schaket) och överdelar (skjortor, T-shirts). För att uppnå detta ska du använda en samling för aktiviteten som innehåller alla möjliga produkttyper du vill ha i platserna i designen. Ange sedan dina första kriterier med ett statiskt filter som begränsar kriterierna så att de bara omfattar ytterkläder, och ange dina andra kriterier med ett statiskt filter som begränsar kriterierna så att de bara omfattar toppar. Lägg slutligen till båda villkoren i en villkorssekvens och begränsa det första villkoret till 2 kortplatser.

     Rekommendationsfältet kan se ut så här på din webbplats:

     ![Rekommendationsfack för aktuella produkter](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Använd skiftläge 2**: Du vill ha en blandning av både alternativa objekt och kompletterande objekt. Ange ett villkor för att använda en visad/visad algoritm och använd ett dynamiskt filter som begränsar de rekommenderade objekten till det aktuella objektets kategori. Ställ in det andra villkoret för att använda en visad/köpt algoritm och använd ett dynamiskt filter som endast innehåller rekommenderade objekt som inte matchar det aktuella objektets kategori. Lägg slutligen till båda villkoren i en sekvens och begränsa det första villkoret till två kortplatser.

1. Fortsätt lägga till ytterligare villkor i sekvensen. Du kan lägga till upp till fem villkor i en sekvens.

1. Aktivera [Alternativ för innehåll för säkerhetskopiering](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Klicka på **[!UICONTROL Create]**.

   Villkorssekvensen visas i listan [!UICONTROL Criteria].

   Mer information om alternativ för rekommendationslogik finns i [Villkor](/help/main/c-recommendations/c-algorithms/algorithms.md).
