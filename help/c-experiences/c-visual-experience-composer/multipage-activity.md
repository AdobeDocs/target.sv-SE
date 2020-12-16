---
keywords: multi-page;journey testing;multipage activity
description: Med en flersidig aktivitet kan du skapa en artikel över flera sidor, med en design som är specifik för varje sida.
title: Flersidig aktivitet
feature: vec
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---


# Flersidig aktivitet{#multipage-activity}

Med en flersidig aktivitet kan du skapa en artikel över flera sidor, med en design som är specifik för varje sida.

Du kanske vill testa ett erbjudande om fri frakt med inköp över ett visst belopp. Du kanske vill att erbjudandet ska visas på landningssidan, på en kategorisida och på vissa produktsidor, men du vill att det ska vara olika stort och på olika platser för varje sidtyp. Du kan visa ett framträdande erbjudande på din hemsida och sedan förstärka erbjudandet med mindre erbjudanden på andra relevanta sidor.

Du kan också använda en flersidig aktivitet för att definiera olika layouter för mobilsajter på datorn och för mobilsajter som inte svarar. Om webbplatsen har en separat mobilwebbplats som [!DNL m.mysite.com] i stället för [!DNL `www.mysite.com`] bör du i stället skapa en [flersidig aktivitet](/help/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48), lägga till [!DNL m.mysite.com] som separata sidor och sedan använda mobilredigering för att göra lämpliga ändringar i skrivbordsversionen och mobilversionen i samma upplevelse. Använd [redigering av mobilupplevelser](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5) för responsiva mobilsajter.

>[!NOTE]
>
>Flersidiga aktiviteter är utformade för aktiviteter där samma erbjudande har olika utseende på flera sidor. Om erbjudandet är detsamma på alla sidor är ett [malltest](/help/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781) effektivare.

Du kan ange mallregler för varje sida i flersidigt test. Du kan t.ex. köra ett flersidigt test över hemsidan och alla kategorisidor genom att tillämpa mallregler på kategorisidan i flersidigt test. Se [Inkludera samma upplevelse på liknande sidor](/help/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781).

Så här lägger du till sidor i ett test:

1. Klicka på kugghjulsikonen **[!UICONTROL Configure]**.
1. Klicka på **[!UICONTROL Add Additional Pages]**.

   Ett navigeringsfält visas till vänster på skärmen.

   ![](assets/multipage_nav.png)

1. Använd navigeringsfältet för att ange sidor och för att ange standardsida.

   Klicka på **[!UICONTROL Add Page]** om du vill lägga till ytterligare en sida.

   Klicka på ikonen med tre lodräta ellipser för att visa en åtgärdsmeny:

   ![](assets/multipage_menu.png)

   Använd den här menyn om du vill byta namn på sidorna, utföra ett omdirigeringstest i flersidesaktiviteten eller ta bort sidan.

1. Använd Visual Experience Composer för att utforma hur erbjudandet ser ut på varje sida.

