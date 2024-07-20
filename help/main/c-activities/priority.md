---
keywords: inställningar;prioritet
description: Lär dig hur [!DNL Adobe Target] avgör vilken aktivitet (eller vilka aktiviteter) som ska levereras till en sida på olika sätt beroende på vilket  [!DNL Target] gränssnitt och vilken funktion du använder för att skapa aktiviteter.
title: Hur tilldelar  [!DNL Target] prioritet till olika aktiviteter?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: be6e45ff301f549eb5be24a65b05c4a9c1cd6089
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 0%

---

# Prioritet

[!DNL Adobe Target] avgör vilken eller vilka aktiviteter som ska levereras till en sida på olika sätt beroende på vilket [!DNL Target] gränssnitt och vilken aktivitetsskapande funktion ([[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) eller [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md)) du använder.

## Endast [!UICONTROL Visual Experience Composer] eller [!UICONTROL Form-Based Experience Composer] som endast använder en global [!DNL Target]-begäran {#section_4A0A317DFED345649B58B0CB5B410C8B}

Om ditt företag använder VEC exklusivt kan innehåll från flera aktiviteter returneras för samma samtal. Verksamheter levereras med hjälp av följande beslutsflöde:

1. Serveranropet [!DNL Target] kommer till [!DNL Target] med information om URL:en.
1. [!DNL Target] hämtar alla aktiviteter som körs på den URL:en.
1. [!DNL Target] försöker matcha besökaren med aktiviteter.

   Om besökaren redan är i en [!UICONTROL A/B Test]- eller [!UICONTROL Multivariate Test]-aktivitet matchar de den aktiviteten tills de konverteras. Om de tidigare fanns i en [!UICONTROL Experience Targeting]-aktivitet måste de matcha in den igen. Om de uppfyller målgruppsreglerna faller besökaren in i dessa aktiviteter och i särskilda upplevelser.

1. Innehåll för alla aktiviteter och upplevelser som besökaren matchar återgår till sidan.
1. Om innehållet för varje aktivitet refererar till olika [CSS-väljare](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337) visas allt innehåll.

   Om det finns en överlappning eller en duplicerad CSS-väljare visas aktivitetsinnehållet med den högsta prioriteten. Resultaten från alla aktiviteter som körs på sidan räknas och återspeglas i rapporterna.

   >[!IMPORTANT]
   >
   >[!DNL Target] returnerar innehållet för alla aktiviteter på sidan, med början med det lägsta prioriterade innehållet, som sedan skrivs över av varje aktivitet, från den lägsta till den högsta prioriteten. Detta resulterar vanligtvis i att innehåll med högst prioritet visas. Om en aktivitet med lägre prioritet ändrar strukturen för sidans DOM, är det möjligt att aktiviteten med högre prioritet inte känner igen sidstrukturen, så innehållet med lägre prioritet visas. Resultaten från alla aktiviteter som körs på sidan räknas och återspeglas i rapporterna.

1. Om flera aktiviteter har samma prioritetsnivå finns det två brytningar:

   * Om bara en aktivitet har målgruppsanpassning visas den aktiviteten.
   * Om alla eller inga har mål visas den aktivitet som först godkändes.

## [!UICONTROL Form-Based Experience Composer] och [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

Om ditt företag använder [!UICONTROL Form-Based Experience Composer] *och* VEC kan innehåll från flera [!UICONTROL Form-Based Experience Composer]- och VEC-aktiviteter leverera. Tidigare kunde bara en aktivitet i det formulärbaserade arbetsflödet levereras. Det finns inte längre någon gräns för hur många formulärbaserade aktiviteter som kan leverera.

Aktivitetsleveransen bestäms med hjälp av följande beslutsflöde:

1. [!DNL Target]-serveranropet kommer till [!DNL Target] med information om [!DNL Target]-begäran och URL:en.
1. [!DNL Target] hämtar alla aktiviteter som körs i den [!DNL Target]-begäran.
1. [!DNL Target] försöker matcha besökaren med aktiviteter.

   Om besökaren redan är i en [!UICONTROL A/B Test]- eller [!UICONTROL Multivariate Test]-aktivitet matchar de det testet tills de konverteras. Om de tidigare fanns i en [!UICONTROL Experience Targeting]-aktivitet måste de matcha in den igen. Om de uppfyller målgruppsreglerna faller besökaren in i dessa aktiviteter och i särskilda upplevelser.

1. Om en formulärbaserad aktivitet har högst prioritet returneras aktivitetsinnehållet tillsammans med allt matchande aktivitetsinnehåll från VEC-aktiviteter.
1. Om en VEC-aktivitet har högst prioritet returneras innehåll från alla matchande VEC-aktiviteter, men inget formulärbaserat aktivitetsinnehåll returneras.

   Resultaten från alla aktiviteter som körs på sidan räknas och återspeglas i rapporterna.

**Exempel**

Om du har två aktiviteter, den ena med nyckelordet Nike som mål och den andra med nyckelordet &quot;nekare&quot; som inte är varumärkta, kontrolleras prioriteten för båda aktiviteterna. Om Nike-aktiviteten har högre prioritet visas det innehållet. Om nekare-aktiviteten har högre prioritet visas dess innehåll.

Om båda målinriktade aktiviteter har samma prioritet visas den aktivitet som senast visades. Om besökaren är nybörjare på sidan visas den aktivitet som aktiverades senast.

## [!UICONTROL Form-Based Experience Composer] med icke-globala [!DNL Target]-begäranden {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

Om ditt företag använder [!DNL Target] andra förfrågningar än den globala [!DNL Target]-förfrågan i den formulärbaserade dispositionen kan innehåll från endast en aktivitet returneras per anrop. Aktivitetsleveransen bestäms med hjälp av följande beslutsflöde:

1. Serveranropet [!DNL Target] kommer till [!DNL Target] med information om begäran [!DNL Target] och URL:en.
1. [!DNL Target] hämtar alla aktiviteter som körs i den [!DNL Target]-begäran.
1. [!DNL Target] försöker matcha besökaren med aktiviteten med högst prioritet.

   Om besökaren redan är i en [!UICONTROL A/B Test]- eller [!UICONTROL Multivariate Test]-aktivitet matchar de den aktiviteten tills de konverteras. Om de tidigare fanns i en [!UICONTROL Experience Targeting]-aktivitet måste de matcha in den igen. Om de uppfyller målgruppsreglerna faller besökaren in i dessa aktiviteter och i särskilda upplevelser.

1. Om flera aktiviteter har samma prioritetsnivå finns det två brytningar:

   * Om bara en aktivitet har målgruppsanpassning visas den aktiviteten.
   * Om alla eller inga har mål visas den aktivitet som först godkändes.

## Exempel {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Beroende på dina inställningar varierar prioritetsvärdena. Du kan använda de äldre inställningarna för [!UICONTROL Low], [!UICONTROL Medium] eller [!UICONTROL High], eller så kan du aktivera finjusterade prioriteter från 0 till 999. Mer information finns i [Aktivitetsinställningar](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

Svar: erbjudande1

**Två aktiviteter använder endast erbjudanden som skapats i [!UICONTROL Visual Experience Composer] för olika väljare**

* Aktivitet 1: target-global-mbox, selector1, visualExpCompOffer1, priority low
* Aktivitet 2: target-global-mbox, selector2, visualExpCompOffer2, priority high

Svar: visualExpCompOffer1, visualExpCompOffer2

**Två aktiviteter använder bara erbjudanden som skapats i [!UICONTROL Visual Experience Composer] för samma väljare**

* Aktivitet 1: target-global-mbox, selector1, visualExpCompOffer1, priority low
* Aktivitet 2: target-global-mbox, selector1, visualExpCompOffer2, priority high

Svar: visualExpCompOffer1, visualExpCompOffer2

## Utbildningsvideo: Aktivitetsinställningar (3:02)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/17381)
