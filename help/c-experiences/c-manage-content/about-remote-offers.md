---
keywords: fjärterbjudande;matris för urval av fjärrerbjudanden;cachelagrat innehåll;dynamiskt innehåll;URL-typ
description: Kan jag använda fjärrerbjudanden för att lagra externt innehåll?
title: Skapa fjärrerbjudanden
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 0%

---


# Skapa fjärrerbjudanden

Använd fjärrerbjudanden för att lagra innehåll utanför [!DNL Adobe Target] som [!DNL Target] refererar till och levererar till användarnas webbplatser. Det här innehållet kan finnas i ett CMS-system eller andra system, antingen av användarvänliga skäl eller av säkerhetsskäl.

>[!NOTE]
>
>Fjärrerbjudanden kan skapas på [!UICONTROL Offers] > [!UICONTROL Code Offers]-sidan eller i [Forms-baserad Experience Composer](/help/c-experiences/form-experience-composer.md). Du kan inte skapa eller använda fjärrerbjudanden i Visual Experience Composer (VEC). Innehållet kommer att injiceras på förfrågningsplatserna för [!DNL Target], så de passar troligtvis inte för en global [!DNL Target]-begäran.
>
>[!DNL Target Classic] innehåller liknande funktioner:  [!UICONTROL Offer on Your Site] och  [!UICONTROL Offer Outside Test&Target].

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

* Om testet innehåller data som genereras dynamiskt av servern kan det vara rätt alternativ för [!UICONTROL Dynamic].
* Om du bara vill testa utseendet på ditt befintliga innehåll för fjärrerbjudanden använder du [!UICONTROL Visual Experience Composer] för att ändra utseendet på det innehåll som returneras från innehållshanteringssystemet.
* Använd [matrisen för val av fjärrerbjudande](#reference_B23BEDD29DDD47709A7651AFD27E776B) (nedan) för att få hjälp att välja det erbjudande som passar ditt specialfall bäst. Kontakta din kontorepresentant om du har frågor.

## Skapa ett fjärrerbjudande från sidan Koderbjudanden

1. Klicka på **[!UICONTROL Offers]** och välj sedan fliken **[!UICONTROL Code Offers]**.

   ![Erbjudanden > Koderbjudanden](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![Skapa fjärrerbjudande, dialogruta](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Ange ett beskrivande namn för erbjudandet.

   Med ett beskrivande namn kan du och andra snabbt hitta erbjudandet i [!UICONTROL Assets]-biblioteket.

1. Ange URL-typen för omdirigering.

   Se [Omdirigerings-URL-typ: Cachelagrad eller dynamisk](#url-type) nedan om du vill ha mer information.

1. Ange fjärr-URL för fjärrerbjudandet.

1. Klicka på **[!UICONTROL Save]**.

## Skapa ett fjärrerbjudande med formulärbaserad Experience Composer

1. När du skapar en aktivitet med [formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md) väljer du den plats där avsnittet **[!UICONTROL Content]** ska visas.

   ![Innehållsavsnitt i formulärbaserad Experience Composer](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. Klicka på listrutan **[!UICONTROL Default Content]** och klicka sedan på **[!UICONTROL Change Remote Offer]**.

   ![Ändra alternativ för fjärrerbjudande](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![Skapa fjärrerbjudande, dialogruta](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Ange ett beskrivande namn för erbjudandet.

   Med ett beskrivande namn kan du och andra snabbt hitta erbjudandet i [!UICONTROL Assets]-biblioteket.

1. Ange URL-typen för omdirigering.

   Se [Omdirigerings-URL-typ: Cachelagrad eller dynamisk](#url-type) nedan om du vill ha mer information.

1. Ange fjärr-URL för fjärrerbjudandet.

1. Klicka på **[!UICONTROL Save]**.

## Omdirigerings-URL-typ: Cachelagrad eller dynamisk {#url-type}

Följande information hjälper dig att förstå skillnaderna mellan de två alternativen:

### Cachelagrad URL

Innehållet i ett cachelagrat fjärrerbjudande hanteras från [!DNL Target].

Varannan timme hämtar [!DNL Target] innehållet på fjärr-URL:en och lagrar sedan innehållet i [!DNL Target]. När besökare läser in en webbplats med en upplevelse som inkluderar ett fjärrerbjudande levereras erbjudandet av [!DNL Target].

Cachelagrade fjärrerbjudanden ger förbättrad säkerhet eftersom någon som är inloggad på [!DNL Target] inte kan ändra innehållet. För att ändra innehållet måste någon logga in på innehållshanteringen eller något annat system och ändra innehållet där.

Du kan ange en absolut eller relativ URL för ett cachelagrat fjärrerbjudande.

### Dynamisk URL

Ett dynamiskt fjärrerbjudande levereras från innehållshanteringen eller något annat system i stället för från [!DNL Target].

Du kanske inte vill att innehållet ska cachelagras regelbundet och sedan levereras av [!DNL Target] när besökarna läser in en webbplats med en upplevelse som inkluderar ett fjärrerbjudande. I stället vill du anropa det system som är värd för innehållet och eventuellt skicka in specifik information så att det returnerade erbjudandet kan vara dynamiskt (eller olika) för varje användare. Om en användare till exempel loggar in på en webbplats för ett kreditkort som innehåller en upplevelse med ett dynamiskt fjärrerbjudande, kan du skicka parametrar till URL:en för användarens kontoinformation. Därefter kan webbplatsen innehålla användarspecifik information, t.ex. kontosaldo.

Du kan klicka på **[!UICONTROL Add Parameter]** om du vill lägga till en eller flera [!DNL Target]-begäranden eller frågeparametrar.

## Använd fjärrerbjudanden i aktiviteter

Du måste tillämpa fjärrerbjudanden med [!UICONTROL Form-Based Experience Composer]. Du kan för närvarande inte använda fjärrerbjudanden med VEC.

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] är ett gränssnitt för icke-visuell upplevelse och erbjuder skapandegränssnitt som är användbart när du skapar upplevelser som kan användas i aktiviteterna [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) och [!UICONTROL Recommendations] när den visuella upplevelsedispositionen inte är tillgänglig eller praktisk att använda. Du kan till exempel använda [!UICONTROL Form-Based Experience Composer] för att skapa upplevelser som använder fjärrerbjudanden.

1. Skapa eller redigera en aktivitet i [!UICONTROL Form-Based Experience Composer].

   I [Formulärbaserad Experience Composer](/help/c-experiences/form-experience-composer.md) finns detaljerade stegvisa instruktioner.

1. Ange önskad plats och lägg till eventuella målgruppsförbättringar efter behov.

1. Klicka på listrutan i avsnittet **[!UICONTROL Content]** och klicka sedan på **[!UICONTROL Change Remote Offer]**.

   ![Ändra alternativ för fjärrerbjudande](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Välj önskat fjärrerbjudande i dialogrutan [!UICONTROL Select Remote Offer] och klicka sedan på **[!UICONTROL Done]**.

1. Slutför konfigurationen av aktiviteten.

## Så fungerar dynamiska fjärrerbjudanden {#concept_CC2A969420B34364A9FA78C1CE251818}

Dynamiska fjärrerbjudanden använder er dynamiska sidteknologi för att skicka värden till erbjudandet.

Erbjudandet verkställs när du har återgett sidan. En osynlig iframe samlar in data, kopierar dem utanför ramen och infogar dem på sidan och läser in de värden som skickas.

![](assets/remote_offer_howitworks_2.jpeg)

## Markeringsmatris för fjärrerbjudande {#reference_B23BEDD29DDD47709A7651AFD27E776B}

Med hjälp av matrisen för val av fjärrerbjudande kan du bestämma vilken typ av fjärrerbjudande du vill välja: [!UICONTROL Cached] eller [!UICONTROL Dynamic].

| Funktion | Cachelagrad | Dynamisk |
|--- |--- |--- |
| Uppdateringar varje gång en besökare gör en begäran | Nej | Ja |
| Innehållsuppdateringar | Cachelagras varannan timme | Uppdateras omedelbart efter varje begäran |
| Inläsningstid | Snabbare | Långsammare på grund av behandling av begäran |
| Kan se JavaScript på sidan | Ja | Nej, men kan skicka via URL |
| Erbjudandena kan omfatta JavaScript | Ja | Ja |
| Erbjudandets URL | Absolut eller relativt | Relativ |
| Begär dator | Adobe-servrar | Besökarens dator som bär besökarens cookies |

## Utbildningsvideo: Formulärbaserad disposition ![Tutorial badge](/help/assets/tutorial.png)

Den här videon innehåller en demonstration av den formulärbaserade dispositionen, som du kan använda för att skapa fjärrerbjudanden.

* Skapa en aktivitet med formulärbaserad Experience Composer
* Förstå när formulärbaserad Experience Composer ska användas jämfört med Visual Experience Composer
* Använd förfiningar för att ange en plats som mål

>[!VIDEO](https://video.tv.adobe.com/v/17390)