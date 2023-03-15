---
keywords: deduplicera;tillåta dubbletter;exkludera dubblerade erbjudanden;automatiserad personalisering;Tillåt inte dubblerade erbjudanden;exkludera;standardinnehåll;exkluderingsgrupp;
description: Hantera undantag i Adobe [!DNL Target] Automated Personalization-aktiviteter. Skapa exkluderingsgrupper och exkludera dubblerade erbjudanden, specifika upplevelser och standardinnehåll.
title: Hur hanterar jag undantag i Automated Personalization-aktiviteter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 0%

---

# Hantera undantag

Hantera uteslutningar genom att skapa exkluderingsgrupper, exklusive dubblerade erbjudanden, exklusive specifika upplevelser, och exkludera standardinnehåll i [!UICONTROL Automated Personalization] (AP) aktiviteter i [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) aktiviteter.

## Skapa exkluderingsgrupper {#task_AAAA6C7239A84F7696C8492F04B575A2}

Skapa exkluderingsgrupper i Automated Personalization(AP)-aktiviteter för att säkerställa att upplevelser med de angivna erbjudandena automatiskt utesluts.

Uteslutningsgrupper är ett bra sätt att se till att inkompatibla erbjudanden inte visas på samma plats på olika platser. Anta till exempel att du har två erbjudanden: den ena ger 20 % rabatt på alla varor och den andra 15 % rabatt. Ni vill aldrig att dessa två erbjudanden ska presenteras för besökare i samma upplevelse. Om du lägger till dessa två erbjudanden i en exkluderingsgrupp kan du se till att så aldrig blir fallet.

Du kan också begränsa vilka målgrupper som kan se specifika erbjudanden i AP-aktiviteter. Mer information finns i [Automated Personalization erbjudanden](/help/main/c-activities/t-automated-personalization/ap-target-offers.md).

**Så här skapar du en exkluderingsgrupp:**

1. while [skapa eller redigera en AP-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), klicka **[!UICONTROL Manage Content]** i rubrikfältet.

   ![Länken Hantera innehåll](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

1. I [!UICONTROL Manage Content] klickar du på **[!UICONTROL Exclusion Group]**.

   ![Hantera innehåll > Uteslutningsgrupper, dialogruta](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   Om du tidigare har skapat exkluderingsgrupper visas de i listan. Om du ännu inte har skapat någon exkluderingsgrupp uppmanas du att skapa en.

1. Klicka på **[!UICONTROL Create Exclusion Group.]**

   ![Dialogrutan Skapa exkluderingsgrupp](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. (Obligatoriskt) Ange ett beskrivande namn för exkluderingsgruppen.

   Ett beskrivande namn hjälper dig eller andra att snabbt hitta och förstå en grupps syfte.

1. Leta reda på och markera de erbjudanden du vill lägga till i exkluderingsgruppen.

   Du kan välja flera erbjudanden från samma plats i en exkluderingsgrupp.

1. Klicka på **[!UICONTROL Save]**.

Erbjudandena i exkluderingsgruppen exkluderas automatiskt från samma upplevelser som går framåt.

## Exkludera dubbletterbjudanden {#concept_4EF78013F80E48EFA024AE0274C9F037}

Förhindra att erbjudanden från erbjudandebiblioteket dupliceras när de används på olika platser i [!UICONTROL Automated Personalization] verksamhet.

Du kan till exempel ha en aktivitet med sex platser på en sida med 12 erbjudanden. Det finns en risk för att samma erbjudande kan placeras på en eller flera platser i aktiviteten. Den här funktionen förhindrar att dubbletterbjudanden visas samtidigt på olika platser inom samma aktivitet.

Klicka **[!UICONTROL Configure]** > **[!UICONTROL Duplicate Offers]** och sedan klicka **[!UICONTROL Allow Duplicates]** eller **[!UICONTROL Disallow Duplicates]**.

![Alternativ för duplicerade erbjudanden](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## Exkludera specifika upplevelser {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Exkludera specifika upplevelser om du vill utesluta vissa erbjudandekombinationer från din Automated Personalization-aktivitet.

Det kan finnas vissa kombinationer som inte fungerar bra tillsammans, eller så kanske du begränsar antalet testade upplevelser för att minska trafikkraven för din aktivitet.

1. while [skapa eller redigera en AP-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), klicka **Hantera innehåll** i rubrikfältet.

   ![Länken Hantera innehåll](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   The [!UICONTROL Experiences] visas varje upplevelse som genereras av permutationer för allt innehåll och alla platsalternativ.

1. Exkludera upplevelser efter behov.

   Du kan exkludera specifika upplevelser genom att hålla pekaren över den önskade upplevelsen och sedan klicka på exkluderingsikonen.

   ![Uteslut upplevelsen genom att hovra](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   Du kan också gruppera uteslutning/inkludering av upplevelser genom att markera kryssrutan för de relevanta upplevelserna och sedan klicka på **[!UICONTROL Exclude]** i dialogrutans övre högra hörn. The [!UICONTROL Exclude] visas när en eller flera upplevelser är markerade.

   ![Gruppexkludera upplevelser](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   Du kan filtrera den här listvyn så att endast uteslutna eller endast inkluderade aktiviteter visas genom att klicka på [!UICONTROL Status] nedrullningsbar lista.

   Nu kommer upplevelserna att uteslutas från aktiviteten och deras [!UICONTROL Status] visas som [!UICONTROL Excluded].

   ![Exkluderade upplevelser](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## Uteslut standardinnehåll {#task_DCB4528989DF4C05A3A4729E5891D18F}

I vissa fall kanske du inte vill inkludera ditt standardinnehåll som en del av din Automated Personalization-aktivitet. Hur du kommer åt den här inställningen skiljer sig från hur du skapar exkluderingsgrupper. Du kan använda den här metoden om du bara vill ha ett erbjudande (som skiljer sig från ditt standardinnehåll) på en plats som en del av din AP-aktivitet.

Att exkludera standardinnehåll är ett bra sätt att ändra utseendet och känslan hos resten av sidan så att det passar de erbjudanden du testar med din AP-aktivitet. Anta till exempel att du vill matcha färgpaletten för erbjudandena som du testar, att du kan ändra bakgrundsfärgen för sidan och utesluta standardbakgrundsfärgen.

**Så här exkluderar du standardinnehåll med Visual Experience Composer (VEC):**

1. while [skapa eller redigera en AP-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), markera det innehåll som du vill ersätta och klicka för att komma åt **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image]**, eller **[!UICONTROL Change Background Color]**.
1. Skapa nytt innehåll i dialogrutan och avmarkera **Inkludera** till höger om standardinnehållet (eller avmarkera Standardbild/video på skärmen Välj innehåll).

   Beroende på innehålls-/erbjudandetypen kan [!UICONTROL Include] är på en annan plats.

   För text/HTML-innehåll:

   ![Kryssrutan Inkludera i dialogrutan Redigera text/HTML](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   För bild-/videomaterial:

   ![Kryssrutan Inkludera i dialogrutan Välj innehåll](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   För bakgrundsfärg:

   ![Kryssrutan Inkludera i dialogrutan Redigera bakgrundsfärg](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. Klicka på **[!UICONTROL Save]**.

   Du kan se upplevelserna som skapats utifrån erbjudandena som du angav under [!UICONTROL Manage Content]. Du kommer att märka att inga upplevelser skapas i [!UICONTROL Manage Content] med det standarderbjudande du uteslöt.

   ![exclude_content_vec_4 image](assets/exclude_content_vec_4.png)

**Så här exkluderar du standardinnehåll med formulärbaserad Experience Composer:**

1. När du skapar eller redigerar en AP-aktivitet klickar du på **[!UICONTROL Change Text/HTML]** eller **[!UICONTROL Change Image Offer]** under **[!UICONTROL Content]**.
1. Skapa nytt innehåll i dialogrutan och avmarkera **[!UICONTROL Include]** till höger om standardinnehållet (eller avmarkera Standardbild/video på skärmen Välj innehåll).

   Beroende på innehålls-/erbjudandetyp kommer kryssrutan Inkludera att vara på en något annorlunda plats.

   För text/HTML-innehåll:

   ![exclude_content_form_1 image](assets/exclude_content_form_1.png)

   För bild-/videomaterial:

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. Klicka på **[!UICONTROL Save]**.

   Du kan se upplevelserna som skapats utifrån erbjudandena som du angav under [!UICONTROL Manage Content]. Du kommer att märka att inga upplevelser skapas i [!UICONTROL Manage Content] med det standarderbjudande du uteslöt.

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)
