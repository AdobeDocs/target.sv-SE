---
keywords: innehåll;resurser;hantera innehåll;erbjudanden;hantera resurser;ange markeringsläge;markeringsläge
description: Lär dig hur du hanterar kod och bilderbjudanden med hjälp av Erbjudandebiblioteket.
title: Hur hanterar jag erbjudanden för kod och bilder?
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="Vad är Beta-funktioner i [!DNL Adobe Target]."
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: 646472f35ef4623666545f9945255d61bfe16073
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 0%

---

# Erbjudanden

Använd [!UICONTROL Offers] bibliotek i [!DNL Adobe Target] för att hantera koderbjudanden och innehåll i bilderbjudanden.

>[!NOTE]
>
>Den här artikeln innehåller information om uppdateringar av [!DNL Target] användargränssnitt som för närvarande ingår i ett Beta-program. The [!DNL Adobe Target] teamet har ofta nya funktioner för utvalda kunder för testning och feedback. När testperioden är klar aktiveras dessa funktioner för alla kunder i framtiden [!DNL Target Standard/Premium] i versionsinformationen.

1. Klicka **[!UICONTROL Offers]** för att öppna biblioteket.

   Biblioteket innehåller erbjudanden som har konfigurerats via [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM) [!DNL Adobe Mobile Services] (AMS) och API:er. Erbjudanden skapade i [!DNL Target Classic] eller andra lösningar kan redigeras i [!DNL Target Standard/Premium].

   The [!UICONTROL Offers] sidan har två flikar längs den högra sidan: [!UICONTROL Code Offers] och [!UICONTROL Image Offers] som gör att du kan visa erbjudanden efter typ.

   ![Sidan Erbjudanden visar flikarna Koderbjudanden och Bilderbjudanden](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. (Valfritt) Klicka på **[!UICONTROL Type]** nedrullningsbar lista för att filtrera erbjudanden efter typ (HTML Offer, [Upplevelsefragment](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Omdirigeringserbjudande](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Fjärrerbjudande](/help/main/c-experiences/c-manage-content/about-remote-offers.md), [JSON-erbjudanden](/help/main/c-experiences/c-manage-content/create-json-offer.md)och [Mappar](/help/main/c-experiences/c-manage-content/create-content-folder.md)).

   ![offers_filter, bild](assets/offers_filter.png)

1. (Valfritt) Klicka på **[!UICONTROL Source]** nedrullningsbar lista för att filtrera erbjudanden efter källa (Adobe Target, Adobe Target Classic och Adobe Experience Manager).

1. (Valfritt) Utför ytterligare uppgifter genom att hålla markören över önskat erbjudande eller önskad mapp på [!UICONTROL Code Offers] genom att klicka på önskad ikon.

   ![Alternativ för erbjudanden](assets/offer-picker-large.png)

   Alternativen är:

   * Visa (Mer information finns i [Visa definitioner för erbjudanden](#section_6B059DD121434E6292CAB393507D010E) nedan.)
   * Redigera
   * Kopiera
   * Flytta (om du till exempel vill flytta ett eller flera objekt till en mapp klickar du på **[!UICONTROL Move]** -ikonen för det önskade objektet klickar du på önskad mapp och sedan på **[!UICONTROL Drop]**.)
   * Ta bort

   Beroende på din behörighet kanske du inte ser ikoner för alla alternativ. En användare med [!UICONTROL Observer] har inte behörighet att använda [!UICONTROL Copy] alternativ.

   Detaljerad information om de uppgifter du kan utföra på erbjudanden och mappar finns i [Arbeta med innehåll i resursbiblioteket](/help/main/c-experiences/c-manage-content/assets-working.md).

1. (Valfritt) Utför ytterligare åtgärder genom att hålla markören över önskat bilderbjudande eller önskad mapp på [!UICONTROL Image Offers] genom att klicka på önskad ikon.

   ![Alternativ för bilderbjudanden](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   Alternativen är:

   * Välj
   * Ladda ned
   * Visa egenskaper
   * Redigera
   * Anteckna
   * Kopiera

   Detaljerad information om de uppgifter du kan utföra på erbjudanden och mappar finns i [Arbeta med innehåll i resursbiblioteket](/help/main/c-experiences/c-manage-content/assets-working.md).

   >[!NOTE]
   >
   >Bilderbjudandena ingår inte i [Enterprise-användarbehörigheter](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) modell.


## Visa definitioner för erbjudanden {#section_6B059DD121434E6292CAB393507D010E}

Du kan visa information om erbjudandedefinitioner på ett popup-kort i dialogrutan [!UICONTROL Offers] utan att öppna erbjudandet.

Du kan till exempel få åtkomst till följande erbjudande för ett HTML genom att hovra över ett erbjudande på [!UICONTROL Content] och sedan klicka på informationsikonen:

![offer-card-html-bild](assets/offer-card-html.png)

Följande information finns:

* Namn
* Källa
* Typ
* Erbjudande-ID
* Erbjudandesökväg
* Senast ändrad

Klicka på [!UICONTROL Offer Usage] för att visa aktiviteter som refererar till ett koderbjudande i varje erbjudande. Den här funktionen gäller inte bilderbjudanden. På så sätt kan du undvika att andra aktiviteter påverkas när du redigerar erbjudanden. Informationen innehåller [!UICONTROL Live Activities] och [!UICONTROL Inactive Activities].

![bild av kortanvändning](assets/offer-card-usage.png)

Följande kort för erbjudandedefinition för ett omdirigeringserbjudande:

![offer-card-redirect image](assets/offer-card-redirect.png)

Följande information finns:

* Namn
* Källa
* Typ
* Erbjudande-ID
* Erbjudandesökväg
* Senast ändrad
* Omdirigeringsadress
* Inkludera alla URL-parametrar (På eller Av)
* Sessions-ID för lösenordssession (På eller Av)

Följande kort för definition av erbjudande för ett fjärrerbjudande:

![erbjudandekort-fjärrbild](assets/offer-card-remote.png)

Följande information finns:

* Namn
* Källa
* Typ
* Erbjudande-ID
* Erbjudandesökväg
* Senast ändrad
* Omdirigera URL-typ
* Absolut eller relativ URL

## Utbildningsvideo: Innehållsarkivet ![Märket Översikt](/help/main/assets/overview.png)

Den här videon innehåller information om hur du hanterar erbjudanden.

* Anslutning mellan [Experience Cloud resursbibliotek](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) och målinnehållsbiblioteket
* Erbjudanden för anpassade HTML
* Anpassat HTML-erbjudande i Visual Experience Composer

>[!VIDEO](https://video.tv.adobe.com/v/17387)
