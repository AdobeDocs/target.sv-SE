---
keywords: flersidig;resetestning;flersidig aktivitet
description: Lär dig hur du skapar en flersidig aktivitet i Adobe [!DNL Target] där du kan skapa en artikel över flera sidor, med en design som är specifik för varje sida.
title: Hur skapar jag en flersidig aktivitet?
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
source-git-commit: f968ec45f015fa0b195007f5790b9efb743c8b65
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# Flersidig aktivitet

Med en flersidig aktivitet i [!DNL Adobe Target] kan du skapa en artikel över flera sidor, med en design som är specifik för varje sida.

Du kanske vill testa ett erbjudande om fri frakt med inköp över ett visst belopp. Du kanske vill att erbjudandet ska visas på landningssidan, på en kategorisida och på vissa produktsidor, men du vill att det ska vara olika stort och på olika platser för varje sidtyp. Du kan visa ett framträdande erbjudande på din hemsida och sedan förstärka erbjudandet med mindre erbjudanden på andra relevanta sidor.

Du kan också använda en flersidig aktivitet för att definiera olika layouter för mobilsajter på datorn och för mobilsajter som inte svarar. Om webbplatsen har en separat mobilwebbplats som [!DNL m.mysite.com] i stället för [!DNL `www.mysite.com`] bör du i stället skapa en [flersidig aktivitet](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48), lägga till [!DNL m.mysite.com] som separata sidor och sedan använda mobilredigering för att göra lämpliga ändringar i skrivbordsversionen och mobilversionen i samma upplevelse. Använd [redigering av mobilupplevelser](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5) för responsiva mobilwebbplatser.

>[!NOTE]
>
>Flersidiga aktiviteter är utformade för aktiviteter där samma erbjudande har olika utseende på flera sidor. Om erbjudandet visas likadant på alla sidor blir [malltestet](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781) effektivare.

Du kan ange mallregler för varje sida i flersidigt test. Du kan t.ex. köra ett flersidigt test över hemsidan och alla kategorisidor genom att tillämpa mallregler på kategorisidan i flersidigt test. Se [Inkludera samma upplevelse på liknande sidor](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781).

Så här lägger du till sidor i ett test:

1. Klicka på ikonen **[!UICONTROL Configure]** ( ![Konfigurera ikon](/help/main/assets/icons/Setting.svg) ).
1. Klicka på **[!UICONTROL Add Additional Pages]**.

   En [!UICONTROL Pages]-ruta visas till vänster på skärmen.

1. Ange dina sidor och ange standardsida.

   Klicka på **[!UICONTROL Add Page]** ( ![Lägg till ikon](/help/main/assets/icons/Add.svg) ) om du vill lägga till ytterligare en sida, ange sidnamnet och URL-adressen och klicka sedan på **[!UICONTROL Save]**.

1. Använd [!UICONTROL Visual Experience Composer] för att utforma hur erbjudandet ser ut på varje sida.
