---
keywords: Experience Targeting;xt;create
description: Lär dig hur du använder [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target]  för att skapa en [!UICONTROL Experience Targeting]-aktivitet (XT).
title: Hur skapar jag en [!UICONTROL Experience Targeting]-aktivitet?
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Skapa en [!UICONTROL Experience Targeting] (XT) aktivitet

Använd [!UICONTROL Visual Experience Composer] (VEC) för att skapa en [!UICONTROL Experience Targeting] (XT)-aktivitet på en [!DNL Target]-aktiverad sida och för att ändra delar av sidan i [!DNL Adobe Target].

[!UICONTROL Experience Targeting] (XT) levererar innehåll till en viss målgrupp baserat på en uppsättning marknadsföringsdefinierade regler och kriterier.

[!UICONTROL Experience Targeting], inklusive [geo-targeting](/help/main/c-target/c-audiences/c-target-rules/geo.md), är värdefullt för att definiera regler som riktar en viss upplevelse eller innehåll till en viss målgrupp. Flera regler kan definieras i en aktivitet för att leverera olika innehållsvariationer till olika målgrupper.

Mer information om [!UICONTROL Experience Targeting], ett användningsscenario och utbildningsvideor finns i [Experience Targeting](/help/main/c-activities/t-experience-target/experience-target.md).

**Så här skapar du en [!UICONTROL Experience Targeting]-aktivitet:**

1. Klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL Experience Targeting]** i listan [!UICONTROL Activities].

   >[!NOTE]
   >
   >Vilka aktivitetstyper som är tillgängliga beror på ditt [!DNL Target]-konto. Vissa aktivitetstyper kanske inte visas i listan. [!UICONTROL Automated Personalization] är till exempel en [Target Premium-funktion](/help/main/c-intro/intro.md#premium).
   >
   >Mer information om de olika aktivitetstyperna i [!DNL Target] och skillnaderna mellan dem finns i [Aktiviteter](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Se [Målaktivitetstyper](/help/main/c-activities/target-activities-guide.md) som hjälper dig att avgöra vilken aktivitetstyp som bäst uppfyller dina behov.

1. Välj **[!UICONTROL Visual]** om det behövs.

   Om du föredrar att använda [formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) väljer du [!UICONTROL Form].

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer] erbjuder [!DNL Target] Single Page Application VEC. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/main/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Villkorligt) Om du är [!DNL Target Premium]-kund [väljer du en arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   Alternativet [!UICONTROL Choose Workplace] är en [Target Premium](/help/main/c-intro/intro.md)-funktion. Om din organisation har en [!DNL Target Standard]-licens om du inte ser det här alternativet.

1. Ange din [aktivitets-URL](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) och klicka sedan på **[!UICONTROL Create]**.

   Om ditt konto är [konfigurerat med en standard-URL](/help/main/administrating-target/visual-experience-composer-set-up.md) visas den URL:en som standard. Om det behövs kan du ändra från standardadressen till en annan URL.

   VEC-filen öppnas och den sida som anges i URL-adressen visas.

1. Klicka på ikonen **[!UICONTROL Rename]** ( ![Byt namn ](/help/main/assets/icons/MoreSmallListVert.svg) ), klicka på **[!UICONTROL Rename]**, ange ett namn för aktiviteten och klicka sedan på **[!UICONTROL Save]**.

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
