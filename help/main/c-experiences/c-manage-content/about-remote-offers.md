---
keywords: fjärterbjudande;matris för urval av fjärrerbjudanden;cachelagrat innehåll;dynamiskt innehåll;URL-typ
description: Lär dig hur du använder fjärrerbjudanden i Adobe [!DNL Target] för att lagra externt innehåll (innehåll i ett CMS-system eller annat system). Upptäck varför du kanske vill använda fjärrerbjudanden.
title: Hur skapar jag fjärrerbjudanden?
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 0%

---

# Skapa fjärrerbjudanden

Använd fjärrerbjudanden för att lagra innehåll utanför [!DNL Adobe Target] att [!DNL Target] referenser och levererar till användarnas webbplatser. Det här innehållet kan finnas i ett CMS-system eller andra system, antingen av användarvänliga skäl eller av säkerhetsskäl.

>[!NOTE]
>
>Fjärrerbjudanden kan skapas på [!UICONTROL Offers] > [!UICONTROL Code Offers] eller på [Forms-baserad Experience Composer](/help/main/c-experiences/form-experience-composer.md). Du kan inte skapa eller använda fjärrerbjudanden i Visual Experience Composer (VEC). Innehållet kommer att injiceras i [!DNL Target] begärandeplatser, så dessa passar troligtvis inte för en global [!DNL Target] begäran.
>
>[!DNL Target Classic] innehåller liknande funktioner: [!UICONTROL Offer on Your Site] och [!UICONTROL Offer Outside Test&Target].

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

* Om ditt erbjudande finns i samma domän som [!DNL Target] begäran, använda [!UICONTROL Cached] kan du använda relativa URL:er för att beskriva din erbjudandeplats.

   Det innebär att när du flyttar din aktivitet från testservrarna till produktionen blir innehållet automatiskt tillgängligt utan att du behöver ändra URL-adressen manuellt.

* Om testet innehåller data som genererats dynamiskt av servern, [!UICONTROL Dynamic] kan vara rätt alternativ.
* Om du bara vill testa utseendet på ditt befintliga innehåll för fjärrerbjudanden använder du [!UICONTROL Visual Experience Composer] för att ändra utseendet på och känslan i det innehåll som returneras från innehållshanteringssystemet.
* Använd [Markeringsmatris för fjärrerbjudande](#reference_B23BEDD29DDD47709A7651AFD27E776B) (nedan) för att hjälpa dig att välja det erbjudande som passar bäst för just ditt fall. Kontakta din kontorepresentant om du har frågor.

## Skapa ett fjärrerbjudande från sidan Koderbjudanden

1. Klicka på **[!UICONTROL Offers]** och välj sedan fliken **[!UICONTROL Code Offers]**.

   ![Erbjudanden > Koderbjudanden](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![Skapa fjärrerbjudande, dialogruta](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Ange ett beskrivande namn för erbjudandet.

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i [!UICONTROL Assets] bibliotek.

1. Ange URL-typen för omdirigering.

   Se [Omdirigerings-URL-typ: Cachelagrad eller dynamisk](#url-type) nedan om du vill ha mer information.

1. Ange fjärr-URL för fjärrerbjudandet.

1. Klicka på **[!UICONTROL Save]**.

## Skapa ett fjärrerbjudande med formulärbaserad Experience Composer

1. När du skapar en aktivitet med [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md)väljer du den plats där du vill visa **[!UICONTROL Content]** -avsnitt.

   ![Innehållsavsnitt i formulärbaserad Experience Composer](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Klicka på **[!UICONTROL Default Content]** nedrullningsbar lista och klicka sedan på **[!UICONTROL Change Remote Offer]**.

   ![Ändra alternativ för fjärrerbjudande](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![Skapa fjärrerbjudande, dialogruta](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Ange ett beskrivande namn för erbjudandet.

   Ett beskrivande namn hjälper dig och andra att snabbt hitta erbjudandet i [!UICONTROL Assets] bibliotek.

1. Ange URL-typen för omdirigering.

   Se [Omdirigerings-URL-typ: Cachelagrad eller dynamisk](#url-type) nedan om du vill ha mer information.

1. Ange fjärr-URL för fjärrerbjudandet.

1. Klicka på **[!UICONTROL Save]**.

## Omdirigerings-URL-typ: Cachelagrad eller dynamisk {#url-type}

Följande information hjälper dig att förstå skillnaderna mellan de två alternativen:

### Cachelagrad URL

Innehållet i ett cachelagrat fjärrerbjudande hanteras från [!DNL Target].

Varannan timme [!DNL Target] hämtar innehållet på fjärr-URL:en och lagrar sedan innehållet i [!DNL Target]. När besökare läser in en webbplats med en upplevelse som inkluderar ett fjärrerbjudande levereras erbjudandet via [!DNL Target].

Cachelagrade fjärrerbjudanden ger förbättrad säkerhet eftersom någon är inloggad på [!DNL Target] kan inte ändra innehållet. För att ändra innehållet måste någon logga in på innehållshanteringen eller något annat system och ändra innehållet där.

Du kan ange en absolut eller relativ URL för ett cachelagrat fjärrerbjudande.

### Dynamisk URL

Ett dynamiskt fjärrerbjudande levereras från innehållshantering eller andra system i stället för från [!DNL Target].

Du kanske inte vill att innehållet ska cachelagras regelbundet och sedan levereras av [!DNL Target] när besökarna läser in en webbplats med en upplevelse som inkluderar ett fjärrerbjudande. I stället vill du anropa det system som är värd för innehållet och eventuellt skicka in specifik information så att det returnerade erbjudandet kan vara dynamiskt (eller olika) för varje användare. Om en användare till exempel loggar in på en webbplats för ett kreditkort som innehåller en upplevelse med ett dynamiskt fjärrerbjudande, kan du skicka parametrar till URL:en för användarens kontoinformation. Därefter kan webbplatsen innehålla användarspecifik information, t.ex. kontosaldo.

Du kan klicka **[!UICONTROL Add Parameter]** lägga till en eller flera [!DNL Target] förfrågningar eller frågeparametrar.

## Använd fjärrerbjudanden i aktiviteter

Du måste tillämpa fjärrerbjudanden med [!UICONTROL Form-Based Experience Composer]. Du kan för närvarande inte använda fjärrerbjudanden med VEC.

The [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] är en icke-visuell upplevelse och erbjuder ett gränssnitt som är användbart när det gäller att skapa upplevelser som ska användas i [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP), och [!UICONTROL Recommendations] aktiviteter när den visuella upplevelsedispositionen inte är tillgänglig eller praktisk att använda. Du kan till exempel använda [!UICONTROL Form-Based Experience Composer] för att skapa upplevelser som använder fjärrerbjudanden.

1. Skapa eller redigera en aktivitet i [!UICONTROL Form-Based Experience Composer].

   Se [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md) för detaljerade steg-för-steg-instruktioner.

1. Ange önskad plats och lägg till eventuella målgruppsförbättringar efter behov.

1. Klicka på listrutan i dialogrutan **[!UICONTROL Content]** -avsnittet och klicka sedan på **[!UICONTROL Change Remote Offer]**.

   ![Ändra alternativ för fjärrerbjudande](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Välj önskat erbjudande på fjärrkontrollen på [!UICONTROL Select Remote Offer] och sedan klicka på **[!UICONTROL Done]**.

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

## Utbildningsvideo: Formulärbaserad disposition ![Självstudiemärke](/help/main/assets/tutorial.png)

Den här videon innehåller en demonstration av den formulärbaserade dispositionen, som du kan använda för att skapa fjärrerbjudanden.

* Skapa en aktivitet med formulärbaserad Experience Composer
* Förstå när formulärbaserad Experience Composer ska användas jämfört med Visual Experience Composer
* Använd förfiningar för att ange en plats som mål

>[!VIDEO](https://video.tv.adobe.com/v/17390)
