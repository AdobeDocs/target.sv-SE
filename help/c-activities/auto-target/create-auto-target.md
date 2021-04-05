---
keywords: Skapa automatiskt mål;A/B-test;automatiskt mål-aktivitet;ny a/b-aktivitet;automatiskt mål;automatiskt mål för personaliserade upplevelser;personaliserad;optimering
description: Lär dig hur du använder Visual Experience Composer (VEC) i Adobe Target för att skapa A/B-testaktivitet automatiskt direkt på en Target-aktiverad sida.
title: Hur skapar jag en automatiskt målaktivering?
feature: Automatiskt mål
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
translation-type: tm+mt
source-git-commit: 73053526e68e08136ab66b9d4c1aa17958cfc76e
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 0%

---

# ![](/help/assets/premium.png) PREMIUMCkapa en Automatisk målaktivitet

Använd [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target] för att skapa din [!UICONTROL Auto-Target] [!UICONTROL A/B Test]-aktivitet direkt på en [!DNL Target]-aktiverad sida och för att ändra delar av sidan i [!DNL Target].

>[!NOTE]
>
>[!UICONTROL Auto-Target] finns som en del av  [!DNL Target Premium] lösningen. Den här funktionen är inte tillgänglig i [!DNL Target Standard] utan en [!DNL Target Premium]-licens. Mer information om de avancerade funktioner som den här licensen innehåller finns i [Target Premium](/help/c-intro/intro.md).
>
>Förutom [!UICONTROL Auto-Target] [!UICONTROL A/B Test]-aktiviteten (beskrivs i den här artikeln) innehåller [!DNL Target] två andra typer av [!UICONTROL A/B Test]-aktiviteter: [!UICONTROL Manual (Default)] och [!UICONTROL Auto-Allocate].
>
>Se [Typer av A/B-testningsaktiviteter](/help/c-activities/t-test-ab/test-ab.md#types) i *Översikt över A/B-tester*.

Så här skapar du en [!UICONTROL Auto-Target]-aktivitet:

1. Klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]** i listan **[!UICONTROL Activities]**.

   ![Listrutan Skapa aktivitet](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Vilka aktivitetstyper som är tillgängliga beror på ditt [!DNL Target]-konto. Vissa aktivitetstyper kanske inte visas i listan. Till exempel är [!UICONTROL Auto-Target] och [!UICONTROL Recommendations] [Target Premium-funktioner](/help/c-intro/intro.md#premium).
   >
   >Mer information om de olika aktivitetstyperna finns i [Aktiviteter](/help/c-activities/activities.md) och [Målaktivitetsguiden](/help/c-activities/target-activities-guide.md).

1. Välj **[!UICONTROL Visual (Default)]** om det behövs.

   ![Skapa A/B-testaktivitet](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   Om du föredrar att använda [!UICONTROL Form-Based Experience Composer] väljer du [!UICONTROL Form]. Mer information finns i [Formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md).

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer] erbjuder [!DNL Target] Single Page Application VEC. Mer information om de olika dispositionerna finns i [Upplevelser och erbjudanden](/help/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md) om du har problem.
   >
   >Alternativet [[!UICONTROL Choose Workplace]](/help/administrating-target/c-user-management/property-channel/property-channel.md) i föregående bild är en [Target Premium](/help/c-intro/intro.md)-funktion. Din organisation har en [!UICONTROL Target Standard]-licens om du inte ser det här alternativet.

1. Välj en [arbetsyta](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Ange din [aktivitets-URL](/help/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) och klicka sedan på **[!UICONTROL Next]**.

   Om ditt konto är konfigurerat med en standardwebbadress (URL) visas den URL:en som standard. Du kan ändra från standard till en annan URL.

   [!UICONTROL Visual Experience Composer] öppnas och sidan som anges i URL:en visas.

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Ange ett namn för aktiviteten i det angivna utrymmet.

   ![Namnfält](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   Aktivitetsnamnet får inte börja med något av följande tecken:

   | Tecken | Beskrivning |
   |--- |--- |
   | `=` | Lika med |
   | `+` | Plus |
   | `-` | Minus |
   | `@` | Vid tecken |

1. Skapa upplevelser genom att ändra elementen på sidan.

   I [!UICONTROL Visual Experience Composer] visas två flikar till vänster när du har skapat en aktivitet: Upplevelse A och upplevelse B. Upplevelse A är kontrollupplevelsen. Fokus ligger på fliken Experience B, som ni kan ändra efter behov. Experience B är den alternativa upplevelse ni kan lägga till i ert test. Ni kan lägga till flera upplevelser i testet. Du kan också ta bort Experience A från aktiviteten om du inte vill inkludera en standardwebbplatsupplevelse som ett alternativ.

   Mer information om hur du lägger till och ändrar upplevelser i [!UICONTROL Visual Experience Composer] finns i [Lägg till upplevelse](/help/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Om du vill ändra upplevelse B börjar du med steg 3.

1. Klicka på **[!UICONTROL Targeting]** överst i [!UICONTROL Visual Experience Composer] för att gå till nästa steg i det guidade arbetsflödet i tre steg.

   Flödesdiagrammet öppnas.

   ![A/B Test Targeting step](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   Flödesdiagrammet leder dig genom stegen för att välja målgrupp för aktiviteten och skapa upplevelser.

1. Klicka på redigeringsikonen (tre lodräta ellipser) i rutan [!UICONTROL Audience], klicka på **[!UICONTROL Replace Audience]** och [välj målgrupp](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) för din aktivitet.

   Som standard är målgruppen inställd på [!UICONTROL All Visitors].

1. Välj den procentandel kvalificerade besökare som du vill ange aktiviteten för.

   ![Målgruppsprocent](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Du kan t.ex. begränsa antalet deltagare till 50 % av alla besökare eller 45 % av alla dina&quot;Kalifornier&quot;-målgrupper.

1. Ställ in din trafikallokering.

   Ni kan visa flera upplevelser för samma målgrupp. Ett diagram visar den valda målgruppen och de upplevelser du har lagt till i aktiviteten.

   Välj den trafikallokeringsmetod du vill använda. Om du vill skapa en [!UICONTROL Auto-Target]-aktivitet väljer du **[!UICONTROL Auto-Target for personalized experiences]**.

   De tre typerna av trafiktilldelning beskrivs nedan:

   * **[!UICONTROL Manual (Default)]**: Ange hur många procent av deltagarna du vill se varje upplevelse. Ni kan dela upp procentsatserna jämnt mellan alla upplevelser eller ange högre eller lägre procenttal för varje upplevelse. Det totala antalet upplevelser måste vara 100 %. Mer information finns i [Skapa ett A/B-test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Auto-Allocate to best experience]**: De flesta aktivitetspartners dirigeras automatiskt till högpresterande upplevelser. Vissa besökare tilldelas alla upplevelser för att kunna utforska upplevelser och för att identifiera förändringar i prestandatender. Mer information finns i [Översikt över automatisk allokering](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL Auto-Target for personalized experiences]**:  [!DNL Target] använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser och sedan leverera den mest skräddarsydda upplevelsen till besökare baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare.
   Du kan också klicka på **[!UICONTROL Add]** om du vill lägga till en annan upplevelse till aktiviteten.

1. När du är nöjd med din målgrupp, dina upplevelseval och dina val av trafiktilldelning klickar du på **[!UICONTROL Next]** för att gå över till det tredje steget i det guidade arbetsflödet i tre steg.

1. Ange [mål och inställningar](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) för aktiviteten.

   ![A/B-aktivitetsinställningar](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

   >[!NOTE]
   >
   >Om du vill använda [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) med den här aktiviteten, se viktig information i [A4T-stöd för aktiviteterna Automatisk allokering och Automatisk målning](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Klicka på **[!UICONTROL Save & Close]** eller **[!UICONTROL Save]**.

När du har skapat aktiviteten visas information om aktiviteten på fliken [!UICONTROL Overview], inklusive ett diagram över aktiviteten.

## Utbildningsvideo: Skapa A/B-tester (8:36) ![Självstudiemärke](/help/assets/tutorial.png)

I den här videon visas hur du skapar ett A/B-test med hjälp av det guidade arbetsflödet i [!DNL Target] i tre steg.

* Skapa en [!UICONTROL A/B Test]-aktivitet i [!DNL Adobe Target]
* Allokera trafik med manuell, delad eller automatisk trafikallokering

>[!VIDEO](https://video.tv.adobe.com/v/17391)
