---
keywords: aktivitetsinställningar;mål och inställningar för målinriktning av upplevelser;mål och inställningar;målinriktning av upplevelser;målinställningar;målmått;framgångsmått;beroende framgångsmått;avancerade inställningar;primära mål;mål;prioritet;varaktighet;rapporteringslösning;mål;målgrupper för rapportering;Vilket framgångsmått måste uppnås innan det här måttet ökas;Vad kommer att hända när en användare påträffar det här målmåttet;noterar
description: Lär dig hur du använder sidan [!UICONTROL Goals & Settings] i [!DNL Adobe Target] för att ange information om målen för en [!UICONTROL Experience Targeting] (XT)-aktivitet.
title: Hur anger jag [!UICONTROL Goals & Settings] i en [!UICONTROL Experience Targeting]-aktivitet?
feature: Experience Targeting
exl-id: 80cb7eff-4e9c-43d7-a3d8-7a9de79c91b9
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 0%

---

# Mål och inställningar i [!UICONTROL Experience Targeting] (XT)-aktiviteter

På sidan [!UICONTROL Goals & Settings] anger du information om målet för testet:

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

Vilka inställningar som är tillgängliga beror på om du använder [!DNL Target] eller [!DNL Analytics] som rapportkälla.

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

Följande inställningar är tillgängliga:

### [!UICONTROL Objective]

Ange ett valfritt mål. Målet kan vara vilken information som helst som hjälper dig och dina teammedlemmar att identifiera kampanjen.

### [!UICONTROL Priority]

Beroende på dina inställningar varierar användargränssnittet för [!DNL Target] och alternativen för [!UICONTROL Priority]. Du kan använda de äldre inställningarna för [!UICONTROL Low], [!UICONTROL Medium] eller [!UICONTROL High], eller så kan du aktivera finjusterade prioriteter från 0 till 999.

Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas den aktivitet som har högst prioritet.

Om det här alternativet inte är aktiverat i [!UICONTROL Administration] (standardvärdet) anger du en prioritet: [!UICONTROL Low], [!UICONTROL Medium] eller [!UICONTROL High].

Om du vill aktivera finkorniga prioriteringar klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Reporting]** och växlar sedan alternativet [!UICONTROL Enable Fine-Grained Priorities] till På-positionen.

Om det här alternativet är aktiverat anger du ett värde mellan 0 och 999:

* 0 = Låg
* 999 = Hög

För aktiviteter som skapats i tidigare versioner av [!DNL Target] konverteras [!UICONTROL Low] prioritet till 0, [!UICONTROL Medium] konverteras till 5 och [!UICONTROL High] konverteras till 10. Du kan justera dessa värden om det behövs.

>[!NOTE]
>
>Innan du kan inaktivera det här alternativet efter att ha använt finkorniga prickar måste alla prioriteter återställas till 0, 5 och 10.

### [!UICONTROL Duration]

Aktiviteten kan starta när den har godkänts eller du kan ange ett specifikt datum och en viss tid. Aktiviteten kan också avslutas när den är inaktiverad eller du kan ange ett datum och en tid då aktiviteten ska sluta. Tidsväljaren använder en 24-timmars klocka, där 00:00 är midnatt. Tidszonen är inställd på den tidszon som har konfigurerats i webbläsaren. Om du vill använda en annan tidszon anger du en annan tidszon för webbläsaren och startar om webbläsaren.

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

Följande inställningar är tillgängliga:

### [!UICONTROL Reporting Source]

Ange vilka lösningsdata som samlas in från:

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

Om en rapporteringslösning anges i dina [kontoinställningar](/help/main/administrating-target/reporting.md) används den angivna lösningen och den här inställningen syns inte.

Du kan inte ändra rapportkällan efter att aktiviteten har publicerats för att rapporterna ska vara konsekventa.

**[!DNL Adobe Analytics]**: Se [[!DNL Adobe Analytics]  som rapportkälla för  [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) om du vill veta mer om skillnaderna mellan rapporteringslösningarna och fördelarna med varje.

När du väljer [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T) väljer du en [!DNL Analytics] rapportsvit som ska ta emot [!DNL Target] aktivitetsdata. För att göra detta väljer du först något av de [!DNL Analytics] företag som ditt konto är knutet till och väljer sedan lämplig rapportsvit för aktiviteten. Endast rapportsviter som har etablerats för att ansluta till [!DNL Target] är tillgängliga för urval. Om du inte ser den rapportserie du förväntar dig kan du först logga ut och logga in på [!DNL Adobe Experience Cloud] för att försöka igen. Om rapportsviten fortfarande saknas i listan kontaktar du [kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] (A4T) kräver en spårningsserver för att rapportera resultaten korrekt. En standardspårningsserver visas i fältet [!UICONTROL Tracking Server]. Om du använder mer än en spårningsserver måste du ta med rätt spårningsserver i det här fältet. Mer information finns i [Använda en analysspårningsserver](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

**[!DNL Adobe Customer Journey Analytics]**: Mer information om integrationen mellan [[!DNL Target]  och  [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) finns i [!DNL Adobe Customer Journey Analytics]Rapportera i [!DNL Target].

### [!UICONTROL Goal Metric]

Välj den åtgärd som en besökare ska utföra för att uppnå målet. Välj till exempel ett [!UICONTROL Conversion]-mått och ange sedan parametrarna som avgör när resultatet uppnås.

Mer information om att ställa in mått finns i [Ange mått](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB).

>[!NOTE]
>
>Om rapporteringslösningen är inställd på [!DNL Analytics] är det enda tillgängliga målmåttet [!UICONTROL Conversion]. Det går inte att välja [!DNL Analytics]-mått som mål.

När du väljer ett framgångsmått visas en väljare. Använd den här väljaren för att välja de specifika värdena för framgångsmåttet.

Om det här alternativet är aktiverat tillhandahåller fältet [!UICONTROL Estimated Value of the Conversion] (inte tillgängligt för [!UICONTROL Page Score]-mått) ett värde för ditt mål, men inte för andra mått. Detta värde gör att [!DNL Target] kan beräkna en uppskattad ökning av intäkterna. Det här fältet är valfritt, men inkrementella intäkter för icke-intäktsmått kan inte beräknas utan det. För alla intäktsmått ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] och [!UICONTROL Orders]) använder uppskattningen [!UICONTROL Revenue per Visitor]. Datatypen är valuta.

När aktivitetsmålet har uppnåtts fortsätter besökaren att se aktivitetsinnehållet, såvida inte besökaren kvalificerar sig för en aktivitet med högre prioritet. Om besökaren når målet igen räknas det som en annan konvertering. Det här beteendet skiljer sig från standardbeteendet i [!DNL Target Classic], som räknade besökare som nya om de ser testet igen.

### [!UICONTROL Additional Metrics]

Skapa fler framgångsmått.

Den här inställningen är inte tillgänglig om rapporteringslösningen är inställd på [!DNL Analytics]. I det här fallet används de mått som definierats för rapportsviten [!DNL Analytics].

### [!UICONTROL Audiences for Reporting]

Som standard visar rapporter resultat för alla kvalificerade besökare. Du kan lägga till rapportmålgrupper för att bara visa information om specifika målgrupper.

Den här inställningen är inte tillgänglig om du väljer [!DNL Analytics] som rapporteringslösning. Målgruppen som definierats för rapportsviten [!DNL Analytics] används.

## [!UICONTROL Other Meta Data]

Skriv in information om din aktivitet som är användbar för dig själv eller andra teammedlemmar. Det går att ändra storlek på rutan [!UICONTROL Notes].

## [!UICONTROL Advanced Settings] {#section_E2FE441AFB324E498793ABB025ED9974}

Avancerade inställningar är tillgängliga för [!UICONTROL Experience Targeting] målmått.

![Avancerade inställningar](/help/main/c-activities/t-experience-target/t-xt-create/assets/Menu_AdvancedSettings-new.png)

>[!NOTE]
>
>Om du använder [!DNL Analytics] som rapportkälla hanteras inställningarna av servern [!DNL Analytics]. Alternativet [!UICONTROL Advanced Settings] är inte tillgängligt.

Följande inställningar är tillgängliga:

### [!UICONTROL Which success metric must be reached before incrementing this metric?]

Använd det här alternativet om du bara vill räkna besökaren som att uppnå framgångsmåttet om de tidigare har nått ett annat framgångsmått. En testkonvertering kan till exempel bara vara giltig om besökaren klickar på erbjudandet eller når en viss sida innan konverteringen.

Du kan ange beroende av flera mätvärden tillsammans med flexibiliteten att välja om mätvärdet ska nås eller inte för att antalet ska öka.

Du måste definiera båda (eller flera) framgångsmått innan du kan göra en beroende av en annan.

Alternativet [!UICONTROL Add Dependency] tillåter att framgångsmåttet ökar om ett annat framgångsmått har nåtts eller inte har nåtts.

Så här lägger du till ett beroende:

1. När du har lagt till ytterligare mått klickar du på **[!UICONTROL Advanced Settings]**.
2. Klicka på **[!UICONTROL Add Dependency]**:

   ![Lägg till beroendelänk](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency-new.png)

3. Dra och släpp önskade mätvärden från den vänstra rutan till den högra rutan och klicka sedan på **[!UICONTROL Reached]** för att växla mellan [!UICONTROL Reached] och [!UICONTROL Not Reached].

   ![Dialogrutan Lägg till metadatberoende](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency_reached-new.png)

Du kan redigera eller ta bort beroenden när du har lagt till dem.

### [!UICONTROL What will happen after a user encounters this goal metric?]

Det finns tre alternativ för vad som händer när en besökare når målmåttet:

* Välj [!UICONTROL Increment Count & Keep User in Activity] om du vill ange hur antalet ska ökas.
* Välj [!UICONTROL Increment Count, Release User & Allow Reentry] om du vill ange vilken upplevelse som användaren ser om aktiviteten återupptas.
* Välj [!UICONTROL Increment Count, Release User & Bar from Reentry] om du vill ange vad användaren ser i stället för aktivitetsinnehållet.

Mer information om avancerade inställningar finns i [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924).

## Utbildningsvideo: Aktivitetsinställningar (3:02)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/17381)
