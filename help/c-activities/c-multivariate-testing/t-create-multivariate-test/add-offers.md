---
description: Använd Visual Experience Composer (VEC) i Adobe Target för att skapa de erbjudanden du vill inkludera i ditt Multivariate Test (MVT).
title: Skapa kombinationer i multivariata tester (MVT) med Adobe Target
feature: mvt
uuid: 2ee47bf5-f8b3-41e2-b9a5-0ff4ab175373
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 0%

---


# Skapa kombinationer{#create-combinations}

Använd Visual Experience Composer (VEC) i Adobe Target för att skapa de erbjudanden du vill inkludera i ditt Multivariate Test (MVT).

Mer information om hur du använder VEC för att skapa och redigera erbjudanden finns i Alternativ för [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

>[!NOTE]
>
>Du kan klicka **[!UICONTROL Expand Selection]** när du markerar objekt på sidan för att markera det överordnade elementet förutom det ursprungligen markerade elementet. När du markerar ett överordnat element markeras alla underordnade element automatiskt. Du kan expandera markeringen flera gånger.
>
>Du kan också använda [DOM-sökvägen](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) för att navigera bland element.

## Bilderbjudanden {#section_A48333211DB149ED926AE467D0032914}

Testa flera bilder på en plats för att avgöra vilken bild som blir bäst.

1. Klicka på en bild på sidan och välj sedan **[!UICONTROL Change Image]**.

   ![Ändra bild, alternativ](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changeimage.png)

1. Markera alla bilder som du vill ta med i testet och klicka sedan på **[!UICONTROL Save]**.

   ![Välj det innehåll som ska användas för att lägga till bilder](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/addimage.png)

Varje bild blir en separat upplevelse på den platsen.

## HTML-erbjudanden {#section_DF016101AFA9412C9B99862C23DE77B1}

Testa olika text-/HTML-erbjudanden på en plats för att avgöra vilket erbjudande som är mest lyckat.

1. Klicka på ett text-/HTML-erbjudande på sidan och klicka sedan på **[!UICONTROL Change Text/HTML]**.

   ![Ändra text/HTML](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/changehtml.png)

1. Klicka **[!UICONTROL Add Text/HTML Offer]**, namnge erbjudandet och skriv eller klistra in koden för erbjudandet om text/HTML.

   ![Redigera erbjudanden](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   Upprepa för alla ytterligare text-/HTML-erbjudanden som du vill inkludera.

1. Klicka på **[!UICONTROL Save]**.

Varje text-/HTML-erbjudande blir en separat upplevelse på den platsen.

## Bästa praxis {#section_2E98C23D2F1A460FA732A31799CE6291}

* Ta inte med fler platser än nödvändigt för testet. Varje upplevelse du inkluderar i testet ökar avsevärt mängden trafik och den tid som krävs för att uppnå godtagbara resultat. Om du till exempel har sidelement med tre olika erbjudanden finns det nio möjliga kombinationer (3x3). Tre element, där två innehåller tre möjliga erbjudanden och en har två, ger 18 alternativ (3x3x2). Antalet ökar avsevärt för varje ytterligare element och erbjudande.
* När du skapar multivariata tester kan du nu exkludera mer än 10 procent av upplevelserna från testet, förutsatt att du anger att du måste använda offlinerapporter för analys.
* Använd förhandsgranskningsfunktionerna för att undvika oönskade kombinationer av innehåll. Du kan till exempel ha två bilder som ger olika rabatter för samma artikel eller tjänst. Att visa båda dessa bilder på samma sida är ologiskt och kan skapa förvirring.
* Använd Traffic Estimator för att kontrollera att ditt test är utformat för den mängd trafik din sida tar emot. Se till att Traffic Estimator ger din testkonfiguration grönt ljus så att du kan få önskat resultat.
* Du måste ha minst tre element att testa. Om du har färre ska du köra en serie A/B-tester.
* Vi rekommenderar att de olika elementens alternativ skiljer sig avsevärt från varandra.
* Även om det inte är nödvändigt är det god praxis att ha samma antal alternativ för varje element.

