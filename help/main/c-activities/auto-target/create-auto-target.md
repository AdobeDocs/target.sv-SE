---
keywords: Skapa automatiskt mål;A/B-test;automatiskt mål-aktivitet;ny a/b-aktivitet;automatiskt mål;automatiskt mål för personaliserade upplevelser;personaliserad;optimering
description: Lär dig hur du använder [!UICONTROL Visual Experience Composer] (VEC) för att skapa en [!UICONTROL Auto-Target] A/B-testaktivitet.
title: Hur skapar jag en [!UICONTROL Auto-Target]-aktivitet?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=sv-SE#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 0%

---

# Skapa en [!UICONTROL Auto-Target]-aktivitet

Använd [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target] för att skapa din [!UICONTROL Auto-Target] [!UICONTROL A/B Test]-aktivitet direkt på en [!DNL Target]-aktiverad sida och för att ändra delar av sidan i [!DNL Target].

>[!NOTE]
>
>[!UICONTROL Auto-Target] är tillgänglig som en del av lösningen [!DNL Target Premium]. Den här funktionen är inte tillgänglig i [!DNL Target Standard] utan en [!DNL Target Premium]-licens. Mer information om de avancerade funktioner som den här licensen innehåller finns i [Target Premium](/help/main/c-intro/intro.md).

Skapa en [!UICONTROL Auto-Target]-aktivitet:

1. Klicka på **[!UICONTROL Activities]** > **[!UICONTROL Create Activity]** i listan **[!UICONTROL A/B Test]**.

1. I dialogrutan [!UICONTROL Create A/B Test Activity] väljer du **[!UICONTROL Visual]** om det behövs.

   Om du föredrar att använda [!UICONTROL Form-Based Experience Composer] väljer du [!UICONTROL Form]. Mer information finns i [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md).

   >[!NOTE]
   >
   >Förutom VEC och [!UICONTROL Form-Based Experience Composer] erbjuder [!DNL Target] VEC:n [!UICONTROL Single Page Application]. Mer information om de olika dispositionerna finns i [Erfarenheter och erbjudanden](/help/main/c-experiences/experiences.md).
   >
   >Felsökningsinformation om VEC finns i [Felsöka Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Villkorligt) Om du är [Target Premium-kund](/help/main/c-intro/intro.md#premium) väljer du en **[!UICONTROL Choose Workspace]** arbetsyta[&#x200B; i listrutan &#x200B;](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) .

   Alternativet [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) är en [&#x200B; Target Premium](/help/main/c-intro/intro.md)-funktion och kanske inte visas om din organisation har en [!UICONTROL Target Standard]-licens.

1. Ange din **[!UICONTROL Enter Activity URL]** aktivitets-URL[&#x200B; i rutan &#x200B;](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Om ditt konto är [konfigurerat med en standard-URL](/help/main/administrating-target/visual-experience-composer-set-up.md) visas den URL:en som standard. Du kan ändra från standardadressen till en annan URL-adress om det behövs.

1. Klicka på **[!UICONTROL Create]**.

   [!UICONTROL Visual Experience Composer] öppnas och sidan som anges i URL:en visas.

1. Klicka på ikonen **[!UICONTROL Rename]** ( ![Byt namn &#x200B;](/help/main/assets/icons/MoreSmallListVert.svg) ), klicka på **[!UICONTROL Rename]**, ange ett namn för aktiviteten och klicka sedan på **[!UICONTROL Save]**.

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

   [!UICONTROL Visual Experience Composer] visar två flikar till vänster när du har skapat en ny aktivitet: [!UICONTROL Experience A] och [!UICONTROL Experience B]. [!UICONTROL Experience A] är kontrollupplevelsen. Fokus ligger på fliken [!UICONTROL Experience B] som du kan ändra efter behov. [!UICONTROL Experience B] är den alternativa upplevelse som du kan lägga till i testet. Du kan lägga till flera upplevelser i testet genom att klicka på ikonen [!UICONTROL Add] ( ![&#x200B; Lägg till ikon &#x200B;](/help/main/assets/icons/Add.svg) ) högst upp i rutan [!UICONTROL Experiences]. Du kan också ta bort Experience A från aktiviteten om du inte vill inkludera en standardwebbplatsupplevelse som ett alternativ.

   Mer information om hur du lägger till och ändrar upplevelser i [!UICONTROL Visual Experience Composer] finns i [Lägg till upplevelse](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Om du vill ändra upplevelse B börjar du med steg 2.

1. Klicka på **[!UICONTROL Targeting]** överst i [!UICONTROL Visual Experience Composer] för att gå till nästa steg i det guidade arbetsflödet i tre steg.

   Flödesdiagrammet öppnas.

   ![Åtgärd för A/B-test](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   Flödesdiagrammet leder dig genom stegen för att tilldela en målgrupp och dess trafikprocent, välja trafikallokeringsmetod och specificera trafikallokeringen för varje upplevelse i aktiviteten.

1. (Villkorligt) Klicka på kontrollen **[!UICONTROL All Visitors]** för att välja en annan målgrupp för aktiviteten.

   [!UICONTROL All Visitors]-målgruppen är inställd som standard. Om du väljer en annan målgrupp visas dess namn längst till vänster.

   Den högra bildrutan visas, vilket gör att du kan lägga till eller ta bort en målgrupp och tilldela besökarprocenten för aktiviteten.

   1. Om du vill ändra målgruppen klickar du på ikonen **[!UICONTROL Replace]** ( ![ikonen Ersätt](/help/main/assets/icons/Retweet.svg) ) i den högra ramen.
   1. I dialogrutan [!UICONTROL Add Audience] [väljer du önskad målgrupp](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) och klickar sedan på **[!UICONTROL Assign Audience]**.

      Du kan klicka på **Kombinera målgrupper** för att [skapa en målgrupp som kombinerar flera målgrupper](/help/main/c-target/combining-multiple-audiences.md).

      Om du behöver skapa en ny målgrupp som inte redan finns i [!UICONTROL Audience Library] klickar du på **Skapa målgrupp**. Under arbetsflödet [skapa målgrupper](/help/main/c-target/c-audiences/audiences.md) kan du välja bland följande alternativ:

      * **[!UICONTROL Audience Library]**: Skapa en målgrupp på begäran som sparas i [!UICONTROL Audience Library] som kan återanvändas i andra aktiviteter
      * **[!UICONTROL This activity only]**: Skapa en [aktivitetsspecifik målgrupp](/help/main/c-target/creating-activity-only-audience.md) som inte har sparats i [!UICONTROL Audience Library] och som bara kan användas i den aktuella aktiviteten

   1. Klicka på **[!UICONTROL Visitor Percentage]** i den högra bildrutan och välj sedan den procentandel kvalificerade besökare som du vill ange aktiviteten för.

   Du kan t.ex. begränsa antalet deltagare till 50 % av alla besökare eller 45 % av alla dina&quot;Kalifornier&quot;-målgrupper.

1. Klicka på kontrollen **[!UICONTROL Traffic Allocation]** och välj sedan önskad metod för trafikallokering i den högra rutan. I det här scenariot klickar du på **[!UICONTROL Auto-Taget for personalized experiences]**.

   ![Inställningar för trafikallokeringsmetod](/help/main/c-activities/assets/auto-target.png)

   Följande metoder för trafiktilldelning är tillgängliga:

   * **[!UICONTROL Manual (Default)]**: Ange hur många procent deltagare som ska se varje upplevelse. Ni kan dela upp procentsatserna jämnt mellan alla upplevelser eller ange högre eller lägre procenttal för varje upplevelse. Det totala antalet upplevelser måste vara 100 %.

   * **[!UICONTROL Auto-Allocate to best experience]**: De flesta aktivitetsdeltagare dirigeras automatiskt till upplevelser med högre prestanda. Vissa besökare tilldelas alla upplevelser för att kunna utforska upplevelser och för att identifiera förändringar i prestandatender. Mer information finns i [[!UICONTROL Auto-Allocate] - översikt](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Auto-Target for personalized experiences]**: [!DNL Target] använder avancerad maskininlärning för att personalisera innehåll och driva konverteringar genom att identifiera flera högpresterande, marknadsföringsdefinierade upplevelser och sedan leverera den mest anpassade upplevelsen till besökare baserat på deras individuella kundprofiler och tidigare beteenden hos liknande besökare. Mer information finns i [Översikt över Automatisk målning](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

1. Klicka på **[!UICONTROL Experiences]** i den högra rutan och ange sedan önskad trafikallokering för varje upplevelse.

1. När du är nöjd med din målgrupp, dina upplevelseval och dina val av trafikallokering klickar du på **[!UICONTROL Next]** för att gå till det tredje steget i det guidade arbetsflödet i tre steg.

1. Ange [mål och inställningar](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) för aktiviteten.

   >[!NOTE]
   >
   >Om du vill använda [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) med den här aktiviteten läser du viktig information i [A4T-stöd för Automatisk allokering och Automatisk målaktiviteter](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Klicka på **[!UICONTROL Save & Close]** eller **[!UICONTROL Save]**.

När du har skapat aktiviteten visas information om aktiviteten på fliken [!UICONTROL Overview], inklusive ett diagram över din aktivitet.
