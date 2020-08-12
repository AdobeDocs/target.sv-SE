---
keywords: Create A/B;A/B test;A/B activity;new a/b activity
description: Använd Visual Experience Composer i Target för att skapa ditt test direkt på en Target-aktiverad sida och för att ändra delar av sidan i Target.
title: Skapa ett A/B-test
feature: null
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 0%

---


# Skapa ett A/B-test{#create-an-a-b-test}

Använd Visual Experience Composer i Target för att skapa ditt test direkt på en Target-aktiverad sida och för att ändra delar av sidan i Target.

1. From the [!UICONTROL Activities] list, click **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**.

   ![Listrutan Skapa aktivitet](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Vilka aktivitetstyper som är tillgängliga beror på ditt [!DNL Target] konto. Vissa aktivitetstyper kanske inte visas i listan. Det [!UICONTROL Recommendations] är till exempel en [Target Premium-funktion](/help/c-intro/intro.md#premium).
   >
   >Mer information om de olika aktivitetstyperna finns i [Verksamheter](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) och i guiden [](/help/c-activities/target-activities-guide.md)Målaktiviteter.

   ![Skapa A/B-testaktivitet](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

1. Välj **[!UICONTROL Visual (Default)]** vid behov.

   Om du föredrar att använda formulärbaserad Experience Composer väljer du [!UICONTROL Form]. Mer information finns i [Formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md) .

   >[!NOTE]
   >
   >Förutom VEC och Form-Based Experience Composer erbjuder Target Single Page Application VEC och VEC for Mobile Apps. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsökning i Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)om det uppstår problem.
   >
   >Alternativet [!UICONTROL [Choose Workplace](/help/administrating-target/c-user-management/property-channel/property-channel.md) i föregående bild är en [Target Premium](/help/c-intro/intro.md) -funktion. Din organisation har en Target Standard-licens om du inte ser det här alternativet.]

1. (Villkorligt) Om du är [Target Premium-kund](/help/c-intro/intro.md#premium)väljer du en [arbetsyta](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Ange din [aktivitets-URL](../../../c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)och klicka sedan på **[!UICONTROL Next]**.

   Om ditt konto är konfigurerat med en standardwebbadress (URL) visas den URL:en som standard. Du kan ändra från standard till en annan URL.

   Sidan [!UICONTROL Visual Experience Composer] öppnas med den angivna webbadressen.

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

   I dialogrutan visas två [!UICONTROL Visual Experience Composer] flikar till vänster när du har skapat en ny aktivitet: Upplevelse A och upplevelse B. Upplevelse A är kontrollupplevelsen. Fokus ligger på fliken Experience B, som ni kan ändra efter behov. Experience B är den alternativa upplevelse ni kan lägga till i ert test. Ni kan lägga till flera upplevelser i testet. Du kan också ta bort Experience A från aktiviteten om du inte vill inkludera en standardwebbplatsupplevelse som ett alternativ.

   Mer information om hur du lägger till och ändrar upplevelser i [!UICONTROL Visual Experience Composer]finns i [Lägg till upplevelse](../../../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Om du vill ändra upplevelse B börjar du med steg 3.

1. Klicka **[!UICONTROL Targeting]** längst upp i [!UICONTROL Visual Experience Composer] för att gå till nästa steg i det guidade arbetsflödet i tre steg.

   Flödesdiagrammet öppnas.

   ![A/B Test Targeting step](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   Flödesdiagrammet leder dig genom stegen för att välja målgrupp för aktiviteten och skapa upplevelser.
1. Klicka på redigeringsikonen i [!UICONTROL Audience] rutan och [välj sedan målgrupp](../../../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087) för din aktivitet.

   Som standard är målgruppen Alla besökare.

1. Välj den procentandel kvalificerade besökare som du vill ange aktiviteten för.

   ![Målgruppsprocent](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Du kan t.ex. begränsa antalet deltagare till 50 % av alla besökare eller 45 % av alla dina&quot;Kalifornier&quot;-målgrupper.

1. Ställ in din trafikallokering.

   Ni kan visa flera upplevelser för samma målgrupp. Ett diagram visar den valda målgruppen och de upplevelser du har lagt till i aktiviteten.

   Välj den trafikallokeringsmetod du vill använda:

   * **[!UICONTROL Manual (Default)]**: Ange hur många procent av deltagarna du vill se varje upplevelse. Ni kan dela upp procentsatserna jämnt mellan alla upplevelser eller ange högre eller lägre procenttal för varje upplevelse. Det totala antalet upplevelser måste vara 100 %.

   * **[!UICONTROL Auto-allocate to best experience]**: De flesta aktivitetspartners dirigeras automatiskt till högpresterande upplevelser. Vissa besökare tilldelas alla upplevelser för att kunna utforska upplevelser och för att identifiera förändringar i prestandatender. Se [Automatiserad trafikallokering](../../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Auto-target for personalized experiences]**: Target använder avancerade maskininlärningsalgoritmer för att automatiskt rikta in sig på besökare med den bästa upplevelsen för att maximera era era mål. Mer information finns i Optimera [med Automatiskt mål](../../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).
   Du kan också klicka för **[!UICONTROL Add Experience]** att lägga till en annan upplevelse till aktiviteten.

1. När du är nöjd med dina målgrupps- och upplevelseval klickar du för **[!UICONTROL Next]** att gå över till det tredje steget i det guidade arbetsflödet i tre steg.

1. Ange [mål och inställningar](../../../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) för aktiviteten.

   ![A/B-aktivitetsinställningar](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. Klicka på **[!UICONTROL Save]**.

När du har skapat aktiviteten visas information om aktiviteten på fliken Översikt, inklusive ett diagram över aktiviteten.

## Utbildningsvideo: Skapa A/B-tester (8:36) ![självstudiemärke](/help/assets/tutorial.png)

I den här videon visas hur du skapar ett A/B-test med ett guidat arbetsflöde i tre steg. [!DNL Target]

* Skapa en A/B-aktivitet i Adobe Target
* Allokera trafik med manuell, delad eller automatisk trafikallokering

>[!VIDEO](https://video.tv.adobe.com/v/17391)
