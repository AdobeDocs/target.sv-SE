---
keywords: innehållsbibliotek;resurser;anteckna;kopiera;ta bort resurs;hämta resurs;redigera innehåll;dela kort;visa innehållsegenskaper
description: Upptäck hur du organiserar och optimerar din kod och dina bilderbjudanden i biblioteket  [!DNL Target] [!UICONTROL Offers].
title: Huvudinnehållshantering i biblioteket [!UICONTROL Offers]
feature: Experiences and Offers
hide: true
hidefromtoc: true
exl-id: 5d836037-3f51-4c63-8717-65de72e5c793
source-git-commit: c9d987a7e27bbaa605f4d7b45975c854b61783de
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 0%

---

# Arbeta med innehåll i resursbiblioteket

Information om de uppgifter du kan utföra på en resurs i [!UICONTROL Content Library] i [!DNL Adobe Target]. Bland uppgifterna finns anteckning, kopiering, borttagning, hämtning, redigering, delning och visningsegenskaper.

1. Klicka på **[!UICONTROL Offers]** > **[!UICONTROL Code Offers]** eller **[!UICONTROL Image Offers]**.

   Mer information om hur du söker i [!UICONTROL Offer library] och skapar [!UICONTROL Smart Collections] finns i [Filtrera och söka efter innehåll](/help/main/c-experiences/c-manage-content/filter-and-search-content.md#concept_3B59B8F025BF4CEA82ECC5199D365276).

1. (Villkorligt) För bildeffekter växlar du mellan [!UICONTROL Card View] och [!UICONTROL List View] genom att klicka på ikonen [!UICONTROL Card View] eller ikonen [!UICONTROL List View] i det övre högra hörnet av innehållsbiblioteket. Du kan också använda [!UICONTROL View Settings] för att konfigurera kolumnerna när du visar [!UICONTROL List View].

   Följande bild visar de tillgängliga alternativen när du visar [!UICONTROL List View]:

   ![Alternativ för listvisning](/help/main/c-experiences/c-manage-content/assets/view-settings-options.png)

1. Utför den önskade åtgärden enligt följande avsnitt:

## Alternativ för [!UICONTROL Code Offers]

När du visar sidan [!UICONTROL Code Offers] kan du utföra följande åtgärder för ett objekt genom att hålla markören över ett erbjudande eller en mapp och sedan välja lämplig ikon.

![Hovringsikoner på fliken Koderbjudanden](/help/main/c-experiences/c-manage-content/assets/code-offers-hover-icons-new.png)

* **Information**: Klicka på ikonen [!UICONTROL Information] om du vill visa erbjudandets information, inklusive [!UICONTROL Offer ID], [!UICONTROL Type], [!UICONTROL Last Modified] (datum, tid och modifierarens namn). Klicka på [!UICONTROL Full Details] om du vill visa ytterligare information, inklusive erbjudandeattribut och aktivitetsanvändning (aktivitetsnamn, status, arbetsyta och ändringsdatum och -tid).
* **Redigera**: Redigera mappen eller erbjudandet.
* **Kopiera**: Kopiera erbjudandet. Om du kopierar och sedan redigerar erbjudandet kan du enkelt skapa ett liknande nytt erbjudande.
* **Ta bort**: Ta bort erbjudandet eller mappen. Se [Att tänka på när du tar bort objekt](#delete).
* **Flytta**: Klicka på ikonen [!UICONTROL Move], navigera till platsen dit du vill flytta erbjudandet eller mappen och klicka sedan på **[!UICONTROL Move]**. Du kan till exempel flytta en eller flera mappar till en annan mapp för att skapa undermappar.

## Alternativ för [!UICONTROL Image Offers]

När du visar sidan [!UICONTROL Image Offers] kan du utföra följande åtgärder för ett objekt genom att hålla markören över ett erbjudande eller en mapp och sedan välja lämplig ikon.

Följande bild visar hovringsikonerna när [!UICONTROL Card View] visas.

![Hovringsikoner på fliken Bilderbjudanden i kortvyn](/help/main/c-experiences/c-manage-content/assets/image-offers-hover-icons.png)

Följande bild visar hovringsikonerna när [!UICONTROL List View] visas. Om du vill visa ikonerna klickar du på ett objekt i listan.

![Hovringsikoner på fliken Bilderbjudanden i listvyn](/help/main/c-experiences/c-manage-content/assets/list-view-hover.png)

* **Välj**: Markera en eller flera mappar som du vill utföra följande åtgärder på:

   * Ladda ned
   * Kopiera
   * Flytta
   * Ta bort (Se [Att tänka på när du tar bort objekt](#delete).)

  Välj en eller flera bilder som du vill utföra följande åtgärder på:

   * Dela
   * Ladda ned
   * Visa egenskaper
   * Redigera
   * Anteckna
   * Flytta

* **Hämta**: Hämta bilderbjudandet eller mappen och dess innehåll.
* **Visa egenskaper**: Visa objektets egenskaper. Klicka på fliken [!UICONTROL Basic] och fliken [!UICONTROL Advanced] för att visa all tillgänglig information. Du kan redigera egenskaperna och lägga till mer information. Du kan lägga till metadatainformation, publiceringsstatus och licensdata.
* **Fler åtgärder**: Visa ytterligare alternativ i [!UICONTROL Card View].
* **Redigera**: Redigera mappen eller erbjudandet.
* **Anteckning**: Lägg till en anteckning till resursen. Klicka på resursen, markera området som du vill kommentera och skriv anteckningen.
* **Kopiera**: Kopiera erbjudandet. Om du kopierar och sedan redigerar erbjudandet kan du enkelt skapa ett liknande nytt erbjudande.
* **Flytta**: Klicka på ikonen [!UICONTROL Move], navigera till platsen dit du vill flytta erbjudandet eller mappen och klicka sedan på **[!UICONTROL Move]**. Du kan till exempel flytta en eller flera mappar till en annan mapp för att skapa undermappar.

## Att tänka på när du tar bort objekt {#delete}

* Du kan ta bort en hel mapp som innehåller valfritt antal resurser och undermappar. Den här funktionen är tillgänglig i användargränssnittet för [!DNL Target] och i användargränssnittet för [!DNL Adobe Experience Cloud Assets].
* Om du tar bort en mapp med ett stort antal bilder kan processen som körs bakom scenerna ta tid (flera minuter) innan användargränssnittet uppdateras för att visa det slutliga läget. Den tid som krävs är en funktion av antalet bilder, inte bildens storlek. En bra uppskattning är tio minuter för 2 000 bilder. Du kan fortsätta med annat arbete och kontrollera det slutliga läget efter flera minuter för att bekräfta borttagningen.
* Mappar som inte är tomma i [!UICONTROL Image Offer library] kan tas bort. Om inga referenser finns till alla bilder i mappen i någon aktivitet tas hela mappen och dess innehåll bort. Om det finns referenser till vissa bilder i mappen i någon aktivitet, tas alla bilder som inte refereras bort, men refererade bilder och mappar som innehåller dessa bilder behålls.
