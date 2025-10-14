---
keywords: kampanjer;frontkampanjer;back promotions;promotions type;list of items;Promoby attribute;Promot a collection
description: Lär dig hur du lägger till framhävda objekt och styr deras placering i dina Adobe [!DNL Target] Recommendations-designer. Du kan lägga till statiska och dynamiska kampanjer.
title: Hur lägger jag till kampanjer i rekommendationsdesign?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---

# Lägg till kampanjer

Lägg till framhävda objekt och kontrollera deras placering i dina [!DNL Adobe Target Recommendations]-designer. Du kan lägga till statiska och dynamiska kampanjer.

>[!IMPORTANT]
>
>Statiska och dynamiska exkluderingsregler är kraftfulla funktioner som kan hjälpa er med marknadsföringen. Detaljerad information, exempel och användningsscenarier finns i [Använd dynamiska och statiska inkluderingsregler](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

När du skapar en [!DNL Recommendations]-aktivitet kan du välja att ta med framhävda objekt i din [!DNL Recommendations]-design. Kampanjer använder tillgängliga kortplatser i en design och har företräde framför villkorsresultat och rekommendationer för säkerhetskopiering. Om din design till exempel har sex platser och du använder två av dem för kampanjer, är fyra platser tillgängliga för artiklar som rekommenderas baserat på kriterier.

Kampanjer dedupliceras mot objekt som rekommenderas av kriterierna för din aktivitet, så ett visst objekt visas inte två gånger i ett enda rekommendationsfack.

Du kan befordra specifika element, dynamiskt befordra element, befordra element baserat på attribut eller befordra samlingar.

Alternativ för ![[!UICONTROL Front Promotion] och [!UICONTROL Back Promotion] i [!DNL Target] användargränssnittet &#x200B;](assets/add_promotion_toggles.png)

>[!NOTE]
>
>Kampanjer ändrar CSV-strukturen och utdata. Dessa ändringar kan påverka externa processer som innehåller CSV, t.ex. e-post.

1. Klicka på växlingsknappen **[!UICONTROL Options]** eller **[!UICONTROL Front Promotion]** på sidan **[!UICONTROL Back Promotion]**.

   Följande bild visar växlingen [!UICONTROL Front Promotion] i läget &quot;På&quot;.

   ![Lägg till alternativ för framhävning](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   Du kan infoga kampanjer både före *och* efter sökkriteriernas resultat.

1. Ange antalet designplatser som ska användas för upphöjda objekt.

   Du kan använda upp till 20 platser, beroende på din [!DNL Recommendations]-design. Varje plats du använder blir inte tillgänglig för rekommendationer som returneras baserat på dina kriterier.

1. Ange startdatum och slutdatum för dina befordrade objekt.

   Om du inte anger något startdatum börjar kampanjen direkt. Om du inte anger ett slutdatum körs kampanjen oavbrutet.

1. Välj en **[!UICONTROL Promotion Type]**.

   * Markera **[!UICONTROL List of items]** och ange `entity.id`-värden, avgränsade med kommatecken, för de specifika objekt som du vill befordra.

   * Välj **[!UICONTROL Promote by attribute]** och lägg till regler för att definiera attributen för de objekt som du vill befordra.

     Om du väljer [!UICONTROL Promote by Attribute] kan du skapa dynamiska matchningar. Mer information finns i [Använd dynamiska och statiska inkluderingsregler](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * Välj **[!UICONTROL Promote a collection]** och välj den samling med objekt som du vill befordra.

     Du kan skapa nya samlingar som du kan använda för kampanjer. Mer information finns i [Skapa en samling](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08).

   Om du väljer **[!UICONTROL List of Items]** som **[!UICONTROL Promotion Type]** kan du markera kryssrutan **[!UICONTROL Randomize Item Order]** om du vill.

   Standardsorteringsordningen för [!UICONTROL List of Items] baseras på den ordning som du angav i [!DNL Target]-gränssnittet eller API:t. Om din lista innehåller fler objekt än det antal platser som du anger för kampanjer, randomiserar alternativet [!UICONTROL Randomize Item Order] de framhävda objekt som visas i din design. Om du väljer det här alternativet väljs [!DNL Target] slumpmässigt ut de objekt som är aktiverade för kampanjer i mallen från hela erbjudandeuppsättningen för varje träff.

   Om dina enheter inte har något `entity.value`-attribut (du säljer till exempel inte produkter) kan du skicka ett numeriskt värde till `entity.value`-attributet, till exempel publiceringsdatumet. I det här fallet kan upphöjda objekt befordras baserat på det senaste publiceringsdatumet, i fallande ordning. Attributet `entity.value` är av typen dubbel. Strängar accepteras inte.

   Om du valde alternativet **[!UICONTROL Promote by Attribute]** eller **[!UICONTROL Promote a Collection]** kan du inte använda alternativet att slumpmässigt utföra beställningen.

   När du befordrar specifika objekt med alternativen [!UICONTROL Promote by Attribute] eller [!UICONTROL Promote a Collection], baseras den standardordning i vilken objekten presenteras på attributet `entity.value` i fallande numerisk ordning.

   I följande tabell visas skillnaderna mellan dessa alternativ:

   | Erbjudandetyp | Standardsortering | Säkerhetskopiera sortering | Alternativet för dynamisk filtrering |
   | --- | --- | --- | --- |
   | [!UICONTROL List of Items] | Ordning angiven i målgränssnittet/API | Slumpmässig (när den väljs via UI/API) | Nej |
   | [!UICONTROL Promote by Attribute] | `entity.value` (fallande ordning) | Ingen slumpgenerering | Ja |
   | [!UICONTROL Promote a Collection] | `entity.value` (fallande ordning) | Ingen slumpgenerering | Nej |

1. Klicka på **[!UICONTROL Save]**.

Kampanjer tillämpas på alla upplevelser i aktiviteten.
