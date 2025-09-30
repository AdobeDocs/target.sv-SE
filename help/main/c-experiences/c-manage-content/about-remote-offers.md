---
keywords: fjärterbjudande;cachelagrat innehåll;dynamiskt innehåll;URL-typ
description: Upptäck hur ni kan utnyttja fjärrerbjudanden i  [!DNL Target]  för att lagra externt innehåll från CMS eller andra system.
title: Hur skapar jag fjärrerbjudanden?
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: 856396264c4a7b7e3370cd268e7f010092e2eae2
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 0%

---

# Skapa fjärrerbjudanden

Använd fjärrerbjudanden för att lagra innehåll utanför [!DNL Adobe Target], så att [!DNL Target] kan referera till och leverera det här innehållet till användarens webbplatser. Det här innehållet kan finnas i ett innehållshanteringssystem (CMS) eller i ett annat system av användarvänliga eller säkerhetsskäl.

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

* Fjärrerbjudanden stöds i:

   * A/B-verksamhet
   * XT-aktiviteter (Experience Targeting)
   * Formulärbaserade arbetsflöden

* Fjärrerbjudanden stöds inte i:

   * [Premiumfunktioner](/help/main/c-intro/intro.md#premium) (Automated Personalization (AP), Automatiskt mål och rekommendationer)
   * Multivariate Testing (MVT), eftersom VEC är beroende av, som inte stöder fjärrerbjudanden.

* Om ditt erbjudande finns i samma domän som [!DNL Target]-förfrågningarna kan du med alternativet [!UICONTROL Cached] använda relativa URL:er för att beskriva din erbjudandeplats.

  Det innebär att när du flyttar din aktivitet från testservrarna till produktionen blir innehållet automatiskt tillgängligt utan att du behöver ändra URL-adressen manuellt.

* Om ditt test innehåller data som genererats dynamiskt av servern kan alternativet [!UICONTROL Dynamic] vara det rätta valet.
* Om du bara vill testa utseendet på ditt befintliga innehåll för fjärrerbjudanden använder du [!UICONTROL Visual Experience Composer] för att ändra utseendet på innehållet som returneras från innehållshanteringssystemet.
* Använd matrisen [för val av fjärrerbjudande](#reference_B23BEDD29DDD47709A7651AFD27E776B) (nedan) för att få hjälp att välja det erbjudande som passar ditt specifika fall bäst. Kontakta din kontorepresentant om du har frågor.

## Skapa ett fjärrerbjudande från sidan [!UICONTROL Code Offers]

1. Klicka på **[!UICONTROL Offers]** och välj sedan fliken **[!UICONTROL Code Offers]**.

1. Klicka på **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

1. Ange ett beskrivande namn för erbjudandet i dialogrutan [!UICONTROL Create Remote Offer].

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i biblioteket [!UICONTROL Offers].

1. (Villkorligt) Om du har ett [Target Premium-konto](/help/main/c-intro/intro.md#premium) väljer du önskad [arbetsyta](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. Ange typ av omdirigerings-URL.

   Mer information finns i [Omdirigerings-URL-typ: [!UICONTROL Onsite Cached] eller [!UICONTROL Onsite Dynamic]](#url-type) nedan.

1. Ange den absoluta fjärr-URL:en för fjärrerbjudandet.

1. Klicka på **[!UICONTROL Create]**.

## Skapa ett fjärrerbjudande med [!UICONTROL Form-Based Experience Composer]

1. När du skapar en aktivitet med [formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) väljer du platsen där avsnittet **[!UICONTROL Content]** ska visas.
1. Klicka på listrutan **[!UICONTROL Content]**, klicka på ikonen **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) och sedan på **[!UICONTROL Change Remote Offer]**.

1. Klicka på **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

1. Ange ett beskrivande namn för erbjudandet.

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i biblioteket [!UICONTROL Assets].

1. (Villkorligt) Om du har ett [Target Premium-konto](/help/main/c-intro/intro.md#premium) väljer du önskad [arbetsyta](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. Ange typ av omdirigerings-URL.

   Mer information finns i [Omdirigerings-URL-typ: [!UICONTROL Onsite Cached] eller [!UICONTROL Onsite Dynamic]](#url-type) nedan.

1. Ange fjärr-URL för fjärrerbjudandet.

1. Klicka på **[!UICONTROL Create]**.

## Omdirigerings-URL-typ: [!UICONTROL Onsite Cached] eller [!UICONTROL Onsite Dynamic] {#url-type}

Följande information hjälper dig att förstå skillnaderna mellan de två alternativen:

### URL för [!UICONTROL Onsite Cached]

Innehållet i ett cachelagrat fjärrerbjudande hanteras från [!DNL Target].

Varannan timme hämtar [!DNL Target] innehållet på fjärr-URL:en och lagrar sedan innehållet i [!DNL Target]. När besökare läser in en webbplats med en upplevelse som inkluderar ett fjärrerbjudande, levererar [!DNL Target] erbjudandet.

Cachelagrade fjärrerbjudanden ger förbättrad säkerhet eftersom någon som är inloggad på [!DNL Target] inte kan ändra innehållet. För att ändra innehållet måste någon logga in på innehållshanteringen eller något annat system och ändra innehållet där.

Du kan ange en absolut eller relativ URL för ett cachelagrat fjärrerbjudande.

### URL för [!UICONTROL Onsite Dynamic]

Ett dynamiskt fjärrerbjudande levereras från innehållshanteringen eller något annat system i stället för från [!DNL Target].

Du kanske inte vill att innehållet ska cachelagras regelbundet och sedan levereras av [!DNL Target] när besökarna läser in en webbplats med en upplevelse som inkluderar ett fjärrerbjudande. I stället vill du anropa det system som är värd för innehållet och eventuellt skicka in specifik information så att det returnerade erbjudandet kan vara dynamiskt (eller olika) för varje användare. Om en användare till exempel loggar in på en webbplats för ett kreditkort som innehåller en upplevelse med ett dynamiskt fjärrerbjudande, kan du skicka parametrar till URL:en för användarens kontoinformation. Därefter kan webbplatsen innehålla användarspecifik information, t.ex. kontosaldo.

Du kan klicka på **[!UICONTROL Add Parameter]** om du vill lägga till en eller flera [!DNL Target]-begäranden eller frågeparametrar.

## Använd fjärrerbjudanden i aktiviteter

Använd fjärrerbjudanden med [!UICONTROL Form-Based Experience Composer]. Du kan för närvarande inte använda fjärrerbjudanden med [!UICONTROL Visual Experience Composer] (VEC).

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] är en icke-visuell upplevelse och erbjuder ett gränssnitt för att skapa upplevelser som är användbara när det gäller att skapa upplevelser som kan användas i [!UICONTROL A/B Tests]-, [!UICONTROL Experience Targeting] (XT)-, [!UICONTROL Automated Personalization] (AP)- och [!UICONTROL Recommendations]-aktiviteter när [!UICONTROL Visual Experience Composer] inte är tillgänglig eller praktiskt att använda. Du kan till exempel använda [!UICONTROL Form-Based Experience Composer] för att skapa upplevelser som använder fjärrerbjudanden.

1. Skapa eller redigera en aktivitet i [!UICONTROL Form-Based Experience Composer].

   I [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) finns detaljerade stegvisa instruktioner.

1. Ange önskad plats och lägg till eventuella målgruppsförbättringar efter behov.

1. Klicka på listrutan **[!UICONTROL Content]**, klicka på ikonen **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) och sedan på **[!UICONTROL Change Remote Offer]**.

1. Välj önskat fjärrerbjudande i dialogrutan [!UICONTROL Change Remote Offer] och klicka sedan på **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

1. Slutför konfigurationen av aktiviteten.

## Så fungerar dynamiska fjärrerbjudanden {#concept_CC2A969420B34364A9FA78C1CE251818}

Dynamiska fjärrerbjudanden använder er dynamiska sidteknologi för att skicka värden till erbjudandet.

Erbjudandet verkställs när du har återgett sidan. En osynlig iFrame samlar in data, kopierar dem från ramen och infogar dem på sidan och läser in de värden som skickas.

![remote_offer_howitworks_2 image](assets/remote_offer_howitworks_2.jpeg)

1. Besökarens webbläsare begär en sida från servern.

2. Webbläsaren återger sidan, inklusive rutor.

3. `mboxCreate`-anropet innehåller parametrar som krävs för att återge dynamiskt innehåll.

4. [!DNL Target] returnerar en URL med platsen för dynamiskt innehåll och dess parametrar. Anger en iFrame i rutan.

5. Webbläsaren begär webbadressen och återger den på sidan.

## Markeringsmatris för fjärrerbjudande {#reference_B23BEDD29DDD47709A7651AFD27E776B}

Med matrisen för val av fjärrerbjudande kan du avgöra vilken typ av fjärrerbjudande du ska välja: [!UICONTROL Onsite Cached] eller [!UICONTROL Onsite Dynamic].

| Funktion | Cachelagrad på plats | Dynamisk på plats |
|--- |--- |--- |
| Uppdateringar varje gång en besökare gör en begäran | Nej | Ja |
| Innehållsuppdateringar | Cachelagras varannan timme | Uppdateras omedelbart efter varje begäran |
| Inläsningstid | Snabbare | Långsammare på grund av behandling av begäran |
| Kan se JavaScript på en sida | Ja | Nej, men kan skicka via URL |
| Erbjudandena kan omfatta JavaScript | Ja | Ja |
| Erbjudandets URL | Absolut eller relativt | Relativ |
| Begär dator | Adobe-servrar | Besökarens dator som bär besökarens cookies |
