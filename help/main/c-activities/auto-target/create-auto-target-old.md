---
keywords: Skapa automatiskt mål;A/B-test;automatiskt mål-aktivitet;ny a/b-aktivitet;automatiskt mål;automatiskt mål för personaliserade upplevelser;personaliserad;optimering
description: Lär dig hur du använder [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target]  för att skapa en [!UICONTROL Auto-Target] A/B-testaktivitet.
title: Hur skapar jag en [!UICONTROL Auto-Target]-aktivitet?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 0%

---

# Skapa en [!UICONTROL Auto-Target]-aktivitet

Använd [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target] för att skapa din [!UICONTROL Auto-Target] [!UICONTROL A/B Test]-aktivitet direkt på en [!DNL Target]-aktiverad sida och för att ändra delar av sidan i [!DNL Target].

>[!NOTE]
>
>[!UICONTROL Auto-Target] är tillgänglig som en del av lösningen [!DNL Target Premium]. Den här funktionen är inte tillgänglig i [!DNL Target Standard] utan en [!DNL Target Premium]-licens. Mer information om de avancerade funktioner som den här licensen innehåller finns i [Target Premium](/help/main/c-intro/intro.md).

Skapa en [!UICONTROL Auto-Target]-aktivitet:

1. Klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]** i listan **[!UICONTROL Activities]**.

   ![Listrutan Skapa aktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   Vilka aktivitetstyper som är tillgängliga beror på ditt [!DNL Target]-konto. Vissa aktivitetstyper kanske inte visas i listan. [!UICONTROL Recommendations] är till exempel en [Target Premium-funktion](/help/main/c-intro/intro.md#premium). Mer information om de olika aktivitetstyperna finns i [Aktiviteter](/help/main/c-activities/activities.md) och i [Målaktivitetsguiden](/help/main/c-activities/target-activities-guide.md).

1. Välj **[!UICONTROL Visual]** om det behövs.

   Om du föredrar att använda [!UICONTROL Form-Based Experience Composer] väljer du [!UICONTROL Form]. Mer information finns i [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md).

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer] erbjuder [!DNL Target] Single Page Application VEC. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/main/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsökning av Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md) om du har problem.

1. (Villkorligt) Om du är [Target Premium-kund](/help/main/c-intro/intro.md#premium) väljer du en [arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Ange din [aktivitets-URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) och klicka sedan på **[!UICONTROL Next]**.

   Om ditt konto är konfigurerat med en standardwebbadress (URL) visas den URL:en som standard. Du kan ändra från standard till en annan URL.

   [!UICONTROL Visual Experience Composer] öppnas och sidan som anges i URL:en visas.

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

   [!UICONTROL Visual Experience Composer] visar två flikar till vänster när du har skapat en aktivitet: Upplevelse A och Upplevelse B. Upplevelse A är kontrollupplevelsen. Fokus ligger på fliken Experience B, som ni kan ändra efter behov. Upplevelse B är den alternativa upplevelse som ni kan lägga till i ert test. Ni kan lägga till flera upplevelser i testet. Du kan också ta bort Experience A från aktiviteten om du inte vill inkludera en standardwebbplatsupplevelse som ett alternativ.

   Mer information om hur du lägger till och ändrar upplevelser i [!UICONTROL Visual Experience Composer] finns i [Lägg till upplevelse](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Om du vill ändra upplevelse B börjar du med steg 2.

1. Klicka på **[!UICONTROL Targeting]** överst i [!UICONTROL Visual Experience Composer] för att gå till nästa steg i det guidade arbetsflödet i tre steg.

   Flödesdiagrammet öppnas.

   ![Åtgärd för A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   Flödesdiagrammet leder dig genom stegen för att välja målgrupp för aktiviteten och skapa upplevelser.

1. Klicka på redigeringsikonen (den lodräta ellipsen) i rutan [!UICONTROL Audience], klicka på **[!UICONTROL Replace Audience]** och sedan [välj målgrupp](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) för din aktivitet.

   Som standard är målgruppen inställd på [!UICONTROL All Visitors].

1. Välj den procentandel kvalificerade besökare som du vill ange aktiviteten för.

   ![Målgruppsprocent](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Du kan t.ex. begränsa antalet deltagare till 50 % av alla besökare eller 45 % av alla dina&quot;Kalifornier&quot;-målgrupper.

1. Ställ in din trafikallokering.

   Ni kan visa flera upplevelser för samma målgrupp. Ett diagram visar den valda målgruppen och de upplevelser du har lagt till i aktiviteten.

   Välj den trafikallokeringsmetod du vill använda. Om du vill skapa en [!UICONTROL Auto-Target]-aktivitet väljer du **[!UICONTROL Auto-Target for personalized experiences]**.

   De tre typerna av trafiktilldelning beskrivs nedan:

   * **[!UICONTROL Manual (Default)]**: Ange hur många procent deltagare som ska se varje upplevelse. Ni kan dela upp procentsatserna jämnt mellan alla upplevelser eller ange högre eller lägre procenttal för varje upplevelse. Det totala antalet upplevelser måste vara 100 %. Mer information finns i [Skapa ett A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Auto-Allocate to best experience]**: De flesta aktivitetsdeltagare dirigeras automatiskt till upplevelser med högre prestanda. Vissa besökare tilldelas alla upplevelser för att kunna utforska upplevelser och för att identifiera förändringar i prestandatender. Mer information finns i [Översikt över automatisk allokering](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL Auto-Target for personalized experiences]**: [!DNL Target] använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser och sedan leverera den mest anpassade upplevelsen till besökare baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare.

   Du kan också klicka på **[!UICONTROL Add]** om du vill lägga till en annan upplevelse till aktiviteten.

1. När du är nöjd med din målgrupp, dina upplevelseval och dina val av trafikallokering klickar du på **[!UICONTROL Next]** för att gå till det tredje steget i det guidade arbetsflödet i tre steg.

1. Ange [mål och inställningar](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) för aktiviteten.

   >[!NOTE]
   >
   >Om du vill använda [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) med den här aktiviteten läser du viktig information i [A4T-stöd för Automatisk allokering och Automatisk målaktiviteter](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Klicka på **[!UICONTROL Save & Close]** eller **[!UICONTROL Save]**.

När du har skapat aktiviteten visas information om aktiviteten på fliken [!UICONTROL Overview], inklusive ett diagram över din aktivitet.

## Utbildningsvideo: Skapa A/B-tester (8:36)

I den här videon visas hur du skapar ett A/B-test med hjälp av det guidade arbetsflödet i [!DNL Target] i tre steg.

* Skapa en [!UICONTROL A/B Test]-aktivitet i [!DNL Adobe Target]
* Allokera trafik med manuell, delad eller automatisk trafikallokering

>[!VIDEO](https://video.tv.adobe.com/v/17391)
