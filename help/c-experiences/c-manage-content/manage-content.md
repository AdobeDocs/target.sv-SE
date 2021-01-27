---
keywords: content;assets;manage content;offers;manage assets;enter selection mode;selection mode
description: Hur hanterar jag erbjudanden om kod och bilder?
title: Erbjudanden
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 70547a05155aa2909b0e66a1f26b0fd2cc730dd9
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---


# Erbjudanden

Använd [!UICONTROL Offers]-biblioteket i [!DNL Adobe Target] för att hantera erbjudandekoden och erbjudandeinnehållet för bilder.

1. Klicka på **[!UICONTROL Offers]** för att öppna biblioteket.

   Biblioteket innehåller erbjudanden som har konfigurerats via [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) och API:er. Erbjudanden som skapats i [!DNL Target Classic] eller andra lösningar kan redigeras i [!DNL Target Standard/Premium].

   Sidan [!UICONTROL Offers] har två flikar längs den högra sidan: [!UICONTROL Code Offers] och [!UICONTROL Image Offers] som gör att du kan visa erbjudanden efter typ.

   ![Sidan Erbjudanden visar flikarna Koderbjudanden och Bilderbjudanden](/help/c-experiences/c-manage-content/assets/offers-page.png)

1. (Valfritt) Klicka på listrutan **[!UICONTROL Type]** för att filtrera erbjudanden efter typ (HTML-erbjudande, [Experience Fragments](/help/c-experiences/c-manage-content/aem-experience-fragments.md), [Omdirigeringserbjudande](/help/c-experiences/c-manage-content/offer-redirect.md), [Fjärrerbjudande](/help/c-experiences/c-manage-content/about-remote-offers.md), [JSON-erbjudanden](/help/c-experiences/c-manage-content/create-json-offer.md) och [Mappar](/help/c-experiences/c-manage-content/create-content-folder.md) ).

   ![](assets/offers_filter.png)

1. (Valfritt) Klicka på listrutan **[!UICONTROL Source]** för att filtrera erbjudanden efter källa (Adobe Target, Adobe Target Classic och Adobe Experience Manager).

1. (Valfritt) Utför ytterligare åtgärder genom att hålla markören över önskat erbjudande eller mapp på fliken [!UICONTROL Code Offers] och sedan klicka på önskad ikon.

   ![Alternativ för erbjudanden](assets/offer-picker-large.png)

   Alternativen är:

   * Visa (Mer information finns i [Visa definitioner av erbjudanden](#section_6B059DD121434E6292CAB393507D010E) nedan.)
   * Redigera
   * Kopiera
   * Flytta (Om du till exempel vill flytta ett eller flera objekt till en mapp klickar du på ikonen **[!UICONTROL Move]** för det önskade objektet, klickar på önskad mapp och sedan på **[!UICONTROL Drop]**.)
   * Ta bort

   Beroende på din behörighet kanske du inte ser ikoner för alla alternativ. En användare med behörigheterna [!UICONTROL Observer] har till exempel inte behörighet att använda alternativet [!UICONTROL Copy].

1. (Valfritt) Utför ytterligare åtgärder genom att hålla markören över önskat bilderbjudande eller önskad mapp på fliken [!UICONTROL Image Offers] och sedan klicka på önskad ikon.

   ![Alternativ för bilderbjudanden](/help/c-experiences/c-manage-content/assets/image-offers-icons.png)

   Alternativen är:

   * Välj
   * Hämta
   * Visa egenskaper
   * Redigera
   * Anteckna
   * Kopiera

## Visa definitioner för erbjudanden {#section_6B059DD121434E6292CAB393507D010E}

Du kan visa information om erbjudandedefinitioner på ett popup-kort i [!UICONTROL Offers]-biblioteket utan att öppna erbjudandet.

Du kan till exempel få åtkomst till följande erbjudande genom att hovra över ett erbjudande i [!UICONTROL Content]-listan och sedan klicka på informationsikonen:

![](assets/offer-card-html.png)

Följande information finns:

* Namn
* Källa
* Typ
* Erbjudande-ID
* Erbjudandesökväg
* Senast ändrad

Klicka på fliken [!UICONTROL Offer Usage] för att visa aktiviteterna som refererar till ett koderbjudande i varje erbjudande. Den här funktionen gäller inte bilderbjudanden. På så sätt kan du undvika att andra aktiviteter påverkas när du redigerar erbjudanden. Informationen innehåller [!UICONTROL Live Activities] och [!UICONTROL Inactive Activities].

![](assets/offer-card-usage.png)

Följande kort för erbjudandedefinition för ett omdirigeringserbjudande:

![](assets/offer-card-redirect.png)

Följande information finns:

* Namn
* Källa
* Typ
* Erbjudande-ID
* Erbjudandesökväg
* Senast ändrad
* Omdirigerings-URL
* Inkludera alla URL-parametrar (På eller Av)
* Sessions-ID för lösenordssession (På eller Av)

Följande kort för definition av erbjudande för ett fjärrerbjudande:

![](assets/offer-card-remote.png)

Följande information finns:

* Namn
* Källa
* Typ
* Erbjudande-ID
* Erbjudandesökväg
* Senast ändrad
* Omdirigera URL-typ
* Absolut eller relativ URL

## Utbildningsvideo: The Content Repository ![Overview badge](/help/assets/overview.png)

Den här videon innehåller information om hur du hanterar erbjudanden.

* Anslutning mellan [Experience Cloud-resursbiblioteket](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) och målinnehållsbiblioteket
* Anpassade HTML-erbjudanden
* Anpassat HTML-erbjudande i Visual Experience Composer

>[!VIDEO](https://video.tv.adobe.com/v/17387)