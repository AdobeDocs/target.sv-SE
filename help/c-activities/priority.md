---
keywords: settings;priority
description: Adobe Target avgör vilken eller vilka aktiviteter som ska levereras till en sida på olika sätt beroende på vilket Target-gränssnitt och vilken aktivitetsskapande funktion (Visual Experience Composer eller Form Based Composer) du använder.
title: Prioritet i Adobe Target
feature: activities
topic: Standard
uuid: 114cd625-2716-4c4c-983b-a7f677717b07
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 0%

---


# Prioritet{#priority}

Mål avgör vilken aktivitet (eller vilka aktiviteter) som ska levereras till en sida på olika sätt beroende på vilket Target-gränssnitt och vilken aktivitetsskapande funktion (Visual Experience Composer eller Form Based Composer) du använder.

## Target Standard/Premium Visual Experience Composer Only eller Form-Based Composer Using Global Target Request Only {#section_4A0A317DFED345649B58B0CB5B410C8B}

Om ditt företag enbart använder Target Standard/Premium och Visual Experience Composer kan innehåll från flera aktiviteter returneras för samma anrop. Verksamheter levereras med hjälp av följande beslutsflöde:

1. Målserveranropet kommer till Target med information om URL:en.
1. Mål hämtar alla aktiviteter som körs på den URL:en.
1. Målförsök att matcha besökaren med aktiviteter.

   Om besökaren redan deltar i ett A/B-test eller multivariattest kommer de att matcha det testet tills de konverteras. Om de tidigare hade en upplevelseinriktad aktivitet måste de matcha sig mot den igen. Om de uppfyller målgruppsreglerna faller besökaren in i dessa aktiviteter och i särskilda upplevelser.

1. Innehåll för alla aktiviteter och upplevelser som besökaren matchar återgår till sidan.
1. Om innehållet för varje aktivitet refererar till olika [CSS-väljare](/help/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337)visas allt innehåll.

   Om det finns en överlappning eller en duplicerad CSS-väljare visas aktivitetsinnehållet med den högsta prioriteten. Resultaten från alla aktiviteter som körs på sidan räknas och återspeglas i rapporterna.

   >[!IMPORTANT]
   >
   >Mål returnerar innehållet för alla aktiviteter på sidan, med början med det lägsta prioriterade innehållet, som sedan skrivs över av varje aktivitet, från den lägsta till den högsta prioriteten. I de flesta fall innebär detta att innehåll med högst prioritet visas. Om en aktivitet med lägre prioritet ändrar strukturen för sidans DOM, är det möjligt att aktiviteten med högre prioritet inte känner igen sidstrukturen, så innehållet med lägre prioritet visas. Resultaten från alla aktiviteter som körs på sidan räknas och återspeglas i rapporterna.

1. Om flera aktiviteter har samma prioritetsnivå finns det två nivåer:

   * Om bara en aktivitet har målgruppsanpassning visas den aktiviteten.
   * Om alla eller inga har mål visas den aktivitet som godkändes först.

## Target Standard/Premium Form-Based Composer och Target Standard/Premium Visual Experience Composer {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>Den här informationen gäller även alla kampanjer som körs och som har skapats i [!DNL Target Classic].

Om ditt företag använder den formulärbaserade dispositionen i Target Standard/Premium och Target Standard/Premium Visual Experience Composer kan innehåll från flera Visual Experience Composer-aktiviteter leverera, men bara en aktivitet från det formulärbaserade arbetsflödet. Aktivitetsleveransen bestäms med hjälp av följande beslutsflöde:

1. Målserveranropet kommer till Target med information om [!DNL Target] begäran och URL.
1. Target Classic och Standard drar alla aktiviteter som körs i den [!DNL Target] begäran.
1. Målförsök att matcha besökaren med aktiviteter.

   Om besökaren redan deltar i ett A/B-test eller multivariattest kommer de att matcha det testet tills de konverteras. Om de tidigare hade en upplevelseinriktad aktivitet måste de matcha sig mot den igen. Om de uppfyller målgruppsreglerna faller besökaren in i dessa aktiviteter och i särskilda upplevelser.

1. Om en formulärbaserad aktivitet har högst prioritet returneras aktivitetsinnehållet tillsammans med allt matchande aktivitetsinnehåll från Visual Experience Composer-aktiviteter.
1. Om en aktivitet i Visual Experience Composer har högst prioritet returneras innehåll från alla matchande aktiviteter i Visual Experience Composer, men inget Target Classic- eller formulärbaserat aktivitetsinnehåll returneras.

   Resultaten från alla aktiviteter som körs på sidan räknas och återspeglas i rapporterna.

**Exempel**

Om du har två aktiviteter, den ena med nyckelordet Nike som varumärkeskländare och den andra med nyckelordet som inte är varumärkesprofilerade, kontrolleras prioriteten för båda aktiviteterna. Om Nike-aktiviteten har högre prioritet visas det innehållet. Om nekare-aktiviteten har högre prioritet visas dess innehåll.

Om båda målinriktade aktiviteter har samma prioritet visas den aktivitet som senast visades. Om besökaren är nybörjare på sidan visas den aktivitet som aktiverades senast.

## Målstandarddisposition/förstklassig formulärbaserad disposition med icke-globala målbegäranden {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>Den här informationen gäller även alla kampanjer som körs och som har skapats i Target Classic.

Om ditt företag använder andra [!DNL Target] förfrågningar än den globala [!DNL Target] förfrågningen i den formulärbaserade dispositionen kan innehåll från endast en aktivitet returneras per anrop. Aktivitetsleveransen bestäms med hjälp av följande beslutsflöde:

1. Serveranropet [!DNL Target] innehåller information [!DNL Target] om [!DNL Target] begäran och URL:en.
1. [!DNL Target] hämtar alla aktiviteter som körs i den [!DNL Target] begäran.
1. [!DNL Target] försöker att matcha besökaren med den högsta prioritetsaktiviteten.

   Om besökaren redan deltar i ett A/B-test eller multivariattest kommer de att matcha det testet tills de konverteras. Om de tidigare hade en upplevelseinriktad aktivitet måste de matcha sig mot den igen. Om de uppfyller målgruppsreglerna faller besökaren in i dessa aktiviteter och i särskilda upplevelser.

1. Om flera aktiviteter har samma prioritetsnivå finns det två nivåer:

   * Om bara en aktivitet har målgruppsanpassning visas den aktiviteten.
   * Om alla eller inga har mål visas den aktivitet som godkändes först.

## Exempel {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Beroende på dina inställningar varierar prioritetsvärdena. Du kan använda de äldre inställningarna Låg, Medel eller Hög, eller aktivera finkorniga prioriteringar mellan 0 och 999. Mer information finns i [Aktivitetsinställningar](/help/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

**Två Target Classic-kampanjer använder icke-globala Target-begäranden**

* Kampanj 1: homePageHero, offer1, priority high
* Kampanj 2: homePageHero, offer2, priority low

Svar: offer1

**Två aktiviteter använder endast erbjudanden som skapats i Visual Experience Composer för olika väljare**

* Aktivitet 1: target-global-mbox, selector1, visualExpCompOffer1, priority low
* Aktivitet 2: target-global-mbox, selector2, visualExpCompOffer2, priority high

Svar: visualExpCompOffer1, visualExpCompOffer2

**Två aktiviteter använder endast erbjudanden som skapats i Visual Experience Composer för samma väljare**

* Aktivitet 1: target-global-mbox, selector1, visualExpCompOffer1, priority low
* Aktivitet 2: target-global-mbox, selector1, visualExpCompOffer2, priority high

Svar: visualExpCompOffer1, visualExpCompOffer2

>[!NOTE]
>
>Detta är samma svar som i det andra användningsfallet ovan eftersom Target Classic inte hanterar väljarkollisioner. Target Standard fångar upp sådant beteende och andra användningsfall när väljare kan kollidera både i DOM och visuellt (vanligtvis på upplevelseredigeringsnivå eller i kampanjsimuleringsläge).

**Två aktiviteter använder erbjudanden som skapats i Visual Experience Composer och två Target Classic-kampanjer**

* Aktivitet 1: target-global-mbox, selector1, visualExpCompOffer1, medium high
* Aktivitet 2: target-global-mbox, selector2, visualExpCompOffer2, priority low
* Kampanj 1: target-global-mbox, offer1, priority high
* Kampanj 2: target-global-mbox, offer2, priority low

Svar: offer1, visualExpCompOffer2, visualExpCompOffer1

>[!NOTE]
>
>Ordningen för kombinerade svar är att klassiskt innehåll kommer först (endast ett klassiskt svar kommer att behandlas som i fallet 1) och sedan erbjuder Visual Experience Composer svar som sorteras efter inverterad prioritet.

## Utbildningsvideo: Aktivitetsinställningar (3:02)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/17381)