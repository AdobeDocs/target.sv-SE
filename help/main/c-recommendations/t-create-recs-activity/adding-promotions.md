---
keywords: kampanjer;frontkampanjer;back promotions;promotions type;list of items;Promoby attribute;Promot a collection
description: Lär dig hur du lägger till framhävda objekt och styr deras placering i Adobe [!DNL Target] Recommendations designar. Du kan lägga till statiska och dynamiska kampanjer.
title: Hur lägger jag till kampanjer i Recommendations Designs?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 0%

---

# Lägg till kampanjer

Lägg till framhävda objekt och styr deras placering i [!DNL Adobe Target Recommendations] design. Du kan lägga till statiska och dynamiska kampanjer.

>[!IMPORTANT]
>
>Statiska och dynamiska exkluderingsregler är kraftfulla funktioner som kan hjälpa er med marknadsföringen. Detaljerad information, exempel och användningsscenarier finns i [Använd dynamiska och statiska inkluderingsregler](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

När du skapar en [!DNL Recommendations] har du möjlighet att inkludera framhävda objekt i [!DNL Recommendations] design. Kampanjer använder tillgängliga kortplatser i en design och har företräde framför villkorsresultat och rekommendationer för säkerhetskopiering. Om din design till exempel har sex platser och du använder två av dem för kampanjer, är fyra platser tillgängliga för artiklar som rekommenderas baserat på kriterier.

Kampanjer dedupliceras mot objekt som rekommenderas av kriterierna för din aktivitet, så ett visst objekt visas inte två gånger i ett enda rekommendationsfack.

Du kan befordra specifika element, dynamiskt befordra element, befordra element baserat på attribut eller befordra samlingar.

![[!UICONTROL Front Promotion] och [!UICONTROL Back Promotion] alternativ i [!DNL Target] UI](assets/add_promotion_toggles.png)

>[!NOTE]
>
>Kampanjer ändrar CSV-strukturen och utdata. Dessa ändringar kan påverka externa processer som innehåller CSV, t.ex. e-post.

1. På **[!UICONTROL Options]** klickar du på **[!UICONTROL Front Promotion]** eller **[!UICONTROL Back Promotion]** växla.

   Följande bild visar [!UICONTROL Front Promotion] växla i läget &quot;På&quot;.

   ![Lägg till alternativ för Främre befordran](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   Du kan infoga erbjudanden båda före *och* efter sökkriterierna.

1. Ange antalet designplatser som ska användas för upphöjda objekt.

   Du kan använda upp till 20 kortplatser, beroende på dina [!DNL Recommendations] design. Varje plats du använder blir inte tillgänglig för rekommendationer som returneras baserat på dina kriterier.

1. Ange startdatum och slutdatum för dina befordrade objekt.

   Om du inte anger något startdatum börjar kampanjen direkt. Om du inte anger ett slutdatum körs kampanjen oavbrutet.

1. Välj en **[!UICONTROL Promotion Type]**.

   * Välj **[!UICONTROL List of items]** och anger `entity.id` värden, avgränsade med kommatecken, för de specifika objekt som du vill befordra.

   * Välj **[!UICONTROL Promote by attribute]** och lägg till regler för att definiera attributen för de objekt som du vill befordra.

      Om du väljer [!UICONTROL Promote by Attribute]kan du skapa dynamiska matchningar. Mer information finns i [Använd dynamiska och statiska inkluderingsregler](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * Välj **[!UICONTROL Promote a collection]** och välj den samling med objekt som du vill befordra.

      Du kan skapa nya samlingar som du kan använda för kampanjer. Se [Skapa en samling](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) för mer information.
   Om du valde **[!UICONTROL List of Items]** som **[!UICONTROL Promotion Type]** kan du välja **[!UICONTROL Randomize Item Order]** om du vill.

   Standardsorteringsordning för [!UICONTROL List of Items] baseras på den ordning du har angett i [!DNL Target] Gränssnitt eller API. Om din lista innehåller fler objekt än det antal platser som du har angett för kampanjer visas [!UICONTROL Randomize Item Order] det här alternativet gör att de upphöjda objekt som visas i din design slumpmässigt väljs ut. Om du väljer det här alternativet får du [!DNL Target] slumpmässigt välja artiklar som är aktiverade för kampanjer i mallen från hela erbjudandelistan för varje träff.

   Om dina enheter inte har en `entity.value` attribute (you do not sell products) you can pass a numeric value into the `entity.value` -attribut, t.ex. publiceringsdatum. I det här fallet kan upphöjda objekt befordras baserat på det senaste publiceringsdatumet, i fallande ordning. The `entity.value` Attributet är av typen double. den godkänner inte strängar.

   Om du valde **[!UICONTROL Promote by Attribute]** eller **[!UICONTROL Promote a Collection]** Alternativet att göra ordern slumpmässig är inte tillämpligt.

   När du befordrar specifika objekt med [!UICONTROL Promote by Attribute] eller [!UICONTROL Promote a Collection] alternativ, den standardordning i vilken objekten presenteras baseras på `entity.value` i fallande numerisk ordning.

   I följande tabell visas skillnaderna mellan dessa alternativ:

   | Erbjudandetyp | Standardsortering | Säkerhetskopiera sortering | Alternativet för dynamisk filtrering |
   | --- | --- | --- | --- |
   | [!UICONTROL List of Items] | Ordning angiven i målgränssnittet/API | Slumpmässig (när den väljs via UI/API) | Nej |
   | [!UICONTROL Promote by Attribute] | `entity.value` (fallande ordning) | Ingen slumpgenerering | Ja |
   | [!UICONTROL Promote a Collection] | `entity.value` (fallande ordning) | Ingen slumpgenerering | Nej |

1. Klicka på **[!UICONTROL Save]**.

Kampanjer tillämpas på alla upplevelser i aktiviteten.
