---
keywords: remote offer;remote offer selection matrix;cached content;dynamic content
description: Använd fjärrerbjudanden för att lagra innehåll utanför Adobe Target som Target refererar till och levererar till användarnas webbplatser. Det här innehållet kan finnas i ett innehållshanteringssystem eller i ett annat system, antingen av användarvänliga skäl eller av säkerhetsskäl.
title: Skapa fjärrerbjudanden
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 1%

---


# Skapa fjärrerbjudanden

Använd fjärrerbjudanden för att lagra innehåll utanför [!DNL Adobe Target] som Target refererar till och levererar till användarnas webbplatser. Det här innehållet kan finnas i ett innehållshanteringssystem eller i ett annat system, antingen av användarvänliga skäl eller av säkerhetsskäl.

>[!NOTE]
>
>Fjärrerbjudanden kan bara skapas i den formulärbaserade dispositionen. Innehållet kommer att injiceras på förfrågningsplatserna för [!DNL Target], så de passar troligtvis inte för en global [!DNL Target]-begäran.
>
>[!DNL Target Classic] innehåller liknande funktioner:  [!UICONTROL Offer on Your Site] och  [!UICONTROL Offer Outside Test&Target].

Några exempel på fjärrerbjudanden är:

* Olika versioner av era korsförsäljning
* Dynamiska kundvagnsmeddelanden
* Forms
* Beräkningar
* Ränteuppdateringar

**Så här skapar du ett fjärrerbjudande:**

1. Klicka på **[!UICONTROL Offers]** och välj sedan fliken **[!UICONTROL Code Offers]**.
1. Klicka på **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![](assets/remote_offer_ui.png)

1. Ange ett beskrivande namn för erbjudandet.

   Med ett beskrivande namn kan du och andra snabbt hitta erbjudandet i [!UICONTROL Assets]-biblioteket.

1. Ange fjärr-URL för fjärrerbjudandet:

   | Alternativ | Beskrivning |
   |--- |--- |
   | Cachelagrad | Innehållet i ett cachelagrat fjärrerbjudande levereras från Target.<br>Varannan timme  [!DNL Target] hämtar innehållet på fjärr-URL:en och lagrar sedan innehållet inuti Target. När besökare läser in en webbplats med en upplevelse som inkluderar ett fjärrerbjudande levereras erbjudandet av Target.<br>Cachelagrade fjärrerbjudanden ger förbättrad säkerhet eftersom någon som är inloggad på toTarget inte kan ändra innehållet. För att ändra innehållet måste någon logga in på innehållshanteringen eller något annat system och ändra innehållet där.<br>Du kan ange en absolut eller relativ URL för ett cachelagrat fjärrerbjudande. |
   | Dynamisk | Ett dynamiskt fjärrerbjudande levereras från innehållshanteringen eller något annat system i stället för från Target.<br>Du kanske inte vill att innehållet ska cachelagras regelbundet och sedan levereras av Target när besökarna läser in en webbplats med en upplevelse som inkluderar ett fjärrerbjudande. I stället vill du anropa det system som är värd för innehållet och eventuellt skicka in specifik information så att det returnerade erbjudandet kan vara dynamiskt, eller olika, för varje användare.<br>Om en användare till exempel loggar in på en webbplats för ett kreditkort som innehåller en upplevelse med ett dynamiskt fjärrerbjudande, kan du skicka parametrar till URL:en för användarens kontoinformation. Därefter kan webbplatsen innehålla användarspecifik information, t.ex. kontosaldo.<br>Klicka  [!UICONTROL Add Parameter] för att lägga till en eller flera  [!DNL Target] begäranden eller frågeparametrar. |

1. Klicka på **[!UICONTROL Save]**.

## Bästa tillvägagångssätt för att använda fjärrerbjudanden {#section_7718512D08E14121B6F6B8C38134F4BC}

Bästa tillvägagångssätt för att använda fjärrerbjudanden i dina aktiviteter:

* Om ditt erbjudande finns i samma domän som [!DNL Target]-förfrågningarna kan du med alternativet [!UICONTROL Cached] använda relativa URL:er för att beskriva din erbjudandeplats.

   Det innebär att när du flyttar din aktivitet från testservrarna till produktionen blir innehållet automatiskt tillgängligt utan att du behöver ändra URL-adressen manuellt.

* Om testet innehåller data som genereras dynamiskt av servern kan det vara rätt alternativ för [!UICONTROL Dynamic].
* Om du bara vill testa utseendet på ditt befintliga innehåll för fjärrerbjudanden använder du [!UICONTROL Visual Experience Composer] för att ändra utseendet på det innehåll som returneras från innehållshanteringssystemet.
* Använd matrisen för val av fjärrerbjudanden för att hjälpa dig att välja det erbjudande som passar bäst för just ditt fall. Kontakta din kontorepresentant om du har frågor.

## Så här fungerar dynamiska fjärterbjudanden {#concept_CC2A969420B34364A9FA78C1CE251818}

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