---
keywords: deduplicera;tillåt dubbletter;utelämna dubbletterbjudanden;automatiserad personalisering;tillåt inte dubbletterbjudanden;exkludera;standardinnehåll;
description: Hantera undantag i [!UICONTROL Automated Personalization] (AP)-aktiviteter.
title: Hur hanterar jag undantag i [!UICONTROL Automated Personalization] aktiviteter?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Se vad som ingår i Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: a68e7501fbb157a1ac5b0c0cbb3d574abdb747dd
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 0%

---

# Hantera undantag

Ta kontroll över din [!UICONTROL Automated Personalization] (AP)-strategi genom att bemästra undantag. Oavsett om ni förhindrar dubblerade erbjudanden, kombinationer av förfinade upplevelser eller tar bort standardinnehåll, ger uteslutningar er möjlighet att leverera tydligare och mer relevanta upplevelser som anpassar sig efter era mål och målgruppens förväntningar.

## Tillåt eller neka dubbletterbjudanden {#concept_4EF78013F80E48EFA024AE0274C9F037}

Förhindra att erbjudanden från erbjudandebiblioteket dupliceras när de används på olika platser i AP-aktiviteter.

Du kan till exempel ha en aktivitet med sex platser på en sida med tolv erbjudanden. Det finns en risk för att samma erbjudande kan placeras på en eller flera platser i aktiviteten. Med den här funktionen kan du förhindra att dubbletterbjudanden visas samtidigt på olika platser inom samma aktivitet.

1. När du [skapar eller redigerar en AP-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) klickar du på ikonen **[!UICONTROL Configure]** ( ![ikonen Konfigurera](/help/main/assets/icons/Setting.svg) ) > på **[!UICONTROL Allow Duplicate Offers]** för att aktivera och inaktivera den här funktionen, beroende på dina behov.

## Exkludera specifika upplevelser {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Exkludera specifika upplevelser om du vill utesluta vissa erbjudandekombinationer från din AP-aktivitet.

Det kan finnas vissa kombinationer som inte fungerar tillsammans, eller så kanske du begränsar antalet testade upplevelser för att minska trafikkraven för din aktivitet.

1. När du [skapar eller redigerar en AP-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) klickar du på ikonen **Hantera innehåll** ( ![ikonen Hantera innehåll](/help/main/assets/icons/Experience.svg) ).

   Listan [!UICONTROL Experiences] visar varje upplevelse som genererats från permutationer för allt innehåll och alla platsalternativ.

1. Exkludera upplevelser efter behov.

   Du kan exkludera specifika upplevelser genom att klicka på ikonen [!UICONTROL **Fler åtgärder**] ( ![ikonen Fler åtgärder](/help/main/assets/icons/MoreSmall.svg) ) och sedan på [!UICONTROL **Uteslut**].

   Du kan också gruppexkludera upplevelser genom att markera kryssrutan för relevanta upplevelser och sedan klicka på **[!UICONTROL Exclude]**. Ikonen [!UICONTROL Exclude] visas när en eller flera upplevelser kontrolleras.

   ![Gruppexkludera upplevelser](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   Upplevelserna är nu uteslutna från aktiviteten och deras [!UICONTROL Status]-program är [!UICONTROL Excluded].

## Uteslut standardinnehåll {#task_DCB4528989DF4C05A3A4729E5891D18F}

Ibland kanske du inte vill inkludera ditt standardinnehåll som en del av din AP-aktivitet. Du kan använda den här metoden om du bara vill ha ett erbjudande (som skiljer sig från ditt standardinnehåll) på en plats som en del av din aktivitet.

Att exkludera standardinnehåll är ett bra sätt att ändra utseendet och känslan hos resten av sidan så att det passar de erbjudanden du testar med din AP-aktivitet. Anta till exempel att du vill matcha färgpaletten för erbjudandena som du testar, att du kan ändra bakgrundsfärgen för sidan och utesluta standardbakgrundsfärgen.

**Om du vill exkludera standardinnehåll med [!UICONTROL Visual Experience Composer] (VEC):**

1. När du [skapar eller redigerar en AP-aktivitet](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) markerar du det innehåll du vill ersätta och klickar för att komma åt **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image Offer]** eller **[!UICONTROL Change Background Color]**. Vilka alternativ som är tillgängliga varierar beroende på typ av innehåll.

   ![Ändra alternativ](/help/main/c-activities/t-automated-personalization/assets/options.png)
1. Skapa nytt innehåll.

1. Klicka på ikonen **[!UICONTROL More Actions]** ( ![Fler åtgärder](/help/main/assets/icons/Setting.svg) ) och klicka sedan på alternativet **Uteslut standarderbjudande/Inkludera standard**/ för att exkludera eller inkludera standarderbjudande.

   <!-- Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)-->

<!-- 1. Click **[!UICONTROL Save]**.

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_vec_4 image](assets/exclude_content_vec_4.png)

**To exclude default content using the [!UICONTROL Form-Based Experience Composer]:** 

1. While creating or editing an AP activity, click **[!UICONTROL Change Text/HTML]** or **[!UICONTROL Change Image Offer]** under **[!UICONTROL Content]**. 
1. In the dialog box, create your new content and uncheck **[!UICONTROL Include]** to the right of the default content (or uncheck the Default Image/Video in the [!UICONTROL Select Content] screen). 

   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![exclude_content_form_1 image](assets/exclude_content_form_1.png)

   For Image/Video content: 

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. Click **[!UICONTROL Save]**. 

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)-->
