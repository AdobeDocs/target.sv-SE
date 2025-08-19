---
keywords: deduplicera;tillåt dubbletter;utelämna dubbletterbjudanden;automatiserad personalisering;tillåt inte dubbletterbjudanden;exkludera;standardinnehåll;
description: Hantera undantag i [!UICONTROL Automated Personalization] (AP)-aktiviteter.
title: Hur hanterar jag undantag i [!UICONTROL Automated Personalization] aktiviteter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: c5016d212edafa908b8755044e73d28167e20e8a
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 0%

---

# Hantera undantag

Hantera undantag genom att exkludera dubblerade erbjudanden, exkludera specifika upplevelser och exkludera standardinnehåll i [!UICONTROL Automated Personalization] (AP)-aktiviteter i [!DNL Adobe Target].

## Exkludera dubbletterbjudanden {#concept_4EF78013F80E48EFA024AE0274C9F037}

Förhindra att erbjudanden från erbjudandebiblioteket dupliceras när de används på olika platser i [!UICONTROL Automated Personalization]-aktiviteter.

Du kan till exempel ha en aktivitet med sex platser på en sida med tolv erbjudanden. Det finns en risk för att samma erbjudande kan placeras på en eller flera platser i aktiviteten. Den här funktionen förhindrar att dubbletterbjudanden visas samtidigt på olika platser inom samma aktivitet.

Klicka på ikonen **[!UICONTROL Configure]** > **[!UICONTROL Duplicate Offers]** och sedan på **[!UICONTROL Allow Duplicates]** eller **[!UICONTROL Disallow Duplicates]**.

![Alternativ för duplicerade erbjudanden](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## Exkludera specifika upplevelser {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Undanta specifika upplevelser om du vill utesluta vissa erbjudandekombinationer från din [!UICONTROL Automated Personalization]-aktivitet.

Det kan finnas vissa kombinationer som inte fungerar tillsammans, eller så kanske du begränsar antalet testade upplevelser för att minska trafikkraven för din aktivitet.

1. Klicka på [Hantera innehåll](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) i rubrikfältet när du **skapar eller redigerar en AP-aktivitet**.

   ![Länken Hantera innehåll](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   Listan [!UICONTROL Experiences] visar varje upplevelse som genererats från permutationer för allt innehåll och alla platsalternativ.

1. Exkludera upplevelser efter behov.

   Du kan exkludera specifika upplevelser genom att hålla pekaren över den önskade upplevelsen och sedan klicka på exkluderingsikonen.

   ![Uteslut upplevelsen genom att hovra](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   Du kan också gruppexkludera upplevelser genom att markera kryssrutan för de relevanta upplevelserna och sedan klicka på ikonen **[!UICONTROL Exclude]** i dialogrutans övre högra hörn. Ikonen [!UICONTROL Exclude] visas när en eller flera upplevelser kontrolleras.

   ![Gruppexkludera upplevelser](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   Du kan filtrera den här listvyn så att endast uteslutna eller endast inkluderade aktiviteter visas genom att klicka på listrutan [!UICONTROL Status].

   Upplevelserna är nu uteslutna från aktiviteten och deras [!UICONTROL Status]-program är [!UICONTROL Excluded].

   ![Undantagna upplevelser](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## Uteslut standardinnehåll {#task_DCB4528989DF4C05A3A4729E5891D18F}

Ibland kanske du inte vill inkludera ditt standardinnehåll som en del av din [!UICONTROL Automated Personalization]-aktivitet. Hur du kommer åt den här inställningen skiljer sig från hur du skapar exkluderingsgrupper. Du kan använda den här metoden om du bara vill ha ett erbjudande (som skiljer sig från ditt standardinnehåll) på en plats som en del av din AP-aktivitet.

Att exkludera standardinnehåll är ett bra sätt att ändra utseendet och känslan hos resten av sidan så att det passar de erbjudanden du testar med din AP-aktivitet. Anta till exempel att du vill matcha färgpaletten för erbjudandena som du testar, att du kan ändra bakgrundsfärgen för sidan och utesluta standardbakgrundsfärgen.

**Om du vill exkludera standardinnehåll med [!UICONTROL Visual Experience Composer] (VEC):**

1. När du [skapar eller redigerar en AP-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) markerar du det innehåll du vill ersätta och klickar för att komma åt **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image]** eller **[!UICONTROL Change Background Color]**.
1. Skapa ditt nya innehåll i dialogrutan och avmarkera **Inkludera** till höger om standardinnehållet (eller avmarkera Standardbild/video på skärmen [!UICONTROL Select Content]).

   Beroende på innehåll eller erbjudandetyp finns kryssrutan [!UICONTROL Include] på en något annorlunda plats.

   För text/HTML-innehåll:

   ![Kryssrutan Inkludera i dialogrutan Redigera text/HTML](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   För bild-/videomaterial:

   ![Kryssrutan Inkludera i dialogrutan Välj innehåll](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   För bakgrundsfärg:

   ![Kryssrutan Inkludera i dialogrutan Redigera bakgrundsfärg](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. Klicka på **[!UICONTROL Save]**.

   Du kan se upplevelserna som skapats med erbjudandena som du angav under [!UICONTROL Manage Content]. Du märker att inga upplevelser skapas i [!UICONTROL Manage Content] med det standarderbjudande du uteslöt.

   ![exclude_content_vec_4 image](assets/exclude_content_vec_4.png)

**Om du vill exkludera standardinnehåll med [!UICONTROL Form-Based Experience Composer]:**

1. Klicka **[!UICONTROL Change Text/HTML]** eller **[!UICONTROL Change Image Offer]** under **[!UICONTROL Content]** när du skapar eller redigerar en AP-aktivitet.
1. Skapa ditt nya innehåll i dialogrutan och avmarkera **[!UICONTROL Include]** till höger om standardinnehållet (eller avmarkera standardbilden/standardvideon på skärmen [!UICONTROL Select Content]).

   Beroende på innehåll eller erbjudandetyp finns kryssrutan [!UICONTROL Include] på en något annorlunda plats.

   För text/HTML-innehåll:

   ![exclude_content_form_1 bild](assets/exclude_content_form_1.png)

   För bild-/videomaterial:

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. Klicka på **[!UICONTROL Save]**.

   Du kan se upplevelserna som skapats med erbjudandena som du angav under [!UICONTROL Manage Content]. Du märker att inga upplevelser skapas i [!UICONTROL Manage Content] med det standarderbjudande du uteslöt.

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)
