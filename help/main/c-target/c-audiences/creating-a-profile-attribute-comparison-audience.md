---
keywords: målgrupp;benägenhet;profilattribut;jämför;jämförelse;skapa målgrupp;skapa målgrupp
description: Lär dig definiera en målgrupp för att jämföra två profilattribut.
title: Kan jag jämföra två profilattribut som kan användas i målgrupper?
feature: Audiences
exl-id: 033e90f1-5a05-4fce-a520-68826860a908
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---

# Skapa en målgrupp för profilattributsjämförelse

Definiera en målgrupp i [!DNL Adobe Target] om du vill jämföra två profilattribut för ditt [målgruppsbibliotek](/help/main/c-target/c-audiences/audiences.md) eller för en [målgrupp som bara är aktivt](/help/main/c-target/creating-activity-only-audience.md). Med operatorer, till exempel större än, mindre än eller lika med, kan du definiera en målgrupp för att dynamiskt jämföra värdena för två olika profilattribut.

>[!NOTE]
>
>Den här funktionen är endast tillgänglig för kategorin [[!UICONTROL Visitor Profile]](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

## Ökning {#section_303CBC78194D49A2A004945D425441E1}

Målgrupper definieras av regler som bestämmer vem som är inkluderad eller exkluderad från en [!DNL Target]-aktivitet. En målgruppsdefinition kan innehålla flera regler, och varje regel kan innehålla flera parametrar. Om en av reglerna som du inkluderar använder kategorin [!UICONTROL Visitor Profile] kan du definiera en regel baserat på ett besökarprofilattribut specifika värde eller jämföra värdet för det attributet med ett annat attribut för besökarprofilen.

Låt oss anta att du arbetar för ett möbelföretag och har överfört två kundbenägenhetspoäng till [!DNL Target]:

* Sannolikheten att köpa möbler till matsalar under de kommande 90 dagarna
* Sannolikheten att köpa möbler för vardagsrumsmöbler under de kommande 90 dagarna

Du kan skapa en målgrupp som definieras som att benägenheten att köpa möbler för matsalar är större än benägenheten att köpa möbler för vardagsrum. [!DNL Target] skulle sedan dynamiskt jämföra poängen för matsalen och livsrummets benägenhet för en viss besökare för att avgöra om besökaren uppfyller kraven för den här målgruppen.

Mer information finns i [Metoder för att hämta data till målet](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=sv-SE){target=_blank}.

## Skapa en målgrupp för profilattributsjämförelse {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. Klicka på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Namnge målgruppen och lägg till en valfri beskrivning.
1. Dra och släpp **[!UICONTROL Visitor Profile]** i rutan för målgruppsbyggaren.
1. Välj ett attribut i listrutan **[!UICONTROL Visitor Profile]**:

   ![Propensitetspoäng 1](assets/propensity_score_1.png)

1. Välj utvärderare:

   ![Propensitetspoäng 2](assets/propensity_score_2.png)

1. Välj **[!UICONTROL Attribute]** i listrutan **[!UICONTROL Choose Comparison Type]**.

   Jämförelsetypen för&quot;statiskt värde&quot; gör att du kan jämföra din besökarprofils attribut med specifika värden.

   ![Propensitetspoäng 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >Om du använder någon av standardkategorierna för besökarprofiler (till exempel Ny besökare eller Återkommande besökare) kan du bara välja alternativet för statiskt värde. Alternativen för dynamisk jämförelse är inte tillgängliga för standardkategorier. Andra exempel där alternativen för dynamisk jämförelse inte är tillgängliga är&quot;Första sidan av sessionen&quot;,&quot;Inte i andra tester&quot;,&quot;Inte första sidan av sessionen&quot; och&quot;Kategoritillhörighet&quot;.

1. Välj det ytterligare attribut du vill jämföra med det ursprungliga attributet.

   ![propensity_score_4 image](assets/propensity_score_4.png)

1. Klicka på **[!UICONTROL Done]**.

## Utbildningsvideoklippet ![Översikt](/help/main/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

Titta på följande video för mer information och ett scenario där du kan använda den här funktionen:

>[!VIDEO](https://video.tv.adobe.com/v/23218/)
