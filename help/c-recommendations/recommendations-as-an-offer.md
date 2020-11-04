---
keywords: Recommendations;offer
description: Adobe Recommendations som ett erbjudande i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting)
title: Adobe Recommendations som ett erbjudande i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och XT-aktiviteter (Experience Targeting)
feature: recs creation
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 0%

---


# ![PREMIUM](/help/assets/premium.png) Recommendations som erbjudande

Nu kan du inkludera rekommendationer inuti [!UICONTROL A/B Test] (inklusive [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]) och [!UICONTROL Experience Targeting] (XT) aktiviteter.

Den här funktionen öppnar upp helt nya funktioner, som:

* Testa och målinrikta rekommendationer och innehåll som inte är rekommendationer inom samma aktivitet.
* Experimentera enkelt med olika rekommendationer på sidan, t.ex. i vilken ordning olika rekommendationer ska ges.
* Skicka automatiskt trafik till den bästa rekommenderade upplevelsen med [!UICONTROL Auto-Allocate].
* Tilldela besökare dynamiskt skräddarsydda rekommendationer baserat på deras profil med [!UICONTROL Auto-Target].

Om du vill komma igång skapar du en [!UICONTROL A/B Test] eller [!UICONTROL Experience Targeting] aktivitet med hjälp av [!UICONTROL Visual Experience Composer] och använder [!UICONTROL Insert Before], [!UICONTROL Insert After]eller [!UICONTROL Replace With] åtgärd för att lägga till rekommendationer i en upplevelse.

## Lägg till en rekommendation som ett erbjudande i en A/B-test eller en XT-aktivitet

1. Starta det guidade trestegsarbetsflödet med Visual Experience Composer (VEC) för att skapa en [A/B Test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) - eller [Experience Targeting](/help/c-activities/t-experience-target/t-xt-create/xt-create.md) -aktivitet (XT).

   >[!NOTE]
   >
   >För A/B-tester måste du komma ihåg att du kan välja alternativet [Automatisk fördelning](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) för att automatiskt överföra trafik till de bästa rekommendationerna eller alternativet [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md) för att tilldela besökare anpassade rekommendationer baserat på deras profil.

1. När du skapar en [upplevelse](/help/c-experiences/c-visual-experience-composer/viztarget-options.md)klickar du på elementet som du vill lägga till en rekommendation till som ett erbjudande, väljer **[!UICONTROL Insert Before]**, **[!UICONTROL Insert After]** eller **[!UICONTROL Replace With]** väljer åtgärd och sedan [!UICONTROL Recommendation].

   I följande bild visas [!UICONTROL Insert After > Recommendation] alternativet.

   ![Infoga rekommendation som erbjudande](/help/c-recommendations/assets/replace-after-recommendations.png)

1. Välj bland följande alternativ för att visa vanliga rekommendationer per sidtyp:

   * Kundsida
   * Kategorisida
   * Hemsida
   * Landningssida
   * Produktsida
   * Sökresultatsida
   * Tack
   * Övriga

1. Markera önskade [villkor](/help/c-recommendations/c-algorithms/algorithms.md)och klicka sedan på [!UICONTROL Next].
1. Markera önskad [design](/help/c-recommendations/c-design-overview/design-overview.md)och klicka sedan [!UICONTROL Next].
1. Ange följande i [!UICONTROL Options] dialogrutan:

   * Välj en [samling](/help/c-recommendations/c-products/collections.md).
   * Konfigurera alternativen för [Front Promotion och Back Promotion](/help/c-recommendations/t-create-recs-activity/adding-promotions.md) efter behov.

1. Klicka på [!UICONTROL Save].
1. Slutför konfigurationen av A/B-testaktiviteten eller XT-aktiviteten med det guidade arbetsflödet i tre delar.

## Redigera konfigurationen för ett rekommendationserbjudande

Det finns två sätt att redigera konfigurationen för ett erbjudande:

* Använda [!UICONTROL Edit] menyn
* Använda [!UICONTROL Modifications] panelen

### Redigera ett rekommendationserbjudande med Redigera-menyn

1. Klicka på det erbjudande du vill redigera och klicka sedan på **[!UICONTROL Edit]**.

   ![Redigera rekommendationserbjudande](/help/c-recommendations/assets/recs-offer-edit.png)

1. Välj bland följande alternativ:

   * [Ändra villkor](/help/c-recommendations/c-algorithms/algorithms.md)
   * [Ändra design](/help/c-recommendations/c-design-overview/design-overview.md)
   * [Ändra samling](/help/c-recommendations/c-products/collections.md)
   * [Ändra kampanj](/help/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. Redigera.

### Redigera ett rekommendationserbjudande med hjälp av panelen Ändringar

1. Klicka på [!UICONTROL Modifications] ikonen **( `</>` )** för att visa [ändringspanelen](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) .
1. Håll muspekaren över önskat funktionsmakro och klicka sedan på **[!UICONTROL Edit]** -ikonen.

   ![Panelen Ändringar](/help/c-recommendations/assets/recs-offer-modifications.png)

1. Redigera.

## Ta bort ett rekommendationserbjudande

Det finns två sätt att ta bort ett rekommendationserbjudande:

* Använda [!UICONTROL Edit] menyn
* Använda [!UICONTROL Modifications] panelen

### Ta bort ett rekommendationserbjudande med hjälp av menyn Redigera

1. Klicka på det erbjudande du vill ta bort och klicka sedan på **[!UICONTROL Layout > Remove]**.

   ![Ta bort](/help/c-recommendations/assets/recs-offer-remove.png)

### Ta bort ett rekommendationserbjudande med hjälp av panelen Ändringar

1. Klicka på [!UICONTROL Modifications] ikonen **( &lt;/> )** för att visa rutan [Ändringar](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) .
1. Håll muspekaren över önskat funktionsmakro och klicka sedan på [!UICONTROL Delete] -ikonen.

   ![Ikonen Ta bort](/help/c-recommendations/assets/recs-offer-delete.png)

### Visa rekommendationserbjudandets status {#status}

Rekommendationserbjudandets (algoritm) status visas längst ned på [!UICONTROL Overview] sidan för A/B Test- och XT-aktiviteter som innehåller Recommendations:

* Resultatförberedda
* Resultaten är inte klara
* Feed-fel

![Recommendations erbjudandestatus](/help/c-recommendations/assets/recs-offer-status.png)

## Utbildningsvideo: Recommendations som ![skylt för erbjudandeöversikt](/help/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)