---
keywords: Recommendations;erbjudande
description: Lär dig hur du använder Adobe Recommendations som ett erbjudande i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och Experience Targeting-aktiviteter (XT).
title: Hur använder jag Recommendations som erbjudande i andra aktivitetstyper?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 0%

---

# Recommendations som erbjudande

Nu kan du inkludera rekommendationer i [!UICONTROL A/B Test] (inklusive [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]) och [!UICONTROL Experience Targeting] (XT) aktiviteter.

Den här funktionen öppnar upp helt nya funktioner, som:

* Testa och målinrikta rekommendationer och innehåll som inte är rekommendationer inom samma aktivitet.
* Experimentera enkelt med olika rekommendationer på sidan, t.ex. i vilken ordning olika rekommendationer ska ges.
* Skicka automatiskt trafik till den bästa rekommenderade upplevelsen med [!UICONTROL Auto-Allocate].
* Tilldela besökare dynamiskt skräddarsydda rekommendationer baserat på deras profil med [!UICONTROL Auto-Target].

Skapa en [!UICONTROL A/B Test] eller [!UICONTROL Experience Targeting] aktivitet med [!UICONTROL Visual Experience Composer] och använder [!UICONTROL Insert Before], [!UICONTROL Insert After], eller [!UICONTROL Replace With] åtgärd för att lägga till rekommendationer i en upplevelse.

## Lägg till en rekommendation som ett erbjudande i en A/B-test eller en XT-aktivitet

1. Starta det guidade arbetsflödet i tre steg med Visual Experience Composer (VEC) för att skapa ett [A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) eller [Experience Targeting](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT) aktivitet.

   >[!NOTE]
   >
   >Kom ihåg att du kan välja [Automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) möjlighet att automatiskt flytta trafik till de bästa rekommendationerna eller [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) möjlighet att tilldela besökare skräddarsydda rekommendationer baserat på deras profil.

1. När en [upplevelse](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), klicka på elementet som du vill lägga till en rekommendation i som ett erbjudande, välj **[!UICONTROL Insert Before]**, **[!UICONTROL Insert After]**, eller **[!UICONTROL Replace With]** åtgärd, välj [!UICONTROL Recommendation].

   Följande bild visar [!UICONTROL Insert After > Recommendation] alternativ.

   ![Infoga rekommendation som erbjudande](/help/main/c-recommendations/assets/replace-after-recommendations.png)

1. Välj bland följande alternativ för att visa vanliga rekommendationer per sidtyp:

   * Kundsida
   * Kategorisida
   * Hemsida
   * Landningssida
   * Produktsida
   * Sökresultatsida
   * Tack
   * Övriga

1. Markera önskat [kriterier](/help/main/c-recommendations/c-algorithms/algorithms.md)och sedan klicka [!UICONTROL Next].
1. Markera önskat [design](/help/main/c-recommendations/c-design-overview/design-overview.md)och sedan klicka [!UICONTROL Next].
1. I [!UICONTROL Options] anger du följande:

   * Välj en [samling](/help/main/c-recommendations/c-products/collections.md).
   * Konfigurera [Främre kampanj och Bakåtmarknadsföring](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md) vid behov.

1. Klicka på [!UICONTROL Save].
1. Slutför konfigurationen av A/B-testaktiviteten eller XT-aktiviteten med det guidade arbetsflödet i tre delar.

## Redigera konfigurationen för ett rekommendationserbjudande

Det finns två sätt att redigera konfigurationen för ett erbjudande:

* Använda [!UICONTROL Edit] meny
* Använda [!UICONTROL Modifications] panel

### Redigera ett rekommendationserbjudande med Redigera-menyn

1. Klicka på erbjudandet som du vill redigera och klicka sedan på **[!UICONTROL Edit]**.

   ![Redigera rekommendationserbjudande](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. Välj bland följande alternativ:

   * [Ändra villkor](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [Ändra design](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [Ändra samling](/help/main/c-recommendations/c-products/collections.md)
   * [Ändra kampanj](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. Redigera.

### Redigera ett rekommendationserbjudande med hjälp av panelen Ändringar

1. Klicka på [!UICONTROL Modifications] icon  **( `</>` )** för att visa [Ändringar](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) fönster.
1. Håll muspekaren över önskad åtgärd och klicka sedan på **[!UICONTROL Edit]** ikon.

   ![Panelen Ändringar](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. Redigera.

## Ta bort ett rekommendationserbjudande

Det finns två sätt att ta bort ett rekommendationserbjudande:

* Använda [!UICONTROL Edit] meny
* Använda [!UICONTROL Modifications] panel

### Ta bort ett rekommendationserbjudande med hjälp av menyn Redigera

1. Klicka på erbjudandet som du vill ta bort och klicka sedan på **[!UICONTROL Layout > Remove]**.

   ![Ta bort](/help/main/c-recommendations/assets/recs-offer-remove.png)

### Ta bort ett rekommendationserbjudande med hjälp av panelen Ändringar

1. Klicka på [!UICONTROL Modifications] icon **( &lt;/> )** för att visa [Ändringar](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) fönster.
1. Håll muspekaren över önskad åtgärd och klicka sedan på [!UICONTROL Delete] ikon.

   ![Ikonen Ta bort](/help/main/c-recommendations/assets/recs-offer-delete.png)

### Visa rekommendationserbjudandets status {#status}

Rekommendationserbjudandets (algoritm) status visas längst ned i [!UICONTROL Overview] sida för A/B Test- och XT-aktiviteter som innehåller Recommendations erbjuder:

* Resultatförberedda
* Resultaten är inte klara
* Feed-fel

![Recommendations erbjudandestatus](/help/main/c-recommendations/assets/recs-offer-status.png)

## Utbildningsvideo: Recommendations som erbjudande ![Märket Översikt](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
