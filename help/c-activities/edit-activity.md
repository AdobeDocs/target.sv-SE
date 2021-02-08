---
keywords: aktiviteter;aktivitet;aktivitetstyper;redigera aktivitet;redigera;utkast
description: Lär dig olika sätt att redigera en befintlig aktivitet i Adobe Target, inklusive att spara en aktivitet i ett utkast.
title: Hur redigerar jag en aktivitet eller sparar som utkast?
feature: Activities
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Redigera en aktivitet eller spara som utkast

Information om olika sätt att redigera en befintlig aktivitet i [!DNL Adobe Target], inklusive att spara en aktivitet i ett utkast.

Target innehåller olika platser i användargränssnittet där du kan redigera befintliga aktiviteter. Processen varierar beroende på vilken metod du väljer.

## Redigera en aktivitet genom att använda hovringsknappen på aktivitetssidan {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. Håll markören över aktiviteten som du vill redigera på **[!UICONTROL Activities]**-sidan och klicka sedan på ikonen **[!UICONTROL Edit]**.

   ![Ikonen Redigera](/help/c-activities/assets/hover_edit.png)

   Målet öppnar aktiviteten i Visual Experience Composer (VEC) och du ser sidan [!UICONTROL Experiences] (det första steget i det guidade arbetsflödet i tre steg).

1. Redigera aktiviteten efter behov med [VEC-alternativen](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

1. Klicka på delningsknappen för att gå vidare till nästa steg eller för att spara aktiviteten.

   ![Dela, knapp](/help/c-activities/assets/edit_split_button_2.png)

   * **Nästa:** Om du vill redigera en annan sida i trestegsarbetsflödet klickar du  **[!UICONTROL Next]** för att gå vidare till önskat steg. I bilden ovan visas till exempel steget [!UICONTROL Next] när du klickar på [!UICONTROL Targeting].
   * **Spara och stäng:** Gör önskade ändringar i det aktuella steget, klicka på listrutan på delningsknappen och välj sedan  **[!UICONTROL Save and Close]** att spara ändringarna och visa aktivitetens  [!UICONTROL Overview] sida.
   * **Spara:** Gör önskade ändringar i ett steg, klicka på listrutan på delningsknappen och välj sedan  **[!UICONTROL Save]** att spara ändringarna och stanna kvar på det steget där du kan fortsätta göra ändringarna. Vänta tills sparandet är klart innan du gör ytterligare ändringar. VEC läses in igen med de uppdaterade ändringarna när sparandet är slutfört.

## Redigera en aktivitet genom att öppna aktiviteten genom att klicka på aktivitetens namn på aktivitetssidan {#section_176180DAD17E40CEA441903F39E0AA1C}

1. Om du vill undvika att behöva stega dig igenom arbetsflödet klickar du på önskad aktivitet på sidan Aktiviteter för att öppna den och väljer sedan ett alternativ i listrutan **[!UICONTROL Edit Activity]**.

   ![Listrutan Redigera aktivitet](/help/c-activities/assets/edit_activity.png)

1. Välj önskat alternativ:

   * **Redigera upplevelser:** Går direkt till  [!UICONTROL Experiences] sidan (det första steget i det guidade arbetsflödet). Gör önskade ändringar och använd sedan knappen Dela (se ovan) för att spara aktiviteten.

      * Klicka på **[!UICONTROL Save & Close]** för att spara ändringarna och visa aktivitetens översiktssida.
      * Klicka på **[!UICONTROL Save]** om du vill spara ändringarna och fortsätta där du kan fortsätta göra ändringarna. Vänta tills sparandet är klart innan du gör ytterligare ändringar. VEC läses in igen med de uppdaterade ändringarna när sparandet är slutfört.
   * **Redigera mål:** Går direkt till  [!UICONTROL Targeting] sidan (det andra steget i det guidade arbetsflödet). Gör önskade ändringar och använd sedan knappen Dela (se ovan) för att spara aktiviteten.

      * Klicka på **[!UICONTROL Save & Close]** för att spara ändringarna och visa aktivitetens översiktssida.
      * Klicka på **[!UICONTROL Save]** om du vill spara ändringarna och fortsätta där du kan fortsätta göra ändringarna. Vänta tills sparandet är klart innan du gör ytterligare ändringar. VEC läses in igen med de uppdaterade ändringarna när sparandet är slutfört.
   * **Redigera mål och inställningar:** Går direkt till  [!UICONTROL Goals & Settings] sidan (det sista steget i det guidade arbetsflödet). Gör önskade ändringar och använd sedan knappen Dela (se ovan) för att spara aktiviteten.

      * Klicka på **[!UICONTROL Save & Close]** för att spara ändringarna och visa aktivitetens översiktssida.
      * Klicka på **[!UICONTROL Save]** om du vill spara ändringarna och fortsätta där du kan fortsätta göra ändringarna. Vänta tills sparandet är klart innan du gör ytterligare ändringar. VEC läses in igen med de uppdaterade ändringarna när sparandet är slutfört.



## Arbeta med äldre aktiviteter som skapats i Recommendations Classic {#classic}

I [!UICONTROL Activities]-listan visas aktiviteter som har skapats i olika källor, bland annat [!DNL Recommendations Classic]. Följande åtgärder är tillgängliga när du arbetar med äldre aktiviteter som skapats i [!DNL Recommendations Classic]:

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

Du kan inte redigera en [!DNL Recommendations]-aktivitet direkt. Om du vill redigera aktiviteten bör du skapa en kopia av aktiviteten med [!DNL Target Premium] och sedan spara den nya aktiviteten. Den nyligen skapade aktiviteten kan redigeras efter behov.

## Spara en aktivitet i utkastformulär {#section_968CD7A63027432EBD8FAE3A0F7404C3}

När du skapar en ny aktivitet som ännu inte har sparats, eller du redigerar en aktivitet som tidigare har sparats i ett utkast, visas alternativet Spara utkast i delningsknappen.

Du kan spara en aktivitet i utkastläge om aktivitetsinställningarna har startats men inte är klara att köras.

1. Skapa ny aktivitet eller redigera en befintlig aktivitet som är i utkastform.
1. Välj önskat alternativ från delningsknappen:

   ![Spara utkast](/help/c-activities/assets/save_draft.png)

   * **Nästa:** Om du vill redigera en annan sida i trestegsarbetsflödet klickar du  **[!UICONTROL Next]** för att gå vidare till önskat steg.
   * **Spara utkast och stäng:** Gör önskade ändringar i det aktuella steget, klicka på listrutan på delningsknappen och välj sedan  **[!UICONTROL Save Draft and Close]** att spara ändringarna och visa aktivitetens  [!UICONTROL Overview] sida.
   * **Spara utkast:** Gör önskade ändringar i ett steg, klicka på listrutan på delningsknappen och välj sedan  **[!UICONTROL Save Draft]** att spara ändringarna och stanna kvar på det steget.

## Kopiera/redigera en aktivitet när du använder arbetsytor {#section_45A92E1DD3934523B07E71EF90C4F8B6}

Med en arbetsyta kan en organisation tilldela en viss uppsättning användare till en viss uppsättning egenskaper. På många sätt liknar en arbetsyta en rapportserie i [!DNL Adobe Analytics].

>[!NOTE]
>
>Arbetsytor är en del av de egenskaper och behörigheter som är tillgängliga som en del av [!DNL Target Premium]-lösningen. De är inte tillgängliga i [!DNL Target Standard] utan en [!DNL Target Premium]-licens.

Om du är en del av en flernationell organisation kan du ha en arbetsyta för dina europeiska webbsidor, egenskaper eller webbplatser och en annan arbetsyta för dina amerikanska webbsidor, egenskaper eller webbplatser. Om du är en del av en organisation med flera varumärken kan du ha en separat arbetsyta för varje varumärke.

Mer information om arbetsytor och funktionerna för Enterprise-användarbehörigheter finns i [Enterprise-användarbehörigheter](/help/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838).

Om Enterprise-användarbehörigheter är aktiverade i din miljö kan du kopiera aktiviteter till samma arbetsyta eller till en annan arbetsyta. Du kan för närvarande inte flytta en aktivitet från en arbetsyta till en annan. Om du vill kopiera en aktivitet till en annan arbetsyta håller du markören över den aktivitet du vill kopiera från sidan [!UICONTROL Activities], klickar på ikonen [!UICONTROL Copy] och väljer sedan önskad arbetsyta i listrutan.

Tänk på följande när du använder kopiera/redigera-funktionen med arbetsytor:

* När du kopierar en aktivitet inom samma arbetsyta öppnas det första steget i skapandeflödet för den nyligen kopierade aktiviteten i redigeringsläge.
* När du kopierar en aktivitet till en annan arbetsyta kopieras aktiviteten till den andra arbetsytan utan att den öppnas i flödet där aktiviteten skapas. När aktiviteten har kopierats visas ett meddelande som anger att aktiviteten har kopierats och innehåller en länk för att öppna den nya aktiviteten.

Om din miljö inte har funktionen Enterprise-användarbehörigheter aktiverad, öppnas alla aktiviteter i redigeringsläget innan de kopieras.
