---
keywords: Skapa A/B;A/B-test;A/B-aktivitet;ny a/b-aktivitet;skapa a/b
description: Lär dig hur du använder Visual Experience Composer (VEC) i Adobe [!DNL Target] för att skapa en A/B-testaktivitet direkt på en [!DNL Target]-aktiverad sida.
title: Hur skapar jag ett A/B-test?
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
source-git-commit: ec1041fd1823d1ab7f1af147af5825c3ae8662b5
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 0%

---

# Skapa ett A/B-test

Använd [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Adobe Target] för att skapa [!UICONTROL A/B Test] direkt på en [!DNL Target]-aktiverad sida och ändra delar av sidan på [!DNL Target].

>[!NOTE]
>
>Förutom manualen (standard) [!UICONTROL A/B Test] verksamhet (diskuteras i denna artikel), [!DNL Target] innehåller ytterligare två typer av [!UICONTROL A/B Test] verksamhet: [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target].
>
>Se [Typ av A/B-testning](/help/main/c-activities/t-test-ab/test-ab.md#types) in *Översikt över A/B-test*.

Skapa en handbok [!UICONTROL A/B Test] aktivitet:

1. Från **[!UICONTROL Activities]** lista, klicka på **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**.

   ![Listrutan Skapa aktivitet](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Vilka aktivitetstyper som är tillgängliga beror på din [!DNL Target] konto. Vissa aktivitetstyper kanske inte visas i listan. Till exempel: [!UICONTROL Recommendations] är en [Target Premium-funktion](/help/main/c-intro/intro.md#premium).
   >
   >Mer information om de olika aktivitetstyperna finns i [Verksamhet](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) och [Verksamhetens syfte](/help/main/c-activities/target-activities-guide.md).

1. I dialogrutan Skapa A/B-testaktivitet väljer du **[!UICONTROL Visual (Default)]**, om det behövs.

   Om du föredrar att använda [!UICONTROL Form-Based Experience Composer], markera [!UICONTROL Form]. Se [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) för mer information.

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer], [!DNL Target] erbjuder Single Page Application VEC. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/main/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Villkorligt) Om du är en [Target Premium-kund](/help/main/c-intro/intro.md#premium), från **[!UICONTROL Choose Workspace]** väljer du en [arbetsyta](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   The [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) i föregående bild är ett [Mål Premium](/help/main/c-intro/intro.md) och kanske inte visas om din organisation har en [!UICONTROL Target Standard] licens.

1. I **[!UICONTROL Enter Activity URL]** ruta, ange [aktivitets-URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md)och sedan klicka **[!UICONTROL Create]**.

   Om ditt konto är [konfigurerad med en standard-URL](/help/main/administrating-target/visual-experience-composer-set-up.md)visas den URL-adressen som standard. Du kan ändra från standardadressen till en annan URL-adress om det behövs.

   The [!UICONTROL Visual Experience Composer] öppnas och sidan som anges i URL:en visas.

1. Klicka **[!UICONTROL Untitled Activity]** överst i VEC anger du ett namn för aktiviteten i det angivna utrymmet.

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

1. Skapa nya upplevelser genom att ändra elementen på sidan.

   The [!UICONTROL Visual Experience Composer] visar två flikar till vänster efter att du har skapat en ny aktivitet: Upplevelse A och Upplevelse B. Upplevelse A är kontrollupplevelsen. Fokus ligger på fliken Experience B, som ni kan ändra efter behov. Upplevelse B är den alternativa upplevelse som ni kan lägga till i ert test. Ni kan lägga till flera upplevelser i testet. Du kan också ta bort Experience A från aktiviteten om du inte vill inkludera en standardwebbplatsupplevelse som ett alternativ.

   Mer information om hur du lägger till och ändrar upplevelser i [!UICONTROL Visual Experience Composer], se [Lägg till upplevelse](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Om du vill ändra upplevelse B börjar du med steg 2.

1. Klicka **[!UICONTROL Targeting]** högst upp på [!UICONTROL Visual Experience Composer] för att gå vidare till nästa steg i det guidade arbetsflödet i tre steg.

   Flödesdiagrammet öppnas.

   ![A/B Test Targeting step](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   Flödesdiagrammet leder dig genom stegen för att välja målgrupp för aktiviteten och skapa upplevelser.

1. I **[!UICONTROL Audience]** klickar du på redigeringsikonen (den lodräta ellipsen) och klickar på **[!UICONTROL Replace Audience]** sedan [välj målgrupp](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) för din aktivitet.

   Som standard är målgruppen inställd på [!UICONTROL All Visitors].

1. Välj den procentandel kvalificerade besökare som du vill ange aktiviteten för.

   ![Målgruppsprocent](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Du kan t.ex. begränsa antalet deltagare till 50 % av alla besökare eller 45 % av alla dina&quot;Kalifornier&quot;-målgrupper.

1. Ställ in din trafikallokering.

   Ni kan visa flera upplevelser för samma målgrupp. Ett diagram som visar den valda målgruppen och de upplevelser som du har lagt till i aktiviteten.

   Välj den trafikallokeringsmetod du vill använda:

   * **[!UICONTROL Manual (Default)]**: Ange hur många procent av deltagarna du vill se varje upplevelse. Ni kan dela upp procentsatserna jämnt mellan alla upplevelser eller ange högre eller lägre procenttal för varje upplevelse. Det totala antalet upplevelser måste vara 100 %.

   * **[!UICONTROL Auto-allocate to best experience]**: De flesta aktivitetsdeltagare dirigeras automatiskt till högpresterande upplevelser. Vissa besökare tilldelas alla upplevelser för att kunna utforska upplevelser och för att identifiera förändringar i prestandatender. Mer information finns i [[!UICONTROL Auto-Allocate] översikt](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Auto-target for personalized experiences]**: [!DNL Target] använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser och sedan leverera den mest skräddarsydda upplevelsen till besökare baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare. Mer information finns i [Översikt över Automatiskt mål](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   Du kan också klicka **[!UICONTROL Add]** om du vill lägga till ytterligare en upplevelse till aktiviteten.

1. När du är nöjd med din publik, dina upplevelseval och dina val för trafiktilldelning klickar du **[!UICONTROL Next]** för att gå till det tredje steget i det guidade arbetsflödet i tre steg.

1. Ange [mål och inställningar](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) för aktiviteten.

1. Klicka **[!UICONTROL Save & Close]** eller **[!UICONTROL Save]**.

När du har skapat aktiviteten kan du [!UICONTROL Overview] -fliken visar information om aktiviteten, inklusive ett diagram över din aktivitet.

## Utbildningsvideo: Skapa A/B-tester (8:36) ![Självstudiemärke](/help/main/assets/tutorial.png)

I den här videon visas hur du skapar ett A/B-test med [!DNL Target] guidat arbetsflöde i tre steg.

* Skapa en [!UICONTROL A/B Test] aktivitet i [!DNL Adobe Target]
* Allokera trafik med manuell, delad eller automatisk trafikallokering

>[!VIDEO](https://video.tv.adobe.com/v/17391)
