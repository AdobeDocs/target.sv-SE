---
keywords: Skapa automatiskt mål;A/B-test;automatiskt mål-aktivitet;ny a/b-aktivitet;automatiskt mål;automatiskt mål för personaliserade upplevelser;personaliserad;optimering
description: Lär dig använda [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] för att skapa [!UICONTROL Auto-Target] A/B-testaktivitet.
title: Hur skapar jag en [!UICONTROL Auto-Target] Aktivitet?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 0%

---

# Skapa en [!UICONTROL Auto-Target] aktivitet

Använd [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] för att skapa [!UICONTROL Auto-Target] [!UICONTROL A/B Test] direkt på en [!DNL Target]-aktiverad sida och ändra delar av sidan på [!DNL Target].

>[!NOTE]
>
>[!UICONTROL Auto-Target] är tillgängligt som en del av [!DNL Target Premium] lösning. Den här funktionen är inte tillgänglig i [!DNL Target Standard] utan [!DNL Target Premium] licens. Mer information om de avancerade funktionerna i den här licensen finns i [Mål Premium](/help/main/c-intro/intro.md).

Skapa en [!UICONTROL Auto-Target] aktivitet:

1. Från **[!UICONTROL Activities]** lista, klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**.

   ![Listrutan Skapa aktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   Vilka aktivitetstyper som är tillgängliga beror på din [!DNL Target] konto. Vissa aktivitetstyper kanske inte visas i listan. Till exempel: [!UICONTROL Recommendations] är en [Target Premium-funktion](/help/main/c-intro/intro.md#premium). Mer information om de olika aktivitetstyperna finns i [Verksamhet](/help/main/c-activities/activities.md) och [Verksamhetens syfte](/help/main/c-activities/target-activities-guide.md).

1. Välj **[!UICONTROL Visual]**, om det behövs.

   Om du föredrar att använda [!UICONTROL Form-Based Experience Composer], markera [!UICONTROL Form]. Se [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) för mer information.

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer], [!DNL Target] erbjuder Single Page Application VEC. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/main/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Villkorligt) Om du är en [Target Premium-kund](/help/main/c-intro/intro.md#premium)väljer du en [arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Ange [aktivitets-URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)och sedan klicka **[!UICONTROL Next]**.

   Om ditt konto är konfigurerat med en standardwebbadress (URL) visas den URL:en som standard. Du kan ändra från standard till en annan URL.

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

   The [!UICONTROL Visual Experience Composer] visar två flikar till vänster efter att du har skapat en aktivitet: Upplevelse A och Upplevelse B. Upplevelse A är kontrollupplevelsen. Fokus ligger på fliken Experience B, som ni kan ändra efter behov. Upplevelse B är den alternativa upplevelse som ni kan lägga till i ert test. Ni kan lägga till flera upplevelser i testet. Du kan också ta bort Experience A från aktiviteten om du inte vill inkludera en standardwebbplatsupplevelse som ett alternativ.

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

1. Ställ in din trafikallokering.

   Ni kan visa flera upplevelser för samma målgrupp. Ett diagram visar den valda målgruppen och de upplevelser du har lagt till i aktiviteten.

   Välj den trafikallokeringsmetod du vill använda. Skapa en [!UICONTROL Auto-Target] aktivitet, välja **[!UICONTROL Auto-Target for personalized experiences]**.

   De tre typerna av trafiktilldelning beskrivs nedan:

   * **[!UICONTROL Manual (Default)]**: Ange hur många procent av deltagarna du vill se varje upplevelse. Ni kan dela upp procentsatserna jämnt mellan alla upplevelser eller ange högre eller lägre procenttal för varje upplevelse. Det totala antalet upplevelser måste vara 100 %. Mer information finns i [Skapa ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Auto-Allocate to best experience]**: De flesta aktivitetsdeltagare dirigeras automatiskt till högpresterande upplevelser. Vissa besökare tilldelas alla upplevelser för att kunna utforska upplevelser och för att identifiera förändringar i prestandatender. Mer information finns i [Automatisk allokering - översikt](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL Auto-Target for personalized experiences]**: [!DNL Target] använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser och sedan leverera den mest skräddarsydda upplevelsen till besökare baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare.

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
