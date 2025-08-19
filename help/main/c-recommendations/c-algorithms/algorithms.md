---
keywords: rekommendationer;rekommendationsaktivitet;kriterier;algoritm;rekommendationsnyckel;anpassad nyckel;branschvertikal;återförsäljning;e-handel;lead generation;b2b;finansiella tjänster;media;publicering
description: Lär dig hur du använder villkor i Adobe [!DNL Target] [!DNL Recommendations].
title: Hur använder jag villkor i  [!DNL Target] rekommendationer?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%

---

# [!UICONTROL Criteria]

[!UICONTROL Criteria] i [!DNL Adobe Target] [!DNL Recommendations] är regler som avgör vilka produkter eller vilket innehåll som ska rekommenderas baserat på en förbestämd uppsättning besökarbeteenden. Kriterierna kan baseras på populära trender, en besökares aktuella och tidigare beteenden eller liknande produkter och innehåll. Du kan testa flera rekommendationstyper mot varandra genom att lägga till flera villkor.

I följande avsnitt beskrivs mer om villkorstangenterna och rekommendationslogiken som du kan använda för varje nyckel. Klicka på länkarna för mer detaljerad information.

## Branschvertikal {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

När du skapar villkor väljer du en bransch vertikalt baserad på syftet med dina rekommendationer.

| Branschvertikal | Mål |
|--- |--- |
| [!UICONTROL Retail/Ecommerce] | Konvertering som resulterar i inköp |
| [!UICONTROL Lead Generation/B2B/Financial Services] | Konvertering utan köp |
| [!UICONTROL Media/Publishing] | Engagemang |

Andra kriteriealternativ ändras beroende på vilken vertikal du väljer i branschen. Du kan ställa in din standardbransch vertikalt på sidan **[!UICONTROL Administration]>[!UICONTROL Recommendations]** eller så kan du ange branschvertikalt för varje villkor.

## Algoritmtyp {#section_885B3BB1B43048A88A8926F6B76FC482}

Den algoritmtyp du väljer avgör vilka algoritmer som är tillgängliga.

I följande tabell förklaras de olika algoritmtyperna och deras tillhörande algoritmer.

| Algoritmtyp | När ska du använda | Tillgängliga algoritmer |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | Utför rekommendationer baserat på användarens kundvagnsinnehåll. | <ul><li>[!UICONTROL People Who Viewed These, Also Viewed]</li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul>Mer information finns i [Kundvagnsbaserad](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) i *Basera rekommendationen på en rekommendationsnyckel*. |
| [!UICONTROL Popularity-Based] | Utför rekommendationer baserat på hur populärt ett objekt på webbplatsen är eller utifrån hur populärt det är att ha objekt inom en användares favoritkategori, varumärke, genre osv. | <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
| [!UICONTROL Item-Based] | Rekommendationer baserade på sökning efter liknande objekt för ett objekt som användaren för närvarande visar eller nyligen har visat. | <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
| [!UICONTROL User-Based] | Utför rekommendationer baserat på användarens beteende. | <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
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

## Visa villkorsinformation {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Du kan visa villkorsinformation genom att klicka på de önskade villkoren i kolumnen [!UICONTROL Name].

I avsnitten **[!UICONTROL Attributes]** och Detaljer kan du visa allmän information om de valda villkoren, inklusive dess [!UICONTROL Name], [!UICONTROL Description], [!UICONTROL Industry Vertical], [!UICONTROL Page Types], [!UICONTROL Recommendation Key], [!UICONTROL Recommendation Logic], [!UICONTROL Algorithm ID] och senast ändrade information (datum och vem som ändrade algoritmen).

I avsnittet **[!UICONTROL Usage]** kan du visa en lista med aktiviteter som refererar till de valda villkoren.

>[!NOTE]
>
>Funktionen [!UICONTROL Algorithm Usage] stöds för närvarande endast för [!DNL Recommendations]-aktiviteter. Den här funktionen stöds för närvarande inte för aktiviteter av typen [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] och [!UICONTROL Experience Targeting] (XT) som innehåller [rekommendationer som ett erbjudande](/help/main/c-recommendations/recommendations-as-an-offer.md).
