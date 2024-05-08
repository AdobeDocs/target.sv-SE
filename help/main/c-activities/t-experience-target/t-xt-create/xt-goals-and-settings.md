---
keywords: aktivitetsinställningar;mål och inställningar för målinriktning av upplevelser;mål och inställningar;målinriktning av upplevelser;målinställningar;målmått;framgångsmått;beroende framgångsmått;avancerade inställningar;primära mål;mål;prioritet;varaktighet;rapporteringslösning;mål;målgrupper för rapportering;Vilket framgångsmått måste uppnås innan det här måttet ökas;Vad kommer att hända när en användare påträffar det här målmåttet;noterar
description: Lär dig använda [!UICONTROL Goals & Settings] sida in [!DNL Adobe Target] för att ange information om målen för ett [!UICONTROL Experience Targeting] (XT) aktivitet.
title: Hur anger jag [!UICONTROL Goals & Settings] i en [!UICONTROL Experience Targeting] Aktivitet?
feature: Experience Targeting
exl-id: 80cb7eff-4e9c-43d7-a3d8-7a9de79c91b9
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 0%

---

# Mål och inställningar i [!UICONTROL Experience Targeting] (XT) aktiviteter

The [!UICONTROL Goals & Settings] Här anger du information om testets mål:

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

Vilka inställningar som är tillgängliga beror på om du använder [!DNL Target] eller [!DNL Analytics] som rapportkälla.

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

Följande inställningar är tillgängliga:

### [!UICONTROL Objective]

Ange ett valfritt mål. Målet kan vara vilken information som helst som hjälper dig och dina teammedlemmar att identifiera kampanjen.

### [!UICONTROL Priority]

Beroende på dina inställningar kan [!DNL Target] Användargränssnitt och alternativ för [!UICONTROL Priority] varierar. Du kan använda de äldre inställningarna för [!UICONTROL Low], [!UICONTROL Medium], eller [!UICONTROL High]eller så kan du aktivera finkorniga prioriteringar mellan 0 och 999.

Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas den aktivitet som har högst prioritet.

Om det här alternativet inte är aktiverat i [!UICONTROL Administration] (standard), ange en prioritet: [!UICONTROL Low], [!UICONTROL Medium], eller [!UICONTROL High].

Om du vill aktivera detaljerade prioriteringar klickar du på **[!UICONTROL Administration]** > **[!UICONTROL Reporting]** och växla sedan [!UICONTROL Enable Fine-Grained Priorities] till På-positionen.

Om det här alternativet är aktiverat anger du ett värde mellan 0 och 999:

* 0 = Låg
* 999 = Hög

För aktiviteter som skapats i tidigare versioner av [!DNL Target], [!UICONTROL Low] prioriteten konverteras till 0, [!UICONTROL Medium] konverteras till 5, och [!UICONTROL High] konverteras till 10. Du kan justera dessa värden om det behövs.

>[!NOTE]
>
>Innan du kan inaktivera det här alternativet efter att ha använt finkorniga prickar måste alla prioriteter återställas till 0, 5 och 10.

### [!UICONTROL Duration]

Aktiviteten kan starta när den har godkänts eller du kan ange ett specifikt datum och en viss tid. Aktiviteten kan också avslutas när den är inaktiverad eller du kan ange ett datum och en tid då aktiviteten ska sluta. Tidsväljaren använder en 24-timmarsklocka, där 00:00 är midnatt. Tidszonen är inställd på den tidszon som har konfigurerats i webbläsaren. Om du vill använda en annan tidszon anger du en annan tidszon för webbläsaren och startar om webbläsaren.

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

Följande inställningar är tillgängliga:

### [!UICONTROL Reporting Source]

Ange vilka lösningsdata som samlas in från:

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

Om en rapporteringslösning har angetts i [kontoinställningar](/help/main/administrating-target/reporting.md)används den angivna lösningen och den här inställningen syns inte.

Du kan inte ändra rapportkällan efter att aktiviteten har publicerats för att rapporterna ska vara konsekventa.

**[!DNL Adobe Analytics]**: Se [[!DNL Adobe Analytics] som rapportkälla för [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) för att lära sig om skillnaderna mellan rapporteringslösningarna och fördelarna med varje lösning.

Vid val [!DNL Analytics] som rapportkälla för [!DNL Target] (A4T) väljer du en [!DNL Analytics] rapportsvit att ta emot [!DNL Target] aktivitetsdata. Om du vill göra det måste du först välja något av de [!DNL Analytics] företag som ditt konto är knutet till och väljer sedan lämplig rapportsserie för aktiviteten. Rapportera endast programsviter som har etablerats för att ansluta till [!DNL Target] kan väljas. Om du inte ser den rapportserie du förväntar dig kan du först logga ut och logga in på [!DNL Adobe Experience Cloud] för att försöka igen. Om rapportsviten fortfarande saknas i listan kontaktar du [Kundtjänst](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

[!DNL Analytics for Target] (A4T) kräver att en spårningsserver rapporterar resultaten korrekt. En standardspårningsserver visas i [!UICONTROL Tracking Server] fält. Om du använder mer än en spårningsserver måste du ta med rätt spårningsserver i det här fältet. Se [Använda en analysspårningsserver](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) för mer information.

**[!DNL Adobe Customer Journey Analytics]**: Se [[!DNL Target] rapportering i [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) för mer information om integrationen mellan [!DNL Adobe Customer Journey Analytics] och [!DNL Target].

### [!UICONTROL Goal Metric]

Välj den åtgärd som en besökare ska utföra för att uppnå målet. Välj till exempel en [!UICONTROL Conversion] anger du sedan parametrarna som avgör när resultatet uppnås.

Mer information om att ställa in mätvärden finns i [Ange mått](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB).

>[!NOTE]
>
>Om rapporteringslösningen är inställd på [!DNL Analytics]är det enda tillgängliga målmåttet [!UICONTROL Conversion]. [!DNL Analytics] Det går inte att välja mått som mål.

När du väljer ett framgångsmått visas en väljare. Använd den här väljaren för att välja de specifika värdena för framgångsmåttet.

Om den är aktiverad visas [!UICONTROL Estimated Value of the Conversion] fält (ej tillgängligt för [!UICONTROL Page Score] mätvärden) ger ett värde för ditt mål, men inte för andra mätvärden. Detta värde aktiverar [!DNL Target] att beräkna en uppskattad ökning av intäkterna. Det här fältet är valfritt, men inkrementella intäkter för icke-intäktsmått kan inte beräknas utan det. För alla intäktsmått ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales]och [!UICONTROL Orders]), uppskattningens användning [!UICONTROL Revenue per Visitor]. Datatypen är valuta.

När aktivitetsmålet har uppnåtts fortsätter besökaren att se aktivitetsinnehållet, såvida inte besökaren kvalificerar sig för en aktivitet med högre prioritet. Om besökaren når målet igen räknas det som en annan konvertering. Det här beteendet skiljer sig från standardbeteendet i [!DNL Target Classic], som räknade besökarna som nya om de såg testet igen.

### [!UICONTROL Additional Metrics]

Skapa fler framgångsmått.

Den här inställningen är inte tillgänglig om rapporteringslösningen är inställd på [!DNL Analytics]. I det här fallet är de mått som definierats för [!DNL Analytics] rapporteringsprogram används.

### [!UICONTROL Audiences for Reporting]

Som standard visar rapporter resultat för alla kvalificerade besökare. Du kan lägga till rapportmålgrupper för att bara visa information om specifika målgrupper.

Den här inställningen är inte tillgänglig om du väljer [!DNL Analytics] som er rapporteringslösning. Målgruppen som definierats för [!DNL Analytics] rapportsviten används.

## [!UICONTROL Other Meta Data]

Skriv in information om din aktivitet som är användbar för dig själv eller andra teammedlemmar. The [!UICONTROL Notes] fönstret kan storleksändras.

## [!UICONTROL Advanced Settings] {#section_E2FE441AFB324E498793ABB025ED9974}

Avancerade inställningar är tillgängliga för [!UICONTROL Experience Targeting] målstatistik.

![Avancerade inställningar](/help/main/c-activities/t-experience-target/t-xt-create/assets/Menu_AdvancedSettings-new.png)

>[!NOTE]
>
>Om du [!DNL Analytics] som rapportkälla hanteras inställningarna av [!DNL Analytics] server. The [!UICONTROL Advanced Settings] alternativet är inte tillgängligt.

Följande inställningar är tillgängliga:

### [!UICONTROL Which success metric must be reached before incrementing this metric?]

Använd det här alternativet om du bara vill räkna besökaren som att uppnå framgångsmåttet om de tidigare har nått ett annat framgångsmått. En testkonvertering kan till exempel bara vara giltig om besökaren klickar på erbjudandet eller når en viss sida innan konverteringen.

Du kan ange beroende av flera mätvärden tillsammans med flexibiliteten att välja om mätvärdet ska nås eller inte för att antalet ska öka.

Du måste definiera båda (eller flera) framgångsmått innan du kan göra en beroende av en annan.

The [!UICONTROL Add Dependency] gör det möjligt för framgångsmåttet att öka om ett annat framgångsmått har nåtts eller inte har nåtts.

Så här lägger du till ett beroende:

1. När du har lagt till ytterligare mätvärden klickar du på **[!UICONTROL Advanced Settings]**.
2. Klicka **[!UICONTROL Add Dependency]**:

   ![Lägg till beroendelänk](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency-new.png)

3. Dra och släpp önskade mätvärden från den vänstra rutan till den högra rutan och klicka sedan på **[!UICONTROL Reached]** för att växla mellan [!UICONTROL Reached] och [!UICONTROL Not Reached].

   ![Dialogrutan Lägg till måttberoende](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency_reached-new.png)

Du kan redigera eller ta bort beroenden när du har lagt till dem.

### [!UICONTROL What will happen after a user encounters this goal metric?]

Det finns tre alternativ för vad som händer när en besökare når målmåttet:

* Välj [!UICONTROL Increment Count & Keep User in Activity] för att ange hur antalet ökas.
* Välj [!UICONTROL Increment Count, Release User & Allow Reentry] för att ange den upplevelse som användaren ser om aktiviteten återupptas.
* Välj [!UICONTROL Increment Count, Release User & Bar from Reentry] för att ange vad användaren ser i stället för aktivitetsinnehållet.

Se [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) om du vill ha mer information om avancerade inställningar.

## Utbildningsvideo: Aktivitetsinställningar (3:02)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/17381)
