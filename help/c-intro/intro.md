---
keywords: Målstandard;Recommendations;Target Premium;Automated Personalization;auto target;auto target;permissions;what is adobe target;
description: Lär dig grunderna i Adobe Target Standard och Adobe Target Premium. Target Premium innehåller avancerade funktioner som inte finns i standardprodukten.
landing-page-description: Personalisera kundernas upplevelse för att maximera intäkterna från era webbplatser och mobilsajter, appar, sociala medier och andra digitala kanaler.
title: Vad är Target?
feature: Overview
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '933'
ht-degree: 0%

---


# Introduktion till Target{#introduction-to-target}

[!DNL Adobe Target] är den  [!DNL Adobe Experience Cloud] lösning som innehåller allt ni behöver för att skräddarsy och personalisera kundernas upplevelse och maximera intäkterna på era webbplatser, mobilsajter, appar, sociala medier och andra digitala kanaler.

[!DNL Adobe Target]-lösningen innehåller flera komponenter:

## Målstandard {#section_ACD5EFF17AAB4E979CBEFA0145CCD905}

[!DNL Target Standard] är ett gränssnitt  [!DNL Adobe Target] som hjälper dig att visuellt skapa och hantera A/B-tester och regelbaserade målinriktningsaktiviteter samt att ansluta till Adobe Experience Cloud. [!DNL Target Standard] har stöd för anpassad kodinfogning både i och utanför  [!UICONTROL Visual Experience Composer] arbetsflödet. [!DNL Target Standard] erbjuder en förenklad implementeringsstrategi med digitala resurser: bara en enda kodrad på varje sida hanterar all kommunikation som krävs mellan webbplatsen och  [!DNL Adobe Target].

De bästa metoderna för branschen är inbyggda i [!DNL Target Standard] och de är utformade för att användas av både nya och erfarna användare. Du kan dela data och resultat och enkelt samarbeta med andra teammedlemmar som använder [!DNL Adobe Experience Cloud].

## Mål-Premium {#premium}

[!DNL Target Premium] är en avancerad  [!DNL Target] licens som ger  [!DNL Target Standard]extra premiumfunktioner.

[!DNL Target Premium] Hjälpavsnitten innehåller Premium-märket överst på sidan:

![Premium-märke](/help/assets/premium.png)

Target Premium innehåller följande premiumfunktioner:

### Automated Personalization

[Automatiserad ](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) personalisering ger avancerade algoritmer för maskininlärning för att skapa personaliserade upplevelser och förbättrade konverteringsgrader för digitala upplevelser.

Automatiserad personalisering (tidigare Test&amp;Target 1:1) registrerar besökaraktivitet på webbplatsen och skapar en besökarprofil så att innehåll kan riktas till liknande besökare. Den spårar svaren på innehåll, både för enskilda personer och för hela befolkningen, och använder sedan avancerade modelleringsmetoder för att automatiskt rikta sig till varje individ genom att redovisa allt som är känt om besökaren.

Automatiserad personalisering lär sig på egen hand och kräver minsta möjliga mänskliga analys. Helt automatiserat lär man sig kontinuerligt. Systemet bygger modeller och lär sig automatiskt vilka produkter en enskild besökare är mest intresserad av. Varje gång en besökare interagerar med webbplatsen samlas information in och lagras i besökarprofilen. Det finns flera tillgängliga algoritmer som ger den bästa modellen för ditt system.

### Automatiskt mål

[Automatiska ](/help/c-activities/auto-target/auto-target-to-optimize.md) målgrupper använder avancerad maskininlärning för att identifiera flera högpresterande marknadsföringsdefinierade upplevelser och levererar den mest skräddarsydda upplevelsen till varje besökare baserat på deras individuella kundprofil och beteendet hos tidigare besökare med liknande profiler, för att personalisera innehåll och driva konverteringar.

### Recommendations

[Rekommendationer ](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) visar automatiskt produkter eller innehåll som kan intressera dina kunder baserat på tidigare användaraktiviteter. Recommendations hjälper kunderna att hänvisa till relevanta saker som de annars kanske inte känner till.

En rekommendation avgör hur en produkt föreslås till en kund, beroende på kundens aktiviteter på webbplatsen. Exempel:

* Uppmuntra människor som köper en ryggsäck att överväga att köpa vandrande skor och leksaker.

   Skapa en rekommendation som visar objekt som ofta köpts tillsammans med hjälp av villkoret&quot;Personer som köpt detta även köpte det&quot;.

* Öka den tid besökarna lägger på er mediematerial genom att rekommendera liknande videomaterial som det de ser just nu.

   Skapa en rekommendation som föreslår andra videoklipp med villkoret&quot;Personer som visade det här&quot;.

* Föreslå att kunder som har tittat på information om sparplaner på din bank även läser om IRA-konton.

   Visa andra produkter som köpts in efter att ha tittat på en produkt utan att visa den första produkten i rekommendationerna, med hjälp av&quot;personer som tittade på den här produkten även har köpt&quot;-kriterierna.

### Recommendations som erbjudande

[Med Recommendations som ](/help/c-recommendations/recommendations-as-an-offer.md) erbjudande kan du inkludera rekommendationer i  [!UICONTROL A/B Test] (inklusive  [!UICONTROL Auto-Allocate] och  [!UICONTROL Auto-Target]) och  [!UICONTROL Experience Targeting] (XT) aktiviteter.

Den här funktionen öppnar upp helt nya funktioner, som:

* Testa och målinrikta rekommendationer och innehåll som inte är rekommendationer inom samma aktivitet.
* Experimentera enkelt med olika rekommendationer på sidan, t.ex. i vilken ordning olika rekommendationer ska ges.
* Använd [!UICONTROL Auto-Allocate] för att automatiskt överföra trafik till den bästa rekommenderade upplevelsen.
* Tilldela besökare dynamiskt anpassade rekommendationer baserat på deras profil med [!UICONTROL Auto-Target].

### Enterprise-användarbehörigheter

[Med Enterprise User ](/help/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838) Permission kan du skapa olika projekt (så kallade&quot;produktprofiler&quot; i  [!DNL Adobe Admin Console for Enterprise]) så att du kan tilldela olika behörigheter till en enskild användare som bestämmer den användarens åtkomstbehörighet för varje projekt. Dessa distinkta projekt kan jämföras med hur rapportsviterna fungerar i [!DNL Adobe Analytics]. Varje projekt kan ha specifika användare med specifika roller som gäller för en uppsättning egenskaper. Resultatet blir att kunderna kan begränsa åtkomst till vy, redigering, godkännande och publicering för sina användare baserat på region, miljö (dev/stage/prod), kanal eller andra anpassade kriterier.

## Recommendations Classic {#section_9554068100054D2DBDB298CBE5A0E413}

>[!IMPORTANT]
>
>[!DNL Recommendations Classic] är en äldre produkt som inte längre är licensierad till nya kunder. Uppgradera till [!DNL Recommendations] aktiviteter som är tillgängliga i [!DNL Adobe Target Premium] för att få bästa möjliga [!DNL Recommendations]-upplevelse. Se beskrivningen ovan.

[!DNL Recommendations Classic] visar automatiskt produkter eller innehåll som kan intressera dina kunder baserat på tidigare användaraktiviteter på din webbplats. Recommendations hjälper kunderna att dirigera till objekt de annars kanske inte känner till, vilket förbättrar försäljningen på er webbplats.

Mer information finns i [Recommendations Classic-dokumentationen](/help/assets/adobe-recommendations-classic.pdf).

## Experience League: Adobe Target Welcome Kit {#kit}

Bygg ditt optimerings- och personaliseringsprogram på Adobe Target med detta välkomstpaket! Det innehåller viktig information, verktyg och resurser som hjälper dig att förbereda dig för och starta din första [!DNL Adobe Target]-aktivitet, med kortvariga snabbvinster och långsiktiga optimeringsstrategier.

[Adobe Target Welcome Kit](https://expleague.azureedge.net/pdf/Adobe-Target-Welcome-Kit.pdf)

## Utbildningsvideo: Aktivitetstyper (9:03) ![Översikt](/help/assets/overview.png)

I följande video förklaras vilka aktivitetstyper som är tillgängliga i [!DNL Target Standard/Premium] och hur du kan uppnå webbplatsmålen med Target trestegsguidade arbetsflöde.

* Beskriv de typer av aktiviteter som ingår i Adobe Target
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)
