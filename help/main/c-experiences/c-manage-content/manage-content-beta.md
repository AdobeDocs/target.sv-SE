---
keywords: innehåll;resurser;hantera innehåll;erbjudanden;hantera resurser;ange markeringsläge;markeringsläge
description: Lär dig hur du hanterar kod och bilderbjudanden med hjälp av Erbjudandebiblioteket.
title: Hur hanterar jag erbjudanden för kod och bilder?
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="Vad är Beta-funktioner i [!DNL Adobe Target]."
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: cd8035d9e2a369b9503763474ce09c4fe2434ae9
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 0%

---

# Erbjudanden

Använd [!UICONTROL Offers] bibliotek i [!DNL Adobe Target] för att hantera koden och bilderbjudandeinnehållet.

>[!NOTE]
>
>Den här artikeln innehåller information om uppdateringar av [!DNL Target] användargränssnitt som för närvarande ingår i ett Beta-program. The [!DNL Adobe Target] teamet har ofta nya funktioner för utvalda kunder för testning och feedback. När testperioden är klar aktiveras dessa funktioner för alla kunder i framtiden [!DNL Target Standard/Premium] i versionsinformationen.

Klicka på **[!UICONTROL Offers]** överst på [!DNL Target] Gränssnitt för att visa [!UICONTROL Offers] bibliotek.

![Erbjudandebibliotek i Adobe Target](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

The [!UICONTROL Offers] biblioteket innehåller erbjudanden som har konfigurerats via [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM) [!DNL Adobe Mobile Services] (AMS) och API:er. Erbjudanden skapade i [!DNL Target Classic] eller andra lösningar kan redigeras i [!DNL Target Standard/Premium].

Biblioteket för erbjudanden innehåller en översikt över all kod och alla bilder som erbjuds, och där kan du utföra olika åtgärder:

| Element | Beskrivning |
|--- |--- |
| Vänster navigeringsspår | Växla mellan listor [!UICONTROL Code Offers] eller [!UICONTROL Image Offers]. |
| [!UICONTROL Show filters] icon<P>![Ikonen Visa filter](/help/main/c-activities/assets/show-filters-icon.png) | Klicka på **[!UICONTROL Show filters]** ikon för att filtrera erbjudanden efter [!UICONTROL Type], [!UICONTROL Source]och [!UICONTROL AEM Type]<P>Mer information finns i [Använda filter i listan Erbjudanden](#filters) nedan. |
| Sökfält | Använd **[!UICONTROL Search in]** fält för att snabbt hitta ett erbjudande eller för att minska antalet erbjudanden som visas i [!UICONTROL Offers] bibliotek. Du kan söka efter [!UICONTROL Offer Name], [!UICONTROL AEM Paths], eller [!UICONTROL AEM Tags]. |
| [!UICONTROL Create Folder] | Klicka på Skapa mapp för att skapa mappar i [!UICONTROL Offer] bibliotek för koderbjudanden, bilderbjudanden och andra mappar för att skapa en undermappsstruktur. Mer information finns i [Skapa erbjudandemappar](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Create Offer]] | Skapa ett erbjudande. Mer information om hur du skapar olika typer av erbjudanden finns i: <ul><li>HTML</li><li>[JSON-erbjudande](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[Omdirigeringserbjudande](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[Fjärrerbjudande](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| Kryssrutor för gruppåtgärd | Utför massåtgärder för alla aktiviteter eller för valda aktiviteter.<P>En lista över tillgängliga åtgärder (beroende på din behörighet och erbjudandestatus) finns i [Utför snabbåtgärder](#quick-actions) nedan. |
| [!UICONTROL Name] | Namnet på varje erbjudande.<P>Klicka på **[!UICONTROL Quick Info]** -ikonen bredvid varje erbjudandenamn om du vill visa mer information om erbjudandet på ett popup-kort, inklusive erbjudande-ID, typ, datum då erbjudandet senast ändrades och av vem, med mera.<p>Klicka på **[!UICONTROL More actions]** -ikonen (den vågräta ellipsen) bredvid varje erbjudandenamn för att öppna en meny där du kan utföra snabba åtgärder för en aktivitet. Följande åtgärder är tillgängliga (beroende på din behörighet och erbjudandestatus): [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete]och [!UICONTROL Move]. Mer information om de olika åtgärderna finns i [Utför snabbåtgärder](#quick-actions) nedan.<P>Klicka på tabellrubriken om du vill sortera listan i stigande eller fallande ordning efter namn. |
| [!UICONTROL Type] | Erbjudandetyp: HTML Offers, [Omdirigeringserbjudanden](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Fjärrerbjudanden](/help/main/c-experiences/c-manage-content/about-remote-offers.md)och [JSON-erbjudanden](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | Visar var erbjudandet skapades: [!DNL Adobe Target], [!DNL Adobe Target Classic]och [!DNL Adobe Experience Manager]. |

## Använda filter i erbjudandebiblioteket {#filters}

Klicka på **[!UICONTROL Show filters]** ikon ( ![Ikonen Visa filter på sidan Erbjudanden](/help/main/c-experiences/c-manage-content/assets/show-filters-icon.png) ) för att filtrera erbjudanden efter [!UICONTROL Type], [!UICONTROL Source]och [!UICONTROL AEM Type].

![offers_filter, bild](assets/offers-filter-new.png)

The **[!UICONTROL Show filters]** Med ikonen kan du filtrera erbjudanden efter följande kategorier:

* **Typ**: HTML, [JSON-erbjudande](/help/main/c-experiences/c-manage-content/create-json-offer.md), [Omdirigeringserbjudande](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Fjärrerbjudande](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

* **Källa**: [!DNL Adobe Target], [!DNL Adobe Target Classic]och [!DNL Adobe Experience Manager].

* **AEM**: [Innehållsfragment](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) och [Upplevelsefragment](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). Mer information om de olika fragmenttyperna finns i [Översikt över AEM Experience Fragments och Content Fragments](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Utför snabbåtgärder {#quick-actions}

Du kan utföra följande snabbåtgärder genom att klicka på lämplig ikon:

### Snabbinformation

Klicka på **[!UICONTROL Quick Info]** -ikonen bredvid varje erbjudandenamn om du vill visa mer information om erbjudandet på ett popup-kort, inklusive erbjudande-ID, typ, datum då erbjudandet senast ändrades och av vem, med mera. Vilka alternativ som är tillgängliga beror på erbjudandetypen: HTML, [JSON-erbjudande](/help/main/c-experiences/c-manage-content/create-json-offer.md), [Omdirigeringserbjudande](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Fjärrerbjudande](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

![](/help/main/c-experiences/c-manage-content/assets/quick-actions.png)

### Fler åtgärder

Vilka åtgärder som är tillgängliga för Koderbjudanden och Bilderbjudanden skiljer sig något åt. Följande avsnitt innehåller mer information:

#### [!UICONTROL Code Offer] alternativ

Klicka på **[!UICONTROL More actions]** -ikonen (den vågräta ellipsen) bredvid varje erbjudandenamn för att öppna en meny där du kan utföra snabba åtgärder för en aktivitet. Följande åtgärder är tillgängliga (beroende på din behörighet och erbjudandestatus): [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete]och [!UICONTROL Move].

![Alternativet Fler åtgärder i målerbjudandebiblioteket](/help/main/c-experiences/c-manage-content/assets/more-actions.png)

* Redigera
* Kopiera
* Ta bort
* Flytta (om du till exempel vill flytta ett eller flera objekt till en mapp klickar du på **[!UICONTROL Move]** -ikonen för det önskade objektet klickar du på önskad mapp och sedan på **[!UICONTROL Drop]**.)

Beroende på din behörighet kanske du inte ser ikoner för alla alternativ. En användare med [!UICONTROL Observer] har inte behörighet att använda [!UICONTROL Copy] alternativ.

Detaljerad information om de uppgifter du kan utföra på erbjudanden och mappar finns i [Arbeta med innehåll i resursbiblioteket](/help/main/c-experiences/c-manage-content/assets-working.md).

#### [!UICONTROL Image Offer] alternativ

Utför ytterligare åtgärder genom att hålla markören över önskat bilderbjudande eller önskad mapp på [!UICONTROL Image Offers] genom att klicka på önskad ikon.

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
