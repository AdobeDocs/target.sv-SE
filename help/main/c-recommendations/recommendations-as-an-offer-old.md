---
keywords: Rekommendationer;erbjudande
description: Lär dig hur du använder Adobe Recommendations som ett erbjudande i A/B-tester (inklusive Automatisk allokering och Automatiskt mål) och Experience Targeting-aktiviteter (XT).
title: Hur använder jag rekommendationer som erbjudande i andra aktivitetstyper?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 3821d868f45b85d2f6f0e204f9828544b759067b
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Rekommendationer som ett erbjudande

Du kan nu inkludera rekommendationer inuti [!UICONTROL A/B Test] (inklusive [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]) och [!UICONTROL Experience Targeting] (XT) aktiviteter.

Den här funktionen öppnar upp helt nya funktioner, som:

* Testa och målinrikta rekommendationer och innehåll som inte är rekommendationer inom samma aktivitet.
* Experimentera enkelt med hur rekommendationerna ska placeras på sidan, inklusive ordningen för olika rekommendationer.
* Skicka automatiskt trafik till den bästa rekommenderade upplevelsen med [!UICONTROL Auto-Allocate].
* Tilldela besökare dynamiskt anpassade rekommendationer baserat på deras profil med [!UICONTROL Auto-Target].

Om du vill komma igång skapar du en [!UICONTROL A/B Test]- eller [!UICONTROL Experience Targeting]-aktivitet med [!UICONTROL Visual Experience Composer] och använder åtgärden [!UICONTROL Recommend] för att lägga till rekommendationer i en upplevelse.

## Lägg till en rekommendation som ett erbjudande i en A/B-test eller en XT-aktivitet

1. Starta det guidade trestegsarbetsflödet med Visual Experience Composer (VEC) för att skapa en [A/B Test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)- eller [Experience Targeting](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)-aktivitet (XT).

   >[!NOTE]
   >
   >För A/B-tester måste du komma ihåg att du kan välja alternativet [Automatisk fördelning](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) för att automatiskt överföra trafik till de bästa rekommendationerna eller alternativet [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md) för att tilldela besökare anpassade rekommendationer baserat på deras profil.

1. När du skapar en [upplevelse](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) klickar du på elementet som du vill lägga till en rekommendation i som ett erbjudande, klickar på **[!UICONTROL Replace Content]** ( ![ikonen Ersätt innehåll](/help/main/assets/icons/Switch.svg) ) och väljer sedan **[!UICONTROL Recommendation]** .

   ![Infoga rekommendation som ett erbjudande](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. I fältet [!UICONTROL Recommendation] till höger klickar du på **[!UICONTROL Select a Recommendation]** för att visa dialogrutan [!UICONTROL Select Criteria].

1. Klicka på **[!UICONTROL Create Criteria]** eller välj ett befintligt villkor.

1. (Valfritt) Klicka på ikonen **[!UICONTROL Filter]** ( ![Filterikon](/help/main/assets/icons/Filter.svg) ) för att välja bland följande alternativ för att visa vanliga rekommendationer per sidtyp:

   * Kundsida
   * Kategorisida
   * Hemsida
   * Landningssida
   * Produktsida
   * Sökresultatsida
   * Tack
   * Övriga

1. Klicka på **[!UICONTROL Create Criteria]** eller välj ett befintligt [villkor](/help/main/c-recommendations/c-algorithms/algorithms.md) och klicka sedan på **[!UICONTROL Next]** för att visa dialogrutan [!UICONTROL Select Design].

1. Klicka på **[!UICONTROL Create Design]** eller markera en befintlig [design](/help/main/c-recommendations/c-design-overview/design-overview.md) och klicka sedan på **[!UICONTROL &#x200B; Next]**.

1. Ange följande i dialogrutan [!UICONTROL Options]:

   * Välj en [samling](/help/main/c-recommendations/c-products/collections.md).
   * Konfigurera alternativen för [Främre befordran och Bakåt &#x200B;](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md) efter behov.

1. Klicka på **[!UICONTROL Save]**.
1. Slutför konfigurationen av A/B-testaktiviteten eller XT-aktiviteten med det guidade arbetsflödet i tre delar.

## Redigera konfigurationen för ett rekommendationserbjudande

1. Klicka på ikonen [!UICONTROL Recommendation] ( **[!UICONTROL Edit]** redigeringsikonen ![&#x200B; ) bredvid &#x200B;](/help/main/assets/icons/Edit.svg), [!UICONTROL Criteria Name] eller [!UICONTROL Design Name] i [!UICONTROL Collection Name]-listen för att ändra elementet.

## Ta bort ett rekommendationer

1. Klicka på ikonen **[!UICONTROL Delete]** ( ![&#x200B; ikonen Ta bort &#x200B;](/help/main/assets/icons/Delete.svg) ) högst upp på panelen [!UICONTROL Recommendation].

### Visa rekommendationserbjudandets status {#status}

Rekommendationserbjudandestatusen (algoritm) visas längst ned på aktivitetens [!UICONTROL Overview]-sida för A/B-tester och XT-aktiviteter som innehåller rekommendationer:

* Resultatförberedda
* Resultaten är inte klara
* Feed-fel
