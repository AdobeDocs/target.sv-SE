---
keywords: Experience Targeting;xt;create
description: Lär dig använda [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] för att skapa [!UICONTROL Experience Targeting] (XT) aktivitet.
title: Hur skapar jag en [!UICONTROL Experience Targeting] Aktivitet?
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 4faafcef38d02674072d8b20ae03d3e2ef2115d6
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# Skapa en [!UICONTROL Experience Targeting] (XT) aktivitet

Använd [!UICONTROL Visual Experience Composer] (VEC) för att skapa en [!UICONTROL Experience Targeting] (XT) på en [!DNL Target]-aktiverad sida och ändra delar av sidan på [!DNL Adobe Target].

[!UICONTROL Experience Targeting] (XT) levererar innehåll till en viss målgrupp baserat på en uppsättning marknadsföringsdefinierade regler och kriterier.

[!UICONTROL Experience Targeting], inklusive [målinriktning](/help/main/c-target/c-audiences/c-target-rules/geo.md), är värdefullt för att definiera regler som riktar sig till en viss upplevelse eller innehåll till en viss målgrupp. Flera regler kan definieras i en aktivitet för att leverera olika innehållsvariationer till olika målgrupper.

Mer information om [!UICONTROL Experience Targeting], ett fallscenario och utbildningsvideor finns på [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md).

**Skapa en [!UICONTROL Experience Targeting] aktivitet:**

1. Från [!UICONTROL Activities] lista, klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL Experience Targeting]**.

   ![Skapa aktivitet > Experience Targeting](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Vilka aktivitetstyper som är tillgängliga beror på din [!DNL Target] konto. Vissa aktivitetstyper kanske inte visas i listan. Till exempel: [!UICONTROL Automated Personalization] är en [Target Premium-funktion](/help/main/c-intro/intro.md#premium).
   >
   >Mer information om de olika aktivitetstyperna finns i [!DNL Target] och skillnaderna [Verksamhet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Se [Typ av målaktivitet](/help/main/c-activities/target-activities-guide.md) för att hjälpa dig att avgöra vilken typ av aktivitet som bäst passar dina behov.

1. Välj **[!UICONTROL Visual (Default)]**, om det behövs.

   Om du föredrar att använda [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md), markera [!UICONTROL Form].

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer], [!DNL Target] erbjuder Single Page Application VEC. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/main/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Villkorligt) Om du är en [!DNL Target Premium] kund, [välja en arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   The [!UICONTROL Choose Workplace] alternativ är [Mål Premium](/help/main/c-intro/intro.md) -funktion. Om din organisation har en [!DNL Target Standard] licensiera om du inte ser det här alternativet.

1. Ange [aktivitets-URL](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)och sedan klicka **[!UICONTROL Create]**.

   Om ditt konto är [konfigurerad med en standard-URL](/help/main/administrating-target/visual-experience-composer-set-up.md)visas den URL-adressen som standard. Om det behövs kan du ändra från standardadressen till en annan URL.

   VEC-filen öppnas och den sida som anges i URL-adressen visas.

   ![Upplevelseanpassad aktivitet inom VEC](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. Ange ett namn för aktiviteten i det angivna utrymmet.

   ![Namnfält](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

   Aktivitetsnamnet får inte börja med något av följande tecken:

   | Tecken | Beskrivning |
   |--- |--- |
   | `=` | Lika med |
   | `+` | Plus |
   | `-` | Minus |
   | `@` | Vid tecken |

   Aktivitetsnamnet får inte innehålla någon av följande teckensekvenser:

   | Teckensekvens | Beskrivning |
   |--- |--- |
   | ;= | Semikolon, lika med |
   | ;+ | Semikolon, Plus |
   | ;- | Semikolon, minus |
   | ;@ | Semikolon, tecken |
   | ,= | Komma, motsvarar |
   | ,+ | komma, plus |
   | ,- | Komma, Minus |
   | ,@ | Komma, Vid tecken |
   | `[`&quot; | Öppen hakparentes, dubbla citattecken |
   | &quot;`]` | Dubbla citattecken, avslutande hakparentes |

1. Skapa nya upplevelser för olika målgrupper.

   Stegvisa instruktioner finns i [Lägg till upplevelse](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Ange [mål och inställningar](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) för aktiviteten.
