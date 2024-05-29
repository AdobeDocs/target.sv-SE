---
keywords: inställningar;prioritet
description: Lär dig mer [!DNL Adobe Target] avgör vilken aktivitet (eller vilka aktiviteter) som ska levereras till en sida på olika sätt beroende på vilken [!DNL Target] och vilken aktivitetsskapande funktion du använder.
title: Hur [!DNL Target] Vill du tilldela prioritet till olika aktiviteter?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: f935b963d8686ca8991544a96720adfc32b1083e
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 0%

---

# Prioritet

[!DNL Adobe Target] avgör vilken aktivitet (eller vilka aktiviteter) som ska levereras till en sida på olika sätt beroende på vilken [!DNL Target] gränssnitt och funktion för att skapa aktiviteter ([[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) eller [Formulärbaserad Experience Composer](/help/main/c-experiences/form-experience-composer.md)) som du använder.

## [!DNL Target Standard/Premium] [!UICONTROL Visual Experience Composer] endast eller [!UICONTROL Form-Based Experience Composer] använda en global [!DNL Target] endast begäran {#section_4A0A317DFED345649B58B0CB5B410C8B}

Om ditt företag använder [!DNL Target Standard/Premium] och VEC exklusivt kan innehåll från flera aktiviteter returneras för samma anrop. Verksamheter levereras med hjälp av följande beslutsflöde:

1. The [!DNL Target] serversamtal kommer till [!DNL Target] med information om URL:en.
1. [!DNL Target] Hämtar alla aktiviteter som körs på den URL:en.
1. [!DNL Target] försök att matcha besökaren med aktiviteter.

   Om besökaren redan är i en [!UICONTROL A/B Test] eller [!UICONTROL Multivariate Test] -aktivitet, matchar de i den aktiviteten tills de konverteras. Om de tidigare var i [!UICONTROL Experience Targeting] måste de matcha in i det igen. Om de uppfyller målgruppsreglerna faller besökaren in i dessa aktiviteter och i särskilda upplevelser.

1. Innehåll för alla aktiviteter och upplevelser som besökaren matchar återgår till sidan.
1. Om innehållet för varje aktivitet refererar till olika [CSS-väljare](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)och allt innehåll visas.

   Om det finns en överlappning eller en duplicerad CSS-väljare visas aktivitetsinnehållet med den högsta prioriteten. Resultaten från alla aktiviteter som körs på sidan räknas och återspeglas i rapporterna.

   >[!IMPORTANT]
   >
   >[!DNL Target] returnerar innehållet för alla aktiviteter på sidan, med början med det lägsta prioriterade innehållet, som sedan skrivs över av varje aktivitet, från den lägsta till den högsta prioriteten. Detta resulterar vanligtvis i att innehåll med högst prioritet visas. Om en aktivitet med lägre prioritet ändrar strukturen för sidans DOM, är det möjligt att aktiviteten med högre prioritet inte känner igen sidstrukturen, så innehållet med lägre prioritet visas. Resultaten från alla aktiviteter som körs på sidan räknas och återspeglas i rapporterna.

1. Om flera aktiviteter har samma prioritetsnivå finns det två brytningar:

   * Om bara en aktivitet har målgruppsanpassning visas den aktiviteten.
   * Om alla eller inga har mål visas den aktivitet som först godkändes.

## [!DNL Target Standard/Premium] [!UICONTROL Form-Based Experience Composer] och [!DNL Target Standard/Premium] [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>Denna information gäller även alla aktiviteter som körs och som skapats i [!DNL Target Classic].

Om ditt företag använder [!UICONTROL Form-Based Experience Composer] *och* VEC, innehåll från flera [!UICONTROL Form-Based Experience Composer] och VEC-aktiviteter kan leverera. Tidigare kunde bara en aktivitet i det formulärbaserade arbetsflödet levereras. Det finns inte längre någon gräns för hur många formulärbaserade aktiviteter som kan leverera.

Aktivitetsleveransen bestäms med hjälp av följande beslutsflöde:

1. [!DNL Target] serversamtal kommer till [!DNL Target] med information om [!DNL Target] request och URL.
1. [!DNL Target Standard/Premium] hämtar all aktivitet som körs i [!DNL Target] begäran.
1. [!DNL Target] försök att matcha besökaren med aktiviteter.

   Om besökaren redan är i en [!UICONTROL A/B Test] eller [!UICONTROL Multivariate Test] -aktivitet, matchar de i det testet tills de konverteras. Om de tidigare var i [!UICONTROL Experience Targeting] måste de matcha in i det igen. Om de uppfyller målgruppsreglerna faller besökaren in i dessa aktiviteter och i särskilda upplevelser.

1. Om en formulärbaserad aktivitet har högst prioritet returneras aktivitetsinnehållet tillsammans med allt matchande aktivitetsinnehåll från VEC-aktiviteter.
1. Om en VEC-aktivitet har högst prioritet returneras innehåll från alla matchande VEC-aktiviteter, men inget [!DNL Target Classic] eller formulärbaserat aktivitetsinnehåll returneras.

   Resultaten från alla aktiviteter som körs på sidan räknas och återspeglas i rapporterna.

**Exempel**

Om du har två aktiviteter, den ena med nyckelordet Nike som mål och den andra med nyckelordet &quot;nekare&quot; som inte är varumärkta, kontrolleras prioriteten för båda aktiviteterna. Om Nike-aktiviteten har högre prioritet visas det innehållet. Om nekare-aktiviteten har högre prioritet visas dess innehåll.

Om båda målinriktade aktiviteter har samma prioritet visas den aktivitet som senast visades. Om besökaren är nybörjare på sidan visas den aktivitet som aktiverades senast.

## [!DNL Target Standard/Premium] [!UICONTROL Form-Based Experience Composer] med icke-global [!DNL Target] förfrågningar {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>Denna information gäller även alla aktiviteter som körs och som skapats i [!DNL Target Classic].

Om ditt företag använder [!DNL Target] andra förfrågningar än de globala [!DNL Target] -begäran i den formulärbaserade dispositionen kan innehåll från endast en aktivitet returneras per anrop. Aktivitetsleveransen bestäms med hjälp av följande beslutsflöde:

1. The [!DNL Target] serversamtal kommer till [!DNL Target] med information om [!DNL Target] request och URL.
1. [!DNL Target] hämtar all aktivitet som körs i [!DNL Target] begäran.
1. [!DNL Target] försöker att matcha besökaren med den högsta prioritetsaktiviteten.

   Om besökaren redan är i en [!UICONTROL A/B Test] eller [!UICONTROL Multivariate Test] -aktivitet, matchar de i den aktiviteten tills de konverteras. Om de tidigare var i [!UICONTROL Experience Targeting] måste de matcha in i det igen. Om de uppfyller målgruppsreglerna faller besökaren in i dessa aktiviteter och i särskilda upplevelser.

1. Om flera aktiviteter har samma prioritetsnivå finns det två brytningar:

   * Om bara en aktivitet har målgruppsanpassning visas den aktiviteten.
   * Om alla eller inga har mål visas den aktivitet som först godkändes.

## Exempel {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Beroende på dina inställningar varierar prioritetsvärdena. Du kan använda de äldre inställningarna för [!UICONTROL Low], [!UICONTROL Medium], eller [!UICONTROL High]eller så kan du aktivera finkorniga prioriteringar mellan 0 och 999. Mer information finns i [Aktivitetsinställningar](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

**Två [!DNL Target Classic] aktiviteter använder icke-globala [!DNL Target] förfrågningar**

* Aktivitet 1: homePageHero, offer1, priority high
* Aktivitet 2: homePageHero, offer2, priority low

Svar: erbjudande1

**Två aktiviteter använder endast erbjudanden som skapats i [!UICONTROL Visual Experience Composer] för olika väljare**

* Aktivitet 1: target-global-mbox, selector1, visualExpCompOffer1, priority low
* Aktivitet 2: target-global-mbox, selector2, visualExpCompOffer2, priority high

Svar: visualExpCompOffer1, visualExpCompOffer2

**Två aktiviteter använder endast erbjudanden som skapats i [!UICONTROL Visual Experience Composer] för samma väljare**

* Aktivitet 1: target-global-mbox, selector1, visualExpCompOffer1, priority low
* Aktivitet 2: target-global-mbox, selector1, visualExpCompOffer2, priority high

Svar: visualExpCompOffer1, visualExpCompOffer2

>[!NOTE]
>
>Detta är samma svar som i det andra användningsfallet ovan eftersom [!DNL Target Classic] Hanterade inte väljarkollisioner. [!DNL Target Standard/Premium] fångar upp sådant beteende och andra användningsfall när väljare kan kollidera både i DOM och visuellt (vanligtvis på upplevelseredigeringsnivå eller i aktivitetssimuleringsläge).

**Två aktiviteter använder erbjudanden som skapats i [!UICONTROL Visual Experience Composer] och två [!DNL Target Classic] verksamhet**

* Aktivitet 1: target-global-mbox, selector1, visualExpCompOffer1, medium high
* Aktivitet 2: target-global-mbox, selector2, visualExpCompOffer2, priority low
* Aktivitet 1: target-global-mbox, offer1, priority high
* Aktivitet 2: target-global-mbox, offer2, priority low

Svar: offer1, visualExpCompOffer2, visualExpCompOffer1

>[!NOTE]
>
>Ordningen för kombinerade svar är att [!DNL Target Classic] innehåll kommer först. Bara en [!DNL Target Classic] Svar behandlas som i fall 1, och sedan [!UICONTROL Visual Experience Composer] erbjuder svar som ordnas med omvänd prioritet.

## Utbildningsvideo: Aktivitetsinställningar (3:02)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/17381)
