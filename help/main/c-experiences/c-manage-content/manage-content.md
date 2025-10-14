---
keywords: innehåll;resurser;hantera innehåll;erbjudanden;hantera resurser;ange markeringsläge;markeringsläge
description: Upptäck hur du effektivt kan hantera kod- och bilderbjudanden med hjälp av biblioteket [!UICONTROL Offers].
title: Hur hanterar jag erbjudanden för kod och bilder?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: f034aba7fe4f54b937dee0846140af140052694c
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 0%

---

# Erbjudanden

Upptäck hur du effektivt hanterar kod och bilderbjudanden med hjälp av biblioteket [!UICONTROL Offers] i [!DNL Adobe Target].

Om du vill visa biblioteket [!UICONTROL Offers] klickar du på fliken **[!UICONTROL Offers]** högst upp i användargränssnittet för [!DNL Target].

![Sidan Erbjudanden](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

Biblioteket [!UICONTROL Offers] innehåller erbjudanden som har konfigurerats via [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) och API:er. Erbjudanden som skapats i [!DNL Target Classic] eller andra lösningar kan redigeras i [!DNL Target Standard/Premium].

Biblioteket [!UICONTROL Offers] ger en översikt över all kod och alla bilder som erbjuds och låter dig utföra olika åtgärder:

| Element | Beskrivning |
|--- |--- |
| Vänster navigeringsspår | Växla mellan att visa [!UICONTROL Code Offers] eller [!UICONTROL Image Offers]. |
| [!UICONTROL Show Folders] / [!UICONTROL Hide Folders]<P>![Ikonen Visa filter/dölj filter](/help/main/assets/icons/RailLeft.svg) | Klicka på ikonen **[!UICONTROL Show Folders]** eller **[!UICONTROL Hide Folders]** om du vill växla mellan att visa mappstrukturen för erbjudanden eller att inte visa mappstrukturen.<P>Mer information finns i [Skapa erbjudandemappar](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| ikonen [!UICONTROL Show filters]<P>![Ikonen Visa filter](/help/main/assets/icons/Filter.svg) | Klicka på ikonen **[!UICONTROL Show filters]** om du vill filtrera erbjudanden efter [!UICONTROL Type], [!UICONTROL Source] och [!UICONTROL AEM Type].<P>Mer information finns i [Använda filter i listan &#x200B;](#filters) nedan. |
| Sökfält | Använd fälten **[!UICONTROL Search in]** för att snabbt hitta ett erbjudande eller för att minska antalet erbjudanden som visas i biblioteket [!UICONTROL Offers]. Du kan söka efter [!UICONTROL Offer Name], [!UICONTROL AEM Paths] eller [!UICONTROL AEM Tags]. Sökalternativen är sessionskonstanta. |
| [!UICONTROL Create Folder] | Klicka på **[!UICONTROL Create Folder]** om du vill skapa mappar i biblioteket [!UICONTROL Offer] som innehåller koderbjudanden, bilderbjudanden och andra mappar för att skapa en undermappsstruktur.<P>Mer information finns i [Skapa erbjudandemappar](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Create Offer]] | Klicka på **[!UICONTROL Create Offer]** om du vill skapa ett erbjudande.<P>Mer information om hur du skapar olika typer av erbjudanden finns i: <ul><li>HTML-erbjudande</li><li>[JSON-erbjudande](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[Omdirigeringserbjudande](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[Fjärrerbjudande](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| Kryssrutor för gruppåtgärd<P>![Ikon för gruppåtgärd](/help/main/assets/icons/Rectangle.svg) | Klicka på kryssrutorna [!UICONTROL Bulk Operations] för att utföra gruppåtgärder för alla erbjudanden eller för valda erbjudanden.<P>En lista med tillgängliga åtgärder (beroende på dina behörigheter och erbjudandestatus) finns i [Utför snabbåtgärder](#quick-actions) nedan. |
| [!UICONTROL Name] | Namnet på varje erbjudande.<P>Klicka på ikonen **[!UICONTROL Quick Info]** ( ![Snabbinfo-ikon &#x200B;](/help/main/assets/icons/InfoOutline.svg) ) bredvid varje erbjudandenamn om du vill visa mer information om erbjudandet på ett popup-kort, inklusive erbjudande-ID, typ, datum då erbjudandet senast ändrades och av vem, med mera.<p>Klicka på ikonen **[!UICONTROL More Actions]** ( ![Fler åtgärder-ikon](/help/main/assets/icons/MoreSmallList.svg) ) bredvid varje erbjudandenamn för att öppna en meny där du kan utföra snabbåtgärder för en aktivitet. Följande åtgärder är tillgängliga (beroende på din behörighet och erbjudandestatus): [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete] och [!UICONTROL Move]. Mer information om de olika åtgärderna finns i [Utför snabbåtgärder](#quick-actions) nedan.<P>Klicka på tabellrubriken om du vill sortera listan i stigande eller fallande ordning efter namn. |
| [!UICONTROL Type] | Erbjudandetypen: [!UICONTROL HTML Offers], [[!UICONTROL Redirect Offers]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offers]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) och [[!UICONTROL JSON Offers]](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | Visar var erbjudandet skapades: [!DNL Adobe Target], [!DNL Adobe Target Classic] och [!DNL Adobe Experience Manager]. |
| [!UICONTROL Last updated] | Visar datum och tid då erbjudandet senast ändrades och av vem.<P>Klicka på tabellrubriken om du vill sortera listan i stigande eller fallande ordning efter datum. |

## Använda filter i erbjudandebiblioteket {#filters}

Klicka på ikonen **[!UICONTROL Show filters]** ( ![Visa filter-ikonen på sidan Erbjudanden](/help/main/assets/icons/Filter.svg)) om du vill filtrera erbjudanden efter [!UICONTROL Type], [!UICONTROL Source] och [!UICONTROL AEM Type].

Med ikonen **[!UICONTROL Show filters]** kan du filtrera erbjudanden efter följande kategorier:

* **[!UICONTROL Type]**: [!UICONTROL HTML Offer], [[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) och [[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md).

* **[!UICONTROL Source]**: [!DNL Adobe Target], [!DNL Adobe Target Classic] och [!DNL Adobe Experience Manager].

* **AEM Type**: [Content Fragments](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) och [Experience Fragments](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). Mer information om de olika fragmenttyperna finns i [Översikt över AEM Experience Fragments och Content Fragments](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

Filter är sessionskonstanta.

## Utför snabbåtgärder {#quick-actions}

Du kan utföra följande snabbåtgärder genom att klicka på lämplig ikon:

### Snabbinformation

Klicka på ikonen **[!UICONTROL Quick Info]** ( ![Snabbinfo-ikon &#x200B;](/help/main/assets/icons/InfoOutline.svg) ) bredvid varje erbjudandenamn om du vill visa mer information om erbjudandet på ett popup-kort, inklusive erbjudande-ID, typ, datum då erbjudandet senast ändrades och av vem, med mera. De tillgängliga alternativen beror på erbjudandetypen: [!UICONTROL HTML Offer], [[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md), [[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

### Fler åtgärder

De åtgärder som är tillgängliga för [!UICONTROL Code Offers] och för [!UICONTROL Image Offers] skiljer sig något åt. Följande avsnitt innehåller mer information:

#### Alternativ för [!UICONTROL Code Offer]

Klicka på ikonen **[!UICONTROL More actions]** ( ![Fler åtgärder-ikon](/help/main/assets/icons/MoreSmallList.svg) ) bredvid varje erbjudandenamn för att öppna en meny där du kan utföra snabbåtgärder för en aktivitet.

Följande åtgärder är tillgängliga (beroende på din behörighet och erbjudandestatus):

* [!UICONTROL Edit]
* [!UICONTROL Copy]
* [!UICONTROL Delete]
* [!UICONTROL Move] (Om du till exempel vill flytta ett eller flera objekt till en mapp klickar du på **[!UICONTROL Move]** bredvid det önskade objektet, klickar på önskad mapp och sedan på **[!UICONTROL Move]**.)

Beroende på din behörighet kanske du inte ser ikoner för alla alternativ. En användare med behörigheten [!UICONTROL Observer] har till exempel inte behörighet att använda alternativet [!UICONTROL Copy].

Mer information om de åtgärder du kan utföra på erbjudanden och mappar finns i [Arbeta med innehåll i resursbiblioteket](/help/main/c-experiences/c-manage-content/assets-working.md).

#### Alternativ för [!UICONTROL Image Offer]

Utför ytterligare åtgärder genom att hålla markören över önskat bilderbjudande eller önskad mapp på fliken [!UICONTROL Image Offers] och sedan klicka på önskad ikon.

Alternativen är:

* [!UICONTROL Select]
* [!UICONTROL Download]
* [!UICONTROL View Properties]
* [!UICONTROL More Actions]
* [!UICONTROL Edit]
* [!UICONTROL Annotate]
* [!UICONTROL Copy]

Mer information om de åtgärder du kan utföra på erbjudanden och mappar finns i [Arbeta med innehåll i resursbiblioteket](/help/main/c-experiences/c-manage-content/assets-working.md).

>[!NOTE]
>
>Bilderbjudandena ingår inte i modellen [Enterprise User Permissions](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) .

## Visa definitioner för erbjudanden {#section_6B059DD121434E6292CAB393507D010E}

Om du vill visa information om erbjudandedefinitioner på ett popup-kort i [!UICONTROL Offers]-biblioteket utan att öppna erbjudandet klickar du på ikonen ( ![Snabbinformation &#x200B;](/help/main/assets/icons/InfoOutline.svg) ).

Följande information finns:

* [!UICONTROL Name]
* [!UICONTROL Offer ID]
* [!UICONTROL Type]
* [!UICONTROL Last Modified]

Klicka på länken [!UICONTROL View Full Details] om du vill visa attributen och aktiviteterna för erbjudandet som refererar till ett koderbjudande i varje erbjudande. Den här funktionen gäller inte bilderbjudanden. På så sätt kan du undvika att andra aktiviteter påverkas när du redigerar erbjudanden. Informationen innehåller information om [!UICONTROL Live Activities] och [!UICONTROL Inactive Activities].
