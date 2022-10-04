---
keywords: flersidig;resetestning;flersidig aktivitet
description: Lär dig hur du skapar en flersidig aktivitet i Adobe [!DNL Target] Med kan du skapa en artikel över flera sidor, med en design som är specifik för varje sida.
title: Hur skapar jag en flersidig aktivitet?
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---

# Flersidig aktivitet

En flersidig aktivitet i [!DNL Adobe Target] Med kan du skapa en artikel över flera sidor, med en design som är specifik för varje sida.

Du kanske vill testa ett erbjudande om fri frakt med inköp över ett visst belopp. Du kanske vill att erbjudandet ska visas på landningssidan, på en kategorisida och på vissa produktsidor, men du vill att det ska vara olika stort och på olika platser för varje sidtyp. Du kan visa ett framträdande erbjudande på din hemsida och sedan förstärka erbjudandet med mindre erbjudanden på andra relevanta sidor.

Du kan också använda en flersidig aktivitet för att definiera olika layouter för mobilsajter på datorn och för mobilsajter som inte svarar. Om webbplatsen har en separat mobilwebbplats som [!DNL m.mysite.com] i stället för [!DNL `www.mysite.com`]bör du i stället skapa en [flersidig aktivitet](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48), lägga till [!DNL m.mysite.com] som separata sidor och sedan använda mobilredigering för att göra lämpliga ändringar i persondatorversionen och mobilversionen i samma upplevelse. För responsiva mobilsajter använder du [redigera mobilupplevelser](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5).

>[!NOTE]
>
>Flersidiga aktiviteter är utformade för aktiviteter där samma erbjudande har olika utseende på flera sidor. Om erbjudandet är detsamma på alla sidor är [malltest](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781) är mer effektivt.

Du kan ange mallregler för varje sida i flersidigt test. Du kan t.ex. köra ett flersidigt test över hemsidan och alla kategorisidor genom att tillämpa mallregler på kategorisidan i flersidigt test. Se [Inkludera samma upplevelse på liknande sidor](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781).

Så här lägger du till sidor i ett test:

1. Klicka på **[!UICONTROL Configure]** kugghjulsikon.
1. Klicka på **[!UICONTROL Add Additional Pages]**.

   Ett navigeringsfält visas till vänster på skärmen.

   ![multipage_nav-bild](assets/multipage_nav.png)

1. Använd navigeringsfältet för att ange sidor och för att ange standardsida.

   Klicka **[!UICONTROL Add Page]** om du vill lägga till ytterligare en sida.

   Klicka på ikonen med tre lodräta ellipser för att visa en åtgärdsmeny:

   ![multipage_menu-bild](assets/multipage_menu.png)

   Använd den här menyn om du vill byta namn på sidorna, utföra ett omdirigeringstest i flersidesaktiviteten eller ta bort sidan.

1. Använd Visual Experience Composer för att utforma hur erbjudandet ser ut på varje sida.
