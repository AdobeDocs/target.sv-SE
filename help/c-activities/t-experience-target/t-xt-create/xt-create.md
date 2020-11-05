---
description: Använd Visual Experience Composer för att skapa en XT-aktivitet (Experience Targeting) på en målaktiverad sida och för att ändra delar av sidan i Adobe Target.
title: Skapa en Experience Targeting-aktivitet
feature: xt
subtopic: Multivariate Test
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---


# Skapa en Experience Targeting-aktivitet{#create-an-experience-targeting-activity}

Använd [!UICONTROL Visual Experience Composer] (VEC) för att skapa en [!UICONTROL Experience Targeting] (XT) aktivitet på en målaktiverad sida och för att ändra delar av sidan i [!DNL Adobe Target].

Experience Targeting (XT) levererar innehåll till en viss målgrupp baserat på en uppsättning marknadsföringsdefinierade regler och kriterier.

Experience Targeting, inklusive [geoanpassning](/help/c-target/c-audiences/c-target-rules/geo.md), är värdefullt för att definiera regler som riktar en viss upplevelse eller innehåll till en viss målgrupp. Flera regler kan definieras i en aktivitet för att leverera olika innehållsvariationer till olika målgrupper.

Mer information om Experience Targeting, ett användningsscenario och utbildningsvideor finns i [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md).

**Så här skapar du en XT-aktivitet:**

1. From the [!UICONTROL Activities] list, click **[!UICONTROL Create Activity]** > **[!UICONTROL Experience Targeting]**.

   ![Skapa aktivitet > Experience Targeting](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Vilka aktivitetstyper som är tillgängliga beror på ditt Target-konto. Vissa aktivitetstyper kanske inte visas i listan. Det [!UICONTROL Automated Personalization] är till exempel en [Target Premium-funktion](/help/c-intro/intro.md#premium).
   >
   >Mer information om de olika aktivitetstyperna som finns i [!DNL Target] och skillnaderna mellan dem finns i [Verksamheter](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Se [Målaktivitetstyper](/help/c-activities/target-activities-guide.md) som hjälper dig att avgöra vilken typ av aktivitet som bäst passar dina behov.

1. Välj **[!UICONTROL Visual (Default)]** vid behov.

   ![Dialogrutan Skapa aktivitet för mål för upplevelse](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Om du föredrar att använda formulärbaserad Experience Composer väljer du [!UICONTROL Form]. Mer information finns i [Formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md) .

   >[!NOTE]
   >
   >Förutom VEC och Form-Based Experience Composer erbjuder Target Single Page Application VEC och VEC for Mobile Apps. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsökning i Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)om det uppstår problem.
   >
   >Alternativet [!UICONTROL Choose Workplace] i föregående bild är en [Target Premium](/help/c-intro/intro.md) -funktion. Din organisation har en Target Standard-licens om du inte ser det här alternativet.

1. (Villkorligt) Om du är en Target Premium-kund [väljer du en arbetsyta](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Ange din [aktivitets-URL](/help/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)och klicka sedan på **[!UICONTROL Next]**.

   Om ditt konto är [konfigurerat med en standard-URL](/help/administrating-target/visual-experience-composer-set-up.md)visas den URL:en som standard. Om det behövs kan du ändra från standardadressen till en annan URL.

   VEC-filen öppnas och den sida som anges i URL-adressen visas.

   ![Upplevelseanpassad aktivitet inom VEC](/help/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. Ange ett namn för aktiviteten i det angivna utrymmet.

   ![Namnfält](/help/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

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

1. Skapa nya upplevelser för olika målgrupper.

   Stegvisa instruktioner finns i [Lägga till en upplevelse](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Ange [mål och inställningar](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) för aktiviteten.