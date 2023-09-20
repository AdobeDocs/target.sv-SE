---
keywords: skapa automatisk allokering;A/B-test;autoallokera aktivitet;ny a/b-aktivitet;autoallokera;autoallokera till bästa upplevelse;allokera;autoallokera
description: Lär dig använda [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] för att skapa [!UICONTROL Auto-Allocate] A/B-testaktivitet.
title: Hur skapar jag en [!UICONTROL Auto-Allocate] Aktivitet?
feature: Auto-Allocate
exl-id: 30bc95e0-4f5e-4d1f-bad2-7b20b8f3c7d2
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 0%

---

# Skapa en [!UICONTROL Auto-Allocate] aktivitet

Använd [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] för att skapa [!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] direkt på en [!DNL Target]-aktiverad sida och ändra delar av sidan på [!DNL Target].

Förutom [!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] verksamhet (diskuteras i denna artikel), [!DNL Target] innehåller ytterligare två typer av [!UICONTROL A/B Test] verksamhet: [!UICONTROL Manual (Default)] och [!UICONTROL Auto-Target]. Se [Typ av A/B-testning](/help/main/c-activities/t-test-ab/test-ab.md#types) in *Översikt över A/B-test*.

Skapa en [!UICONTROL Auto-Allocate] aktivitet:

1. Från **[!UICONTROL Activities]** lista, klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**.

   ![Listrutan Skapa aktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   Vilka aktivitetstyper som är tillgängliga beror på din [!DNL Target] konto. Vissa aktivitetstyper kanske inte visas i listan. Till exempel: [!UICONTROL Recommendations] är en [Target Premium-funktion](/help/main/c-intro/intro.md#premium). Mer information om de olika aktivitetstyperna finns i [Verksamhet](/help/main/c-activities/activities.md) och [Verksamhetens syfte](/help/main/c-activities/target-activities-guide.md).

1. I **[!UICONTROL Create A/B Test Activity]** väljer **[!UICONTROL Visual]**, om det behövs.

   Om du föredrar att använda [!UICONTROL Form-Based Experience Composer], markera [!UICONTROL Form]. Se [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) för mer information.

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer], [!DNL Target] erbjuder Single Page Application VEC. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/main/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Villkorligt) Om du är en [Target Premium-kund](/help/main/c-intro/intro.md#premium)väljer du en [arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Ange [aktivitets-URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)och sedan klicka **[!UICONTROL Create]**.

   Om ditt konto är konfigurerat med en standardwebbadress (URL) visas den URL:en som standard. Du kan ändra från standardadressen till en annan URL-adress om det behövs.

   The [!UICONTROL Visual Experience Composer] öppnas och sidan som anges i URL:en visas.

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Ange ett namn för aktiviteten i det angivna utrymmet.

   ![Namnfält](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   Aktivitetsnamnet får inte börja med något av följande tecken:

   | Tecken | Beskrivning |
   |--- |--- |
   | `=` | Lika med |
   | `+` | Plus |
   | `-` | Minus |
   | `@` | Vid tecken |

1. Skapa upplevelser genom att ändra elementen på sidan.

   The [!UICONTROL Visual Experience Composer] visar två flikar till vänster efter att du har skapat en ny aktivitet: Upplevelse A och Upplevelse B. Upplevelse A är kontrollupplevelsen. Fokus ligger på fliken Experience B, som ni kan ändra efter behov. Experience B är den alternativa upplevelse ni kan lägga till i ert test. Ni kan lägga till flera upplevelser i testet. Du kan också ta bort Experience A från aktiviteten om du inte vill inkludera en standardwebbplatsupplevelse som ett alternativ.

   Mer information om hur du lägger till och ändrar upplevelser i [!UICONTROL Visual Experience Composer], se [Lägg till upplevelse](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Om du vill ändra upplevelse B börjar du med steg 2.

1. Klicka **[!UICONTROL Targeting]** högst upp på [!UICONTROL Visual Experience Composer] för att gå vidare till nästa steg i det guidade arbetsflödet i tre steg.

   Flödesdiagrammet öppnas.

   ![A/B Test Targeting step](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   Flödesdiagrammet leder dig genom stegen för att välja målgrupp för aktiviteten och skapa upplevelser.

1. I [!UICONTROL Audience] klickar du på redigeringsikonen (den lodräta ellipsen) och klickar på **[!UICONTROL Replace Audience]** sedan [välj målgrupp](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) för din aktivitet.

   Som standard är målgruppen inställd på [!UICONTROL All Visitors].

1. Välj den procentandel kvalificerade besökare som du vill ange aktiviteten för.

   ![Målgruppsprocent](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Du kan t.ex. begränsa antalet deltagare till 50 % av alla besökare eller 45 % av alla dina&quot;Kalifornier&quot;-målgrupper.

1. Ställ in din trafikallokeringsmetod.

   Ni kan visa flera upplevelser för samma målgrupp. Ett diagram visar den valda målgruppen och de upplevelser du har lagt till i aktiviteten.

   Välj den trafikallokeringsmetod du vill använda. Skapa en [!UICONTROL Auto-Allocate] aktivitet, välja **[!UICONTROL Auto-Allocate to best experience]**.

   De tre typerna av trafiktilldelning beskrivs nedan:

   * **[!UICONTROL Manual (Default)]**: Ange hur många procent av deltagarna du vill se varje upplevelse. Ni kan dela upp procentsatserna jämnt mellan alla upplevelser eller ange högre eller lägre procenttal för varje upplevelse. Det totala antalet upplevelser måste vara 100 %. Mer information finns i [Skapa ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Auto-allocate to best experience]**: De flesta aktivitetsdeltagare dirigeras automatiskt till högpresterande upplevelser. Vissa besökare tilldelas alla upplevelser för att kunna utforska upplevelser och för att identifiera förändringar i prestandatender.

   * **[!UICONTROL Auto-target for personalized experiences]**: [!DNL Target] använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser och sedan leverera den mest skräddarsydda upplevelsen till besökare baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare. Mer information finns i [Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   Du kan också klicka **[!UICONTROL Add]** om du vill lägga till ytterligare en upplevelse till aktiviteten.

1. När du är nöjd med din publik, dina upplevelseval och dina val för trafiktilldelning klickar du **[!UICONTROL Next]** för att gå till det tredje steget i det guidade arbetsflödet i tre steg.

1. Ange [mål och inställningar](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) för aktiviteten.

   >[!NOTE]
   >
   >Om du vill använda [Analyser för Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) med den här aktiviteten, se viktig information i [A4T-stöd för Automatisk allokering och Automatiskt mål-aktiviteter](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Klicka **[!UICONTROL Save & Close]** eller **[!UICONTROL Save]**.

När du har skapat aktiviteten kan du [!UICONTROL Overview] -fliken visar information om aktiviteten, inklusive ett diagram över din aktivitet.

## Utbildningsvideo: Skapa A/B-tester (8:36)

I den här videon visas hur du skapar ett A/B-test med [!DNL Target] guidat arbetsflöde i tre steg.

* Skapa en [!UICONTROL A/B Test] aktivitet i [!DNL Adobe Target]
* Allokera trafik med manuell, delad eller automatisk trafikallokering

>[!VIDEO](https://video.tv.adobe.com/v/17391)
