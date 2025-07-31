---
keywords: aktiviteter;aktivitet;aktivitetstyper;redigera aktivitet;redigera;kopiera
description: Lär dig mer om olika sätt att redigera en befintlig aktivitet.
title: Hur redigerar jag en aktivitet?
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: 53bac4b1e778fb760a37e7287e0d8dbbe3a56b47
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 0%

---

# Redigera en aktivitet

Lär dig redigera befintliga aktiviteter i [!DNL Adobe Target]. I den här artikeln beskrivs de olika metoder som är tillgängliga i gränssnittet [!DNL Target] för att ändra aktiviteter. Oavsett om du uppdaterar upplevelser, justerar målinriktningsregler eller konfigurerar mål, säkerställer [!DNL Target] att dina ändringar sparas på ett säkert sätt före aktiveringen.

[!DNL Target] innehåller olika platser i användargränssnittet där du kan redigera befintliga aktiviteter. Processen varierar beroende på vilken metod du väljer.

## Redigera en aktivitet genom att använda ikonen hovring [!UICONTROL More Actions] på aktivitetssidan {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. På sidan **[!UICONTROL Activities]** klickar du på ikonen **[!UICONTROL More Actions]** ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmall.svg) ) bredvid den aktivitet som du vill redigera och sedan på [!UICONTROL **Redigera**].

   [!DNL Target] öppnar aktiviteten i [!UICONTROL Visual Experience Composer] (VEC) och du ser sidan [!UICONTROL Experiences] (det första steget i det guidade arbetsflödet i tre steg).

1. Redigera aktiviteten efter behov med [VEC-alternativen](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

1. Klicka på **[!UICONTROL Next]** för att gå vidare till nästa steg och gör sedan nödvändiga ändringar.

1. När du kommer till sidan **Mål och inställningar** har du följande alternativ:

   * **[!UICONTROL Save & Close]:** Klicka **[!UICONTROL Save and Close]** om du vill spara ändringarna och visa aktivitetens [!UICONTROL Overview]-sida.
   * **Spara:** Klicka på ikonen **[!UICONTROL More Actions]** ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmallListVert.svg) ) och välj sedan **[!UICONTROL Save]** om du vill spara ändringarna och stanna kvar i VEC där du kan fortsätta göra ändringarna. Vänta tills sparandet är klart innan du gör ytterligare ändringar. VEC läses in igen med de uppdaterade ändringarna när sparandet är slutfört.

## Redigera en aktivitet genom att klicka på dess namn på sidan [!UICONTROL Activities] {#section_176180DAD17E40CEA441903F39E0AA1C}

1. Om du vill undvika att behöva stega dig igenom arbetsflödet klickar du på önskad aktivitet på sidan [!UICONTROL Activities] för att öppna den, väljer ett alternativ i listrutan **[!UICONTROL Edit Activity]** och väljer sedan önskat alternativ.

   * **Redigera upplevelser:** Går direkt till sidan [!UICONTROL Experiences] (det första steget i det guidade arbetsflödet i tre steg).
   * **Redigera mål**: Går direkt till sidan [!UICONTROL Targeting] (det andra steget i det guidade arbetsflödet i tre steg).
   * **[!UICONTROL Goals & Settings]**: Går direkt till sidan [!UICONTROL Goals & Settings] (det tredje steget i det guidade arbetsflödet i tre steg).

1. Gör önskade ändringar och spara sedan aktiviteten.

   * **[!UICONTROL Save & Close]:** Klicka **[!UICONTROL Save and Close]** om du vill spara ändringarna och visa aktivitetens [!UICONTROL Overview]-sida.
   * **Spara:** Klicka på ikonen **[!UICONTROL More Actions]** ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmallListVert.svg) ) och välj sedan **[!UICONTROL Save]** om du vill spara ändringarna och stanna kvar i VEC där du kan fortsätta göra ändringarna. Vänta tills sparandet är klart innan du gör ytterligare ändringar. VEC läses in igen med de uppdaterade ändringarna när sparandet är slutfört.

## Kopiera/redigera en aktivitet när du använder arbetsytor {#section_45A92E1DD3934523B07E71EF90C4F8B6}

Med en arbetsyta kan en organisation tilldela en viss uppsättning användare till en viss uppsättning egenskaper. På många sätt liknar en arbetsyta en rapportserie i [!DNL Adobe Analytics].

>[!NOTE]
>
>Arbetsytor är en del av de [!UICONTROL Properties and Permissions]-funktioner som är tillgängliga som en del av lösningen [!DNL Target Premium]. De är inte tillgängliga i [!DNL Target Standard] utan en [!DNL Target Premium]-licens.

Om du är en del av en flernationell organisation kan du ha en arbetsyta för dina europeiska webbsidor, egenskaper eller webbplatser och en annan arbetsyta för dina amerikanska webbsidor, egenskaper eller webbplatser. Om du är en del av en organisation med flera varumärken kan du ha en separat arbetsyta för varje varumärke.

Mer information om arbetsytor och funktionerna för Enterprise-användarbehörigheter finns i [Enterprise-användarbehörigheter](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838).

Om du har [!UICONTROL Enterprise User Permissions] aktiverat i din miljö kan du kopiera aktiviteter till samma arbetsyta eller till en annan arbetsyta. Du kan för närvarande inte flytta en aktivitet från en arbetsyta till en annan. Om du vill kopiera en aktivitet till en annan arbetsyta går du till sidan [!UICONTROL Activities] och klickar på ikonen **[!UICONTROL More Actions]** ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmall.svg) ) bredvid den aktivitet som du vill kopiera. Klicka sedan på [!UICONTROL **Kopiera**].

Tänk på följande när du använder kopiera/redigera-funktionen med arbetsytor:

* Om du kopierar en aktivitet inom samma arbetsyta eller från standardarbetsytan till en icke-standardarbetsyta, öppnas Aktivitetsguiden automatiskt. I kopior som omfattar flera arbetsytor kanske du bara behöver uppdatera aktivitetsegenskaperna.
* När en aktivitet kopieras från en icke-standardarbetsyta till en annan arbetsyta (oavsett om den är standard eller inte) öppnas Aktivitetsguiden och vissa manuella indata krävs för att slutföra installationen:
   * **[!UICONTROL Properties]**: Egenskaperna kan skilja sig åt mellan arbetsytorna. Den här situationen kan utlösa en varning:

      * I [!UICONTROL Form-Based Experience Composer] visas varningar direkt i användargränssnittet för omedelbar synlighet.

        ![Formulärbaserad arbetsyta - varning](/help/main/c-activities/assets/form-based-warning.png)

      * I VEC visas varningar när du klickar på [!UICONTROL Configure] > [!UICONTROL Properties].

        ![vec-warning](/help/main/c-activities/assets/vec-warning.png)

        Lös problemet genom att klicka på [!UICONTROL Add/Remove] så att endast de egenskaper som är tillgängliga i målarbetsytan visas för markering.

   * **Publiker och erbjudanden**: När en aktivitet kopieras till en ny arbetsyta dupliceras alla associerade målgrupper och erbjudanden från den ursprungliga arbetsytan med formatet `Entity Name Copy <Date>`.

     Beteendeinformation:

      * Kopierade målgrupper och erbjudanden visas inte i listorna [!UICONTROL Audiences] och [!UICONTROL Offers] förrän aktiviteten har sparats och öppnats igen.
      * Dessa entiteter kan inte redigeras direkt efter kopiering. Kunder kan se tomt innehåll i VEC för dessa objekt under den inledande redigeringssessionen.
      * Kunder kan vid behov ersätta kopierade målgrupper eller erbjudanden med andra från målarbetsytan.

     Denna process ger smidigare funktioner för arbete på flera arbetsytor samtidigt som flexibiliteten för anpassning bibehålls.

     När du kopierar en aktivitet måste kombinerade målgrupper, icke-målgrupper och erbjudanden som inte har sparats på den aktuella arbetsytan eller standardarbetsytan ersättas manuellt.

     Genom att manuellt ersätta dessa kombinerade målgrupper, målgrupper och erbjudanden säkerställs att endast giltiga, tillgängliga enheter används i den kopierade aktiviteten och att fel förhindras vid redigering eller leverans.

     ![Varningsmeddelande](/help/main/c-activities/assets/copy.png)

>[!NOTE]
>
>Om miljön inte har funktionen [!UICONTROL Enterprise User Permissions] aktiverad öppnas alla aktiviteter i redigeringsläge innan de kopieras.

## Spara en aktivitet i utkastet {#section_968CD7A63027432EBD8FAE3A0F7404C3}

Funktionen [!UICONTROL Save as Draft] är inte längre tillgänglig. Mer information finns i *[!UICONTROL Status]* under [Tillämpa filter på aktivitetslistan](/help/main/c-activities/activities.md#filters).

## Arbeta med äldre aktiviteter skapade i [!DNL Recommendations Classic] {#classic}

I listan [!UICONTROL Activities] visas aktiviteter som har skapats i olika källor, bland annat [!DNL Recommendations Classic]. Följande åtgärder är tillgängliga när du arbetar med äldre aktiviteter som skapats i [!DNL Recommendations Classic]:

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

Du kan inte redigera en [!DNL Recommendations]-aktivitet direkt. Om du vill redigera aktiviteten bör du skapa en kopia av aktiviteten med [!DNL Target Premium] och sedan spara den nyligen skapade aktiviteten. Den nyligen skapade aktiviteten kan redigeras efter behov.