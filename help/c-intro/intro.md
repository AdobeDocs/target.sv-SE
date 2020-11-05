---
keywords: Target Standard;Recommendations;Target Premium;Automated Personalization;auto-target;auto target;permissions;what is adobe target;
description: Adobe Target är en Adobe Experience Cloud-lösning som innehåller allt ni behöver för att skräddarsy och personalisera kundernas upplevelse och maximera intäkterna från era webbplatser, mobilsajter, appar, sociala medier och andra digitala kanaler.
title: Introduktion till Adobe Target
feature: intro
topic: Advanced
uuid: 70ccfbe9-c240-4380-9f43-522af51c1d5f
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 0%

---


# Introduktion till Target{#introduction-to-target}

[!DNL Adobe Target] är den [!DNL Adobe Experience Cloud] lösning som innehåller allt ni behöver för att skräddarsy och personalisera kundernas upplevelse och maximera intäkterna på era webbplatser och mobilsajter, appar, sociala medier och andra digitala kanaler.

Lösningen innehåller flera [!DNL Adobe Target] komponenter:

## Målstandard {#section_ACD5EFF17AAB4E979CBEFA0145CCD905}

[!DNL Target Standard] är en startpunkt för [!DNL Adobe Target] att visuellt skapa och hantera A/B-tester och regelbaserade målinriktningsaktiviteter samt ansluta till Adobe Experience Cloud. [!DNL Target Standard] har stöd för anpassad kodinfogning både i och utanför [!UICONTROL Visual Experience Composer] arbetsflödet. [!DNL Target Standard] erbjuder en förenklad implementeringsstrategi med digitala resurser: bara en enda kodrad på varje sida hanterar all kommunikation som krävs mellan webbplatsen och [!DNL Adobe Target].

De bästa metoderna för branschen är inbyggda [!DNL Target Standard]i och har utformats för att användas av både nya och erfarna användare. Ni kan dela data och resultat och enkelt samarbeta med andra teammedlemmar som använder [!DNL Adobe Experience Cloud].

## Mål Premium {#premium}

[!DNL Target Premium] är en avancerad [!DNL Target] licens som ger [!DNL Target Standard]extra premiumfunktioner.

[!DNL Target Premium] Hjälpavsnitten innehåller Premium-märket överst på sidan:

![Premium-märke](/help/assets/premium.png)

Target Premium innehåller följande premiumfunktioner:

### Automated Personalization

[Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) har avancerade algoritmer för maskininlärning för att skapa personaliserade upplevelser och förbättrade konverteringsgrader för digitala upplevelser.

Automatiserad personalisering (tidigare Test&amp;Target 1:1) registrerar besökaraktivitet på webbplatsen och skapar en besökarprofil så att innehåll kan riktas till liknande besökare. Den spårar svaren på innehåll, både för enskilda personer och för hela befolkningen, och använder sedan avancerade modelleringsmetoder för att automatiskt rikta sig till varje individ genom att redovisa allt som är känt om besökaren.

Automatiserad personalisering lär sig på egen hand och kräver minsta möjliga mänskliga analys. Helt automatiserat lär man sig kontinuerligt. Systemet bygger modeller och lär sig automatiskt vilka produkter en enskild besökare är mest intresserad av. Varje gång en besökare interagerar med webbplatsen samlas information in och lagras i besökarprofilen. Det finns flera tillgängliga algoritmer som ger den bästa modellen för ditt system.

### Automatiskt mål

[Auto-Target](/help/c-activities/auto-target/auto-target-to-optimize.md) använder avancerad maskininlärning för att identifiera flera högpresterande marknadsföringsdefinierade upplevelser och levererar den mest skräddarsydda upplevelsen till varje besökare baserat på deras individuella kundprofil och beteendet hos tidigare besökare med liknande profiler, för att personalisera innehåll och driva konverteringar.

### Recommendations

[Recommendations](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) -aktiviteter visar automatiskt produkter eller innehåll som kan intressera dina kunder baserat på tidigare användaraktiviteter. Recommendations hjälper kunderna att hänvisa till relevanta saker som de annars kanske inte känner till.

En rekommendation avgör hur en produkt föreslås till en kund, beroende på kundens aktiviteter på webbplatsen. Exempel:

* Uppmuntra människor som köper en ryggsäck att överväga att köpa vandrande skor och leksaker.

   Skapa en rekommendation som visar objekt som ofta köpts tillsammans med hjälp av villkoret&quot;Personer som köpt detta även köpte det&quot;.

* Öka den tid besökarna lägger på er mediematerial genom att rekommendera liknande videomaterial som det de ser just nu.

   Skapa en rekommendation som föreslår andra videoklipp med villkoret&quot;Personer som visade det här&quot;.

* Föreslå att kunder som har tittat på information om sparplaner på din bank även läser om IRA-konton.

   Visa andra produkter som köpts in efter att ha tittat på en produkt utan att visa den första produkten i rekommendationerna, med hjälp av&quot;personer som tittade på den här produkten även har köpt&quot;-kriterierna.

### Recommendations som erbjudande

[Med Recommendations som erbjudande](/help/c-recommendations/recommendations-as-an-offer.md) kan ni inkludera rekommendationer inuti [!UICONTROL A/B Test] (inklusive [!UICONTROL Auto-Allocate] och [!UICONTROL Auto-Target]) och [!UICONTROL Experience Targeting] (XT) aktiviteter.

Den här funktionen öppnar upp helt nya funktioner, som:

* Testa och målinrikta rekommendationer och innehåll som inte är rekommendationer inom samma aktivitet.
* Experimentera enkelt med olika rekommendationer på sidan, t.ex. i vilken ordning olika rekommendationer ska ges.
* Skicka automatiskt trafik till den bästa rekommenderade upplevelsen med [!UICONTROL Auto-Allocate].
* Tilldela besökare dynamiskt skräddarsydda rekommendationer baserat på deras profil med [!UICONTROL Auto-Target].

### Enterprise-användarbehörigheter

[Med funktionerna för Enterprise-användarbehörigheter](/help/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838) kan du skapa olika projekt (så kallade&quot;produktprofiler&quot; i [!DNL Adobe Admin Console for Enterprise]) så att du kan tilldela olika behörigheter till en enskild användare som anger vilken användares åtkomstbehörighet för varje projekt. Dessa distinkta projekt kan jämföras med hur rapportsviterna fungerar i [!DNL Adobe Analytics]. Varje projekt kan ha specifika användare med specifika roller som gäller för en uppsättning egenskaper. Resultatet blir att kunderna kan begränsa åtkomst till vy, redigering, godkännande och publicering för sina användare baserat på region, miljö (dev/stage/prod), kanal eller andra anpassade kriterier.

## Recommendations Classic {#section_9554068100054D2DBDB298CBE5A0E413}

[!DNL Recommendations Classic] visar automatiskt produkter eller innehåll som kan intressera dina kunder baserat på tidigare användaraktiviteter på din webbplats. Recommendations hjälper kunderna att dirigera till objekt de annars kanske inte känner till, vilket förbättrar försäljningen på er webbplats.

Mer information finns i dokumentationen [till](/help/assets/adobe-recommendations-classic.pdf)Recommendations Classic.

## Experience League: Adobe Target Welcome Kit {#kit}

Bygg ditt optimerings- och personaliseringsprogram på Adobe Target med detta välkomstpaket! Det innehåller viktig information, verktyg och resurser som hjälper er att förbereda er för och lansera den första [!DNL Adobe Target] aktiviteten, med kortsiktiga snabbvinster och långsiktiga optimeringsstrategier.

[Adobe Target Welcome Kit](https://expleague.azureedge.net/pdf/Adobe-Target-Welcome-Kit.pdf)

## Utbildningsvideo: Aktivitetstyper (9:03) ![Översikt](/help/assets/overview.png)

I följande video förklaras vilka aktivitetstyper som är tillgängliga i [!DNL Target Standard/Premium] och hur du kan uppnå webbplatsmålen med Target trestegsguidade arbetsflöde.

* Beskriv de typer av aktiviteter som ingår i Adobe Target
* Välj lämplig aktivitetstyp för att uppnå dina mål
* Beskriv det guidade arbetsflödet i tre steg som gäller för alla aktivitetstyper

>[!VIDEO](https://video.tv.adobe.com/v/17386)
