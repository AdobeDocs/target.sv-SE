---
keywords: Rekommendationer;erbjudande
description: Lär dig hur du använder Adobe Recommendations som ett erbjudande i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och Experience Targeting-aktiviteter (XT).
title: Hur använder jag rekommendationer som erbjudande i andra aktivitetstyper?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
source-git-commit: f848c79cb95009b5810a1707d04e548a57220e12
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 0%

---

# Rekommendationer som ett erbjudande

Du kan nu inkludera rekommendationer inuti [!UICONTROL A/B Test] (inklusive [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]) och [!UICONTROL Experience Targeting] (XT) aktiviteter.

Den här funktionen öppnar upp helt nya funktioner, som:

* Testa och målinrikta rekommendationer och innehåll som inte är rekommendationer inom samma aktivitet.
* Experimentera enkelt med olika rekommendationer på sidan, t.ex. i vilken ordning olika rekommendationer ska ges.
* Skicka automatiskt trafik till den bästa rekommenderade upplevelsen med [!UICONTROL Auto-Allocate].
* Tilldela besökare dynamiskt anpassade rekommendationer baserat på deras profil med [!UICONTROL Auto-Target].

Om du vill komma igång skapar du en [!UICONTROL A/B Test]- eller [!UICONTROL Experience Targeting]-aktivitet med [!UICONTROL Visual Experience Composer] och använder åtgärden [!UICONTROL Insert Before], [!UICONTROL Insert After] eller [!UICONTROL Replace With] för att lägga till rekommendationer till en upplevelse.

## Lägg till en rekommendation som ett erbjudande i en A/B-test eller en XT-aktivitet

1. Starta det guidade trestegsarbetsflödet med Visual Experience Composer (VEC) för att skapa en [A/B Test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)- eller [Experience Targeting](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)-aktivitet (XT).

   >[!NOTE]
   >
   >För A/B-tester måste du komma ihåg att du kan välja alternativet [Automatisk fördelning](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) för att automatiskt överföra trafik till de bästa rekommendationerna eller alternativet [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) för att tilldela besökare anpassade rekommendationer baserat på deras profil.

1. När du skapar en [upplevelse](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) klickar du på elementet som du vill lägga till en rekommendation till som ett erbjudande, klickar på **[!UICONTROL Replace Content]** och väljer sedan **[!UICONTROL Recommendation]**.

   ![Infoga rekommendation som ett erbjudande](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. Välj bland följande alternativ för att visa vanliga rekommendationer per sidtyp:

   * Kundsida
   * Kategorisida
   * Hemsida
   * Landningssida
   * Produktsida
   * Sökresultatsida
   * Tack
   * Övriga

1. Välj önskat [villkor](/help/main/c-recommendations/c-algorithms/algorithms.md) och klicka sedan på [!UICONTROL Next].
1. Välj önskad [design](/help/main/c-recommendations/c-design-overview/design-overview.md) och klicka sedan på [!UICONTROL Next].
1. Ange följande i dialogrutan [!UICONTROL Options]:

   * Välj en [samling](/help/main/c-recommendations/c-products/collections.md).
   * Konfigurera alternativen för [Främre befordran och Bakåt &#x200B;](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md) efter behov.

1. Klicka på [!UICONTROL Save].
1. Slutför konfigurationen av A/B-testaktiviteten eller XT-aktiviteten med det guidade arbetsflödet i tre delar.

## Redigera konfigurationen för ett rekommendationserbjudande

Det finns två sätt att redigera konfigurationen för ett erbjudande:

* Använda menyn [!UICONTROL Edit]
* Använda panelen [!UICONTROL Modifications]

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

1. Klicka på ikonen [!UICONTROL Modifications] **( `</>` )** för att visa rutan [Ändringar](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Håll pekaren över önskad åtgärd och klicka sedan på ikonen **[!UICONTROL Edit]**.

   ![Panelen Ändringar](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. Redigera.

## Ta bort ett rekommendationer

Det finns två sätt att ta bort ett rekommendationserbjudande:

* Använda menyn [!UICONTROL Edit]
* Använda panelen [!UICONTROL Modifications]

### Ta bort ett rekommendationserbjudande med hjälp av menyn Redigera

1. Klicka på erbjudandet som du vill ta bort och klicka sedan på **[!UICONTROL Layout > Remove]**.

   ![Ta bort](/help/main/c-recommendations/assets/recs-offer-remove.png)

### Ta bort ett rekommendationserbjudande med hjälp av panelen Ändringar

1. Klicka på ikonen [!UICONTROL Modifications] **( &lt;/> )** för att visa rutan [Ändringar](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Håll pekaren över önskad åtgärd och klicka sedan på ikonen [!UICONTROL Delete].

   ![Ta bort ikon](/help/main/c-recommendations/assets/recs-offer-delete.png)

### Visa rekommendationserbjudandets status {#status}

Rekommendationserbjudandets (algoritm) status visas längst ned på sidan [!UICONTROL Overview] för A/B Test- och XT-aktiviteter som innehåller rekommendationer:

* Resultatförberedda
* Resultaten är inte klara
* Feed-fel

![Status för rekommenderat erbjudande](/help/main/c-recommendations/assets/recs-offer-status.png)

## Utbildningsvideo: Rekommendationer som ett erbjudande ![Översikt &#x200B;](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
