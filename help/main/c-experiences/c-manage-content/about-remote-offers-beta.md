---
keywords: fjärterbjudande;cachelagrat innehåll;dynamiskt innehåll;URL-typ
description: Lär dig hur du använder fjärrerbjudanden i  [!DNL Target]  för att lagra externt innehåll (innehåll i ett CMS-system eller annat system).
title: Hur skapar jag fjärrerbjudanden?
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="Vad är Beta-funktioner i  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
exl-id: e83ad57e-716d-4595-b5cf-3a882fcb9e37
source-git-commit: dedef7763a1d69f80c569a0e7edaadfb310b1a15
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 0%

---

# Skapa fjärrerbjudanden

Använd fjärrerbjudanden som värd för innehåll utanför [!DNL Adobe Target] som [!DNL Target] refererar till och levererar till användarens webbplatser. Det här innehållet kan finnas i ett CMS-system eller andra system, antingen av användarvänliga skäl eller av säkerhetsskäl.

>[!NOTE]
>
>Den här artikeln innehåller information om uppdateringar av användargränssnittet [!DNL Target] som för närvarande ingår i ett Beta-program. [!DNL Adobe Target]-teamet aktiverar ofta nya funktioner för utvalda kunder i testnings- och feedbacksyfte. När testperioden är klar aktiveras dessa funktioner för alla kunder i framtida [!DNL Target Standard/Premium]-versioner och presenteras i versionsinformationen.

Fjärrerbjudanden kan skapas på [!UICONTROL Offers] > [!UICONTROL Code Offers]-sidan eller i [Forms-baserad Experience Composer](/help/main/c-experiences/form-experience-composer.md). Du kan inte skapa eller använda fjärrerbjudanden i [!UICONTROL Visual Experience Composer] (VEC). Innehållet injiceras på [!DNL Target]-begärandeplatserna, så de här platserna passar troligtvis inte för en global [!DNL Target]-begäran.

Några exempel på fjärrerbjudanden är:

* Olika versioner av era korsförsäljning
* Dynamiska kundvagnsmeddelanden
* Forms
* Beräkningar
* Ränteuppdateringar
* E-post
* Kiosker
* Röstassistenter

## Bästa tillvägagångssätt för att använda fjärrerbjudanden {#section_7718512D08E14121B6F6B8C38134F4BC}

Bästa tillvägagångssätt för att använda fjärrerbjudanden i dina aktiviteter:

* Om ditt erbjudande finns i samma domän som [!DNL Target]-förfrågningarna kan du med alternativet [!UICONTROL Cached] använda relativa URL:er för att beskriva din erbjudandeplats.

  Det innebär att när du flyttar din aktivitet från testservrarna till produktionen blir innehållet automatiskt tillgängligt utan att du behöver ändra URL-adressen manuellt.

* Om ditt test innehåller data som genererats dynamiskt av servern kan alternativet [!UICONTROL Dynamic] vara det rätta valet.
* Om du bara vill testa utseendet på ditt befintliga innehåll för fjärrerbjudanden använder du [!UICONTROL Visual Experience Composer] för att ändra utseendet på innehållet som returneras från innehållshanteringssystemet.
* Använd matrisen [för val av fjärrerbjudande](#reference_B23BEDD29DDD47709A7651AFD27E776B) (nedan) för att få hjälp att välja det erbjudande som passar ditt specifika fall bäst. Kontakta din kontorepresentant om du har frågor.

## Skapa ett fjärrerbjudande från sidan [!UICONTROL Code Offers]

1. Klicka på **[!UICONTROL Offers]** och välj sedan fliken **[!UICONTROL Code Offers]**.

   ![Erbjudanden > Koderbjudanden](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. Klicka på **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

   ![Dialogrutan Skapa fjärrerbjudande](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui_new.png)

1. Ange ett beskrivande namn för erbjudandet.

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i biblioteket [!UICONTROL Assets].

1. (Villkorligt) Om du har ett [målPremium-konto](/help/main/c-intro/intro.md#premium) väljer du önskad [arbetsyta](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. Ange typ av omdirigerings-URL.

   Mer information finns i [Omdirigerings-URL-typ: cachelagrad eller dynamisk](#url-type) nedan.

1. Ange den absoluta fjärr-URL:en för fjärrerbjudandet.

1. Klicka på **[!UICONTROL Create]**.

## Skapa ett fjärrerbjudande med [!UICONTROL Form-Based Experience Composer]

1. När du skapar en aktivitet med [formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) väljer du platsen där avsnittet **[!UICONTROL Content]** ska visas.

   ![Innehållsavsnitt i formulärbaserad Experience Composer](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Klicka på listrutan **[!UICONTROL Default Content]** och sedan på **[!UICONTROL Change Remote Offer]**.

   ![Ändra alternativ för fjärrerbjudande](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![Dialogrutan Skapa fjärrerbjudande](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Ange ett beskrivande namn för erbjudandet.

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i biblioteket [!UICONTROL Assets].

1. Ange typ av omdirigerings-URL.

   Mer information finns i [Omdirigerings-URL-typ: cachelagrad eller dynamisk](#url-type) nedan.

1. Ange fjärr-URL för fjärrerbjudandet.

1. Klicka på **[!UICONTROL Save]**.

## Omdirigerings-URL-typ: cachelagrad eller dynamisk {#url-type}

Följande information hjälper dig att förstå skillnaderna mellan de två alternativen:

### Cachelagrad URL

Innehållet i ett cachelagrat fjärrerbjudande hanteras från [!DNL Target].

Varannan timme hämtar [!DNL Target] innehållet på fjärr-URL:en och lagrar sedan innehållet i [!DNL Target]. När besökare läser in en webbplats med en upplevelse som inkluderar ett fjärrerbjudande, levererar [!DNL Target] erbjudandet.

Cachelagrade fjärrerbjudanden ger förbättrad säkerhet eftersom någon som är inloggad på [!DNL Target] inte kan ändra innehållet. För att ändra innehållet måste någon logga eller annat system och ändra innehållet där.

Du kan ange en absolut eller relativ URL för ett cachelagrat fjärrerbjudande.

### Dynamisk URL

Ett dynamiskt fjärrerbjudande levereras från innehållshanteringen eller något annat system i stället för från [!DNL Target].

Du kanske inte vill att innehållet ska cachelagras regelbundet och sedan levereras av [!DNL Target] när besökarna läser in en webbplats med en upplevelse som inkluderar ett fjärrerbjudande. I stället vill du anropa det system som är värd för innehållet och eventuellt skicka in specifik information så att det returnerade erbjudandet kan vara dynamiskt (eller olika) för varje användare. Om en användare till exempel loggar in på en webbplats för ett kreditkort som innehåller en upplevelse med ett dynamiskt fjärrerbjudande, kan du skicka parametrar till URL:en för användarens kontoinformation. Därefter kan webbplatsen innehålla användarspecifik information, t.ex. kontosaldo.

Du kan klicka på **[!UICONTROL Add Parameter]** om du vill lägga till en eller flera [!DNL Target]-begäranden eller frågeparametrar.

## Använd fjärrerbjudanden i aktiviteter

Du måste tillämpa fjärrerbjudanden med [!UICONTROL Form-Based Experience Composer]. Du kan för närvarande inte använda fjärrerbjudanden med [!UICONTROL Visual Experience Composer] (VEC).

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] är en icke-visuell upplevelse och erbjuder ett gränssnitt för att skapa upplevelser som är användbara när det gäller att skapa upplevelser som kan användas i [!UICONTROL A/B Tests]-, [!UICONTROL Experience Targeting] (XT)-, [!UICONTROL Automated Personalization] (AP)- och [!UICONTROL Recommendations]-aktiviteter när [!UICONTROL Visual Experience Composer] inte är tillgänglig eller praktiskt att använda. Du kan till exempel använda [!UICONTROL Form-Based Experience Composer] för att skapa upplevelser som använder fjärrerbjudanden.

1. Skapa eller redigera en aktivitet i [!UICONTROL Form-Based Experience Composer].

   I [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) finns detaljerade stegvisa instruktioner.

1. Ange önskad plats och lägg till eventuella målgruppsförbättringar efter behov.

1. Klicka på listrutan i avsnittet **[!UICONTROL Content]** och sedan på **[!UICONTROL Change Remote Offer]**.

   ![Ändra alternativ för fjärrerbjudande](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Välj önskat fjärrerbjudande i dialogrutan [!UICONTROL Select Remote Offer] och klicka sedan på **[!UICONTROL Done]**.

1. Slutför konfigurationen av aktiviteten.

## Så fungerar dynamiska fjärrerbjudanden {#concept_CC2A969420B34364A9FA78C1CE251818}

Dynamiska fjärrerbjudanden använder er dynamiska sidteknologi för att skicka värden till erbjudandet.

Erbjudandet verkställs när du har återgett sidan. En osynlig iFrame samlar in data, kopierar dem från ramen och infogar dem på sidan och läser in de värden som skickas.

![remote_offer_howitworks_2 image](assets/remote_offer_howitworks_2.jpeg)

1. Besökarens webbläsare begär en sida från servern.

2. Webbläsaren återger sidan, inklusive rutor.

3. `mboxCreate`-anropet innehåller parametrar som krävs för att återge dynamiskt innehåll.

4. [!DNL Target] returnerar en URL med platsen för dynamiskt innehåll och dess parametrar. Anger en iFrame i mbox-området.

5. Webbläsaren begär URL och återger på sidan.

## Markeringsmatris för fjärrerbjudande {#reference_B23BEDD29DDD47709A7651AFD27E776B}

Med matrisen för val av fjärrerbjudande kan du avgöra vilken typ av fjärrerbjudande du vill välja: [!UICONTROL Cached] eller [!UICONTROL Dynamic].

| Funktion | Cachelagrad | Dynamisk |
|--- |--- |--- |
| Uppdateringar varje gång en besökare gör en begäran | Nej | Ja |
| Innehållsuppdateringar | Cachelagras varannan timme | Uppdateras omedelbart efter varje begäran |
| Inläsningstid | Snabbare | Långsammare på grund av behandling av begäran |
| Kan se JavaScript på en sida | Ja | Nej, men kan skicka via URL |
| Erbjudandena kan omfatta JavaScript | Ja | Ja |
| Erbjudandets URL | Absolut eller relativt | Relativ |
| Begär dator | Adobe-servrar | Besökarens dator som bär besökarens cookies |

## Utbildningsvideo: Formulärbaserad disposition ![Tutorial badge](/help/main/assets/tutorial.png)

Den här videon innehåller en demonstration av [!UICONTROL Form-Based Experience Composer] som du kan använda för att skapa fjärrerbjudanden.

* Skapa en aktivitet med [!UICONTROL Form-Based Experience Composer]
* Förstå när [!UICONTROL Form-Based Experience Composer] ska användas jämfört med [!UICONTROL Visual Experience Composer]
* Använd förfiningar för att ange en plats som mål

>[!VIDEO](https://video.tv.adobe.com/v/17390)
