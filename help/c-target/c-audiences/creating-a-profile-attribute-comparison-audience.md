---
keywords: målgrupp;benägenhet;profilattribut;jämför;jämförelse;skapa målgrupp;skapa målgrupp
description: Definiera en målgrupp för att jämföra två profilattribut för målpublikbiblioteket eller för en målgrupp som bara är aktiv. Med operatorer, till exempel större än, mindre än eller lika med, kan du definiera en målgrupp för att dynamiskt jämföra värdena för två olika profilattribut.
title: Skapa en målgrupp för jämförelse av profilattribut
feature: Audiences
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---


# Skapa en målgrupp för profilattributsjämförelse{#create-a-profile-attribute-comparison-audience}

Definiera en målgrupp för att jämföra två profilattribut för ditt [målgruppsbibliotek](/help/c-target/c-audiences/audiences.md) eller i en [målgrupp som endast är aktivt](/help/c-target/creating-activity-only-audience.md). Med operatorer, till exempel större än, mindre än eller lika med, kan du definiera en målgrupp för att dynamiskt jämföra värdena för två olika profilattribut.

>[!NOTE]
>
>Den här funktionen är endast tillgänglig för kategorin [Besöksprofil](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

## Översikt {#section_303CBC78194D49A2A004945D425441E1}

Målgrupper definieras av regler som bestämmer vem som är inkluderad eller utesluten från en Target-aktivitet. En målgruppsdefinition kan innehålla flera regler, och varje regel kan innehålla flera parametrar. Om en av reglerna som du inkluderar använder kategorin Besökarprofil kan du definiera en regel baserat på ett besökarprofilattributs specifika värde eller jämföra värdet för det attributet med ett annat attribut för besökarprofil.

Låt oss anta att du arbetar för ett möbelföretag och överförde två kundbenägenhetspoängen till Target:

* Sannolikheten att köpa möbler till matsalar under de kommande 90 dagarna
* Sannolikheten att köpa möbler för vardagsrumsmöbler under de kommande 90 dagarna

Du kan skapa en målgrupp som definieras som att benägenheten att köpa möbler för matsalar är större än sannolikheten att köpa möbler för vardagsrum. Target skulle sedan dynamiskt jämföra poängen för matsalen och livsrummets benägenhet för en viss besökare för att avgöra om besökaren uppfyller kraven för denna målgrupp.

Mer information finns i [Metoder för att hämta data till målet](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17).

## Skapa en målgrupp för jämförelse av profilattribut {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. Klicka på **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]** > **[!UICONTROL Add Rule]** > **[!UICONTROL Visitor Profile]**.
1. Välj ett attribut i listrutan **[!UICONTROL Visitor Profile]**:

   ![Propensitetspoäng 1](assets/propensity_score_1.png)

1. Välj utvärderare:

   ![Propensitetspoäng 2](assets/propensity_score_2.png)

1. Välj **[!UICONTROL Attribute]** i listrutan **[!UICONTROL Choose Comparison Type]**.

   Jämförelsetypen för&quot;statiskt värde&quot; gör att du kan jämföra din besökarprofils attribut med specifika värden.

   ![Propensivt poäng 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >Om du använder någon av standardkategorierna för besökarprofiler i steg 1 (till exempel Ny besökare eller Återkommande besökare) kan du bara välja alternativet för statiskt värde. Alternativen för dynamisk jämförelse är inte tillgängliga för standardkategorier. Andra exempel där alternativen för dynamisk jämförelse inte är tillgängliga är&quot;Första sidan av sessionen&quot;,&quot;Inte i andra tester&quot;,&quot;Inte första sidan av sessionen&quot; och&quot;Kategoritillhörighet&quot;.

1. Välj det ytterligare attribut du vill jämföra med det ursprungliga attributet.

   ![](assets/propensity_score_4.png)

## Utbildningsvideo ![Översikt](/help/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

Titta på följande video för mer information och ett scenario där du kan använda den här funktionen:

>[!VIDEO](https://video.tv.adobe.com/v/23218/)