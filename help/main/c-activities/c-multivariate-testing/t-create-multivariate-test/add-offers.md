---
keywords: mvt;multivariate test;offers;combinations
description: Lär dig hur du använder [!UICONTROL Visual Experience Composer] (VEC) i Adobe [!DNL Target]  för att skapa erbjudanden som du vill inkludera i din [!UICONTROL Multivariate Test] (MVT).
title: Hur skapar jag kombinationer i en [!UICONTROL Multivariate Test] (MVT)?
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
source-git-commit: 8f9c0ea65197fd639d463628e54db79db993c2da
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 0%

---

# Skapa kombinationer

Använd [!UICONTROL Visual Experience Composer] (VEC) i [!DNL Adobe Target] för att skapa de erbjudanden du vill inkludera i din [!UICONTROL Multivariate Test] (MVT).

Mer information om hur du använder VEC för att skapa och redigera erbjudanden finns i [Alternativ för Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

>[!NOTE]
>
>Du kan klicka på **[!UICONTROL Expand Selection]** när du markerar objekt på sidan om du vill markera det överordnade elementet förutom det element som ursprungligen markerats. När du markerar ett överordnat element markeras alla underordnade element automatiskt. Du kan expandera markeringen flera gånger.
>
>Du kan också använda [DOM-sökvägen](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) för att navigera bland element.

## Bilderbjudanden {#section_A48333211DB149ED926AE467D0032914}

Testa flera bilder på en plats för att avgöra vilken bild som blir bäst.

1. Klicka på en bild på sidan och välj sedan **[!UICONTROL Change Image Offer]**.

1. I dialogrutan [!UICONTROL Image Offer] markerar du alla bilder som du vill ta med i testet och klickar sedan på **[!UICONTROL Add]**.

Varje bild blir en separat upplevelse på den platsen.

## HTML-erbjudanden {#section_DF016101AFA9412C9B99862C23DE77B1}

Testa olika HTML-erbjudanden på en plats för att se vilket erbjudande som är bäst.

1. Klicka på ett HTML-erbjudande på sidan och klicka sedan på **[!UICONTROL Change HTML Offer]**.

1. Klicka på **[!UICONTROL Create Offer]**, klicka på **[!UICONTROL HTML Offer]**, namnge erbjudandet, skriv in eller klistra in koden för HTML-erbjudandet och klicka sedan på **[!UICONTROL Create]**.

   Upprepa för alla andra HTML-erbjudanden du vill inkludera.

1. Klicka på **[!UICONTROL Save]**.

Varje HTML-erbjudande blir en separat upplevelse på den platsen.

## Bästa praxis {#section_2E98C23D2F1A460FA732A31799CE6291}

* Ta inte med fler platser än nödvändigt för testet. Varje upplevelse du inkluderar i testet ökar avsevärt mängden trafik och den tid som krävs för att uppnå godtagbara resultat. Om du till exempel har sidelement med tre olika erbjudanden finns det nio möjliga kombinationer (3x3). Tre element, där två innehåller tre möjliga erbjudanden och en har två, ger 18 alternativ (3x3x2). Antalet ökar avsevärt för varje ytterligare element och erbjudande.
* När du skapar multivariata tester kan du exkludera mer än 10 procent av upplevelserna från testet, förutsatt att du bekräftar att du måste använda offlinerapporter för analys.
* Använd förhandsgranskningsfunktionerna för att undvika oönskade kombinationer av innehåll. Du kan till exempel ha två bilder som ger olika rabatter för samma artikel eller tjänst. Att visa båda dessa bilder på samma sida är ologiskt och kan skapa förvirring.
* Använd [Trafikberäkning](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) för att kontrollera att ditt test är utformat för den mängd trafik som sidan tar emot. Se till att Traffic Estimator ger din testkonfiguration grönt ljus så att du kan få önskat resultat.
* Du måste ha minst tre element att testa. Om du har färre ska du köra en serie A/B-tester.
* Alternativen för varje element bör skilja sig avsevärt från varandra.
* Även om det inte är nödvändigt är det god praxis att ha samma antal alternativ för varje element.
