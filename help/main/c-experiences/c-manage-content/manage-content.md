---
keywords: innehåll;resurser;hantera innehåll;erbjudanden;hantera resurser;ange markeringsläge;markeringsläge
description: Lär dig hantera kod- och bilderbjudanden med hjälp av Erbjudandebiblioteket i Adobe Target.
title: Hur hanterar jag erbjudanden för kod och bilder?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: f93e33e91fb7be9c0d1772a2014864b46c1dfe47
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# Erbjudanden

Använd biblioteket [!UICONTROL Offers] i [!DNL Adobe Target] för att hantera ditt erbjudande och innehåll i bilderbjudande.

1. Klicka på **[!UICONTROL Offers]** för att öppna biblioteket.

   Biblioteket innehåller erbjudanden som har konfigurerats via [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) och API:er. Erbjudanden som skapats i [!DNL Target Classic] eller andra lösningar kan redigeras i [!DNL Target Standard/Premium].

   Sidan [!UICONTROL Offers] har två flikar längs den högra sidan: [!UICONTROL Code Offers] och [!UICONTROL Image Offers] som gör att du kan visa erbjudanden efter typ.

   ![Sidan Erbjudanden innehåller flikarna Koderbjudanden och Bilderbjudanden](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. (Valfritt) Klicka på listrutan **[!UICONTROL Type]** om du vill filtrera erbjudanden efter typ (HTML-erbjudande, [Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Redirect Offer](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Remote Offer](/help/main/c-experiences/c-manage-content/about-remote-offers.md), [JSON Offers](/help/main/c-experiences/c-manage-content/create-json-offer.md) och [Folders](/help/main/c-experiences/c-manage-content/create-content-folder.md)).

   ![offers_filter-bild](assets/offers_filter.png)

1. (Valfritt) Klicka på listrutan **[!UICONTROL Source]** om du vill filtrera erbjudanden efter källa (Adobe Target, Adobe Target Classic och Adobe Experience Manager).

1. (Valfritt) Utför ytterligare åtgärder genom att hålla markören över önskat erbjudande eller mapp på fliken [!UICONTROL Code Offers] och sedan klicka på önskad ikon.

   ![Alternativ för erbjudanden av kod](assets/offer-picker-large.png)

   Alternativen är:

   * Visa (Mer information finns i [Visa definitioner för erbjudanden](#section_6B059DD121434E6292CAB393507D010E) nedan.)
   * Redigera
   * Kopiera
   * Flytta (Om du till exempel vill flytta ett eller flera objekt till en mapp klickar du på ikonen **[!UICONTROL Move]** för det önskade objektet, klickar på önskad mapp och sedan på **[!UICONTROL Drop]**.)
   * Ta bort

   Beroende på din behörighet kanske du inte ser ikoner för alla alternativ. En användare med behörigheten [!UICONTROL Observer] har till exempel inte behörighet att använda alternativet [!UICONTROL Copy].

   Mer information om de åtgärder du kan utföra på erbjudanden och mappar finns i [Arbeta med innehåll i resursbiblioteket](/help/main/c-experiences/c-manage-content/assets-working.md).

1. (Valfritt) Utför ytterligare åtgärder genom att hålla markören över önskat bilderbjudande eller önskad mapp på fliken [!UICONTROL Image Offers] och sedan klicka på önskad ikon.

   ![Alternativ för bilderbjudanden](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   Alternativen är:

   * Välj
   * Ladda ned
   * Visa egenskaper
   * Redigera
   * Anteckna
   * Kopiera

   Mer information om de åtgärder du kan utföra på erbjudanden och mappar finns i [Arbeta med innehåll i resursbiblioteket](/help/main/c-experiences/c-manage-content/assets-working.md).

   >[!NOTE]
   >
   >Bilderbjudandena ingår inte i modellen [Enterprise User Permissions](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) .


## Visa definitioner för erbjudanden {#section_6B059DD121434E6292CAB393507D010E}

Du kan visa information om erbjudandedefinitioner på ett popup-kort i biblioteket [!UICONTROL Offers] utan att öppna erbjudandet.

Du kan till exempel få åtkomst till följande erbjudande för ett HTML genom att klicka på informationsikonen:

![offer-card-html-bild](assets/offer-card-html-new.png)

Följande information finns:

* Namn
* Erbjudande-ID
* Typ
* Senast ändrad

Klicka på länken [!UICONTROL View Full Details] för att visa erbjudandeinnehållet och aktiviteterna som refererar till ett koderbjudande. På så sätt kan du undvika att andra aktiviteter påverkas när du redigerar erbjudanden. Informationen innehåller [!UICONTROL Live Activities] och [!UICONTROL Inactive Activities].

Tillgänglig information på varje kort varierar beroende på erbjudandetyp: HTML, [Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Redirect Offer](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Remote Offer](/help/main/c-experiences/c-manage-content/about-remote-offers.md) eller [JSON Offers](/help/main/c-experiences/c-manage-content/create-json-offer.md).

Funktionen för erbjudandeinformation gäller inte för bilderbjudanden.

<!--

## Training video: The Content Repository ![Overview badge](/help/main/assets/overview.png)

This video includes information about managing offers.

* Connection between the [Experience Cloud Asset Library](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) and the Target Content Library 
* Custom HTML Offers 
* Custom HTML Offer in the [!UICONTROL Visual Experience Composer]

>[!VIDEO](https://video.tv.adobe.com/v/17387)

-->
