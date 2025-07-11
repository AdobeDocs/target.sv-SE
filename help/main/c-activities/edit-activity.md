---
keywords: aktiviteter;aktivitet;aktivitetstyper;redigera aktivitet;redigera;utkast
description: Lär dig mer om olika sätt att redigera en befintlig aktivitet, inklusive att spara en aktivitet i ett utkast.
title: Hur redigerar jag en aktivitet eller sparar som utkast?
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: fd368ba4a59c855fe9fc7c4bada4d93fcda006f0
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 0%

---

# Redigera en aktivitet eller spara som ett utkast

Lär dig hur du redigerar befintliga aktiviteter i [!DNL Adobe Target], inklusive hur du sparar ändringar som utkast. I den här artikeln beskrivs de olika metoder som är tillgängliga i gränssnittet [!DNL Target] för att ändra aktiviteter. Oavsett om ni uppdaterar upplevelser, justerar målinriktningsregler eller konfigurerar mål, ser Target till att era ändringar sparas på ett säkert sätt före aktiveringen.

[!DNL Target] innehåller olika platser i användargränssnittet där du kan redigera befintliga aktiviteter. Processen varierar beroende på vilken metod du väljer.

## Redigera en aktivitet genom att använda ikonen hovring [!UICONTROL More Actions] på aktivitetssidan {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. På sidan **[!UICONTROL Activities]** klickar du på ikonen **[!UICONTROL More Actions]** ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmall.svg) ) bredvid den aktivitet som du vill redigera och sedan på [!UICONTROL **Redigera**].

   Målet öppnar aktiviteten i [!UICONTROL Visual Experience Composer] (VEC) och du ser sidan [!UICONTROL Experiences] (det första steget i det guidade arbetsflödet i tre steg).

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

## Arbeta med äldre aktiviteter skapade i [!DNL Recommendations Classic] {#classic}

I listan [!UICONTROL Activities] visas aktiviteter som har skapats i olika källor, bland annat [!DNL Recommendations Classic]. Följande åtgärder är tillgängliga när du arbetar med äldre aktiviteter som skapats i [!DNL Recommendations Classic]:

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

Du kan inte redigera en [!DNL Recommendations]-aktivitet direkt. Om du vill redigera aktiviteten bör du skapa en kopia av aktiviteten med [!DNL Target Premium] och sedan spara den nyligen skapade aktiviteten. Den nyligen skapade aktiviteten kan redigeras efter behov.

## Spara en aktivitet i utkastet {#section_968CD7A63027432EBD8FAE3A0F7404C3}

När du skapar en ny aktivitet som ännu inte har sparats, eller du redigerar en aktivitet som tidigare har sparats i ett utkast, visas alternativen för [!UICONTROL Save Draft] i delningsknappen.

Du kan spara en aktivitet i utkastläge om aktivitetsinställningarna har startats men inte är klara att köras.

1. Skapa en ny aktivitet eller redigera en befintlig aktivitet som är i utkastform.
1. Välj önskat alternativ från delningsknappen:

   ![Spara utkast](/help/main/c-activities/assets/save_draft.png)

   * **Nästa:** Om du vill redigera en annan sida i trestegsarbetsflödet klickar du på **[!UICONTROL Next]** för att gå vidare till önskat steg.
   * **Spara utkast och stäng:** Gör önskade ändringar i det aktuella steget, klicka på listrutan på delningsknappen och välj sedan **[!UICONTROL Save Draft and Close]** för att spara ändringarna och visa aktivitetens [!UICONTROL Overview]-sida.
   * **Spara utkast:** Gör önskade ändringar i ett steg, klicka på listrutan på delningsknappen och välj sedan **[!UICONTROL Save Draft]** för att spara ändringarna och stanna kvar på det steget.

## Kopiera/redigera en aktivitet när du använder arbetsytor {#section_45A92E1DD3934523B07E71EF90C4F8B6}

Med en arbetsyta kan en organisation tilldela en viss uppsättning användare till en viss uppsättning egenskaper. På många sätt liknar en arbetsyta en rapportserie i [!DNL Adobe Analytics].

>[!NOTE]
>
>Arbetsytor är en del av de egenskaper och behörigheter som är tillgängliga som en del av lösningen [!DNL Target Premium]. De är inte tillgängliga i [!DNL Target Standard] utan en [!DNL Target Premium]-licens.

Om du är en del av en flernationell organisation kan du ha en arbetsyta för dina europeiska webbsidor, egenskaper eller webbplatser och en annan arbetsyta för dina amerikanska webbsidor, egenskaper eller webbplatser. Om du är en del av en organisation med flera varumärken kan du ha en separat arbetsyta för varje varumärke.

Mer information om arbetsytor och funktionerna för Enterprise-användarbehörigheter finns i [Enterprise-användarbehörigheter](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838).

Om Enterprise-användarbehörigheter är aktiverade i din miljö kan du kopiera aktiviteter till samma arbetsyta eller till en annan arbetsyta. Du kan för närvarande inte flytta en aktivitet från en arbetsyta till en annan. Om du vill kopiera en aktivitet till en annan arbetsyta går du till sidan [!UICONTROL Activities] och klickar på ikonen **[!UICONTROL More Actions]** ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmall.svg) ) bredvid den aktivitet som du vill kopiera. Klicka sedan på [!UICONTROL **Kopiera**].

Tänk på följande när du använder kopiera/redigera-funktionen med arbetsytor:

* När du kopierar en aktivitet inom samma arbetsyta öppnas det första steget i skapandeflödet för den nyligen kopierade aktiviteten i redigeringsläge.
* När du kopierar en aktivitet till en annan arbetsyta kopieras aktiviteten till den andra arbetsytan utan att den öppnas i flödet där aktiviteten skapas. När aktiviteten har kopierats visas ett meddelande som anger att aktiviteten har kopierats och innehåller en länk för att öppna den nya aktiviteten.

Om din miljö inte har funktionen Enterprise-användarbehörigheter aktiverad, öppnas alla aktiviteter i redigeringsläget innan de kopieras.