---
keywords: Create auto-allocate;A/B test;auto-allocate activity;new a/b activity;auto allocate;auto-allocate to best experience;allocate
description: Använd Visual Experience Composer i Adobe Target för att skapa A/B Test-aktiviteten automatiskt direkt på en Target-aktiverad sida och för att ändra delar av sidan i Target.
title: Skapa en automatiskt fördelad aktivitet
feature: ab
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 0%

---


# Skapa en automatiskt fördelad aktivitet

Använd [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target] för att skapa din [!UICONTROL Auto-Allocate] [!UICONTROL A/B Test]-aktivitet direkt på en [!DNL Target]-aktiverad sida och för att ändra delar av sidan i [!DNL Target].

>[!NOTE]
>
>Förutom [!UICONTROL Auto-Allocate] [!UICONTROL A/B Test]-aktiviteten (beskrivs i den här artikeln) innehåller [!DNL Target] ytterligare två typer av [!UICONTROL A/B Test]-aktiviteter: [!UICONTROL Manual (Default)] och [!UICONTROL Auto-Target].
>
>Se [Typer av A/B-testningsaktiviteter](/help/c-activities/t-test-ab/test-ab.md#types) i *Översikt över A/B-tester*.

Så här skapar du en [!UICONTROL Auto-Allocate]-aktivitet:

1. Klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]** i listan **[!UICONTROL Activities]**.

   ![Listrutan Skapa aktivitet](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Vilka aktivitetstyper som är tillgängliga beror på ditt [!DNL Target]-konto. Vissa aktivitetstyper kanske inte visas i listan. [!UICONTROL Recommendations] är till exempel en [Target Premium-funktion](/help/c-intro/intro.md#premium).
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

1. (Villkorligt) Om du är [målPremium-kund](/help/c-intro/intro.md#premium) väljer du en [arbetsyta](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Ange din [aktivitets-URL](/help/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) och klicka sedan på **[!UICONTROL Next]**.

   Om ditt konto är konfigurerat med en standardwebbadress (URL) visas den URL:en som standard. Du kan ändra från standard till en annan URL.

   [!UICONTROL Visual Experience Composer] öppnas och sidan som anges i URL:en visas.

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Ange ett namn för aktiviteten i det angivna utrymmet.

   ![Namnfält](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   Följande tecken tillåts inte i aktivitetsnamn:

   | Tecken | Beskrivning |
   |--- |--- |
   | `/` | Snedstreck |
   | `?` | Frågetecken |
   | `#` | Nummertecken |
   | `:` | Colon |
   | `=` | Lika med |
   | `+` | Plus |
   | `-` | Minus |
   | `@` | Vid tecken |

1. Skapa nya upplevelser genom att ändra elementen på sidan.

   I [!UICONTROL Visual Experience Composer] visas två flikar till vänster när du har skapat en ny aktivitet: Upplevelse A och upplevelse B. Upplevelse A är kontrollupplevelsen. Fokus ligger på fliken Experience B, som ni kan ändra efter behov. Experience B är den alternativa upplevelse ni kan lägga till i ert test. Ni kan lägga till flera upplevelser i testet. Du kan också ta bort Experience A från aktiviteten om du inte vill inkludera en standardwebbplatsupplevelse som ett alternativ.

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

   Välj den trafikallokeringsmetod du vill använda. Om du vill skapa en [!UICONTROL Auto-Allocate]-aktivitet väljer du **[!UICONTROL Auto-Allocate to best experience]**.

   De tre typerna av trafiktilldelning beskrivs nedan:

   * **[!UICONTROL Manual (Default)]**: Ange hur många procent av deltagarna du vill se varje upplevelse. Ni kan dela upp procentsatserna jämnt mellan alla upplevelser eller ange högre eller lägre procenttal för varje upplevelse. Det totala antalet upplevelser måste vara 100 %. Mer information finns i [Skapa ett A/B-test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Auto-allocate to best experience]**: De flesta aktivitetspartners dirigeras automatiskt till högpresterande upplevelser. Vissa besökare tilldelas alla upplevelser för att kunna utforska upplevelser och för att identifiera förändringar i prestandatender.

   * **[!UICONTROL Auto-target for personalized experiences]**:  [!DNL Target] använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser och sedan leverera den mest skräddarsydda upplevelsen till besökare baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare. Mer information finns i [Automatiskt mål](/help/c-activities/auto-target/auto-target-to-optimize.md).
   Du kan också klicka på **[!UICONTROL Add]** om du vill lägga till en annan upplevelse till aktiviteten.

1. När du är nöjd med din målgrupp, dina upplevelseval och dina val av trafiktilldelning klickar du på **[!UICONTROL Next]** för att gå över till det tredje steget i det guidade arbetsflödet i tre steg.

1. Ange [mål och inställningar](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) för aktiviteten.

   ![A/B-aktivitetsinställningar](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. Klicka på **[!UICONTROL Save & Close]** eller **[!UICONTROL Save]**.

När du har skapat aktiviteten visas information om aktiviteten på fliken [!UICONTROL Overview], inklusive ett diagram över aktiviteten.

## Utbildningsvideo: Skapa A/B-tester (8:36) ![Självstudiemärke](/help/assets/tutorial.png)

I den här videon visas hur du skapar ett A/B-test med hjälp av det guidade arbetsflödet i [!DNL Target] i tre steg.

* Skapa en [!UICONTROL A/B Test]-aktivitet i [!DNL Adobe Target]
* Allokera trafik med manuell, delad eller automatisk trafikallokering

>[!VIDEO](https://video.tv.adobe.com/v/17391)