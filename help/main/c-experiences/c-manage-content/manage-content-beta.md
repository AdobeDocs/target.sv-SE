---
keywords: innehåll;resurser;hantera innehåll;erbjudanden;hantera resurser;ange markeringsläge;markeringsläge
description: Lär dig hur du hanterar kod och bilderbjudanden med hjälp av Erbjudandebiblioteket.
title: Hur hanterar jag erbjudanden för kod och bilder?
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="Vad är Beta-funktioner i  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: 5d14dfd700cb1cec0fa62f66da1400bc8d7fd109
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 0%

---

# Erbjudanden

Använd biblioteket [!UICONTROL Offers] i [!DNL Adobe Target] för att hantera koden och bilderbjudandeinnehållet.

>[!NOTE]
>
>Den här artikeln innehåller information om uppdateringar av användargränssnittet [!DNL Target] som för närvarande ingår i ett Beta-program. [!DNL Adobe Target]-teamet aktiverar ofta nya funktioner för utvalda kunder i testnings- och feedbacksyfte. När testperioden är klar aktiveras dessa funktioner för alla kunder i framtida [!DNL Target Standard/Premium]-versioner och presenteras i versionsinformationen.

Klicka på fliken **[!UICONTROL Offers]** högst upp i [!DNL Target]-gränssnittet för att visa biblioteket [!UICONTROL Offers].

![Erbjudandebibliotek i Adobe Target](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

Biblioteket [!UICONTROL Offers] innehåller erbjudanden som har konfigurerats via [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) och API:er. Erbjudanden som skapats i [!DNL Target Classic] eller andra lösningar kan redigeras i [!DNL Target Standard/Premium].

Biblioteket för erbjudanden innehåller en översikt över all kod och alla bilder som erbjuds, och där kan du utföra olika åtgärder:

| Element | Beskrivning |
|--- |--- |
| Vänster navigeringsspår | Växla mellan listan [!UICONTROL Code Offers] eller [!UICONTROL Image Offers]. |
| ikonen [!UICONTROL Show filters]<P>![Ikonen Visa filter](/help/main/c-activities/assets/show-filters-icon.png) | Klicka på ikonen **[!UICONTROL Show filters]** om du vill filtrera erbjudanden efter [!UICONTROL Type], [!UICONTROL Source] och [!UICONTROL AEM Type]<P>Mer information finns i [Använda filter i listan ](#filters) nedan. |
| Sökfält | Använd fälten **[!UICONTROL Search in]** för att snabbt hitta ett erbjudande eller för att minska antalet erbjudanden som visas i biblioteket [!UICONTROL Offers]. Du kan söka efter [!UICONTROL Offer Name], [!UICONTROL AEM Paths] eller [!UICONTROL AEM Tags]. |
| [!UICONTROL Create Folder] | Klicka på Skapa mapp för att skapa mappar i biblioteket [!UICONTROL Offer] som innehåller koderbjudanden, bilderbjudanden och andra mappar för att skapa en undermappsstruktur. Mer information finns i [Skapa erbjudandemappar](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Create Offer]] | Skapa ett erbjudande. Mer information om hur du skapar olika typer av erbjudanden finns i: <ul><li>HTML</li><li>[JSON-erbjudande](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[Omdirigeringserbjudande](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[Fjärrerbjudande](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| Kryssrutor för gruppåtgärd | Utför massåtgärder för alla aktiviteter eller för valda aktiviteter.<P>En lista med tillgängliga åtgärder (beroende på dina behörigheter och erbjudandestatus) finns i [Utför snabbåtgärder](#quick-actions) nedan. |
| [!UICONTROL Name] | Namnet på varje erbjudande.<P>Klicka på ikonen **[!UICONTROL Quick Info]** bredvid varje erbjudandenamn om du vill visa mer information om erbjudandet på ett popup-kort, inklusive erbjudande-ID, typ, datum då erbjudandet senast ändrades och av vem, med mera.<p>Klicka på ikonen **[!UICONTROL More actions]** (den vågräta ellipsen) bredvid varje erbjudandenamn för att öppna en meny där du kan utföra snabba åtgärder för en aktivitet. Följande åtgärder är tillgängliga (beroende på din behörighet och erbjudandestatus): [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete] och [!UICONTROL Move]. Mer information om de olika åtgärderna finns i [Utför snabbåtgärder](#quick-actions) nedan.<P>Klicka på tabellrubriken om du vill sortera listan i stigande eller fallande ordning efter namn. |
| [!UICONTROL Type] | Erbjudandetypen: HTML, [Omdirigeringserbjudanden](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Fjärrerbjudanden](/help/main/c-experiences/c-manage-content/about-remote-offers.md) och [JSON-erbjudanden](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | Visar var erbjudandet skapades: [!DNL Adobe Target], [!DNL Adobe Target Classic] och [!DNL Adobe Experience Manager]. |

## Använda filter i erbjudandebiblioteket {#filters}

Klicka på ikonen **[!UICONTROL Show filters]** ( ![Visa filter-ikonen på sidan Erbjudanden](/help/main/c-experiences/c-manage-content/assets/show-filters-icon.png) ) om du vill filtrera erbjudanden efter [!UICONTROL Type], [!UICONTROL Source] och [!UICONTROL AEM Type].

![offers_filter-bild](assets/offers-filter-new.png)

Med ikonen **[!UICONTROL Show filters]** kan du filtrera erbjudanden efter följande kategorier:

* **Typ**: HTML, [JSON-erbjudande](/help/main/c-experiences/c-manage-content/create-json-offer.md), [omdirigeringserbjudande](/help/main/c-experiences/c-manage-content/offer-redirect.md), [fjärrabatterbjudande](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

* **Source**: [!DNL Adobe Target], [!DNL Adobe Target Classic] och [!DNL Adobe Experience Manager].

* **AEM typ**: [Innehållsfragment](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) och [Upplevelsefragment](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). Mer information om de olika fragmenttyperna finns i [AEM Översikt över Experience Fragments och Content Fragments](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Utför snabbåtgärder {#quick-actions}

Du kan utföra följande snabbåtgärder genom att klicka på lämplig ikon:

### Snabbinformation

Klicka på ikonen **[!UICONTROL Quick Info]** bredvid varje erbjudandenamn om du vill visa mer information om erbjudandet på ett popup-kort, inklusive erbjudande-ID, typ, datum då erbjudandet senast ändrades och av vem, med mera. Vilka alternativ som är tillgängliga beror på erbjudandetypen: HTML, [JSON-erbjudande](/help/main/c-experiences/c-manage-content/create-json-offer.md), [omdirigeringserbjudande](/help/main/c-experiences/c-manage-content/offer-redirect.md), [fjärrerbjudande](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

![](/help/main/c-experiences/c-manage-content/assets/quick-actions.png)

### Fler åtgärder

Vilka åtgärder som är tillgängliga för Koderbjudanden och Bilderbjudanden skiljer sig något åt. Följande avsnitt innehåller mer information:

#### Alternativ för [!UICONTROL Code Offer]

Klicka på ikonen **[!UICONTROL More actions]** (den vågräta ellipsen) bredvid varje erbjudandenamn för att öppna en meny där du kan utföra snabba åtgärder för en aktivitet. Följande åtgärder är tillgängliga (beroende på din behörighet och erbjudandestatus): [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete] och [!UICONTROL Move].

![Alternativet Fler åtgärder i målerbjudandebiblioteket](/help/main/c-experiences/c-manage-content/assets/more-actions.png)

* Redigera
* Kopiera
* Ta bort
* Flytta (Om du till exempel vill flytta ett eller flera objekt till en mapp klickar du på ikonen **[!UICONTROL Move]** för det önskade objektet, klickar på önskad mapp och sedan på **[!UICONTROL Drop]**.)

Beroende på din behörighet kanske du inte ser ikoner för alla alternativ. En användare med behörigheten [!UICONTROL Observer] har till exempel inte behörighet att använda alternativet [!UICONTROL Copy].

Mer information om de åtgärder du kan utföra på erbjudanden och mappar finns i [Arbeta med innehåll i resursbiblioteket](/help/main/c-experiences/c-manage-content/assets-working.md).

#### Alternativ för [!UICONTROL Image Offer]

Utför ytterligare åtgärder genom att hålla markören över önskat bilderbjudande eller önskad mapp på fliken [!UICONTROL Image Offers] och sedan klicka på önskad ikon.

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

Du kan till exempel få åtkomst till följande erbjudande genom att hovra över ett erbjudande i listan [!UICONTROL Content] och sedan klicka på informationsikonen:

![offer-card-html-bild](assets/offer-card-html.png)

Följande information finns:

* Namn
* Source
* Typ
* Erbjudande-ID
* Erbjudandesökväg
* Senast ändrad

Klicka på fliken [!UICONTROL Offer Usage] om du vill visa aktiviteterna som refererar till ett koderbjudande i varje erbjudandes definitionskort. Den här funktionen gäller inte bilderbjudanden. På så sätt kan du undvika att andra aktiviteter påverkas när du redigerar erbjudanden. Informationen innehåller [!UICONTROL Live Activities] och [!UICONTROL Inactive Activities].

![bild för kortanvändning](assets/offer-card-usage.png)

Följande kort för erbjudandedefinition för ett omdirigeringserbjudande:

![offer-card-redirect image](assets/offer-card-redirect.png)

Följande information finns:

* Namn
* Source
* Typ
* Erbjudande-ID
* Erbjudandesökväg
* Senast ändrad
* Omdirigeringsadress
* Inkludera alla URL-parametrar (På eller Av)
* Sessions-ID för lösenordssession (På eller Av)

Följande kort för definition av erbjudande för ett fjärrerbjudande:

![offer-card-remote image](assets/offer-card-remote.png)

Följande information finns:

* Namn
* Source
* Typ
* Erbjudande-ID
* Erbjudandesökväg
* Senast ändrad
* Omdirigera URL-typ
* Absolut eller relativ URL

## Utbildningsvideo: Märket ![Översikt för innehållsdatabasen](/help/main/assets/overview.png)

Den här videon innehåller information om hur du hanterar erbjudanden.

* Anslutning mellan [Experience Cloud-resursbiblioteket](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) och målinnehållsbiblioteket
* Erbjudanden för anpassade HTML
* Anpassat HTML-erbjudande i Visual Experience Composer

>[!VIDEO](https://video.tv.adobe.com/v/17387)
