---
keywords: aktiviteter;aktivitet;aktivitetstyper;redigera aktivitet;redigera;utkast
description: Lär dig olika sätt att redigera en befintlig aktivitet i Adobe Target, inklusive att spara en aktivitet i ett utkast.
title: Hur redigerar jag en aktivitet eller sparar som utkast?
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 0%

---

# Redigera en aktivitet eller spara som utkast

Information om olika sätt att redigera en befintlig aktivitet i [!DNL Adobe Target], inklusive att spara en aktivitet i formulärutkast.

Target innehåller olika platser i användargränssnittet där du kan redigera befintliga aktiviteter. Processen varierar beroende på vilken metod du väljer.

## Redigera en aktivitet genom att använda hovringsknappen på aktivitetssidan {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. På sidan **[!UICONTROL Activities]** för du pekaren över aktiviteten som du vill redigera och klickar sedan på ikonen **[!UICONTROL Edit]** .

   ![Ikonen Redigera](/help/main/c-activities/assets/hover_edit.png)

   Målet öppnar aktiviteten i Visual Experience Composer (VEC) och du ser sidan [!UICONTROL Experiences] (det första steget i det guidade arbetsflödet i tre steg).

1. Redigera aktiviteten efter behov med [VEC-alternativen](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

1. Klicka på delningsknappen för att gå vidare till nästa steg eller för att spara aktiviteten.

   ![Dela knapp](/help/main/c-activities/assets/edit_split_button_2.png)

   * **Nästa:** Om du vill redigera en annan sida i trestegsarbetsflödet klickar du på **[!UICONTROL Next]** för att gå vidare till önskat steg. I bilden ovan visas till exempel steget [!UICONTROL Targeting] när du klickar på [!UICONTROL Next].
   * **Spara och stäng:** Gör önskade ändringar i det aktuella steget, klicka på listrutan på delningsknappen och välj sedan **[!UICONTROL Save and Close]** för att spara ändringarna och visa aktivitetens [!UICONTROL Overview]-sida.
   * **Spara:** Gör önskade ändringar i ett steg, klicka på listrutan på delningsknappen och välj sedan **[!UICONTROL Save]** för att spara ändringarna och stanna kvar på det steget där du kan fortsätta göra ändringarna. Vänta tills sparandet är klart innan du gör ytterligare ändringar. VEC läses in igen med de uppdaterade ändringarna när sparandet är slutfört.

## Redigera en aktivitet genom att öppna aktiviteten genom att klicka på aktivitetens namn på aktivitetssidan {#section_176180DAD17E40CEA441903F39E0AA1C}

1. Om du vill undvika att behöva stega dig igenom arbetsflödet klickar du på önskad aktivitet på aktivitetssidan för att öppna den och väljer sedan ett alternativ i listrutan **[!UICONTROL Edit Activity]**.

   ![Listrutan Redigera aktivitet](/help/main/c-activities/assets/edit_activity.png)

1. Välj önskat alternativ:

   * **Redigera upplevelser:** Går direkt till sidan [!UICONTROL Experiences] (det första steget i det guidade arbetsflödet). Gör önskade ändringar och använd sedan knappen Dela (se ovan) för att spara aktiviteten.

      * Klicka på **[!UICONTROL Save & Close]** om du vill spara ändringarna och visa aktivitetens översiktssida.
      * Klicka på **[!UICONTROL Save]** om du vill spara ändringarna och fortsätta där du kan fortsätta göra ändringarna. Vänta tills sparandet är klart innan du gör ytterligare ändringar. VEC läses in igen med de uppdaterade ändringarna när sparandet är slutfört.

   * **Redigera mål:** Går direkt till sidan [!UICONTROL Targeting] (det andra steget i det guidade arbetsflödet). Gör önskade ändringar och använd sedan knappen Dela (se ovan) för att spara aktiviteten.

      * Klicka på **[!UICONTROL Save & Close]** om du vill spara ändringarna och visa aktivitetens översiktssida.
      * Klicka på **[!UICONTROL Save]** om du vill spara ändringarna och fortsätta där du kan fortsätta göra ändringarna. Vänta tills sparandet är klart innan du gör ytterligare ändringar. VEC läses in igen med de uppdaterade ändringarna när sparandet är slutfört.

   * **Redigera mål och inställningar:** Går direkt till sidan [!UICONTROL Goals & Settings] (det sista steget i det guidade arbetsflödet). Gör önskade ändringar och använd sedan knappen Dela (se ovan) för att spara aktiviteten.

      * Klicka på **[!UICONTROL Save & Close]** om du vill spara ändringarna och visa aktivitetens översiktssida.
      * Klicka på **[!UICONTROL Save]** om du vill spara ändringarna och fortsätta där du kan fortsätta göra ändringarna. Vänta tills sparandet är klart innan du gör ytterligare ändringar. VEC läses in igen med de uppdaterade ändringarna när sparandet är slutfört.

## Arbeta med äldre aktiviteter som skapats i Recommendations Classic {#classic}

I listan [!UICONTROL Activities] visas aktiviteter som har skapats i olika källor, bland annat [!DNL Recommendations Classic]. Följande åtgärder är tillgängliga när du arbetar med äldre aktiviteter som skapats i [!DNL Recommendations Classic]:

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

Du kan inte redigera en [!DNL Recommendations]-aktivitet direkt. Om du vill redigera aktiviteten bör du skapa en kopia av aktiviteten med [!DNL Target Premium] och sedan spara den nyligen skapade aktiviteten. Den nyligen skapade aktiviteten kan redigeras efter behov.

## Spara en aktivitet i utkastet {#section_968CD7A63027432EBD8FAE3A0F7404C3}

När du skapar en ny aktivitet som ännu inte har sparats, eller du redigerar en aktivitet som tidigare har sparats i ett utkast, visas alternativet Spara utkast i delningsknappen.

Du kan spara en aktivitet i utkastläge om aktivitetsinställningarna har startats men inte är klara att köras.

1. Skapa ny aktivitet eller redigera en befintlig aktivitet som är i utkastform.
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

Om Enterprise-användarbehörigheter är aktiverade i din miljö kan du kopiera aktiviteter till samma arbetsyta eller till en annan arbetsyta. Du kan för närvarande inte flytta en aktivitet från en arbetsyta till en annan. Om du vill kopiera en aktivitet till en annan arbetsyta går du till sidan [!UICONTROL Activities], håller pekaren över den aktivitet du vill kopiera, klickar på ikonen [!UICONTROL Copy] och väljer sedan önskad arbetsyta i listrutan.

Tänk på följande när du använder kopiera/redigera-funktionen med arbetsytor:

* När du kopierar en aktivitet inom samma arbetsyta öppnas det första steget i skapandeflödet för den nyligen kopierade aktiviteten i redigeringsläge.
* När du kopierar en aktivitet till en annan arbetsyta kopieras aktiviteten till den andra arbetsytan utan att den öppnas i flödet där aktiviteten skapas. När aktiviteten har kopierats visas ett meddelande som anger att aktiviteten har kopierats och innehåller en länk för att öppna den nya aktiviteten.

Om din miljö inte har funktionen Enterprise-användarbehörigheter aktiverad, öppnas alla aktiviteter i redigeringsläget innan de kopieras.

## God praxis

* Det bästa sättet är att försöka uppdatera aktiviteten med samma metod (UI eller API) som användes för att skapa aktiviteten från början.

  Aktiviteter som skapats med användargränssnittet för [!DNL Target] bör uppdateras via användargränssnittet för [!DNL Target]. Aktiviteter som skapas via API ska uppdateras via API. Om du ursprungligen skapade en aktivitet med API, till exempel, men sedan redigerar aktiviteten via användargränssnittet i [!DNL Target], uppdateras inte alla ändringar. Alla ändringar lagras på serverdelen och kan uppdateras genom att du gör ett annat API-anrop.


