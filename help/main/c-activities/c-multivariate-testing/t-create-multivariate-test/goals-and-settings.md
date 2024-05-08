---
keywords: aktivitetsinställningar;mål och inställningar;multivariera;mvt
description: Lär dig använda [!UICONTROL Goals & Settings] sida in [!DNL Adobe Target] för att ange information om målen för en [!UICONTROL Multivariate Test] (MVT) aktivitet.
title: Hur anger jag mål och inställningar i en [!UICONTROL Multivariate Test] Aktivitet?
feature: Multivariate Tests
exl-id: 823a1435-ccb9-4357-9c33-a0968d704b7a
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 0%

---

# Mål och inställningar ([!UICONTROL Multivariate Test])

The [!UICONTROL Goals & Settings] sida in [!DNL Adobe Target] är där du anger information om målen för [!UICONTROL Multivariate Test] (MVT).

Följande avsnitt är tillgängliga:

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

Vilka inställningar som är tillgängliga i varje avsnitt beror på om du använder [!DNL Target] eller [!DNL Analytics] som rapportkälla.

## Aktivitetsinställningar {#section_DCBDC354261F420EBD4B43EA34947BAC}

Följande inställningar är tillgängliga:

### Syfte

Ange ett valfritt mål. Målet kan vara vilken information som helst som hjälper dig och dina teammedlemmar att identifiera kampanjen.

### Prioritet

Beroende på dina inställningar kan [!DNL Target] Användargränssnitt och alternativ för [!UICONTROL Priority] varierar. Du kan använda de äldre inställningarna för [!UICONTROL Low], [!UICONTROL Medium], eller [!UICONTROL High]eller så kan du aktivera finkorniga prioriteringar mellan 0 och 999.

Prioriteten används om flera aktiviteter tilldelas till samma plats med samma målgrupp. Om två eller flera aktiviteter har tilldelats platsen visas aktiviteten med den högsta prioriteten.

Om det här alternativet inte är aktiverat i [!UICONTROL Administration] > [!UICONTROL Reporting] (standard), ange en prioritet: [!UICONTROL Low], [!UICONTROL Medium], eller [!UICONTROL High].

Om du vill aktivera detaljerade prioriteringar klickar du på [!UICONTROL Administration] > [!UICONTROL Reporting]och växla sedan [!UICONTROL Enable Fine-Grained Priorities] till På-positionen.

Om det här alternativet är aktiverat anger du ett värde mellan 0 och 999:

* 0 = Låg
* 999 = Hög

För aktiviteter som skapats i tidigare versioner av [!DNL Target], [!UICONTROL Low] prioriteten konverteras till 0, [!UICONTROL Medium] prioriteten konverteras till 5, och [!UICONTROL High] prioriteten konverteras till 10. Du kan justera dessa värden om det behövs.

>[!NOTE]
>
>Innan du kan inaktivera det här alternativet efter att ha använt finkorniga prickar måste alla prioriteter återställas till 0, 5 och 10.

### Varaktighet

Aktiviteten kan starta när den har godkänts eller du kan ange ett specifikt datum och en viss tid. Aktiviteten kan också avslutas när den är inaktiverad eller du kan ange ett datum och en tid. Tidsväljaren använder en 24-timmarsklocka, där 00:00 är midnatt. Tidszonen är inställd på den tidszon som har konfigurerats i webbläsaren. Om du vill använda en annan tidszon anger du en annan tidszon för webbläsaren och startar om webbläsaren.

## Rapportinställningar {#section_13119392051044FBA6387D9B3B1C43CF}

Följande inställningar är tillgängliga:

### Rapporteringskälla

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

### Målmått

Välj den åtgärd som en besökare ska utföra för att uppnå målet. Välj till exempel en [!UICONTROL Conversion] anger du sedan parametrarna som avgör när resultatet uppnås.

>[!NOTE]
>
>Om rapporteringslösningen är inställd på [!DNL Analytics]är det enda tillgängliga målmåttet [!UICONTROL Conversion]. [!DNL Analytics] Det går inte att välja mått som mål.

När du väljer ett framgångsmått visas en väljare. Använd den här väljaren för att välja de specifika värdena för framgångsmåttet.

Om den är aktiverad visas [!UICONTROL Estimated Value of the Conversion] fält (ej tillgängligt för [!UICONTROL Page Score] mätvärden) ger ett värde för ditt mål, men inte för andra mätvärden. Detta värde aktiverar [!DNL Target] att beräkna en uppskattad ökning av intäkterna. Det här fältet är valfritt, men inkrementella intäkter för icke-intäktsmått kan inte beräknas utan det. För alla intäktsmått ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales]och [!UICONTROL Orders]), uppskattningens användning [!UICONTROL Revenue per Visitor]. Datatypen är valuta.

När aktivitetsmålet har uppnåtts fortsätter besökaren att se aktivitetsinnehållet, såvida inte besökaren kvalificerar sig för en aktivitet med högre prioritet. Om besökaren når målet igen räknas det som en annan konvertering. Det här beteendet skiljer sig från standardbeteendet i [!DNL Target Classic], som räknar besökarna som nya om de ser testet igen.

### Ytterligare mått

Skapa fler framgångsmått.

Den här inställningen är inte tillgänglig om rapporteringslösningen är inställd på [!DNL Analytics]. I det här fallet är de mått som definierats för [!DNL Analytics] rapporteringsprogram används.

### Målgrupper för rapportering

Som standard visar rapporter resultat för alla kvalificerade besökare. Du kan lägga till rapportmålgrupper för att bara visa information om specifika målgrupper.

### Avancerade inställningar {#section_E2FE441AFB324E498793ABB025ED9974}

Avancerade inställningar är tillgängliga för [!UICONTROL Multivariate Test] målstatistik.

![Menyn Avancerade inställningar](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>Om du [!DNL Adobe Analytics] som rapportkälla hanteras inställningarna av [!DNL Analytics] server. Alternativet för avancerade inställningar är inte tillgängligt.

#### Vilket framgångsmått måste uppnås innan mätvärdet ökas?

Använd det här alternativet om du bara vill räkna någon som uppnår framgångsmåttet om de tidigare har nått ett annat framgångsmått. En testkonvertering kan till exempel bara vara giltig om besökaren klickar på erbjudandet eller når en viss sida innan konverteringen.

Du kan ange beroende av flera mätvärden tillsammans med flexibiliteten att välja om mätvärdet ska nås eller inte för att antalet ska öka.

Definiera båda (eller flera) framgångsmått innan du kan göra en beroende av en annan.

The [!UICONTROL Add Dependency] gör det möjligt för framgångsmåttet att öka om ett annat framgångsmått har nåtts eller inte har nåtts.

Så här lägger du till ett beroende:

1. När du har lagt till ytterligare mätvärden klickar du på **[!UICONTROL Advanced Settings]**.
2. Klicka på **[!UICONTROL Add Dependency]** alternativ:

   ![Lägg till beroende](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency.png)

3. Dra och släpp önskade mätvärden från den vänstra rutan till den högra rutan och klicka sedan på **[!UICONTROL Reached]** om du vill växla mellan inställningen för Uppnådd och Inte nådd.

   ![Beroende har nåtts](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency_reached.png)

Du kan redigera eller ta bort beroenden när du har lagt till dem.

### Vad händer efter att en användare har påträffat det här målmåttet?

Det finns tre alternativ för vad som händer när en besökare når målmåttet:

* [!UICONTROL Select Increment Count & Keep User in Activity] för att ange hur antalet ökas.
* [!UICONTROL Select Increment Count, Release User & Allow Reentry] för att ange den upplevelse som användaren ser om aktiviteten återupptas.
* [!UICONTROL Select Increment Count, Release User & Bar from Reentry] för att ange vad användaren ser i stället för aktivitetsinnehållet.

Se [Success Metrics](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) om du vill ha mer information om avancerade inställningar.

## Andra metadata {#section_2E8917BEFB954480A4206B9E9E917F80}

Följande inställning är tillgänglig:

### Anteckningar

Skriv in information om din aktivitet som är användbar för dig själv eller andra teammedlemmar. The [!UICONTROL Notes] fönstret kan storleksändras.

## Utbildningsvideor

I följande videofilmer finns mer information om de begrepp som beskrivs i den här artikeln.

### Aktivitetsinställningar (3:02)

Den här videon innehåller information om aktivitetsinställningar.

* Ange ett mål för din aktivitet
* Ange prioritetsnivå för dina aktiviteter
* Schemalägg start- och sluttider för aktivitet
* Lägg till målgrupper för rapportering för att skapa rapportfilter
* Ange anteckningar för dina aktiviteter

>[!VIDEO](https://video.tv.adobe.com/v/17381)

### Skapa multivariata tester (9:25)

I den här videon visas hur du skapar ett multivariata test med [!DNL Target] guidat arbetsflöde i tre steg. Mål och inställningar diskuteras från kl. 7.00.

* Definiera och utforma ett multivariat test
* Skapa ett multivariata test

>[!VIDEO](https://video.tv.adobe.com/v/17395)
