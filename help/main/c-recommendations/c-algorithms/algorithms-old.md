---
keywords: rekommendationer;rekommendationsaktivitet;kriterier;algoritm;rekommendationsnyckel;anpassad nyckel;branschvertikal;återförsäljning;e-handel;lead generation;b2b;finansiella tjänster;media;publicering
description: Lär dig hur du använder villkor i Adobe [!DNL Target] [!DNL Recommendations].
title: Hur använder jag villkor i  [!DNL Target] Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 0%

---

# Kriterier

Kriterier i [!DNL Adobe Target] [!DNL Recommendations] är regler som avgör vilka produkter eller vilket innehåll som ska rekommenderas utifrån en fördefinierad uppsättning besökarbeteenden. Kriterierna kan baseras på populära trender, en besökares aktuella och tidigare beteenden eller liknande produkter och innehåll. Du kan testa flera rekommendationstyper mot varandra genom att lägga till flera villkor.

I följande avsnitt beskrivs mer om villkorsnycklar och den rekommendationslogik du kan använda för varje nyckel. Klicka på länkarna för mer detaljerad information.

## Branschvertikal {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

När du skapar villkor väljer du en bransch vertikalt baserad på syftet med dina rekommendationer.

| Branschvertikal | Mål |
|--- |--- |
| Detaljhandel/e-handel | Konvertering som resulterar i inköp |
| Leadgenerering/B2B/Finansiella tjänster | Konvertering utan köp |
| Media/publicering | Engagemang |

Andra kriteriealternativ ändras beroende på vilken vertikal du väljer i branschen. Du kan ställa in din standardbransch vertikalt på sidan **[!UICONTROL Recommendations > Settings]** eller så kan du ange branschvertikal för varje villkor.

## Algoritmtyp {#section_885B3BB1B43048A88A8926F6B76FC482}

Den algoritmtyp du väljer avgör vilka algoritmer som är tillgängliga. Det finns flera algoritmtyper som visas som kriteriekort när du konfigurerar en [!DNL Recommendations]-aktivitet.

![Villkorssida](assets/criteria-page.png)

I följande tabell förklaras de olika algoritmtyperna och deras tillhörande algoritmer.

| Algoritmtyp | När ska du använda | Tillgängliga algoritmer |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | Utför rekommendationer baserat på användarens kundvagnsinnehåll. | <ul><li>Folk som tittade på de här, såg dem</li><li>Folk som såg de här, köpte de där</li><li>Folk som köpte de här, köpte de där</li></ul>Mer information finns i [Kundvagnsbaserad](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) i *Basera rekommendationen på en rekommendationsnyckel*. |
| [!UICONTROL Popularity-Based] | Utför rekommendationer baserat på hur populärt ett objekt på webbplatsen är eller utifrån hur populärt det är att ha objekt inom en användares favoritkategori, varumärke, genre osv. | <ul><li>Visas bäst på webbplatsen</li><li>Mest visade per kategori</li><li>Mest visad av objektattribut</li><li>De största säljarna på webbplatsen</li><li>De viktigaste säljarna per kategori</li><li>De viktigaste säljarna efter artikelattribut</li><li>Top by Analytics Metric</li></ul> |
| [!UICONTROL Item-Based] | Rekommendationer baserade på sökning efter liknande objekt för ett objekt som användaren för närvarande visar eller nyligen har visat. | <ul><li>Folk som tittade på det här, såg det</li><li>Folk som såg det här, köpte det</li><li>Folk som köpte den här, köpte den där</li><li>Objekt med liknande attribut</li></ul> |
| [!UICONTROL User-Based] | Utför rekommendationer baserat på användarens beteende. | <ul><li>Nyligen visade objekt</li><li>Rekommenderas för dig</li></ul> |
| [!UICONTROL Custom Criteria] | Utför rekommendationer baserat på en anpassad fil som du överför. | <ul><li>Anpassad algoritm</li></ul> |

Mer information om varje algoritm finns i [Basera rekommendationen på en rekommendationsnyckel](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## Använda en anpassad rekommendationsnyckel {#custom-key}

Du kan också basera rekommendationer på värdet för ett anpassat profilattribut.

>[!NOTE]
>
>Anpassade profilparametrar kan skickas till [!DNL Target] via JavaScript, API eller integreringar. Mer information om anpassade profilattribut finns i [Besökarprofiler](/help/main/c-target/c-visitor-profile/visitor-profile.md).

Anta till exempel att du vill visa rekommenderade filmer baserat på den film som en användare senast lade till i kön.

1. Klicka på **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Klicka på **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**.

1. Fyll i informationen i avsnittet [Grundläggande information](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. I avsnittet [Rekommenderad algoritm](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo) väljer du **[!UICONTROL Item Based]** i listan **[!UICONTROL Algorithm Type]**.

1. Välj **[!UICONTROL People Who Viewed This, Viewed That]** i listan **[!UICONTROL Algorithm]**.

1. Välj ditt anpassade profilattribut i listan **[!UICONTROL Recommendation Key]** (till exempel [!UICONTROL Last Show Added to Watchlist]).

   ![Dialogrutan Skapa nytt villkor](assets/custom-key1.png)

## Visa villkorsinformation {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Du kan visa villkorsinformation på ett snabbkort genom att hålla muspekaren över ett kort och klicka på ikonen Information på ett villkorskort utan att öppna villkoret.

![Villkorskortshovring](/help/main/c-recommendations/c-algorithms/assets/criteria_hover.png)

Klicka på fliken **[!UICONTROL Algorithm Info]** om du vill visa allmän information om de valda villkoren, inklusive namn, beskrivningar, industrivertikalt, sidtyp(er), rekommendationsnyckel, rekommendationslogik och algoritm-ID.

![Fliken Information om algoritm](/help/main/c-recommendations/c-algorithms/assets/criteria_info.png)

Klicka på fliken **[!UICONTROL Algorithm Usage]** för att visa en lista över aktiviteter som refererar till de valda villkoren. Kortet innehåller aktiva, inaktiva och utkastsaktiviteter. Klicka på listrutan Aktiva aktiviteter/Inaktiva aktiviteter/Utkastaktiviteter för att visa hela listan med aktiviteter som refererar till det villkoret. Du kan klicka på aktivitetslänken för att öppna aktiviteten för redigering.

![Fliken Algoritmanvändning](/help/main/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>Funktionen [!UICONTROL Algorithm Usage] stöds för närvarande endast för Recommendations-aktiviteter. Den här funktionen stöds för närvarande inte för A/B Test-, Auto-Allocate-, Auto-Target- och Experience Targeting-aktiviteter (XT) som innehåller [rekommendationer som ett erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).
