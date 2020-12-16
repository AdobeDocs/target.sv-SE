---
keywords: promotions;front promotions;back promotions;promotions type;list of items;promote by attribute;promote a collection
description: Lägg in framhävda objekt och styr deras placering i Adobe Target Recommendations. Du kan lägga till statiska och dynamiska kampanjer.
title: Lägg in kampanjer i Adobe Target Recommendations.
feature: recs creation
translation-type: tm+mt
source-git-commit: 180a8064019e8d4a44db13923aad7422f67ccf3f
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Lägg till kampanjer

Lägg in framhävda objekt och styr deras placering i Adobe Target Recommendations. Du kan lägga till statiska och dynamiska kampanjer.

>[!IMPORTANT]
>
>Statiska och dynamiska exkluderingsregler är kraftfulla funktioner som kan hjälpa er med marknadsföringen. Detaljerad information, exempel och användningsscenarier finns i [Använd regler](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)för dynamisk och statisk infogning.

När du skapar en [!DNL Recommendations] aktivitet kan du välja att ta med framhävda objekt i din [!DNL Recommendations] design. Kampanjer använder tillgängliga kortplatser i en design och har företräde framför villkorsresultat och rekommendationer för säkerhetskopiering. Om din design till exempel har sex platser och du använder två av dem för kampanjer, är fyra platser tillgängliga för artiklar som rekommenderas baserat på kriterier.

Kampanjer dedupliceras mot objekt som rekommenderas av kriterierna för din aktivitet, så ett visst objekt visas inte två gånger i ett enda rekommendationsfack.

Du kan befordra specifika element, dynamiskt befordra element, befordra element baserat på attribut eller befordra samlingar.

![](assets/add_promotion_toggles.png)

>[!NOTE]
>
>Kampanjer ändrar CSV-strukturen och utdata. Dessa ändringar kan påverka externa processer som innehåller CSV, t.ex. e-post.

1. På **[!UICONTROL Options]** sidan klickar du på **[!UICONTROL Front Promotion]** eller **[!UICONTROL Back Promotion]** växlar.

   Följande bild visar [!UICONTROL Front Promotion] växlingsknappen i läget &quot;På&quot;.

   ![Lägg till alternativ för Främre befordran](/help/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   Du kan infoga erbjudanden både före *och* efter sökresultatet.
1. Ange antalet designplatser som ska användas för upphöjda objekt.

   Du kan använda upp till 20 kortplatser, beroende på din [!DNL Recommendations] design. Varje plats du använder blir inte tillgänglig för rekommendationer som returneras baserat på dina kriterier.

1. Ange startdatum och slutdatum för dina befordrade objekt.

   Om du inte anger något startdatum börjar kampanjen direkt. Om du inte anger ett slutdatum körs kampanjen oavbrutet.

1. Välj en **[!UICONTROL Promotion Type]**.

   * Markera **[!UICONTROL List of items]** och ange `entity.id` värden, avgränsade med kommatecken, för de specifika objekt som du vill befordra.

   * Välj **[!UICONTROL Promote by attribute]** och lägg till regler för att definiera attributen för de objekt som du vill befordra.

      Om du väljer Befordra efter attribut kan du skapa dynamiska matchningar. Mer information finns i [Använda dynamiska och statiska inkluderingsregler](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * Markera **[!UICONTROL Promote a collection]** och välj den samling med objekt som du vill befordra.

      Du kan skapa nya samlingar som du kan använda för kampanjer. Mer information finns i [Skapa en samling](/help/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) .
   Om du väljer **[!UICONTROL List of Items]** som **[!UICONTROL Promotion Type]** markeringsruta kan du markera **[!UICONTROL Randomize Item Order]** kryssrutan.

   Standardsorteringsordningen för [!UICONTROL List of Items] baseras på den ordning du angav i målgränssnittet eller API:t. Om din lista innehåller fler objekt än det antal platser som du anger för kampanjer, kommer alternativet att göra det till en slumpmässig slumpgenerering av de framhävda objekt som visas i din design. [!UICONTROL Randomize Item Order] Om du väljer det här alternativet väljs [!DNL Target] objekten som är aktiverade för kampanjer i mallen slumpmässigt från hela erbjudandeuppsättningen för varje träff.

   Om dina enheter inte har något `entity.value` -attribut (du säljer till exempel inte produkter) kan du skicka ett numeriskt värde till `entity.value` attributet, till exempel publiceringsdatumet. I det här fallet kan upphöjda objekt befordras baserat på det senaste publiceringsdatumet, i fallande ordning. Attributet `entity.value` är av typen double; den godkänner inte strängar.

   Om du har valt alternativet **[!UICONTROL Promote by Attribute]** eller **[!UICONTROL Promote a Collection]** alternativet, kan du inte göra en slumpmässig beställning.

   När du befordrar specifika objekt med alternativen [!UICONTROL Promote by Attribute] eller [!UICONTROL Promote a Collection] , baseras den standardordning i vilken objekten presenteras på `entity.value` attributet, i fallande numerisk ordning.

   I följande tabell visas skillnaderna mellan dessa alternativ:

   | Erbjudandetyp | Standardsortering | Säkerhetskopieringssortering | Alternativ för dynamisk filtrering |
   | --- | --- | --- | --- |
   | Lista över objekt | Ordning angiven i målgränssnittet/API | Slumpmässigt (när det väljs via UI/API | Nej |
   | Befordra efter attribut | `entity.value` (fallande ordning) | Slumpmässigt för varje begäran (när det inte finns något `entity.value` attribut) | Ja |
   | Befordra en samling | `entity.value` (fallande ordning) | Slumpmässigt för varje begäran (när det inte finns något `entity.value` attribut) | Nej |

1. Klicka på **[!UICONTROL Save]**.

Kampanjer tillämpas på alla upplevelser i aktiviteten.
