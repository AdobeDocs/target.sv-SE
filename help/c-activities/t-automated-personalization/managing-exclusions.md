---
keywords: dedupe;allow duplicates;exclude duplicate offers;automated personalization;disallow duplicate offers
description: Hantera undantag genom att skapa exkluderingsgrupper, exklusive dubblerade erbjudanden, exklusive specifika upplevelser, och exkludera standardinnehåll i Adobe Target Automated Personalization (AP)-aktiviteter.
title: Hantera undantag
solution: Target,Analytics
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![Premium-märke](/help/assets/premium.png) Hantera undantag{#manage-exclusions}

Hantera uteslutningar genom att skapa exkluderingsgrupper, exklusive dubblerade erbjudanden, exklusive specifika upplevelser, och exkludera standardinnehåll i aktiviteter för automatiserad personalisering (AP).

## Skapa exkluderingsgrupper {#task_AAAA6C7239A84F7696C8492F04B575A2}

Skapa exkluderingsgrupper i Automated Personalization (AP)-aktiviteter för att säkerställa att upplevelser med de angivna erbjudandena automatiskt utesluts.

Uteslutningsgrupper är ett bra sätt att se till att inkompatibla erbjudanden inte visas på samma plats på olika platser. Anta till exempel att du har två erbjudanden: den ena ger 20 % rabatt på alla varor och den andra 15 % rabatt. Ni vill aldrig att dessa två erbjudanden ska presenteras för besökare i samma upplevelse. Om du lägger till dessa två erbjudanden i en exkluderingsgrupp kan du se till att så aldrig blir fallet.

Du kan också begränsa vilka målgrupper som kan se specifika erbjudanden i AP-aktiviteter. Mer information finns i [Automatiserad personalisering](/help/c-activities/t-automated-personalization/ap-target-offers.md).

**Så här skapar du en exkluderingsgrupp:**

1. När du [skapar eller redigerar en AP-aktivitet](/help/c-activities/t-automated-personalization/create-ap-activity.md)klickar du **[!UICONTROL Manage Content]** i rubrikfältet.

   ![Länken Hantera innehåll](/help/c-activities/t-automated-personalization/assets/manage-content.png)

1. Klicka på i [!UICONTROL Manage Content] dialogrutan **[!UICONTROL Exclusion Group]**.

   ![Hantera innehåll > Uteslutningsgrupper, dialogruta](/help/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   Om du tidigare har skapat exkluderingsgrupper visas de i listan. Om du ännu inte har skapat någon exkluderingsgrupp uppmanas du att skapa en.

1. Klicka på **[!UICONTROL Create Exclusion Group.]**

   ![Dialogrutan Skapa exkluderingsgrupp](/help/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. (Obligatoriskt) Ange ett beskrivande namn för exkluderingsgruppen.

   Ett beskrivande namn hjälper dig eller andra att snabbt hitta och förstå en grupps syfte.

1. Leta reda på och markera de erbjudanden du vill lägga till i exkluderingsgruppen.

   Du kan välja flera erbjudanden från samma plats i en exkluderingsgrupp.

1. Klicka på **[!UICONTROL Save]**.

Erbjudandena i exkluderingsgruppen exkluderas automatiskt från samma upplevelser som går framåt.

## Exkludera dubbletterbjudanden {#concept_4EF78013F80E48EFA024AE0274C9F037}

Förhindra att erbjudanden från erbjudandebiblioteket dupliceras när de används på olika platser i [!UICONTROL Automated Personalization] aktiviteter.

Du kan till exempel ha en aktivitet med sex platser på en sida med 12 erbjudanden. Det finns en risk för att samma erbjudande kan placeras på en eller flera platser i aktiviteten. Den här funktionen förhindrar att dubbletterbjudanden visas samtidigt på olika platser inom samma aktivitet.

Klicka **[!UICONTROL Configure]** > **[!UICONTROL Duplicate Offers]** och sedan på **[!UICONTROL Allow Duplicates]** eller **[!UICONTROL Disallow Duplicates]**.

![Alternativ för duplicerade erbjudanden](/help/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## Exkludera specifika upplevelser {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Exkludera specifika upplevelser om du vill utesluta vissa erbjudandekombinationer från din automatiserade personaliseringsaktivitet.

Det kan finnas vissa kombinationer som inte fungerar bra tillsammans, eller så kanske du begränsar antalet testade upplevelser för att minska trafikkraven för din aktivitet.

1. När du [skapar eller redigerar en AP-aktivitet](/help/c-activities/t-automated-personalization/create-ap-activity.md)klickar du på **Hantera innehåll** i rubrikfältet.

   ![Länken Hantera innehåll](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   I listan visas varje upplevelse som genereras av permutationer för allt innehåll och alla platsalternativ. [!UICONTROL Experiences]

1. Exkludera upplevelser efter behov.

   Du kan exkludera specifika upplevelser genom att hålla pekaren över den önskade upplevelsen och sedan klicka på exkluderingsikonen.

   ![Uteslut upplevelsen genom att hovra](/help/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   Du kan också gruppexkludera/inkludera upplevelser genom att markera kryssrutan för de relevanta upplevelserna och sedan klicka på ikonen **[UICONTROL-exkludera]** i dialogrutans övre högra hörn. Ikonen visas [!UICONTROL Exclude] när en eller flera upplevelser kontrolleras.

   ![Gruppexkludera upplevelser](/help/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   Du kan filtrera den här listvyn så att endast uteslutna eller endast inkluderade aktiviteter visas genom att klicka på [!UICONTROL Status] listrutan.

   Upplevelserna kommer nu att uteslutas från aktiviteten och visas som [!UICONTROL Status] de [!UICONTROL Excluded].

   ![Exkluderade upplevelser](/help/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## Uteslut standardinnehåll {#task_DCB4528989DF4C05A3A4729E5891D18F}

I vissa fall kanske du inte vill inkludera ditt standardinnehåll som en del av din automatiska personaliseringsaktivitet. Hur du kommer åt den här inställningen skiljer sig från hur du skapar exkluderingsgrupper. Du kan använda den här metoden om du bara vill ha ett erbjudande (som skiljer sig från ditt standardinnehåll) på en plats som en del av din AP-aktivitet.

Att exkludera standardinnehåll är ett bra sätt att ändra utseendet och känslan hos resten av sidan så att det passar de erbjudanden du testar med din AP-aktivitet. Anta till exempel att du vill matcha färgpaletten för erbjudandena som du testar, att du kan ändra bakgrundsfärgen för sidan och utesluta standardbakgrundsfärgen.

**Så här exkluderar du standardinnehåll med Visual Experience Composer (VEC):**

1. När du [skapar eller redigerar en AP-aktivitet](/help/c-activities/t-automated-personalization/create-ap-activity.md)markerar du det innehåll du vill ersätta och klickar för att få åtkomst till **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image]** eller **[!UICONTROL Change Background Color]**.
1. Skapa ditt nya innehåll i dialogrutan och avmarkera **Inkludera** till höger om standardinnehållet (eller avmarkera Standardbild/video på skärmen Välj innehåll).

   Beroende på innehålls-/erbjudandetypen är kryssrutan [!UICONTROL Include] på en något annorlunda plats.

   För text-/HTML-innehåll:

   ![Kryssrutan Inkludera i dialogrutan Redigera text/HTML](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   För bild-/videomaterial:

   ![Kryssrutan Inkludera i dialogrutan Välj innehåll](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   För bakgrundsfärg:

   ![Kryssrutan Inkludera i dialogrutan Redigera bakgrundsfärg](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. Klicka på **[!UICONTROL Save]**.

   Du kan se upplevelserna som skapats utifrån de erbjudanden du angav under [!UICONTROL Manage Content]. Du kommer att märka att inga upplevelser skapas i [!UICONTROL Manage Content] med det standarderbjudande du uteslöt.

   ![](assets/exclude_content_vec_4.png)

**Så här exkluderar du standardinnehåll med formulärbaserad Experience Composer:**

1. När du skapar eller redigerar en AP-aktivitet klickar du på **[!UICONTROL Change Text/HTML]** eller **[!UICONTROL Change Image Offer]** under **[!UICONTROL Content]**.
1. Skapa ditt nya innehåll i dialogrutan och avmarkera **[!UICONTROL Include]** till höger om standardinnehållet (eller avmarkera Standardbild/video på skärmen Välj innehåll).

   Beroende på innehålls-/erbjudandetyp kommer kryssrutan Inkludera att vara på en något annorlunda plats.

   För text-/HTML-innehåll:

   ![](assets/exclude_content_form_1.png)

   För bild-/videomaterial:

   ![](assets/exclude_content_form_2.png)

1. Klicka på **[!UICONTROL Save]**.

   Du kan se upplevelserna som skapats utifrån de erbjudanden du angav under [!UICONTROL Manage Content]. Du kommer att märka att inga upplevelser skapas i [!UICONTROL Manage Content] med det standarderbjudande du uteslöt.

   ![](assets/exclude_content_form_3.png)
